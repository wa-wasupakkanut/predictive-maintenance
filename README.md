Predictive Maintenance System (Vibration Analysis)

Project Overview

Predictive Maintenance ที่ใช้ข้อมูล Vibration (การสั่นสะเทือนของเครื่องจักร) เพื่อตรวจสอบสภาพเครื่องจักรและคาดการณ์ความเสียหายที่อาจเกิดขึ้นในอนาคต

ระบบจะทำการ
* อ่านข้อมูล vibration จากไฟล์
* วิเคราะห์ค่าการสั่นสะเทือน (RMS)
* ประเมินสถานะของเครื่องจักร
* วิเคราะห์แนวโน้มการเสื่อมสภาพ
* คาดการณ์วันที่อาจเกิดความเสียหาย
* สร้างรายงานสรุปผล

ผลลัพธ์สุดท้ายจะถูก Export เป็น ไฟล์รายงาน CSV

Project Structure
โครงสร้างของโปรเจกต์มีดังนี้

predictive-maintenance
│
├── data
│   เก็บข้อมูล vibration ของเครื่องจักร
│
├── output
│   เก็บไฟล์รายงานผลลัพธ์
│
├── source_code
│   ├── processor.py
│   ├── analyzer.py
│   └── predictor.py
│
├── venv
│   virtual environment สำหรับ Python
│
├── main.py
│   โปรแกรมหลักสำหรับรันระบบทั้งหมด
│
└── requirements.txt
    รายการ library ที่ต้องใช้

# Workflow การทำงานของระบบ

ขั้นตอนการทำงานของระบบมีดังนี้

1 อ่านข้อมูลจากโฟลเดอร์ Data

ระบบจะโหลดข้อมูล vibration จากไฟล์ในโฟลเดอร์ data/

ข้อมูลจะประกอบด้วย
* Equipment Name
* RMS value
* Time series data

2 Data Processing
ไฟล์ `processor.py` ทำหน้าที่
* รวมข้อมูลจากหลายไฟล์
* ทำความสะอาดข้อมูล
* จัดรูปแบบข้อมูลให้อยู่ในรูปแบบ DataFrame

Library ที่ใช้หลัก ๆ
* Python
* pandas

3 Vibration Analysis
ไฟล์ `analyzer.py` ทำหน้าที่วิเคราะห์ค่าการสั่นสะเทือน
ระบบจะคำนวณค่า
RMS (Root Mean Square)

แล้วนำไปเปรียบเทียบกับเกณฑ์มาตรฐาน

ตัวอย่างการประเมิน

| RMS     | Status         |
| ------- | -------------- |
| ต่ำ     | Zone A (Green) |
| ปานกลาง | Zone B         |
| สูง     | Zone C         |
| สูงมาก  | Zone D (Red)   |

เพื่อระบุว่าเครื่องจักร
* ปกติ
* เริ่มมีปัญหา
* เสี่ยงเสียหาย

4 Trend Analysis
ระบบจะวิเคราะห์แนวโน้มของ vibration เช่น
* Stable
* Improving
* Degrading

เพื่อดูว่าเครื่องจักรมีแนวโน้ม
* ดีขึ้น
* คงที่
* แย่ลง

5 Failure Prediction
ไฟล์ `predictor.py` ใช้สำหรับ
การคาดการณ์ว่าเครื่องจักรอาจเสียเมื่อไร
โดยใช้แนวโน้มของ RMS
เพื่อประมาณ
Estimated Failure Date

6 Generate Report
หลังจากวิเคราะห์เสร็จ ระบบจะสร้างรายงานสรุป
output/maintenance_report.csv

# How to Run
1 Clone Repository
git clone https://github.com/username/predictive-maintenance.git

2 Install Dependencies
ติดตั้ง library ที่จำเป็น
pip install -r requirements.txt

3 Run Program
รันโปรแกรมหลัก
python main.py

4 Output Result
ผลลัพธ์จะถูกสร้างในโฟลเดอร์
output/
ไฟล์ที่ได้
maintenance_report.csv


# Technologies Used
เทคโนโลยีที่ใช้ในโปรเจกต์นี้
* Python
* pandas
* NumPy
* Git
* GitHub

# Use Case
โปรเจกต์นี้สามารถนำไปใช้กับ
* Predictive Maintenance ในโรงงาน
* Machine Health Monitoring
* Data Analysis ของ vibration sensor

เพื่อช่วยลด
* downtime
* maintenance cost
* machine failure
