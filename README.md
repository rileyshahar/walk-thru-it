# Walk Thru It :footprints:

## Program Overview

### Part 1: Camera Perspective :movie_camera:

The implementation for the camera perspective is the same as
the solution to question 1 of the written assignment. Given
 `center`, `towards`, and `upwards`, `into`, `right`, `up` are calculated as
 the normal of the `towards` vector, the cross product of `into` and the normal of `upwards`, and  the cross product of `right` and `into`, respectively.

 ### Part 2: Projecting Vertices :round_pushpin:

Projection is done with the `project` function which works the same as part 2 of the written assignment. Given `aPoint`
we first find the projection vector given by `aPoint - center`. We use the projection vector to find the depth of the projected point. We then use this information to find the `X` and `Y` position of the point projected in 2-space.

### Part 3: Line Segment Intersections :negative_squared_cross_mark:

We first attempted to implement the line segment intersections
using a priority queue to keep track of the depth of the line segments. We felt that this would be faster than the
suggested algorithm since a priority queue would allow us to order the line segments by depth. Then we would be able to only compare the line segment to those behind it, rather than comparing each line segment to every other. However we ran into some issues with this algorithm and figured it would be easier just to use the suggested algorithm.

Our calculation for this part are taken from Jim's solutions, not our written assignment. Our version requires solving a system of linear equations to find the intersection point which would have been overly complicated in the code.

To find the intersection we can through all the object and compare each edge of the object to every other edge on the page. If there is an intersection we find the breakpoint and mark it in the PDF rendering.

### Part 4: Excluding Subsegments :no_entry_sign:
