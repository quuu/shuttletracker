<template>
  <div class="parent">
    <h1 class="title">Schedules</h1>
    <p class="subtitle">
      Official shuttle schedules from the Parking and Transportation office.
    </p>
    <hr>
    <div class="columns">
      <div class="column" v-for="link in links" v-bind:key="link.url">
        <div class="card">
          <header class="card-header">
            <p class="card-header-title">
              {{ link.name }}
            </p>
          </header>
          <div class="card-content">
            <div class="caption">
              <p v-for="line in link.caption" v-bind:key="line">{{ line }}</p>
            </div>
            <a target="_blank" rel="noopener noreferrer" v-bind:href="link.url">View PDF</a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
export default Vue.extend({
  data() {
    return {
      links: [
        {
          url: 'https://shuttles.rpi.edu/static/EastSchedule.pdf',
          name: 'East Campus',
          caption: ['Monday–Friday, 7 am–11 pm', 'Weekends: 9:30 am–5 pm'],
          color: 'green',
        },
        {
          url: 'https://shuttles.rpi.edu/static/WestSchedule.pdf',
          name: 'West Campus',
          caption: ['Monday–Friday, 7 am–11 pm', 'Weekends: 9:30 am–5 pm'],
          color: 'red',
        },
        {
          url: 'https://shuttles.rpi.edu/static/WeekendSchedule.pdf',
          name: 'Weekend/Late Night',
          caption: ['Friday–Sunday, 8 pm–4 am'],
          color: 'purple',
        },
      ],
    };
  },
});
</script>

<style lang="scss" scoped>
.parent {
  padding: 20px;
}
.caption {
  margin-bottom: 1em;
}
</style>
