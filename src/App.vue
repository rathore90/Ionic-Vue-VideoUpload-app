<template>
  <ion-app>
    <ion-header>
      <ion-toolbar>
        <ion-title>Vue Video Capture</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content class="ion-padding">
      <ion-button @click="takeVideo">Take Video</ion-button>
    </ion-content>
  </ion-app>
</template>
<style src='@ionic/core/css/core.css'></style>
<style src='@ionic/core/css/ionic.bundle.css'></style>
<script>
import { VideoCapturePlus } from "@ionic-native/video-capture-plus";

export default {
  name: "App",
  components: {},
  methods: {
    takeVideo: async function () {
      try {
        let options = { limit: 1, duration: 30 };
        let video = await VideoCapturePlus.captureVideo(options);
        console.log(video[0]);
      } catch (error) {
        console.log(error);
      }
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
