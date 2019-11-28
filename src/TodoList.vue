<template>
  <div>
    <div>
      <input v-model="inputValue" />
      <button @click="handleSubmit">提交</button>
    </div>
    <ul>
      <todo-item v-for="(item,index) of List"
                 :key="index"
                 :content="item"
                 @delete="handleDelete"></todo-item>
    </ul>
  </div>
</template>

<script>
import TodoItem from './components/TodoItem.vue';

export default {
  components: {
    TodoItem
  },
  data () {
    return {
      inputValue: "",
      List: []
    }
  },
  methods: {
    handleSubmit () {
      this.List.push(this.inputValue);
      this.inputValue = ""
    },
    handleDelete (index) {
      this.List.splice(index, 1)
    }
  }
}
</script>

<style>
</style>
