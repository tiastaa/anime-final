<template>
  <main-masterpage-vue>
    <main>
      <div class="main-box">
        <anime-card-list-vue :animeListData="searchAnimes" />
      </div>
    </main>
  </main-masterpage-vue>

  <!-- <footer-vue></footer-vue> -->
</template>

<script>
import AnimeCardListVue from "@/components/AnimeCardList.vue";
import MainMasterpageVue from "@/masterpages/MainMasterpage.vue";
//   import FooterVue from "@/components/Footer.vue";

// import axios from 'axios';
export default {
  name: "Search",
  components: {
    AnimeCardListVue,
    //   FooterVue,
    MainMasterpageVue,
  },

  computed: {
    searchAnimes() {
      console.log(this.$store.state.animeList);
      return this.$store.state.animeList;
    },
  },
  mounted() {
    // console.log(this.receivedAnimeId)
    this.$store.dispatch("fetchAnimeList", this.$route.params.titule);
    // this.$store.dispatch("fetchAnimeImgInfo", this.$route.params.id);
  },
  // mounted() {
  //   this.$store.dispatch("fetchAnimeList")
  // },
};
</script>

<style lang="css" scoped>
main {
  margin: 0 5vw;
  transform: translateY(-14vh);
}
.h3-title {
  /* background-color: aquamarine; */
  text-align: start;
  color: white;
}
input[type="search"]::-webkit-search-cancel-button {
  -webkit-appearance: none;
  width: 0px;
  height: 0px;
}
/* .main-box {
  min-height: 40vh;
} */
</style>
