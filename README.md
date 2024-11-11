# EchoExpedite
A Self Driving car prototype made by students from sliet

Title: Autonomous Vehicle Using Google Maps and LiDAR for Object Detection
Introduction:
This project details the development of an autonomous vehicle that navigates using Google Maps and incorporates LiDAR for object detection. The vehicle uses a Raspberry Pi as the core processing unit, handling GPS data, navigation, and eventually obstacle detection. The project is divided into two main stages: Stage 1 focuses on implementing navigation using Google Maps, while Stage 2 involves integrating LiDAR for enhanced object detection.
Hardware and Software Components:
•	Raspberry Pi Model: Raspberry Pi 4B was chosen for its flexibility and processing power.
•	GPS Module: Neo 6M GPS module and a USB GPS receiver were used to obtain real-time location data.
•	LiDAR Sensor: To be installed in Stage 2 for object detection.
•	Navigation Software: Initially, Navit was tested for offline navigation, but it failed to meet the project requirements, leading to the use of Google Maps APIs. Here is an example which we used. We just used this to save our google maps expenses but at last found it unreliable as compared to google maps. The image below shows an example of our navit software.  
We even extracted the dir4ections steps which was a milestonebut not reliable. Here’s a sample:
 

Project Stages and Steps:
1.	Initial GPS Setup:
o	The Raspberry Pi was configured with a Neo 6M GPS module to provide latitude and longitude coordinates.
•	We initially used the gpsd daemon along with the cgps command for monitoring GPS data. However, the output included too much unnecessary information, such as raw NMEA data. The picture4 below shows the nmea stream which is in raw format so to make it readable, we use some commands. 
o	 To streamline this, we created a Python script to extract only the latitude and longitude from the cgps output. 
2.	Attempted Navit Integration:
o	We initially tried integrating Navit, an open-source navigation software, for offline routing. However, it lacked accuracy and compatibility with our GPS module, causing navigation failures. As discussed above, we dropped the navit software idea and started the code for google maps api setup. 
o	Due to these limitations, we switched to using Google Maps for real-time, reliable navigation. However, using Google Maps resulted in additional API costs, which was a significant trade-off.
3.	Switch to Google Maps Navigation:
o	Google Maps APIs (Directions, Geocoding, Places, Maps JavaScript) were integrated to handle routing and real-time map updates.
o	A search bar was added to allow users to enter destinations, and the current location was continuously updated on the map as a blue dot.
o	The project initially used GPSD with cgps, but the large amount of raw data led us to develop a Python script that only retrieved the essential latitude and longitude values.
4.	Running the Code:
o	The navigation software, including the HTML, CSS, and JavaScript code, was executed on the Raspberry Pi using Node.js.
o	The map was centered on the Punjab region, reflecting the project’s primary area of operation.
5.	Stage 2: LiDAR Integration (Ongoing):
o	The next step involves integrating a LiDAR sensor to detect obstacles and ensure the vehicle can avoid collisions. The sensor data will be processed by the Raspberry Pi, allowing the vehicle to adjust its route dynamically based on its surroundings.
Challenges and Limitations:
•	Raspberry Pi Performance: While the Raspberry Pi 4B is capable, it still has limitations when running multiple tasks like handling GPS data, API requests, and motor control simultaneously.
•	API Costs: Switching to Google Maps brought reliable navigation but incurred ongoing costs due to API usage, which was a drawback compared to free options like Navit.
•	GPS Data Accuracy: Extracting accurate latitude and longitude values was crucial. Initial attempts with GPSD provided raw NMEA data with excessive detail, so we switched to using a custom Python script for simpler output.
Conclusion:
This project demonstrates the development of a low-cost autonomous vehicle platform that leverages Google Maps for reliable navigation. Despite the challenges, the system has evolved to provide efficient GPS-based routing. As the project progresses, the integration of LiDAR will further enhance the vehicle’s capabilities, enabling real-world applications in smart transportation

