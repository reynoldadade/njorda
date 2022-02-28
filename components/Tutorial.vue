<!-- Please remove this file from your project -->
<template>
  <div class="container">
    <h2>Spin Me</h2>
    <div
      id="triangle"
      class="arrow-up"
      role="button"
      @click.prevent="rotateAt20"
    ></div>
    <div>Full rotations = {{ fullRotation }}</div>
  </div>
</template>

<script>
// import { gsap } from 'gsap'
export default {
  name: 'NuxtTutorial',
  data() {
    return {
      rotation: 0,
    }
  },
  computed: {
    fullRotation() {
      // full rotation will be the number of 360 degree in the total number of angles
      // in the rotation

      return Math.floor(this.rotation / 360)
    },
  },
  methods: {
    rotateAt20() {
      this.rotation += 20
      document.getElementById(
        'triangle'
      ).style.transform = `rotate(${this.rotation}deg)`
    },
  },
}
</script>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  align-items: center;
  width: 100%;
  height: 100vh;
  background-color: darkgrey;
}

.arrow-up {
  width: 0;
  height: 0;
  border-left: 120px solid transparent;
  border-right: 120px solid transparent;
  border-bottom: 120px solid black;
  transition: all 1.5s; /* smooth transtion */
  transform: rotate(0deg);
}
</style>
