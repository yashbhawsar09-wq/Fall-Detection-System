# 🚨 Fall Detection System (Hardware-Based Biomedical Project)

## 📌 Project Overview
This project implements a **hardware-based fall detection system** for elderly and patient safety. It uses motion sensors (accelerometer + gyroscope) interfaced with a microcontroller to detect sudden falls in real time. On detecting a fall, the system **activates a buzzer** and **sends an SMS with GPS location** via GSM.

The design emphasizes **reliable sensing, robust interfacing, and low-power portable operation**, making it suitable for wearable healthcare devices.

---

## 🎯 Objectives
- Detect falls using **sensor hardware (MPU6050)**  
- Implement **real-time embedded processing**  
- Trigger **local alarm (buzzer)** and **remote alert (GSM + GPS)**  
- Build a **portable, battery-powered system**  

---

## 🧠 Hardware Working Principle
- **MPU6050** measures 3-axis acceleration and angular velocity  
- Sudden acceleration spike + orientation change → fall event  
- Microcontroller evaluates thresholds and confirms fall  
- On detection:
  - **Buzzer ON**
  - **GPS acquires coordinates**
  - **GSM sends SMS alert**

---

## 🧩 Hardware Components

### 🔧 Core Components
- Microcontroller: Arduino Uno / ESP32  
- IMU Sensor: MPU6050 (Accelerometer + Gyroscope)  
- GSM Module: SIM800L  
- GPS Module: NEO-6M  
- Buzzer (5V)  
- LED Indicators  
- Li-ion Battery (3.7V) / 5V supply  
- Voltage Regulator (AMS1117 / Buck Converter)  

---

## 🔌 Hardware Interfacing

### 📍 MPU6050 (I2C Communication)
- VCC → 5V / 3.3V  
- GND → GND  
- SDA → A4 (Arduino)  
- SCL → A5 (Arduino)  

### 📍 GSM Module (UART)
- TX → RX (Microcontroller)  
- RX → TX (Microcontroller)  
- External power recommended (stable 4V supply)

### 📍 GPS Module (UART)
- TX → RX  
- RX → TX  

### 📍 Output Devices
- Buzzer → Digital Pin  
- LED → Digital Pin (via resistor)

---

## ⚙️ System Architecture (Hardware Flow)
1. Sensor acquires motion data  
2. Microcontroller reads via I2C  
3. Threshold logic executed  
4. If fall detected:
   - Activate buzzer  
   - Fetch GPS coordinates  
   - Send SMS via GSM  
5. Else:
   - Continue monitoring  

---

## 🔋 Power Management
- Use **Li-ion battery (3.7V)** with boost converter  
- GSM module requires **stable high current (~2A peak)**  
- Ensure proper grounding and noise filtering  
- Add capacitors for voltage stabilization  

---

## 🧮 Calibration & Testing
- Allow MPU6050 calibration at startup  
- Set acceleration threshold experimentally (~2g–3g)  
- Test with:
  - Normal walking → no trigger  
  - Sudden fall simulation → alert triggered  

---

## 🚀 Hardware Features
- Real-time motion sensing  
- Portable wearable design  
- On-device alert (buzzer)  
- GSM-based emergency notification  
- GPS location tracking  

---

## ⚠️ Hardware Limitations
- False triggers due to sudden jerks  
- GSM requires strong network signal  
- Battery life constraints  
- Sensor drift if not calibrated  

---

## 🔮 Future Hardware Improvements
- Use **dedicated wearable PCB design**  
- Add **battery management system (BMS)**  
- Replace GSM with **LTE/NB-IoT module**  
- Integrate **compact antenna design**  
- Use **low-power microcontroller (ESP32-S3 / ARM Cortex)**  

---

## 📊 Applications
- Elderly monitoring devices  
- Hospital patient safety systems  
- Home healthcare wearable devices  
- Rehabilitation monitoring  

---

## 🛠️ Setup Instructions (Hardware)
1. Assemble circuit on breadboard/PCB  
2. Verify power supply stability  
3. Connect all modules as per pin diagram  
4. Upload firmware via Arduino IDE  
5. Calibrate sensor  
6. Test fall detection  

---

## 📚 Conclusion
This project demonstrates a **hardware-centric biomedical system** integrating sensors, communication modules, and embedded processing to provide **real-time fall detection and emergency response**.

---

## 👨‍💻 Author
- Name: Yashodeep Bhawsar  
- Field: Biomedical Engineering  

---

## 📄 License
For academic and educational use only.
