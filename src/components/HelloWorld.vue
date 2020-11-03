<template>
  <div class="hello">
    <button @click="cycle">
      Cycle
    </button>
    <h1>
      <component :is="currentView"></component>
    </h1>
  </div>
</template>

<script>
import BookComponent from './BookComponent'
import FormComponent from './FormComponent'
import HeaderComponent from './HeaderComponent'

export default {
  name: 'HelloWorld',
  components: {
    BookComponent,
    FormComponent,
    HeaderComponent
  },
  data() {
    return {
      currentView: BookComponent
    }
  },
  methods: {
    cycle () {
      if (this.currentView === HeaderComponent) {
        this.currentView = BookComponent
      } else {
        this.currentView = this.currentView === BookComponent ? FormComponent : HeaderComponent
      }
    }
  },
}
</script>

<style scoped>
</style>
