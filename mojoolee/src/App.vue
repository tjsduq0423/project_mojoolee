<template>
  <v-app>
    <v-app-bar
      color="brown lighten-1"
      dark
      app
    >
      <v-app-bar-nav-icon @click="drawer = !drawer" />
      <v-toolbar-title>
        <a
          href="/"
          :style="{color : 'white',textDecoration:'none'}"
        >모주리</a>
      </v-toolbar-title>

      <v-spacer />

      <v-btn
        class="ma-2 brown lighten-3"
        to="/user-authentication"
        icon
      >
        <v-icon>mdi-account</v-icon>
      </v-btn>
      <v-btn
        icon
        class="ma-2 brown lighten-3"
        to="/search"
      >
        <v-icon>mdi-magnify</v-icon>
      </v-btn>
      <v-btn
        class="ma-2 brown lighten-3"
        to="/board"
        icon
      >
        <v-icon>mdi-bulletin-board</v-icon>
      </v-btn>
    </v-app-bar>

    <v-navigation-drawer
      v-model="drawer"
      app
    >
      <v-list-item>
        <v-list-item-content>
          <v-list-item-title class="text-h6">
            User Information
          </v-list-item-title>
        </v-list-item-content>
      </v-list-item>

      <v-divider />

      <v-list

        nav
      >
        <v-list-item
          v-for="item in items"
          :key="item.title"
          link
          :to="item.to"
        >
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>


    <v-main app>
      <router-view />
    </v-main>

    <v-footer app>
    <!-- -->
    </v-footer>
  </v-app>
</template>

<script>

export default {
  name: 'App',
data () {
      return {
        drawer : true,
        items: [
          { title: '관심종목', icon: 'mdi-heart',to :'/interest'},
          { title: '찜한 레포트', icon: 'mdi-bookmark', to :'/like-report'},
          { title: '내가 쓴 글', icon: 'mdi-message-reply-text' ,to :'/my-board'},
        ],
        right: null,
      }
    },
  methods:{
  }

};

</script>

<style>
</style>