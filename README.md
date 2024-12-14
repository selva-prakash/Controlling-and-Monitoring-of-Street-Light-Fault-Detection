# Controlling-and-Monitoring-of-Street-Light-Fault-Detection
IOT ENABLED- CONTROLLING AND MONITORING OF STREET LIGHT FAULT DETECTION(To detect the fault street light using IOT Technology)



(ABSTRACT):
Street lighting systems worldwide consume significant amounts of electrical energy, and due to their extensive nature, manual monitoring and control are both challenging and inefficient. Developing a smart system that automates and monitors street lights while providing real-time communication to users via IoT is essential for energy conservation and ease of maintenance. This system continuously tracks the operational status (ON/OFF) of each light by measuring its power consumption. Since street lights are only necessary during nighttime hours, the system automatically turns the lights on at 6 PM and off at 6 AM, optimizing their usage and significantly reducing energy waste. In case of a malfunction, the system detects the fault, disconnects the faulty light from the power supply, and notifies the user. This allows for quick troubleshooting and ensures the faulty street light can be fixed and restored efficiently, improving both reliability and maintainability. Additionally, the system features a real-time monitoring portal, built on the Thing speak IoT platform, that displays key metrics such as voltage, current, power consumption, and fault status. This data can be accessed remotely from any location via the internet, providing convenient, global oversight at all times.






(WORKFLOW):
1. Data Collection
The first step involves gathering data from various sensors to monitor the streetlight system's status. Here's how each component contributes:
•	Arduino DUE and Arduino UNO: These microcontroller boards are used to control and manage the sensors and process the data collected. The Arduino UNO typically manages basic tasks, such as receiving inputs from the LDR sensor (to detect light intensity) and the IR sensor (for motion detection). The Arduino DUE, being a more powerful board with a 32-bit ARM processor, handles complex tasks like processing sensor data, controlling relays, and interfacing with the NODEMCU for IoT communication.
•	ACS-712 Current Sensor: The ACS-712 sensor is used to measure the current flowing through the streetlight circuit. It monitors how much electrical current is being used by the light, which helps in determining whether the streetlight is operating correctly. The current sensor outputs an analog voltage corresponding to the current being measured, which is fed to the Arduino boards for processing.
•	M054 Voltage Sensor: Similarly, the M054 voltage sensor monitors the voltage levels across the system to ensure they are within a safe operating range. Just like the current sensor, the voltage sensor sends its data to the microcontroller to determine the health of the power supply to the streetlights.
These sensors continuously measure key parameters like current, voltage, and light intensity (via the LDR sensor) and send this data to the Arduino microcontroller.
2. Data Transfer to NODEMCU
Once the data is processed by the Arduino boards, it is transmitted to the NODEMCU via serial communication. The NODEMCU is a development board with integrated Wi-Fi capabilities, specifically designed for IoT (Internet of Things) applications. It acts as the communication bridge between the local hardware (sensors and microcontrollers) and the cloud-based IoT platform (like Blynk).
•	Serial Communication: Data transfer occurs over a serial interface, where the Arduino sends the processed sensor data to the NODEMCU, which then transmits it to the cloud via Wi-Fi.
3. Data Upload to the IoT Cloud Platform
The NODEMCU uploads the collected data to a cloud-based platform, such as Blynk, via the Wi-Fi network. This allows users to remotely monitor the streetlight system through a mobile or web interface. The cloud platform stores the sensor data and provides a real-time visualization dashboard.
•	Real-Time Visualization: Users can see real-time graphs and values representing key metrics like current, voltage, light intensity, and motion detection. The IoT platform helps in identifying patterns and allows users to keep track of the system's performance over time.
4. Time-Based Relay Control
The system is designed to work automatically based on the time of day. Using an internal clock, the system checks the time and performs the following actions:
•	Between 6 PM and 6 AM (Nighttime Operation): During these hours, the streetlights are needed to be ON, so the system automatically activates the relay. The relay is a switching device that controls the flow of electricity to the streetlight. When the time is within the specified range (6 PM to 6 AM), the relay is turned ON, allowing power to flow to the streetlight, which then illuminates the area.
•	Outside of 6 PM to 6 AM (Daytime Operation): During the daytime, the streetlights are typically not needed. Therefore, the system automatically switches the relay OFF to conserve energy, ensuring that the lights are turned off when it's bright enough for natural lighting. The indicator light is also turned off in this case to save energy.
This automatic switching is crucial for energy conservation and to avoid unnecessary power usage during the day.
5. Current Analysis and Operational Status Check
In parallel with time-based control, the system also monitors the operational status of the streetlights using the current sensor. The current value is continuously checked to assess the streetlight's performance:
•	Current Value Greater Than Zero: If the current sensor detects a positive reading (i.e., current is flowing through the circuit), it means that the streetlight is receiving power and is operational.  







(HARDWARE IMPLEMENTATION):
A.	ArduinoUNO: The Arduino Uno is a microcontroller board built around the ATmega328P chip. It features 14 digital input/output pins, 6 of which support PWM outputs, along with 6 analog inputs. It operates with a 16 MHz ceramic resonator, includes a USB connection, a power jack, an ICSP header, and a reset button. The board comes with all the necessary components to support the microcontroller, allowing it to be powered through a USB cable from a computer, an AC-to-DC adapter, or a battery.
B.	NODEMCU: NODEMCU is an open-source firmware and development kit designed to help users create IoT applications or prototypes. It is built around the ESP8266 Wi-Fi SoC from Expressif Systems and relies on the ESP-12 module for hardware implementation.
C.	Sensors: The ACS712 Current Sensor, developed by Allegro Microsystems, is capable of accurately measuring both AC and DC currents. It utilizes the Hall Effect principle, with the integrated Hall Effect sensor inside the IC. As for the sensor’s output, it provides an analog voltage that corresponds to the detected AC or DC current. Voltage sensors, on the other hand, are used to measure and monitor the voltage levels of an object, whether AC or DC.
D.	Arduino DUE: The Arduino Due is a microcontroller board powered by the Atmel SAM3X8E ARM Cortex-M3 CPU. It is the first Arduino board to utilize a 32-bit ARM core microcontroller. As outlined in Table 1, it features 54 digital input/output pins, 12 analog inputs, 4 UARTs (serial communication ports), an 84 MHz clock, USB OTG capability, 2 DAC (digital to analog converters), 2 TWI, a power jack, an SPI header, a JTAG header, a reset button, and an erase button. This board is ideal for larger and more complex Arduino projects. It serves as the base for the hardware prototype, which includes components such as the Arduino DUE, Arduino UNO, NODEMCU, current and voltage sensors, and LEDs.
 


(LIST OF THE COMPONENTS USED):
Item Name	    Quantity
Arduino UNO     	1
LDR Sensor	      4
NODEMCU(ESP8266)	1
LEDs (3.3V)     	9
Motor Driver    	1
ATMEGA 328      	1





(CONCLUSON):
This development model emphasizes the design and implementation of a street light monitoring system for two streets, where voltage, current, and power data are displayed using graphical representations. These graphs help in quickly identifying and resolving any issues that arise on the streets. Separate light indicators track the ON/OFF status of each LED, while relays provide control over the LEDs. Faults are detected and communicated to the user through fault indicators. The system utilizes the Blynk IoT platform, allowing for real- time monitoring and analysis of power consumption for each street. This method reduces the need for manual labor, saves time, and enhances the efficiency of detecting and addressing street light malfunctions, making the overall process of monitoring, controlling, and troubleshooting more streamlined and effective.


