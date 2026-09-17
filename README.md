# Smart Door Lock System 

An IoT-based Smart Door Lock System built using Arduino Uno, a fingerprint sensor, and an ESP32-CAM module. The system provides secure, biometric-based access control with an LCD display for real-time status updates and remote camera monitoring.

##  Overview

This project replaces traditional key-based locks with fingerprint authentication. When a registered fingerprint is detected, the system unlocks the door via a relay module and displays a confirmation message on the LCD. Unauthorized or unrecognized fingerprints are denied access, and the ESP32-CAM module allows for remote visual monitoring of the door.

##  Components Used

- Arduino Uno
- Fingerprint Sensor (Adafruit Fingerprint Sensor)
- 16x2 I2C LCD Display
- Relay Module (for door lock mechanism)
- ESP32-CAM Module
- LED Indicators (Red, Yellow, Green)

##  How It Works

1. The fingerprint sensor scans and captures the user's fingerprint.
2. The system compares it against enrolled fingerprint templates stored in the sensor.
3. If a match is found, the relay unlocks the door and the LCD displays "Door Unlocked."
4. If no match is found, access is denied and the LCD displays "Did not find a match."
5. The ESP32-CAM module streams live video for additional remote monitoring and can trigger the relay independently.

##  Project Files

| File | Description |
|------|-------------|
| `Door_lock_using_fingerprint_sensor.ino` | Main program — handles fingerprint scanning, matching, and door lock control |
| `enroll.ino` | Used to register/enroll new fingerprints into the sensor's memory |
| `esp32_cam_relay_control.ino` | Controls the ESP32-CAM module and relay for remote camera access and door control |

##  Setup Instructions

1. Install the required libraries in Arduino IDE:
   - `Adafruit_Fingerprint`
   - `LiquidCrystal_I2C`
   - `SoftwareSerial`
2. Connect the fingerprint sensor, LCD, and relay module to the Arduino Uno as per the pin configuration in the code.
3. Upload `enroll.ino` first to register fingerprints.
4. Upload `Door_lock_using_fingerprint_sensor.ino` to run the main access control system.
5. For camera monitoring, update the Wi-Fi credentials in `esp32_cam_relay_control.ino` and upload it to the ESP32-CAM module.

##  License

This project is licensed under the MIT License.
