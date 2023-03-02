<template>
  <a :href="href">
    <div class="card">
      <div class="flex">
        <div class="details">
          <h2 class="title">{{ title }}</h2>
          <p class="excerpt">{{ truncateText(excerpt, 50) }}</p>
            <div>
              <p class="date">{{ date }}</p>
            </div>
          </div>
        </div>
      </div>
  </a>
</template>
<script>
export default {
  props: {
    title: {
      type: String,
      required: true,
    },
    excerpt: {
      type: String,
      required: true,
    },
    date: {
      type: String,
      required: true,
    },
    href: {
      type: String,
      required: true,
    },
  },
  methods: {
    truncateText(text, length) {
      if (text.length > length) {
        return text.substring(0, length) + "...";
      }
      return text;
    },
  },
};
</script>
