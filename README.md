# PAI - Paradox Alarm Interface

Python-based 'middleware' that aims to use any method to connect to a Paradox Alarm, exposing the interface for monitoring and control via several methods.

This is a complete rewrite from [ParadoxMulti-MQTT](https://github.com/jpbarraca/ParadoxMulti-MQTT)

It supports panels connected through a serial port, which is present in all panels, or through a USB 307 module.


Tested in the following environment:

* Python 3.5.2
* Mosquitto MQTT Broker v1.4.14
* OrangePi 2G-IOT, NanoPi NEO, Raspberry Pi 3 through their built in Serial Port (with a level switch!)
* Ubuntu Server 16.04.3 LTS
* Paradox MG5050 panel
* [Signal Cli](https://github.com/AsamK/signal-cli) through a DBUS interface
* Pushbullet.py


## Structure

* __Paradox__: Object that interfaces with the panel and keeps some internal state. Accepts commands to control partitions, zones and outputs. Exposes changes and events

* __Interfaces__: Expose interfaces to the outside world. Currently, MQTT, Signal and Pushbullet are supported, but other are planned and almost any other is supported.

* __Connections__: Handle communication with the panel, at a lower level. Currently, only Serial connections are supported.


## Acknowledgments

This work is inspired or uses parts from the following projects:

* Tertiush at https://github.com/Tertiush/ParadoxIP150v2
* Spinza at https://github.com/spinza/paradox_mqtt