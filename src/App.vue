<template>
  <div class="black-bg" v-if="modal_stat == true">
    <div class="white-bg">
      <h4>상세페이지임</h4>
      <p>상세페이지 내용임</p>
      <button @click="modal_stat = false">닫기</button>
    </div>
  </div>

  <div class="menu">
    <a v-for="(a, i) in menus" :key="i">{{ a }}</a>
  </div>

  <div v-for="(a, i) in 원룸들" :key="i">
    <img :src="원룸들[i].image" class="room-img" />
    <h4 @click="modal_stat = true">{{ 원룸들[i].title }}</h4>
    <p>{{ 원룸들[i].price }} 원</p>
  </div>
</template>

<script>
import room_info from "./data";
export default {
  name: "App",
  data() {
    return {
      원룸들: room_info,
      prices: [50, 60, 70],
      menus: ["Home", "Shop", "About"],
      신고수: [0, 0, 0],
      modal_stat: false,
    };
  },
  methods: {
    increase() {
      this.신고수 += 1;
    },
  },
  components: {},
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;
}

.room-img {
  width: 100%;
  margin-top: 40px;
}

body {
  margin: 0;
}

div {
  box-sizing: border-box;
}

.black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  padding: 20px;
}

.white-bg {
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}
</style>
