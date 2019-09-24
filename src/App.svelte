<script>
  import HelloWorld from "./components/HelloWorld.svelte";
  import Router from "./components/Router.svelte";

  // added 'localhost' condition to prevent serviceworker from managing the cache while we're developing
  // firefox: go to about:serviceworkers to remove unwanted registered serviceworkers
  if (
    "serviceWorker" in navigator &&
    window.location.hostname !== "localhost"
  ) {
    navigator.serviceWorker.register("/service-worker.js");
  }
</script>

<style lang="postcss">

</style>

<main class="overflow-hidden">
  <Router />
  <HelloWorld />
</main>
