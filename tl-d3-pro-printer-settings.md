# Tenlog TL-D3 Pro

## Printer settings

| Dimension | Size|
| --- |  ---: |
| X | 305 |
| Y | 305 |
| Z | 350 |

## Printhead settings

| Dimension | Size |
| --- |  ---: |
| X min | -75mm |
| Y min | -18mm |
| X max | 18mm |
| Y max | 35mm |
| Gantry height | 55.0mm |

## Start GCode:

```
G21 ;metric values
G90 ;absolute positioning
M82 ;set extruder to absolute mode
M107 ;start with the fan off
G28 ;Move to min endstops
G1 Z15.0 F9000 ;move the platform down 15mm
M117 Printing...
```

## End GCode:

```
M104 T0 S0 ;1st extruder heater off
M104 T1 S0 ;2nd extruder heater off
M140 S0 ;heated bed heater off (if you have it)
G91 ;relative positioning
G1 E-1 F300  ;retract the filament a bit before lifting the nozzle, to release some of the pressure
G1 Z+0.5 E-5 X-20 Y-20 F9000 ;move Z up a bit and retract filament even more
G90 ;absolute positioning
G28 X Y ;move X/Y to min endstops, so the head is out of the way
G1 Y300
M84 ;steppers off
```
