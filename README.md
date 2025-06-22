# smart_lamp_group_6
![Screenshot 2025-06-22 094517](https://github.com/user-attachments/assets/1f2e6579-ec2c-420c-b6d4-7dc41c257de6)

The Smart Light System with Temperature and Humidity Monitoring is an Internet of Things (IoT) solution designed to automatically control a humidifier and lighting based on environmental conditions. The system uses a microcontroller, such as an ESP32 or Arduino, which is connected to a temperature and humidity sensor (like a DHT11 or DHT22). This sensor continuously collects data from the environment and sends it to the microcontroller. The microcontroller is programmed to communicate securely with an MQTT broker using TLS encryption over port 8883, ensuring that data transmission is protected against unauthorized access.

Once the sensor data is published to the MQTT broker, it is then received by a Node-RED server that is subscribed to the relevant topic. Node-RED processes the incoming temperature and humidity values and checks them against predefined thresholds. If the humidity level falls below a certain value, such as 50%, Node-RED sends a command back through the MQTT broker to activate the humidifier via a relay connected to the microcontroller. When the humidity level reaches or exceeds the threshold, the system turns the humidifier off. Additionally, the lighting system can be set to operate based on temperature conditions or can be manually controlled through the Node-RED dashboard interface.

To set up the hardware, the temperature and humidity sensor is connected to the appropriate GPIO pin of the microcontroller, along with power and ground connections. Relays are wired to the microcontroller to control the power to the smart LED light and the humidifier. Once the hardware is connected, the microcontroller firmware is uploaded using the Arduino IDE or PlatformIO, and it includes code to read sensor data and establish a secure MQTT connection. The MQTT broker, configured using Mosquitto, must have TLS enabled on port 8883, with appropriate certificates and password authentication in place.

On the software side, Node-RED must be installed and configured to connect to the MQTT broker. Within Node-RED, flows are created to subscribe to sensor data topics, evaluate the incoming values, and send control commands based on logic conditions. The Node-RED dashboard can also be used to visualize live temperature and humidity readings and allow manual override of the smart light or humidifier. This system architecture ensures both automation and security, making it suitable for smart home or office environments.

Software Use

i) Wokwi 
ii) ngrok
iii) mosquitto
iv) node-red 
v) gitbash

Instructions

1.Put the code in the wokwi
2. run ngrok in the terminal using the command given
cd C:\Users\PC-NAME .\ngrok tcp 8883
 
3. run mosquitto in terminal or gitbash using command given
mosquitto -v -c "C:\Program Files\mosquitto\mosquitto.conf"

4.run node-red using command given 
node-red 

5. run node-red dashboard 
http://127.0.0.1:1880/ui
