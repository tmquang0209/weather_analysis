﻿# weather_analysis

## EXPLAIN VARIABLE

<table class="table">

<thead>

<tr>

<th scope="col">Variable</th>

<th scope="col">Valid time</th>

<th scope="col">Unit</th>

<th scope="col">Description</th>

</tr>

</thead>

<tbody>

<tr>

<th scope="row">temperature_2m</th>

<td>Instant</td>

<td>°C (°F)</td>

<td>Air temperature at 2 meters above ground</td>

</tr>

<tr>

<th scope="row">relative_humidity_2m</th>

<td>Instant</td>

<td>%</td>

<td>Relative humidity at 2 meters above ground</td>

</tr>

<tr>

<th scope="row">dew_point_2m</th>

<td>Instant</td>

<td>°C (°F)</td>

<td>Dew point temperature at 2 meters above ground</td>

</tr>

<tr>

<th scope="row">apparent_temperature</th>

<td>Instant</td>

<td>°C (°F)</td>

<td>Apparent temperature is the perceived feels-like temperature combining wind chill factor, relative humidity and solar radiation</td>

</tr>

<tr>

<th scope="row">pressure_msl
surface_pressure</th>

<td>Instant</td>

<td>hPa</td>

<td>Atmospheric air pressure reduced to mean sea level (msl) or pressure at surface. Typically pressure on mean sea level is used in meteorology. Surface pressure gets lower with increasing elevation.</td>

</tr>

<tr>

<th scope="row">precipitation</th>

<td>Preceding hour sum</td>

<td>mm (inch)</td>

<td>Total precipitation (rain, showers, snow) sum of the preceding hour. Data is stored with a 0.1 mm precision. If precipitation data is summed up to monthly sums, there might be small inconsistencies with the total precipitation amount.</td>

</tr>

<tr>

<th scope="row">rain</th>

<td>Preceding hour sum</td>

<td>mm (inch)</td>

<td>Only liquid precipitation of the preceding hour including local showers and rain from large scale systems.</td>

</tr>

<tr>

<th scope="row">snowfall</th>

<td>Preceding hour sum</td>

<td>cm (inch)</td>

<td>Snowfall amount of the preceding hour in centimeters. For the water equivalent in millimeter, divide by 7\. E.g. 7 cm snow = 10 mm precipitation water equivalent</td>

</tr>

<tr>

<th scope="row">cloud_cover</th>

<td>Instant</td>

<td>%</td>

<td>Total cloud cover as an area fraction</td>

</tr>

<tr>

<th scope="row">cloud_cover_low</th>

<td>Instant</td>

<td>%</td>

<td>Low level clouds and fog up to 2 km altitude</td>

</tr>

<tr>

<th scope="row">cloud_cover_mid</th>

<td>Instant</td>

<td>%</td>

<td>Mid level clouds from 2 to 6 km altitude</td>

</tr>

<tr>

<th scope="row">cloud_cover_high</th>

<td>Instant</td>

<td>%</td>

<td>High level clouds from 6 km altitude</td>

</tr>

<tr>

<th scope="row">shortwave_radiation</th>

<td>Preceding hour mean</td>

<td>W/m²</td>

<td>Shortwave solar radiation as average of the preceding hour. This is equal to the total global horizontal irradiation</td>

</tr>

<tr>

<th scope="row">direct_radiation
direct_normal_irradiance</th>

<td>Preceding hour mean</td>

<td>W/m²</td>

<td>Direct solar radiation as average of the preceding hour on the horizontal plane and the normal plane (perpendicular to the sun)</td>

</tr>

<tr>

<th scope="row">diffuse_radiation</th>

<td>Preceding hour mean</td>

<td>W/m²</td>

<td>Diffuse solar radiation as average of the preceding hour</td>

</tr>

<tr>

<th scope="row">global_tilted_irradiance</th>

<td>Preceding hour mean</td>

<td>W/m²</td>

