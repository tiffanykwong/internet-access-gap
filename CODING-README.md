# cs-3300-proj1
Project 1 for course CS 3300, spring 2015.

Static visualization of U.S. Census data on computer usage, income level, and disability status.


#Data structure
"area" objects refer to an area (e.g. a region or a division) and have the properties:
- name (e.g. "Northeast")
- num00, num01, totalPop, gap : attributes for that whole area
- members : an array containing state objects, each of which corresponds to a state. sorted by gap.

An array 'regions' contains five area objects corresponding to the five regions (including U.S.).
An array 'divisions' contains nine area objects corresponding to the nine divisions.
Both are sorted by average gap of its member states, except for the US area, which is listed first.

Each state object has attributes which are the ones listed in the .csv.

Note that code which accesses this data must be written within the d3.csv call. This is some weird scoping issue. 

# Functions that may come in handy:
drawLightLine(coords) /**draws a light gray line given coordinates in form [[x1,y1],[x2,y2]]**/

drawRect(coord, width, height, id) /**draws a black-filled rectangle given coordinates of top-left corner, width, height, and an id**/

writeTextCentered(coords, text, id) /** draws text that is centered at coordinates coords in form [x,y]. Also gives it the identifier id so that the text can be subsequently found by d3.selectAll('#id'). **/

/**Note that if you use some of these, you can change the attributes and styles by doing
d3.select('#id').attr(...)
so you're not fixed to the default attributes **/

# Constants
Variables that may come in handy:
SVG_HEIGHT, SVG_WIDTH
origin /** coordinates for origin in form [[x1,y1],[x2,y2]] **/
xAxisEndpt /** same as above, for the endpt of the x-axis line **/
yAxisEndpt /** same as above, for the endpt of the y-axis line **/
COLOR00, COLOR01, etc. /**colors for all rectangles with id's #rect00, #rect01, etc. **/



Note that hard-coded constants (e.g. height and width of SVG element, padding around the chart) are given capitalized names.
So if, e.g., you find that the padding on the left doesn't given enough space for writing in state names, then just change the constant LEFT_PADDING. You won't have to worry about changing this at fifteen different points in the code.
Similarly, if you find that you need to use something hard-coded, please check if there's an existing constant for it and if there isn't, please create one! (unless you are totally absolutely certain that at no point ever will this number need to be referred to again).


#Colors
The colors for the four types are hard-coded as COLOR00, COLOR01, etc.