# LED Control Project Using 74HC595 Shift Register and 555 Timer

## Project Overview

This project demonstrates controlling multiple LEDs using a 74HC595 shift register driven by a 555 timer. The 74HC595 allows for efficient expansion of output pins, letting you control multiple LEDs with only a few microcontroller or timer connections. Using the 555 timer as a clock source, this circuit sequentially shifts bits through the shift register, enabling a visual LED pattern.

This project is ideal for learning about shift registers, basic timing circuits, and efficient LED control with minimal I/O usage.

<p align="center">
    <img src="https://github.com/thynavy/LED_Control_Project_Using_74HC595/blob/main/74HC595.png" />
    <br />
    <strong>Figure 1: LED Control Project Using 74HC595 Shift Register and 555 Timer</strong>
</p>

## Features

- Efficient LED Control: Controls multiple LEDs using only three control pins through the 74HC595 shift register.
- Clocked by 555 Timer: Uses a 555 timer IC to generate a steady clock pulse that shifts data through the register, producing an LED sequence.
- Scalable Design: Additional 74HC595 ICs can be chained together to control even more LEDs.

## Components

1. 74HC595 Shift Register - 1x (expandable with additional ICs if more LEDs are needed)
2. 555 Timer - 1x, configured to produce clock pulses
3. LEDs - Number varies depending on the project (typically 8 per 74HC595)
4. Resistors - For LED current limiting and setting 555 timer frequency
5. Capacitors - For stabilizing the 555 timer
6. Potentiometer - Optional, for adjusting the frequency of the 555 timer
7. Breadboard and Jumper Wires
8. Power Supply - 5V or other suitable voltage, depending on LED and IC specifications

## Circuit Diagram

**Note:** [The circuit diagram (PDF)](https://github.com/thynavy/LED_Control_Project_Using_74HC595/blob/main/Schematic.pdf) This circuit shows the 555 timer in astable mode, generating clock pulses for the 74HC595 shift register, which sequentially lights up LEDs connected to its output pins.

## How It Works

1. Clock Pulse Generation with 555 Timer:
    - The 555 timer is configured in astable mode to produce a continuous clock signal. Adjusting resistor and capacitor values (or using a potentiometer) can vary the pulse frequency, changing the speed of the LED sequence.
2. Shift Register Operation with 74HC595:
    - The 74HC595 shift register takes the data input on its SER (Serial Data) pin, shifts the data with each clock pulse, and outputs it across Q0 to Q7 pins.
    - The SRCLK (Shift Register Clock) pin is connected to the 555 timer’s output, which shifts the bits through the register on each pulse.
    - The RCLK (Register Clock/Latch) pin updates the output pins, showing the new data pattern on the LEDs.
3. LED Control:
    - LEDs connected to Q0 to Q7 of the 74HC595 display a pattern depending on the data shifted through the register.
    - Using specific binary data sequences, you can create various LED effects, like a “chase” effect, where each LED lights up in sequence.

## Setup and Usage

1. Circuit Assembly:
    - Place the 74HC595 shift register and 555 timer ICs on a board.
    - Connect the LEDs to the output pins (Q0 to Q7) of the 74HC595, with current-limiting resistors in series to protect the LEDs.
2. Data Loading:
    - Use a microcontroller or manually toggle the data line to the 74HC595’s SER pin to control the bit pattern. This can also be automated with additional 555 or logic circuitry.
3. Power Up and Adjust:
    - Connect a 5V-9V power supply (or as required by the components) and power the circuit.
    - Adjust the potentiometer (if used) to control the speed of the LED sequence.

## Example Applications

This project is suitable for:
  - Learning how to use shift registers and save GPIO pins.
  - Creating visual LED patterns, chaser lights, or other dynamic light displays.
  - Experimenting with clocked and timed circuits.


