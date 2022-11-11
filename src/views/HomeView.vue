<script setup lang="ts">
import { useCounterStore } from '../stores/counter'

const store = useCounterStore()
store.count++
</script>

<template>
  <main>
    <div class="btn-wrapper">
      <button
        class="increment-button btn"
        style="margin-right: 8px"
        @click="store.increment()"
      >
        Increment
      </button>
      <button
        class="increment-button btn"
        @click="store.waitAndAdd()"
      >
        Wait + Increment
      </button>
    </div>
    <div class="btn-wrapper">
      <button
        class="decrement-button btn"
        style="margin-right: 8px"
        @click="store.decrement()"
      >
        Decrement
      </button>
      <button
        class="decrement-button btn"
        @click="store.waitAndReduce()"
      >
        Wait + Decrement
      </button>
    </div>
    <div class="counter-wrapper">
      <p>Count is {{ store.count }}</p>
      <p>Double is {{ store.doubleCount }}</p>
    </div>
  </main>
</template>

<style scoped>
.btn-wrapper {
  margin-bottom: 8px;
}

.btn {
  padding: 12px;
  font-size: 14px;
  border: none;
  transition: 0.4s ease;
  border-radius: 4px;
}

.btn:hover {
  cursor: pointer;
}

.increment-button {
  background-color: var(--increment-bgc-color);
  color: white;
}

.increment-button:hover {
  background-color: var(--increment-bgc-color-hover);
  color: var(--increment-bgc-color);
}

.decrement-button {
  background-color: var(--decrement-bgc-color);
  color: white;
}

.decrement-button:hover {
  background-color: var(--decrement-bgc-color-hover);
  color: var(--decrement-bgc-color);
}

.counter-wrapper {
  display: flex;
  gap: 16px;
}

.counter-wrapper p {
  padding: 14px;
  border: none;
  border-radius: 4px;
  background-color: #f1f1f1;
}
</style>
