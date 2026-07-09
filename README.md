# INA228

Texas Instruments INA228 I2C digital power monitor sensor module for XRobot.

This module configures the INA228 over I2C, periodically samples shunt voltage,
bus voltage, current, power, energy, charge, and die temperature, then publishes
a cached measurement topic from `OnMonitor`.

The I2C name, device address, shunt resistance, ADC range, and sample interval
are constructor arguments so the same module can be reused across board designs.

## Required Hardware

- `ina228_i2c`

## Constructor Arguments

- `i2c_name`: default `"ina228_i2c"`
- `i2c_addr`: default `64`
- `shunt_resistor_uohm`: default `5000`
- `adcrange_div4`: default `false`
- `sample_interval_ms`: default `100`
- `data_topic_name`: default `"ina228_data"`
- `auto_init`: default `true`

## Published Topics

- `data_topic_name`: `INA228::Data`, including shunt voltage, bus voltage, current, power, energy, charge, die temperature, timestamp, and validity state

## XRobot Configuration Example

```yaml
- id: power_monitor
  name: INA228
  constructor_args:
    i2c_name: "ina228_i2c"
    i2c_addr: 64
    shunt_resistor_uohm: 5000
    adcrange_div4: false
    sample_interval_ms: 100
    data_topic_name: "ina228_data"
    auto_init: true
```
