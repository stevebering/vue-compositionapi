<template>
  <div>
    <span>Count is: {{ state.count }}, double is: {{ state.double }}</span>
    <button @click="increment">+</button>
    <button @click="decrement">-</button>
  </div>
</template>

<script lang="ts">
import { createComponent, computed, reactive } from "@vue/composition-api";

export default createComponent({
  setup() {
    const state: any = reactive({
      count: 0,
      double: computed(() => state.count * 2)
    });

    function increment() {
      state.count++;
    }

    function decrement() {
      state.count--;
    }

    return {
      state,
      increment,
      decrement
    };
  }
});
</script>
