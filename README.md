This code is based on a fork of grbl-0.8 of LETARTARE who added experimental 4 axis support.

It as meant to drive a hotwire foam cutter that has 2x2 axes in two indendent planes.
Currently it supports the protoneer cnc shield with 4x Pololu A4988 drivers on an arduino uno.

The following changes to the orginal code where applied:

+ Drive the 4th axis of the protoneer cnc shield which is not on the same arduino port as the other 3 axes. The original code was meant to run on an arduino mega which is not pin compatible with the protoneer cnc shield. The changes where made in stepper.c

+ Make the axes X,Y and U,V independent. The original code had X,Y,Z still beeing dependent and an additional independet rotational axis A,B,C or linar axis U,V,Z. This applies to the feedrate computatation in planner.c. There is still some work to do concerning the acceleration computation.

+ Make the GCode Interpreter understand commands like "G1 X1 Y1 U2 V3". Very simple.

It might be difficult to reintegrate the changes into the orginal code, so i did not fork the original project. This is just here for anyone who wants to drive a hotwire foam cutter with grbl.
The wire runs quite smooth through the foam on my own machine.


