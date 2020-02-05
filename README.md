# Face-Recognition-and-Tracking
Assist Teachers using Face Recognition!!

This program also calculates the time people enter the class and the time they leave it. It also gives you a list of present and absent people of a class. If you run the program, you can see the people who are detected with a name above their heads.

To do this task, we need to detect faces(rectangles) as well as recognition. We call it Face Recognition task.

We gathered data from the faces of my classmates in Computer Vision Course. Then we fed this data to a deep neural network.
This network should try to learn people by their faces.

To do this, there were many Convolutional Layers suggested, but we preferred to use some pre-trained networks. The reason is crystal clear; we did not have enough time and data, so a frozen network with well-trained weights is ideal for us. Transfer Learning is mostly a good idea for these kinds of tasks. 

We used a module named "face_recognition" which has been trained on 3 Million pictures of humans and is known as a powerful model for Face Recognition. The accuracy of this network is about 99.38%.

In the testing section, we have to compare the encoding values of our input video to the ones that we have learned before. 
This is done in the SVM classification section and the ones that are close together are selected.
From these detected boxes, we find the names of the people after comparing them to the list we already had from the train encodings and display them at the top of the box.

Calculate student attendance time:
Our goal with this project is to measure attendance while students are in class.
Due to the inadequacy of the test data and the poor performance of the network, we then consider and measure the time between the two recognitions for each individual so that there is no problem if the student is not identified at the moment. But if the time difference between the two recognitions exceeds the limit, we assume that one is out of class.


For each person, we save the first detection time and calculate the next time it is detected, subtracting the two undetected times between them.

We add these values ​​to each detection of individuals and the final value is equal to the total time the person was in class.

At each detection, we check that the time between two consecutive detections is assumed to have been dropped if more than 1 minute (gained practically) is assumed.

