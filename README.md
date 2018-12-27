
# ESP8266 (Espressif 8266) Prometheus Exporter for DS18B20 Temperature Sensors

Exposes a prometheus exporter endpoint endpoint for scraping DS18B20 temperature sensor readings.


## Usage

1. Configure `ssid` and `password` for wifi network within `main.cpp`
2. [Build library against 8266 platform](https://docs.platformio.org/en/latest/platforms/espressif8266.html)  
3. hit `/metrics` endpoint for reading temperature (C), temperature (F), device resolution, and device count:

```
❯ curl 10.0.1.1/metrics

# HELP beertemp_device_total A count of probe devices connected.
# TYPE beertemp_device_total gauge
beertemp_device_total 1
# HELP beertemp_device_temperature_celsius Current device temperature in celsius.
# TYPE beertemp_device_temperature_celsius gauge
beertemp_device_temperature_celsius{id="28d1813592066618" resolution="12"} 22.69
# HELP beertemp_device_temperature_fahrenheit Current device temperature in fahrenheit.
# TYPE beertemp_device_temperature_fahrenheit gauge
beertemp_device_temperature_fahrenheit{id="28d1813592066618" resolution="12"} 72.84
```

