<template>
  <div class="phone-body">

    <div class="feed" v-show="step === 1">
      <vuegram-post v-for="post in posts" :post="post" :key="posts.indexOf(post)" />
    </div>

    <div v-show="step === 2">
      <div class="selected-image" :class="selectedFilter" :style="{backgroundImage: 'url(' + image + ')' }">
        <div class="filter-container">

        </div>
      </div>
    </div>

    <div v-show="step === 3">
      <div class="selected-image" :class="selectedFilter" :style="{ backgroundImage: 'url(' + image + ')' }">
      </div>
      <div class="caption-container">
        <textarea class="caption-input" placeholder="Write a caption..." type="text">
        </textarea>
      </div>
    </div>

  </div>
</template>

<script>
import VuegramPost from "./VuegramPost";
export default {
  name: "PhoneBody",
  props: {
    posts: Array,
    filters: Array,
    step: Number,
    image: String,
    selectedFilter: String
  },
  components: {
    "vuegram-post": VuegramPost
  }
};
</script>

<style lang="scss" src="../styles/phone-body.scss">
// Styles from stylesheet
</style>