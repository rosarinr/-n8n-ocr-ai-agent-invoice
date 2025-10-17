# -n8n-ocr-ai-agent-invoice

# 🧾 OCR + AI Agent Workflow for Invoice Validation

## 📘 Overview

Workflow นี้ออกแบบมาเพื่อทำให้การ **อ่านใบแจ้งหนี้ (Invoice)** แบบอัตโนมัติเป็นเรื่องง่าย  
โดยใช้ **AI OCR + JSON Parsing + Validation Logic** ผ่าน n8n  

เมื่อผู้ใช้ **อัปโหลดไฟล์รูปภาพหรือ PDF ของใบแจ้งหนี้**, ระบบจะทำการ:
1. 📤 รับไฟล์ผ่าน Form Trigger  
2. 🧠 ใช้ **Google Gemini (Gemini 2.5 Flash)** วิเคราะห์ภาพและสกัดข้อมูลออกมาเป็น JSON  
3. 🪄 ใช้ **AI Agent** แปลงข้อความจาก OCR ให้อยู่ในรูปแบบ JSON ที่มีโครงสร้างชัดเจน  
4. 🔍 แปลงผลลัพธ์เป็น JSON ที่ถูกต้องและตรวจสอบความสมบูรณ์ของข้อมูล  
5. ✅ ตรวจสอบความถูกต้องของยอดรวม, VAT, และ Grand Total ด้วย Node “Validation”

---

## วิธีใช้
1. อัพโหลดไฟล์ผ่าน
   1.1 Test URL http://localhost:5678/form-test/fc6ce69e-4b24-47a1-9756-242ec31a45a2
   1.2 Production URL http://localhost:5678/form/fc6ce69e-4b24-47a1-9756-242ec31a45a2
2. กดรันแล้วรอผลลัพธ์ที่เป็น output จาก Node Validation

