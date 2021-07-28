<template>
  <v-container>
    <v-row class="text-center">
      <v-col cols="12">
        <v-tabs centered >
          <v-tab>Rio De Janeiro</v-tab>
          <v-tab>Beijing</v-tab>
          <v-tab>Los Angeles</v-tab>
        </v-tabs>
      </v-col>

      <v-col class="mb-4">
        <v-card
                class="mx-auto"
                max-width="400"
        >
          <v-list-item two-line>
            <v-list-item-content>
              <v-list-item-title class="text-left text-h5" >
                Next hours
              </v-list-item-title>
              <v-divider></v-divider>
            </v-list-item-content>
          </v-list-item>

          <v-card-text>
            <v-row align="center">

              <v-col class="text-h7" cols="3">

                <v-list>

                  <v-list-item>
                    {{ forecastNextHours[0].temp }}
                  </v-list-item>

                  <v-list-item class="text-center">
                    {{ forecastNextHours[0].humid }}
                  </v-list-item>

                  <v-list-item-subtitle  >
                    <v-icon>{{ forecastNextHours[0].icon }}</v-icon>
                  </v-list-item-subtitle>

                  <v-list-item-subtitle class="text-center">
                    {{ forecastNextHours[0].hour }}
                  </v-list-item-subtitle>

                </v-list>


              </v-col>

              <v-divider vertical height="" ></v-divider>

              <v-col class="text-h5" cols="3">

              kati

              </v-col>

              <v-divider vertical ></v-divider>

              <v-col class="text-h5" cols="3">

                kati

              </v-col>

              <v-divider vertical ></v-divider>

              <v-col class="text-h5" cols="3">

                kati

              </v-col>


                <v-list>

                  <v-list-item
                          v-for="item in forecastNextHours"
                          :key="item.day"
                  >
                    <v-list-item-title>{{ item.day }}</v-list-item-title>

                    <v-list-item-icon>
                      <v-icon>{{ item.icon }}</v-icon>
                    </v-list-item-icon>

                    <v-list-item-subtitle class="text-right">
                      {{ item.temp }}
                    </v-list-item-subtitle>

                    <v-divider ></v-divider>

                  </v-list-item>


                </v-list>







            </v-row>
          </v-card-text>

          <v-list-item>
            <v-list-item-icon>
              <v-icon>mdi-send</v-icon>
            </v-list-item-icon>
            <v-list-item-subtitle>23 km/h</v-list-item-subtitle>
          </v-list-item>

          <v-list-item>
            <v-list-item-icon>
              <v-icon>mdi-cloud-download</v-icon>
            </v-list-item-icon>
            <v-list-item-subtitle>48%</v-list-item-subtitle>
          </v-list-item>

          <v-slider
                  v-model="time"
                  :max="6"
                  :tick-labels="labels"
                  class="mx-4"
                  ticks
          ></v-slider>

          <v-list class="transparent">
            <v-list-item
                    v-for="item in forecastNextHours"
                    :key="item.day"
            >
              <v-list-item-title>{{ item.day }}</v-list-item-title>

              <v-list-item-icon>
                <v-icon>{{ item.icon }}</v-icon>
              </v-list-item-icon>

              <v-list-item-subtitle class="text-right">
                {{ item.temp }}
              </v-list-item-subtitle>
            </v-list-item>
          </v-list>

          <v-divider></v-divider>

          <v-card-actions>
            <v-btn text>
              Full Report
            </v-btn>
          </v-card-actions>
        </v-card>
      </v-col>



      <v-col
        class="mb-5"
        cols="12"
      >
        <h2 class="headline font-weight-bold mb-3">
          Ecosystem
        </h2>

        <v-row justify="center">
          <a
            v-for="(eco, i) in ecosystem"
            :key="i"
            :href="eco.href"
            class="subheading mx-3"
            target="_blank"
          >
            {{ eco.text }}
          </a>
        </v-row>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
  export default {
    name: 'HelloWorld',

    data: () => ({
      labels: ['SU', 'MO', 'TU', 'WED', 'TH', 'FR', 'SA'],
      time: 0,
      forecastNextHours: [
          { day: 'Tuesday', icon: 'mdi-white-balance-sunny', temp: '24\xB0', humid: '0%', hour: '5:00 PM' },
          { day: 'Wednesday', icon: 'mdi-white-balance-sunny', temp: '22\xB0/14\xB0', humid: '0%', hour: '6:00 PM' },
          { day: 'Thursday', icon: 'mdi-cloud', temp: '25\xB0/15\xB0', humid: '0%', hour: '7:00 PM' },
      ],


      whatsNext: [
        {
          text: 'Explore components',
          href: 'https://vuetifyjs.com/components/api-explorer',
        },
        {
          text: 'Select a layout',
          href: 'https://vuetifyjs.com/getting-started/pre-made-layouts',
        },
        {
          text: 'Frequently Asked Questions',
          href: 'https://vuetifyjs.com/getting-started/frequently-asked-questions',
        },
      ],
    }),
  }
</script>
