# Deep Learning and Machine Vision, Deep Dive

## Intro
Machine vision (MV) is a multidisciplinary field that requires knowledge in lighting, optics, sensors/cameras, and their integration. 
And before embarking on a journey of designing such a system, there are many questions that need answers; business case, application, 
software, hardware, integration, human interface, to name a few.
This blog will explain the most common questions that need to be asked in order to design a hardware component on the MV system.

## What is a defect?
Due to humans’ subjective nature, what is seen as a defect by one person, may not be the case for another person. Therefore, the first step 
in designing an MV system is to have a clear understanding of what constitutes a defect.

## How small  is the smallest defect?
Whether you are looking for a dent on an automotive gear tooth, or a missing resistor on a printed circuit board assembly (PCBA), 
you have to ensure that there is enough spatial resolution (pixels) to successfully see that defect.


## How big is the area of interest?
In order to calculate the appropriate size of the imaging sensor in megapixels (MP), you need to know the overall dimensions of the part 
(automotive gear, or PCBA). This is called the field-of-view or (FOV). Additionally, you may need to account for random orientation of the 
part given that it may not be perfectly placed on the conveyor belt every time. So, the final FOV needs to account for this orientation.

## How many cameras (views) do you need?
Oftentimes, the FOV is large and one camera will not cover it. In this case you may need several cameras to see the entire FOV. Furthermore, 
some part will need multiple viewing angles (top-down view, side view, and/or angled view)

## Is the part stationary or moving?
If the part is stationary, you may use a sensor/camera that has a rolling shutter. This is a more affordable option to a global shutter that is 
used when imaging moving parts. Rolling shutter sensors/cameras cost significantly less (50%).


## How fast is the part moving?
If the part is stationary, or moving relatively slow (slower than the shutter speed), then you are looking at an area sensor/camera. 
On the other hand if the part is moving fast, then you need to look into either line scan or TDI sensor/camera. Silicon is expensive, 
therefore larger silicon will cost more.

## Is color identification important?
If you need the color component, then a color sensor/camera is the option. If you do not care about color, then you are better off with a 
monochrome sensor/camera. Price difference is insignificant.


## Is the part transparent or opaque?
This will dictate your illumination strategy. You may need white light, UV, or any other light depending on the application. 
These lights may come in different shapes and forms from ring LED, bar, and panel lights to name a few. 

## Are there any physical constraints for the system?
The system might have a constraint in the vertical direction for example, where a certain height cannot be exceeded. This will dictate the 
working distance, WD, which is the distance from the object to the lens.


## Is there a requirement for the interface?
The speed and the bandwidth of image data are important considerations when designing an MV system. In addition, a system might be located 
far away from the host PC (inference) and a longer physical medium may be needed. Luckily, there are several options when it comes to the 
camera interface; Ethernet (GigEVision), USB (USBVision), Frame grabber (Camera Link, HS Link, CoaXPress, etc.) are amongst the most popular ones.

## Conclusion
Machine vision is a multidisciplinary field that has many different aspects to it. And for this reason, it is very hard to get the design right 
the very first time. You may find yourself iterating over your design several times before you get it right, and this is desirable for two reasons: 
1. Once the system is integrated it is time consuming and cost prohibiting to redesign, and
2. There is a risk of lost opportunity cost should the system be wrong.
