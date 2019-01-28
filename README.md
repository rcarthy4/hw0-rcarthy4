# HW1 MIATT

DUE:  January 31, 2019 @ 4:49pm

ASSIGNMENT: Modify this README.md file that uses github markdown syntax to answers the following questions:

## Short answers:

###  What does the cmake program do?
```
Cmake is the build environment for ITK that manages projects and compilations in a simple platform-independent way (https://itk.org/ItkSoftwareGuide.pdf). It is a cross platform tool to mange the build process, simplify the build process, it is easier to access external libraries, and has auto-configuration (Icon Slide 19 02_01-ITK_Getting_Started.pdf). From my understanding, cmake is somewhat similar to visual studio code or sublime in that it is a source code editor that can compile and run the complexity of ITK. However, unlike Visual studio code or sublime, it is more powerful and is better suited to handle ITK and open-source projects and can use the libraries of projects like ITK.
```

###  How many regions does an ITK image require to be defined?
```
I know there are three regions for ITK which are the LargestPossibleRegion, BufferedRegion, and the RequestedRegion. From the slides on icon and the ITK handbook (https://itk.org/ItkSoftwareGuide.pdf) it seems as though the image must be instantiated and that all three of these regions must be defined to describe the image. 
```

###  Describe the role of each of the ITK image regions.
```
When talking about the three regions I like to compare it to a puzzle:
1. LargestPossibleRegion defines the entire image. This is the overall dataset and, using my analogy, is the entire puzzle that we are working with.
2. BufferedRegion is the portion of the LargestPossibleRegion that is currently in memory. I think of this as a section of the overall puzzle that we are focused on at the moment.
3. RequestedRegion is the portion of the image that is being worked on or proecessed. This is going into the BufferedRegion and processing a smaller section the image in that area.
So overall it should go LargestPossibleRegion >= BufferedRegion >= RequestedRegion where >= refers to larger than or similar in size. I put the = sign because if we are working with a smaller data set, we could theoretically have all three be the same.
````

###  How should the key work "typedef" be used in your homework assignments?
```
I believe from class we changed the key work "typedef" to "using" in C++11 however, it should be used to create/declare/instantiate a type. for example:
using ImageType = itk::Image< unsigned short, 3 >; (from https://itk.org/ItkSoftwareGuide.pdf)
in the example, using is required to instantiate the type Image class and then we can create images by then assigning a varible with a smartpointer.
```

###  What does it mean to be "const correct" when writing ITK classes? (HINT: http://en.wikipedia.org/wiki/Const-correctness)
```
From my understanding, const correct means that there cannot be a mismatch in the type. The example they show in the wiki page is the fact that the variable requires a variable integer but they are trying to pass in a constant integer which will not work since the program does not do polymorphism. 
(http://itk-insight-users.2283740.n2.nabble.com/itk-SmartPointer-problem-making-code-const-correct-td5109890.html)
(https://en.wikipedia.org/wiki/Const_(computer_programming))
```

## Programming assignment

In this part of the assignment you will create a binary program called `HW0.exe`.  The source code for this assignment must be in a directory called `src` with at least the following files:

``` bash
src/CMakeLists.txt
src/HW0.cxx
```

The HW0 binary must instantiate an image that:

* holds `std::complex<double>` values at each voxel location.
* Is a 7 dimensional image
* Has a start index at 0's
* Has 17 voxels in each direction.
* Has an identity direction
* Has spacing of 1.55 units between each voxel in each direction
* Fill the image with the value (2.2+3.3i) 
* Has an Origin as at 0.0's in each direction





