# บันทึกการแก้ไข

## ภาพรวม
เอกสารนี้อธิบายการแก้ไขสิ่งที่ส่งมอบจากโครงงานระยะที่ 1 โดยการแก้ไขได้ดำเนินการตามคำแนะนำจากผู้สอน รวมถึงการปรับปรุงเพิ่มเติมเพื่อให้การวิเคราะห์และออกแบบเหมาะสมยิ่งขึ้นสำหรับการทำโครงงานระยะที่ 2 รายละเอียดการแก้ไขแสดงไว้ด้านล่างนี้

---
## Use Case Model
## Administrator

1. **แก้ไข Use Case: "Analyze usage data" → "Collect usage data"**
   - **เหตุผล:** เพื่อให้ผู้ดูแลระบบสามารถรวบรวมข้อมูลการใช้งาน ซึ่งมีความสำคัญต่อการวิเคราะห์และพัฒนาระบบ

2. **ปรับปรุง Use Case: "Manage fees when employment is successful"**
   - **รายละเอียด:** เพิ่มความสัมพันธ์ << include >> กับ Use Case “Process Payments”
   - **วัตถุประสงค์:** เพื่อให้ระบบสามารถจัดการและบันทึกค่าธรรมเนียมที่เกิดขึ้นหลังการจ้างงานสำเร็จ


## Recruiter

1. **แก้ไข Use Case: "Post and Manage Job Advertisements"**
   - **รายละเอียด:** ลบ Use Case ย่อย “Add Job Description” และ “Add Salary”
   - **เหตุผล:** รวมการดำเนินการเหล่านี้ไว้ใน Use Case หลักเพื่อความสะดวกและไม่ซ้ำซ้อน

2. **ปรับปรุง Use Case: "Schedule Interviews"**
   - **รายละเอียด:** รวม Use Case “Video Conference Interviews,” “View Applicant Profiles,” และ “Select Candidates for Interviews” เข้าด้วยกัน
   - **วัตถุประสงค์:** เพื่อให้การจัดการสัมภาษณ์สะดวกขึ้นใน Use Case เดียว

3. **เพิ่ม Use Case: "Offer and Contract Management"**
   - **รายละเอียด:** เพิ่ม Use Case เพื่อให้ Recruiter จัดการข้อเสนอและสัญญาการจ้างงาน
   - **วัตถุประสงค์:** สนับสนุนกระบวนการหลังการคัดเลือกผู้สมัครและเพิ่มประสิทธิภาพในการบริหารจัดการ

4. **ลบ Use Case: "Report Issues Encountered"**
   - **รายละเอียด:** ย้ายหน้าที่นี้ไปยัง Actor: User
   - **เหตุผล:** เพื่อให้ผู้ใช้งานสามารถรายงานปัญหาได้โดยตรงกับ Support Staff


## User (Applicant และ Recruiter)

1. **เปลี่ยนชื่อ Use Case: "Registration" → "Register"**
   - **รายละเอียด:** ปรับชื่อให้สอดคล้องกับมาตรฐานการตั้งชื่อ Use Case
   - **การปรับปรุงเพิ่มเติม:**
     - เพิ่มความสัมพันธ์ << include >> กับ Use Case “Log In” เพื่อการเข้าสู่ระบบอัตโนมัติหลังลงทะเบียน
     - ลบความสัมพันธ์ << include >> กับ Use Case “Provides Information” โดยรวมข้อมูลพื้นฐานใน Use Case หลัก

2. **ปรับปรุง Use Case: "Manage and Update Profile"**
   - **รายละเอียด:**
     - ลบความสัมพันธ์ << extends >> กับ “Add Personal Information”
     - เพิ่มความสัมพันธ์ << extends >> กับ Use Case “Change Password”
   - **เหตุผล:** เพื่อเพิ่มความปลอดภัยและความสะดวกในการจัดการบัญชี

3. **ลบ Use Case: "Video Conference"**
   - **รายละเอียด:** ย้ายฟังก์ชันนี้ไปยัง Use Case “Schedule Interviews” ภายใต้ Actor: Recruiter
   - **วัตถุประสงค์:** เพื่อปรับปรุงการจัดการกระบวนการสัมภาษณ์

## Support Staff

1. **เปลี่ยนชื่อ Use Case: "Respond to User Inquiries" → "Report Issues Encountered"**
   - **เหตุผล:** เพื่อให้ Support Staff มีหน้าที่รับเรื่องและแก้ไขปัญหาที่ผู้ใช้งานรายงาน
   - **รายละเอียด:** รวมถึงการติดตามและบันทึกปัญหาเพื่อนำไปแก้ไข


![revision](https://github.com/ICT-Mahidol/2024-ITDS262-2-FunFizz/blob/master/phase-2/src/usecase-phase2.png)

---

## DFD Level 0

มีการเปลี่ยนแปลงและเพิ่มเติมดังนี้: 
1. Applicant  
   - ส่งข้อมูลเพิ่มเติมเกี่ยวกับใบแจ้งเตือนการสัมภาษณ์  
2. Recruiter  
   - ส่งข้อมูลเพิ่มเติมเกี่ยวกับรายละเอียดงานและข้อมูลสถานะของการสัมภาษณ์ เพื่อให้การติดตามการสมัครของผู้สมัครมีความต่อเนื่อง 
   - ระบบสามารถรับข้อมูลการชำระเงินในรูปแบบที่ละเอียดขึ้น เช่น ข้อมูลสถานะการชำระเงิน เพื่อความปลอดภัยในการทำธุรกรรม 
3. Administrator 
   - มีการปรับปรุงให้เข้าถึงข้อมูลสถิติการใช้งานที่ละเอียดขึ้น เช่น การวิเคราะห์การใช้งานของผู้ใช้
  
![revision](https://github.com/ICT-Mahidol/2024-ITDS262-2-FunFizz/blob/master/phase-2/src/DFD%20Level%200.png)


