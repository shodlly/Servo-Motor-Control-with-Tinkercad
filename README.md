

# Servo Motor Control with Tinkercad

This README outlines the procedure for connecting and programming a circuit with six servo motors using Tinkercad. The provided code reads analog inputs and maps them to servo angles to control the motors' positions.

## Components

- 6 Servo Motors
- 6 Analog Potentiometers
- Arduino Board

## Circuit Setup

1. **Connect the Servo Motors:**
   - Attach each servo motor to the following pins on the Arduino:
     - Motor 1 to Pin 7
     - Motor 2 to Pin 8
     - Motor 3 to Pin 9
     - Motor 4 to Pin 10
     - Motor 5 to Pin 11
     - Motor 6 to Pin 12

2. **Connect the Potentiometers:**
   - Connect the analog output of each potentiometer to the following analog pins on the Arduino:
     - Potentiometer 1 to Analog Pin A0
     - Potentiometer 2 to Analog Pin A1
     - Potentiometer 3 to Analog Pin A2
     - Potentiometer 4 to Analog Pin A3
     - Potentiometer 5 to Analog Pin A4
     - Potentiometer 6 to Analog Pin A5

## Code

The following code reads the values from the potentiometers, maps them to servo angles, and controls the position of each servo motor.

```cpp
#include <Servo.h>

int x1 = 0;  // Declare variables for potentiometer readings
int x2 = 0;
int x3 = 0;
int x4 = 0;
int x5 = 0;
int x6 = 0;

Servo motor1;   // Declare six servo motors
Servo motor2;
Servo motor3;
Servo motor4;
Servo motor5;
Servo motor6;

void setup(){
    motor1.attach(7);  // Attach each motor to its respective pin
    motor2.attach(8); 
    motor3.attach(9);
    motor4.attach(10);
    motor5.attach(11);
    motor6.attach(12);
}

void loop(){
    x1 = analogRead(A0);        // Read the value from potentiometer 1
    x1 = map(x1,0,1023,0,179);  // Map the value to an angle (0 to 179 degrees)
    motor1.write(x1);           // Set motor 1 position
    delay(10);                  // Short delay for stability

    x2 = analogRead(A1);        // Repeat for all other potentiometers
    x2 = map(x2,0,1023,0,179);
    motor2.write(x2);
    delay(10);

    x3 = analogRead(A2);
    x3 = map(x3,0,1023,0,179);
    motor3.write(x3);
    delay(10);

    x4 = analogRead(A3);
    x4 = map(x4,0,1023,0,179);
    motor4.write(x4);
    delay(10);

    x5 = analogRead(A4);
    x5 = map(x5,0,1023,0,179);
    motor5.write(x5);
    delay(10);

    x6 = analogRead(A5);
    x6 = map(x6,0,1023,0,179);
    motor6.write(x6);
    delay(10);
}
```

## Simulation

1. Open Tinkercad and load your circuit design.
2. Upload the provided code to the Arduino simulation.
3. Adjust the potentiometers to see the corresponding servo motors move according to their angles.
![image](https://github.com/user-attachments/assets/c13d0d4c-c96d-402a-8496-376d44c964d3)

## Notes

- Ensure that all connections are secure in the simulation to avoid any disconnections.
- Adjust the delay if the servo response seems too slow or too fast.

