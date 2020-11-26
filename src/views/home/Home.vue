<template>
  <div id="home">
    <nav-bar class="home-nav">
      <div slot="center"> 购物街</div>
    </nav-bar>

    <home-swiper :banners="banners"></home-swiper>
    <recommend-view :recommends="recommends"></recommend-view>
    <feature-view></feature-view>
    <tab-control :titles ="['流行','新款','精选']"  class="tab-control"/>


    <ul>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li>
      <li>1</li><li>1</li><li>1</li><li>1</li><li>1</li><li>1</li><li>1</li><li>1</li><li>1</li><li>1</li>
    </ul>

  </div>
</template>

<script>
import NavBar from "@/components/common/navbar/NavBar.vue";
import HomeSwiper from "./childComps/HomeSwiper.vue";
import RecommendView from "./childComps/RecommendView";
import FeatureView from "./childComps/FeatureView.vue"
import TabControl from "@/components/content/tabControl/TabControl";

import {getHomeMultidata} from "@/network/home";

export default {
  name: "Home",
  data() {
    return {
      banners: [],
      recommends: []
    }
  },
  components: {
    NavBar,
    HomeSwiper,
    RecommendView,
    FeatureView,
    TabControl
  },
  created() {
    getHomeMultidata().then(res => {
      console.log(res);
      this.banners = res.data.banner.list;
      this.recommends = res.data.recommend.list;
    })
  }

}
</script>

<style scoped>
#home {
  padding-top: 44px;
  /*height: 100vh;*/
  /*position: relative;*/
}

.home-nav {
  background-color: var(--color-tint);
  color: #f6f6f6;

  position: fixed;
  left: 0;
  right: 0;
  top:0;
  z-index: 9;
}

.tab-control {
  position: sticky;
  top: 44px;
}
</style>
