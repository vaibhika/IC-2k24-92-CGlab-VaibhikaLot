#### DDA Line Drawing Algorithm

#### Aim

To implement the Digital Differential Analyzer (DDA) line drawing algorithm in C++ using the graphics library to plot a straight line between two user-defined coordinate points on a scaled Cartesian coordinate system. 

#### Logic Description

The Digital Differential Analyzer (DDA) is a scan-conversion line algorithm based on calculating horizontal or vertical pixel differences (
Δ

𝑥
 and 
Δ

𝑦
). 

The algorithm determines the number of steps required to draw the line by taking the maximum absolute value of either 
Δ

𝑥
 or 
Δ

𝑦
:

steps=max(|Δx|,|Δy|)steps equals max of open paren the absolute value of delta x end-absolute-value  comma the absolute value of delta y end-absolute-value  close paren
steps=max(|Δ𝑥|,|Δ𝑦|)
 

In each iteration, the coordinates are incremented step-by-step using:

xincrement=Δxstepsx sub increment end-sub equals the fraction with numerator delta x and denominator steps end-fraction
𝑥increment=Δ𝑥steps

yincrement=Δystepsy sub increment end-sub equals the fraction with numerator delta y and denominator steps end-fraction
𝑦increment=Δ𝑦steps
 

The program maps the mathematical Cartesian origin 
(

0

,

0

)
 to the center of an 
800

×600
 graphics window 
(

400

,

300

)
. To make the output visually distinct and clear, the coordinates are scaled by a factor of 2, and the exact physical pixel location is calculated by rounding off the floating-point tracking values using the mathematical rounding rule before being plotted on the screen. 

#### Compilation and Execution

To run this program, you need a C++ compiler (like MinGW) configured with the graphics library (graphics.h). 

#### Prerequisites

* Ensure graphics.h and winbgim.h are available in your compiler's include directory.
* Ensure libbgi.a is linked under your linker parameters.

#### Linker Flags

If compiling via terminal or configuring project options, use the following linker flags: 

bash

-lbgi -lgdi32 -lcomdlg32 -luuid -loleaut32 -lole32

Use code with caution.

#### Sample Input and Output

#### Test Case 1: Slanting 45-Degree Line

* **Starting Point (x1 y1):** 0 0
* **Ending Point (x2 y2):** 100 100
* **Result:** A sharp, straight yellow line generating from the center origin and stretching upwards into the first quadrant.

#### Test Case 2: Horizontal Line Across Quadrants

* **Starting Point (x1 y1):** -150 50
* **Ending Point (x2 y2):** 150 50
* **Result:** A horizontal straight line running parallel to the gray X-axis, located in the upper half of the grid.