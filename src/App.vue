<template>
  <div id='app'>

    <h1>Markdown previewer</h1>

    <p>Enter your markdown code to see an HTML preview below.</p>
  
  <!-- this is your input -->
    <textarea 
      name='editor'
      id='editor'
      cols='60'
      rows='10'
      v-on:keyup='transformMarkdown'
      v-model='input'
      >
    </textarea>

  <!-- this is your output -->

    <div 
      id='preview' 
      ref='preview'>
    </div>

    <!-- v-for directive
    <p v-for="(item, index) in list" :key="index"> {{ item }} </p>
    v-if directive
    <h1 v-if="isOn">Hello Lisboa</h1>
    <h2 v-if="isOn">Welcome to Vue</h2>
    <h3 v-if="isOn">So far so good</h3>
    <button v-on:click="toggle">Toggle</button>
    or <button @click="toggle">Toggle</button> -->

  </div>
</template>

<script>

export default {
  name: 'app',
  data() {
    return {
      input:''
    }
  },
  mounted() {
console.log(this.$refs.preview)
  },
  methods:{
    transformMarkdown() {
      this.$refs.preview.innerHTML = marked(this.input, {
        breaks: true
      }) 
    }
  } 
}
</script>

<style>

</style>
