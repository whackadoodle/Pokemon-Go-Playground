# Pokemon Go Playground - based on the Predict'em All dataset on Kaggle

## Overview

PokemonGo is a mobile augmented reality game developed by Niantic inc. for iOS, Android, and Apple Watch devices. It was initially released in selected countries in July 2016. In the game, players use a mobile device's GPS capability to locate, capture, battle, and train virtual creatures, called Pokémon, who appear on the screen as if they were in the same real-world location as the player.

## Dataset

Dataset consists of roughly 293,000 pokemon sightings (historical appearances of Pokemon), having coordinates, time, weather, population density, distance to pokestops/ gyms etc. as features. The target is to train a machine learning algorithm so that it can predict where pokemon appear in future. So, can you predict'em all?)

## Feature description

   - pokemonId - the identifier of a pokemon, should be deleted to not affect predictions. (numeric; ranges between 1 and 151)
   - latitude, longitude - coordinates of a sighting (numeric)
   - appearedLocalTime - exact time of a sighting in format yyyy-mm-dd'T'hh-mm-ss.ms'Z' (nominal)
   - cellId 90-5850m - geographic position projected on a S2 Cell, with cell sizes ranging from 90 to 5850m (numeric)
   - appearedTimeOfDay - time of the day of a sighting (night, evening, afternoon, morning)
   - appearedHour/appearedMinute - local hour/minute of a sighting (numeric)
   - appearedDayOfWeek - week day of a sighting (Monday, Tuesday, Wednesday, Thursday, Friday, Saturday, Sunday)
   - appearedDay/appearedMonth/appearedYear - day/month/year of a sighting (numeric)
   - terrainType - terrain where pokemon appeared described with help of GLCF Modis Land Cover (numeric)
   - closeToWater - did pokemon appear close (100m or less) to water (Boolean, same source as above)
   - city - the city of a sighting (nominal)
   - continent (not always parsed right) - the continent of a sighting (nominal)
   - weather - weather type during a sighting (Foggy Clear, PartlyCloudy, MostlyCloudy, Overcast, Rain, BreezyandOvercast, LightRain, Drizzle, BreezyandPartlyCloudy, HeavyRain, BreezyandMostlyCloudy, Breezy, Windy, WindyandFoggy, Humid, Dry, WindyandPartlyCloudy, DryandMostlyCloudy, DryandPartlyCloudy, DrizzleandBreezy, LightRainandBreezy, HumidandPartlyCloudy, HumidandOvercast, RainandWindy) // Source for all weather features
   - temperature - temperature in celsius at the location of a sighting (numeric)
   - windSpeed - speed of the wind in km/h at the location of a sighting (numeric)
   - windBearing - wind direction (numeric)
   - pressure - atmospheric pressure in bar at the location of a sighting (numeric)
   - weatherIcon - a compact representation of the weather at the location of a sighting (fog, clear-night, partly-cloudy-night, partly-cloudy-day, cloudy, clear-day, rain, wind)
   - sunriseMinutesMidnight-sunsetMinutesBefore - time of appearance relatively to sunrise/sunset Source
   - population density - what is the population density per square km of a sighting (numeric, Source)
   - urban-rural - how urban is location where pokemon appeared (Boolean, built on Population density, \<200 for rural, >=200 and \<400 for midUrban, >=400 and \<800 for subUrban, >800 for urban)
   - gymDistanceKm, pokestopDistanceKm - how far is the nearest gym/pokestop in km from a sighting? (numeric, extracted from this dataset)
   - gymIn100m-pokestopIn5000m - is there a gym/pokestop in 100/200/etc meters? (Boolean)
   - cooc 1-cooc 151 - co-occurrence with any other pokemon (pokemon ids range between 1 and 151) within 100m distance and within the last 24 hours (Boolean)
   - class - says which pokemonId it is, to be predicted. 
