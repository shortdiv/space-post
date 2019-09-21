<template>
  <div class="grid">
    <div class="front" :style="{ backgroundImage: `url('${img}')` }"></div>
    <div class="back">
      <div class="postcard">
        <textarea id="" v-model="message"></textarea>
        <button>send</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String
  },
  data() {
    return {
      message: "",
      img:
        "http://mars.jpl.nasa.gov/msl-raw-images/msss/01000/mcam/1000ML0044631200305217E01_DXXX.jpg"
    };
  },
  mounted() {
    // fetch("/.netlify/functions/fetch-image")
    // .then(res => {
    //   return res.json()
    // }).then(data => {
    //   console.log(data)
    // })
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-template-rows: 1fr 1fr;
  height: 90vh;
  background-color: beige;
}
.front {
  background: orangered;
}
.back {
  position: relative;
  left: -15vw;
  top: 22vh;
}
.postcard {
  background: url("https://mdn.mozillademos.org/files/4151/background.jpg");
  width: 100%;
  height: 100%;
  position: relative;
  background-size: contain;
  background-repeat: no-repeat;
}
#grid > div {
  padding: 20px;
  font-size: 4vw;
  color: white;
}

@media (max-width: 40em) {
  .grid {
    // grid-template-columns: 1fr;
    // grid-template-rows: 1fr;
  }
  .back {
    // grid-row: 2;
  }
}
textarea {
  margin-top: 10px;
  padding: 10px;
  font-size: 0.7em;
  background: transparent;
  line-height: 1.5em;
}
</style>
