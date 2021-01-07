<template>
  <div class="wrapper">
    <div class="wrapper-content">
      <header>
        <div class="logo">
          <img src="https://tocode.ru/static/img/general/logo.png" alt="toCode">
        </div>
        <div class="auth">
          <span class="login" @click="login = true">
            Login
          </span>
          <modalLogin v-show="login" @close="login = false" @change="changeModal()"/>
          <!-- registration modal -->
          <span class="login" @click="registration = true">
            SignUp
          </span>
          <modalRegistration v-show="registration"
          @close="registration = false"
          @change="changeModal()" />
        </div>
      </header>
      <section>

      </section>
    </div>
  </div>
</template>

<script>
import modalLogin from '@/components/ModalLogin.vue';
import modalRegistration from '@/components/ModalRegistration.vue';

export default {
  name: 'App',
  components: {
    modalLogin,
    modalRegistration,
  },
  data() {
    return {
      login: false,
      registration: false,
    };
  },
  methods: {
    changeModal() {
      this.login = !this.login;
      this.registration = !this.registration;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.wrapper {
  align-items: center;
}

.wrapper-content {
  width: 960px;
  background-color: #fff;
}

header {
  display: flex;
  padding: 10px 0 !important;
  justify-content: space-between;
  border-bottom: 2px solid #f7f7f7;
}

.auth {
  width: 120px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.login {
  display: block;
  line-height: 100%;
  align-items: center;
  cursor: pointer;
}
p.changeModal {
  font-size: 12px !important;
  margin: 20px 0 !important;
}
</style>
