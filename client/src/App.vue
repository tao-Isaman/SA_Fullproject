<template>
  <v-app>
    <!-- <v-app-bar app>
      <v-toolbar-title class="headline text-uppercase">
        <span>ระบบ</span>
        <span class="font-weight-light">จัดการผู้ป่วยใน</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn
        text
        href="https://github.com/vuetifyjs/vuetify/releases/latest"
        target="_blank"
      >
        <span class="mr-2">Username : {{username}}</span>
      </v-btn>   
    </v-app-bar> -->

 <div>
    <v-toolbar>
      <v-toolbar-title>ระบบจัดการผู้ป่วยใน</v-toolbar-title>

      <div class="flex-grow-1"></div>

      <v-toolbar-items>
        <v-btn text>Home</v-btn>
        <v-btn @click="goRegister" text>ระบบลงทะเบียนผู้ป่วยใน</v-btn>
        <v-btn @click="goExamination" text>ระบบประเมินอาการผู้ป่วย</v-btn>
        <v-btn @click="goDoctororder" text>ระบบสั่งจ่ายยา</v-btn>
        <v-btn @click="goPayment" text>ระบบชำระเงิน</v-btn>
        <v-btn @click="goAppoint" text>ระบบนัดหมายผู้ป่วย</v-btn>
        <v-btn @click="goReservation" text>ระบบจองเตียง</v-btn>
        <v-btn @click="goDischarge" text>ระบบนำจำหน่าย</v-btn>
        <v-btn @click="logout"  color="red" text>ออกจากระบบ</v-btn>
      </v-toolbar-items>
<!-- 
      <template v-if="$vuetify.breakpoint.smAndUp">
        <v-btn icon>
          <v-icon>mdi-export-variant</v-icon>
        </v-btn>
        <v-btn icon>
          <v-icon>mdi-delete-circle</v-icon>
        </v-btn>
        <v-btn icon>
          <v-icon>mdi-plus-circle</v-icon>
        </v-btn>
      </template> -->
    </v-toolbar>
  </div>
    <v-content>
      <!-- <VideoRental/> -->
      <router-view />
    </v-content>
  </v-app>
</template>

<script>

export default {
  name: 'App',
  data: () => ({
    username: '',
    status:''
  }),
   methods: {
     logout(){
       this.$router.push("/");
     },
     goRegister(){
       this.$router.push("/patient");
     },
     goAppoint(){
       this.$router.push("/appointment");
     },
     goDischarge(){
       this.$router.push("/discharge");
     },
     goExamination(){
       this.$router.push("/examination");
     },
     goReservation(){
       this.$router.push("/reservation");
     },
     goPayment(){
       this.$router.push("/postPayment");
     },
     goDoctororder(){
       this.$router.push("/doctororder");
     }
     


   },
};
</script>
