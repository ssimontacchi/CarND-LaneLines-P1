# **Finding Lane Lines on the Road**
[![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)

<img src="examples/laneLines_thirdPass.jpg" width="480" alt="Combined Image" />
## Writeup

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Pipeline description

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I ....
1. Converting the image to grayscale
2. Applying a Gaussian smoothing to reduce noise
3. Applying Canny edge detection to find the edges of objects
4. Applying a Hough Transform to generate lines from detected points
5. Identify the best candidates for lines

The most interesting part of the process was identifying the best lines, which I did by using the median of the candidate line slopes, and throwing away and lines with slopes that were not between 30 and 60 degrees.  


### 2. Potential shortcomings


One potential shortcoming would be that if a stray light colored pixel appears near a line, it can throw off the angle of the main line momentarily.

To deal with this, if there is no appropriate candidate line, I do not draw any line at all, which leaves brief moments when lane lines are not explicitly identified.


### 3. Possible improvement

A possible improvement would be to shrink the space of the polygonal mask around the lane lines so there would be fewer distracting pixels.

Thanks for reading!
