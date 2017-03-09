#**Finding Lane Lines on the Road** 

The goals / steps of this project are the following:

* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./test_images/solidWhiteCurve.jpg_gscale.jpg "Grayscale"
[image2]: ./test_images/solidWhiteCurve.jpg_gblur.jpg "Gaussianblur"
[image3]: ./test_images/solidWhiteCurve.jpg_canny.jpg "Cannyedge"
[image4]: ./test_images/solidWhiteCurve.jpg_region.jpg "Regionofinterest"
[image5]: ./test_images/solidWhiteCurve.jpg_hough.jpg "Houghtransform"
[image6]: ./test_images/solidWhiteCurve.jpg_region2.jpg "Regionofinterest2"
[image7]: ./test_images/solidWhiteCurve.jpg_output.jpg "Output"

---

### Reflection

###1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consists of 6 steps. First I convert an image into gray scale and use gaussian blur for better result from canny edge detection algorithm. Then I pass it through region of interest to avoid unnecessary edges. This image is then passed through hough transform to retrieve lines on a diagram and then extrapolated line to edge of the image boundary. Again I pass through region of interest and then merge that image with actual image with weights to superimpose line on the image


1.	Convert Image -> Gray Scale
![Gray Scale][image1]

2. Convert Gray Scale -> Gaussian Blur
![Gaussian Blur][image2]

3. Convert Gaussian Blur -> Canny Edge
![Canny Edge][image3]

4. Canny Edge -> Region Of Interest
![Region of Interest][image4]

5. Region of Interest -> Hough Transform
![Hough Transform][image5]

6. Hough Transform -> Region Of Interest
![Region of Interest][image6]

7. Region Of Interest -> Output
![Output][image7]


###2. Identify potential shortcomings with your current pipeline

Current shortcoming I see is smoothness frame over frame. Mainly because slope is calculated in every frame and slope differences makes it a bit jittery

###3. Suggest possible improvements to your pipeline

If some how smoothening can be applied so that slope changes are not abrupt but changes gradually, it would reduce jittery
