<template>
  <div class="container">
    <treeselect
      :multiple="true"
      :options="options"
      placeholder="Select your favourite(s)..."
      v-model="value"
      @input="setSelectedItems"
      class="tree-select"
    />
    <div class="result">{{ items }}</div>
  </div>
</template>
<script>
import Treeselect from "@riophae/vue-treeselect";
import "@riophae/vue-treeselect/dist/vue-treeselect.css";
import { mapState, mapMutations } from "vuex";
export default {
  components: { Treeselect },
  data: () => ({
    value: [],
    options: [
      {
        id: "fruits",
        label: "Fruits",
        children: [
          {
            id: "apple",
            label: "Apple 🍎",
            isNew: true,
          },
          {
            id: "grapes",
            label: "Grapes 🍇",
          },
          {
            id: "pear",
            label: "Pear 🍐",
          },
          {
            id: "strawberry",
            label: "Strawberry 🍓",
          },
          {
            id: "watermelon",
            label: "Watermelon 🍉",
          },
        ],
      },
      {
        id: "vegetables",
        label: "Vegetables",
        children: [
          {
            id: "corn",
            label: "Corn 🌽",
          },
          {
            id: "carrot",
            label: "Carrot 🥕",
          },
          {
            id: "eggplant",
            label: "Eggplant 🍆",
          },
          {
            id: "tomato",
            label: "Tomato 🍅",
          },
        ],
      },
    ],
  }),
  computed: {
    ...mapState(["items"]),
  },
  methods: {
    ...mapMutations(["setSelectedItems"]),
  },
};
</script>