<td>Total radiation received on a tilted pane as average of the preceding hour. The calculation is assuming a fixed albedo of 20% and in isotropic sky. Please specify tilt and azimuth parameter. Tilt ranges from 0° to 90° and is typically around 45°. Azimuth should be close to 0° (0° south, -90° east, 90° west). If azimuth is set to "nan", the calculation assumes a horizontal tracker. If tilt is set to "nan", it is assumed that the panel has a vertical tracker. If both are set to "nan", a bi-axial tracker is assumed.</td>

</tr>

<tr>

<th scope="row">sunshine_duration</th>

<td>Preceding hour sum</td>

<td>Seconds</td>

<td>Number of seconds of sunshine of the preceding hour per hour calculated by direct normalized irradiance exceeding 120 W/m², following the WMO definition.</td>

</tr>

<tr>

<th scope="row">wind_speed_10m
wind_speed_100m</th>

<td>Instant</td>

<td>km/h (mph, m/s, knots)</td>

<td>Wind speed at 10 or 100 meters above ground. Wind speed on 10 meters is the standard level.</td>

</tr>

<tr>

<th scope="row">wind_direction_10m
wind_direction_100m</th>

<td>Instant</td>

<td>°</td>

<td>Wind direction at 10 or 100 meters above ground</td>

</tr>

<tr>

<th scope="row">wind_gusts_10m</th>

<td>Instant</td>

<td>km/h (mph, m/s, knots)</td>

<td>Gusts at 10 meters above ground of the indicated hour. Wind gusts in <mark>CERRA</mark> are defined as the maximum wind gusts of the preceding hour. Please consult the [ECMWF IFS documentation](https://www.ecmwf.int/en/elibrary/81271-ifs-documentation-cy47r3-part-iv-physical-processes) for more information on how wind gusts are parameterized in weather models.</td>

</tr>

<tr>

<th scope="row">et0_fao_evapotranspiration</th>

<td>Preceding hour sum</td>

<td>mm (inch)</td>

<td>ET₀ Reference Evapotranspiration of a well watered grass field. Based on [FAO-56 Penman-Monteith equations](https://www.fao.org/3/x0490e/x0490e04.htm) ET₀ is calculated from temperature, wind speed, humidity and solar radiation. Unlimited soil water is assumed. ET₀ is commonly used to estimate the required irrigation for plants.</td>

</tr>

<tr>

<th scope="row">weather_code</th>

<td>Instant</td>

<td>WMO code</td>

<td>Weather condition as a numeric code. Follow WMO weather interpretation codes. See table below for details. Weather code is calculated from cloud cover analysis, precipitation and snowfall. As barely no information about atmospheric stability is available, estimation about thunderstorms is not possible.</td>

</tr>

<tr>

<th scope="row">snow_depth</th>

<td>Instant</td>

<td>meters</td>

<td>Snow depth on the ground. Snow depth in ERA5-Land tends to be overestimated. As the spatial resolution for snow depth is limited, please use it with care.</td>

</tr>

<tr>

<th scope="row">vapour_pressure_deficit</th>

<td>Instant</td>

<td>kPa</td>

<td>Vapor Pressure Deificit (VPD) in kilopascal (kPa). For high VPD (>1.6), water transpiration of plants increases. For low VPD (<0.4), transpiration decreases</td>

</tr>

<tr>

<th scope="row">soil_temperature_0_to_7cm
soil_temperature_7_to_28cm
soil_temperature_28_to_100cm
soil_temperature_100_to_255cm</th>

<td>Instant</td>

<td>°C (°F)</td>

<td>Average temperature of different soil levels below ground.</td>

</tr>

<tr>

<th scope="row">soil_moisture_0_to_7cm
soil_moisture_7_to_28cm
soil_moisture_28_to_100cm
soil_moisture_100_to_255cm</th>

<td>Instant</td>

<td>m³/m³</td>

<td>Average soil water content as volumetric mixing ratio at 0-7, 7-28, 28-100 and 100-255 cm depths.</td>

</tr>

</tbody>

</table>

<p>Resource: <a href="https://open-meteo.com/en/docs/historical-weather-api">Open-meteo</a></p>
