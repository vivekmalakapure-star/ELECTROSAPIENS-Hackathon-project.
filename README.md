# ELECTROSAPIENS-Hackathon-project.
I along with my teammates have  built a project for industrial motors health prediction using machine learning. We as a team of 3 were supposed to build an Edge AI Predictive Maintenance model for Industrial Motors. We were given 24 hours to build the prototype.

What we wanted to build:

We used 
* R385 motor
* ESP32S2
* Buzzer
* INA226 current and voltage sensor
* MPU6050 accelerometer and gyroscope for measuring vibraion
* Hall sensor for RPM measurement


We will initially measure all the factors like current, voltage, RPM,and vibration as well by running the motor for 10 minutes,using all the sensors,save the output it in the .csv format.
Then we will feed this data to  train an ML model, let it make patterns to understand how does a healthy motor works and also calculate efficiency.After this is done, we will use another ML model for telling us based on the previous model and the live data it is receiving from the R385 motor.
The second model will be an anomaly detection which will make us alert if the efficiency is decreasing rather than just any if-else condition.

What we ended up building: 

We began the process but after sometime (during the evening of 25th Sept 2026) the current sensor INA226 was not working and we realised that two of our parameter are in danger as we cannot measure them.
We did not bring the extra components and I feel this is definitely our mistake.We even tried to get it from the shop. We used Uber's Porter (Parcel Service) and asked the guy to get those required items but unfortunately he misheard the name of the INA226 which we needed and gave us wrong components.
At this moment I was feeling that we might not even develop a working prototype at the end.Then we all 3 teammates decided to train the whole ML model only on RPM and predict the vibration.
We repeated the same procedure as above without current and voltage. Then instead of using another ML model we used a Statistical model.
First we calculated a Threshold Peformance Index (which is formed by using 3-Sigma Rule which is Mean of predictions + 3*Standard Deviation so that we get to know how far is the value of vibration from the mean) based on the predictions of the healthy motor and we made it as a fixed constant value.
Then whenever the model runs on the motor it will calculate PI for every half a second and if it is higher than the Threshold PI for about 5 seconds continuously then it will beep the buzzer.

So this was the project that we built on our first 24 hour hackathon.
