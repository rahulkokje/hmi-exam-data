<template>
  <v-container dark fluid class="pa-0 pb-10"
    :class="{
            'background-gray': !$vuetify.theme.dark,
          }">
    <ExamDataHeader @onTabClick="toggleTab" />
    <v-divider />

    <v-sheet elevation="2" class="my-8 mx-5 px-5">
      <!-- TAB 1 -->
      <ExamsData class="mt-3" v-show="currTab == 0" />
      <!-- TAB 2 -->
      <UploadExam class="mt-3" v-show="currTab == 1" />
    </v-sheet>
  </v-container>
</template>



<script>
import ExamDataHeader from "../components/exams/ExamDataHeader.vue";
import ExamsData from "../components/exams/ExamsData.vue";
import UploadExam from "../components/exams/UploadExam.vue";

export default {
  name: "ExamDataPage",
  components: {
    ExamDataHeader,
    ExamsData,
    UploadExam,
  },
  data: () => ({
    currTab: 0,
  }),
  methods: {
    toggleTab(value) {
      this.currTab = value;
    }
  },
};
</script>

<style>
v-main {
  padding: 0px !important;
}
.background-gray {
  background-color: #efefef;
}
</style>
