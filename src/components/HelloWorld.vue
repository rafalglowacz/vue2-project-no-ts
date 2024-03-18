<script>
export default {
  data() {
    return {
      // Note: "go to definition" works fine on `{{ msg }}`, you're taken here:
      msg: {
        type: String,
        required: true
      }
    }
  },
  methods: {
    // "Go to definition" on `@click=foo` doesn't lead to this method.
    foo() {
      console.log('foo')
    },
    // Calling foo() from another method also isn't recognized.
    bar() {
      this.foo()
    }
  }
}
</script>

<template>
  <div class="greetings">
    <h1 class="green">{{ msg }}</h1>
    <h3>
      You’ve successfully created a project with
      <a @click="foo" target="_blank" href="https://vitejs.dev/">Vite</a> +
      <a target="_blank" href="https://v2.vuejs.org/">Vue 2</a>.
    </h3>
  </div>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    display: block;
    text-align: left;
  }
}
</style>
