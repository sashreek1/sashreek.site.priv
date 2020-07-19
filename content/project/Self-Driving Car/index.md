---
title: Self-Driving Car
summary: An article explaining my Self-Driving Car.
tags:
- Haar Cascade
- OpneCV
- Python
- Raspberry Pi
date: "2020-05-10T00:00:04Z"

# Optional external URL for project (replaces project detail page).
external_link: ""

image:
  caption: picture of the prototype
  focal_point: Smart

links:
url_code: ""
url_pdf: ""
url_slides: ""
url_video: ""

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: example
---

Recently there has been all this talk about self-driving cars and how helpful they can be, apart from this there has also been major talk about how difficult it can be to build one. So I decided to build my own.

## Parts
To build this I have used :
- Raspberry Pi 3 B+
- Raspberry Pi Camera
- HC-SR04 distance sensor x 3
- LEGO Mindstorm pieces (For the Chasis)
- Jumper cables
- Arduino uno 
- L298N Motor Driver
- 1000 RPM, 2 kg-cm motor x 2


## Working
The entire car works based on 2 seperate processes:
- the distance sensor
- camera  

the rudimentary distance sensor provides highly reliable distance data which can drastically reduce the number of crashes. 3 of these sensors have been placed at the front, left and right sides of the car. The sensors on the sides directly control the steering system while the front sensor conteols the acceleration and deceleration.  
  
Along with a functional obstacle detection system the car also has an **object detection system**. The car's onboard camera system provides live data about recognised road signs such as the "stop sign" or the "school ahead sign". The camera also tries to detect the presence of a traffic signal and obey the traffic lights.  
  
While the straight forward logic of running these processes together would be to run these processes in individual threads simultaneously, this is impractical. The Raspberry Pi has very slow GPU and hence performs complex image recognition on an ARM based CPU. Hence running the two processes simultaneously would slow down the reaction time of the car. To over come this, I have queued these processes and also provided a time limit for both the process.

## Code 
You can view all the required code for this project in the following GitHub link
[https://github.com/sashreek1/self-driving-car](https://github.com/sashreek1/self-driving-car)

