<template>
  <v-app>
    <v-navigation-drawer app class="deep-grey accent-4" dark permanent>
      <v-list>
        <nuxt-link to="/admin/home">
          <v-list-item link>
            <v-list-item-icon>
              <v-icon>mdi-view-dashboard</v-icon>
            </v-list-item-icon>

            <v-list-item-content>
              <v-list-item-title>Home</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </nuxt-link>
        <nuxt-link to="/admin/services">
          <v-list-item link>
            <v-list-item-icon>
              <v-icon>mdi-account-wrench</v-icon>
            </v-list-item-icon>

            <v-list-item-content>
              <v-list-item-title>Services</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </nuxt-link>
        <nuxt-link to="/admin/bookings">
          <v-list-item link>
            <v-list-item-icon>
              <v-icon>mdi-book</v-icon>
            </v-list-item-icon>

            <v-list-item-content>
              <v-list-item-title>Bookings</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </nuxt-link>
         <nuxt-link to="/admin/users">
          <v-list-item link>
            <v-list-item-icon>
              <v-icon>mdi-account</v-icon>
            </v-list-item-icon>

            <v-list-item-content>
              <v-list-item-title>Users</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </nuxt-link>
      </v-list>

      <template v-slot:append>
        <div class="pa-2">
          <v-btn block color="red" @click="logout"> Logout </v-btn>
        </div>
      </template>
    </v-navigation-drawer>

    <v-app-bar dark app>
      <h1>RENOZ</h1>
    </v-app-bar>

    <!-- Sizes your content based upon application components -->
    <v-main>
      <!-- Provides the application the proper gutter -->
      <v-container fluid>
        <!-- If using vue-router -->
        <Nuxt />
      </v-container>
    </v-main>

    <v-footer app>
      <!-- -->
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: 'admin',
  middleware: 'isAuthenticated',
  data: () => ({
    menu: true,
    tool: false,
  }),
  methods: {
    async logout() {
      await this.$auth.logout()
    },
  },
}
</script> 

<style scoped>
a {
  font-style: normal;
  color: black;
  text-decoration: none;
}

a.nuxt-link-active {
  font-weight: bold;
}
</style>
