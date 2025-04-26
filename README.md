TransBin OS 2.0

A compact character-based operating system for ATmega328, ATmega1284, and ATmega2560 development boards — featuring its own Lisp interpreter, display, buzzer, and keyboard interface.

📖 Introduction

TransBin OS 2.0 is a self-contained microcontroller-based computer system featuring:

* 21x8 character OLED display

* PS/2 keyboard input

* Onboard buzzer for alerts

* External memory support (SRAM, EEPROM, Flash)

* It is fully programmable using a compact version of Lisp (uLisp) directly from the device or via the Arduino Serial Monitor.

⚡ Specifications

ATmega328 (Arduino Uno, Nano, Pro Mini)

* Display: 21 characters × 8 lines

* Memory: 316 Lisp cells (~1264 bytes)

* EEPROM: 256 Lisp cells (1KB)

* Functions: 122 Lisp functions

* Interfaces: Analog I/O, Digital I/O, I2C, SPI

Notes: Best used with upgraded external SRAM.

ATmega1284

* Display: 21 characters × 8 lines

* Memory: 3001 Lisp cells (~12KB)

* EEPROM: 1024 Lisp cells (4KB)

* Functions: 125 Lisp functions

* Interfaces: Extended analog/digital I/O, I2C, SPI

Notes: Fully supports all external memory interfaces simultaneously.

ATmega2560

* Display: 21 characters × 8 lines

* Memory: 8KB RAM

* EEPROM: 1024 Lisp cells (4KB)

* Functions: 125 Lisp functions

Notes: Only supported under TransBin OS 1.0.

🌟 New Features in 2.0

* Multi-processor support (328, 1284)

* External Memory Interface: SRAM, EEPROM, Flash via SPI/I2C

* Parenthesis Matching: Auto highlights while typing Lisp code

* Serial Monitor Interface: Program via Arduino IDE's Serial Monitor

* Built-in Program Editor: Step through and modify Lisp programs easily

🛠 Setup

* Display: 0.96" 128x64 OLED (SSD1306/SSD1309/SH1106)

* Keyboard: PS/2 standard keyboards (e.g., Dell PS/2)

* Buzzer: 3V DC buzzer for alerts

* External Memories (optional):

  * SRAM: 23LC512

  * EEPROM: 24LC512

  * Flash: Winbond 25Q64

🧠 Example Programs

Example             | Description
Blink               | Flash LED on pin 13 every second
Analog Read         | Continuously read A0–A5 analog values
I2C Interface       | Read from HMC5883L magnetometer
Save/Load           | Save and load Lisp programs to EEPROM

Example - Blink an LED:

(defun b (x) 
  (pinmode 13 t) 
  (digitalwrite 13 x) 
  (delay 500) 
  (b (not x)))
(b nil)

🖥 Program Editing

Modify existing Lisp functions easily:

(edit 'function-name)

Single key commands for navigation and editing:

a: Move to car

d: Move to cdr

r: Replace

c: Cons

x: Delete

b: Back

q: Quit
