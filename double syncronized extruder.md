[extruder]
step_pin: PE2
dir_pin: !PE3
enable_pin: !PD4
##	Update value below when you perform extruder calibration
##	If you ask for 100mm of filament, but in reality it is 98mm:
##	rotation_distance = <previous_rotation_distance> * <actual_extrude_distance> / 100
##  22.6789511 is a good starting point
rotation_distance: 24.5	#bmg 
##	Update Gear Ratio depending on your Extruder Type
##	Use 50:17 for Afterburner/Clockwork (BMG Gear Ratio)
##	Use 80:20 for M4, M3.1
gear_ratio: 7:1				#BMG Gear Ratio
microsteps: 32
full_steps_per_rotation: 200	#200 for 1.8 degree, 400 for 0.9 degree
nozzle_diameter: 0.400
filament_diameter: 1.750
max_extrude_only_velocity: 100
max_extrude_only_accel: 300
max_extrude_only_distance: 102
##      In E0 OUT Position
heater_pin: PA1
#sensor_type: ATC Semitec 104GT-2
sensor_type: PT1000
sensor_pin: PF3

control: pid
pid_kp = 26.213
pid_ki = 1.304
pid_kd = 131.721


min_temp: 5
max_temp: 500
max_power: 1.0
min_extrude_temp: 180

[tmc2209 extruder]
uart_pin: PE1
interpolate: false
run_current: 0.4
hold_current: 0.4
sense_resistor: 0.110
stealthchop_threshold: 0


##  In E4-MOT Position
[extruder_stepper my_extra_stepper]
extruder = extruder  #同步到extruder上
step_pin: PE6
dir_pin: !PA14
enable_pin: !PE0
microsteps:32
rotation_distance: 22.9  #bmg 
gear_ratio: 50:17               #BMG Gear Ratio
full_steps_per_rotation: 200    #200 for 1.8 degree, 400 for 0.9 degree
#shared_heater: extruder
#nozzle_diameter: 0.400
#filament_diameter: 1.75

##  In E4-MOT Position
##  Make sure to update below for your relevant driver (2208 or 2209)
[tmc2209 extruder_stepper my_extra_stepper]
uart_pin: PD3

interpolate: false
run_current: 0.6
hold_current: 0.6
sense_resistor: 0.110
stealthchop_threshold: 0
