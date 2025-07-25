# Outside In - ระบบร่างกายมนุษย์ (Fixed Version)

## ข้อมูลโครงงาน

**ชื่อโครงงาน:** Outside In  
**ประเภท:** เพื่อการศึกษา  
**ระยะเวลา:** 3 เดือน  

**ผู้จัดทำ:**
- ด.ช.พสิษฐ์ แสงประชาธนารักษ์ เลขที่ 13
- ด.ญ.ดุษาร์กร พะณะงาม เลขที่ 27
- ด.ญ.รมณ ชูทรัพย์ เลขที่ 31

**อาจารย์ที่ปรึกษา:** คุณครู ธีระพล พฤฑฒิกุล

## คำอธิบายโครงงาน

เว็บไซต์เพื่อการศึกษาระบบร่างกายมนุษย์แบบอินเทอร์แอคทีฟ ที่ช่วยให้ผู้เรียนสามารถสำรวจร่างกายมนุษย์จากภายนอกสู่ภายในได้อย่างน่าสนใจ

## วัตถุประสงค์

1. พัฒนาเว็บไซต์ที่นำเสนอองค์ความรู้เกี่ยวกับโครงสร้างของร่างกายมนุษย์
2. ส่งเสริมการเรียนรู้ Anatomy ด้วยวิธีที่เข้าใจง่ายและน่าสนใจ
3. ให้ผู้ใช้งานสามารถสำรวจระบบต่างๆ ในร่างกายอย่างมีลำดับขั้น
4. ฝึกทักษะการออกแบบและพัฒนาเว็บไซต์ด้วย HTML, CSS และ JavaScript

## ระบบที่ครอบคลุม

1. **ระบบผิวหนัง** - เรียนรู้เกี่ยวกับผิวหนังและหน้าที่ป้องกันร่างกาย
2. **ระบบกล้ามเนื้อ** - ทำความเข้าใจกล้ามเนื้อและการเคลื่อนไหว
3. **ระบบกระดูก** - ศึกษาโครงสร้างกระดูกและข้อต่อ
4. **อวัยวะภายใน** - เรียนรู้อวัยวะสำคัญภายในร่างกาย
5. **ระบบไหลเวียนเลือด** - ทำความเข้าใจการไหลเวียนของเลือด

## การแก้ไขข้อบกพร่อง (Bug Fixes)

### ปัญหาที่พบในเวอร์ชันเดิม:
1. **Layer Visibility Bug** - ชั้นของร่างกายในส่วน Hero ไม่แสดงผลอย่างถูกต้อง
2. **Modal Function Errors** - ฟังก์ชันเปิด Modal มีการเรียกใช้ที่ไม่ถูกต้อง
3. **Missing Error Handling** - ไม่มีการจัดการข้อผิดพลาด
4. **Animation Conflicts** - Animation บางตัวทำงานซ้ำซ้อนกัน

### การแก้ไข:

#### 1. Fixed Body Layers Visibility
```css
.layer {
    opacity: 0.6;
    pointer-events: auto;
    z-index: proper-stacking;
}

.layer:hover {
    opacity: 1 !important;
    transform: scale(1.02);
    z-index: 10 !important;
}
```

#### 2. Fixed Modal Functions
```javascript
// แก้ไขชื่อฟังก์ชันให้สอดคล้องกัน
window.openSystemModal = function (systemType) {
    // Fixed implementation with error handling
}
```

#### 3. Added Error Handling
```javascript
try {
    // Code execution
} catch (error) {
    console.error("Error:", error);
    showErrorMessage("เกิดข้อผิดพลาด");
}
```

#### 4. Improved Animation System
```javascript
// ปรับปรุงระบบ Animation ให้มี fallback
if (typeof gsap === "undefined") {
    initFallbackAnimations();
}
```

## ฟีเจอร์หลัก

- **Interactive Body Layers** - คลิกและ hover เพื่อดูระบบต่างๆ
- **Modal System Information** - ข้อมูลละเอียดของแต่ละระบบ
- **Quiz System** - แบบทดสอบความเข้าใจ
- **Responsive Design** - รองรับทุกอุปกรณ์
- **Smooth Animations** - การเคลื่อนไหวที่ลื่นไหล
- **Error Recovery** - ระบบฟื้นตัวจากข้อผิดพลาด

## เทคโนโลยีที่ใช้

- **HTML5** - โครงสร้างเว็บไซต์
- **CSS3** - การออกแบบและ animation
- **JavaScript ES6+** - ฟังก์ชันการทำงาน
- **GSAP** - Advanced animations (optional)
- **Font Awesome** - ไอคอน
- **Google Fonts** - ฟอนต์ Kanit

## การติดตั้งและใช้งาน

### วิธีที่ 1: เปิดไฟล์โดยตรง
```bash
# เปิดไฟล์ index.html ด้วยเบราว์เซอร์
```

### วิธิที่ 2: ใช้ Python Server
```bash
python -m http.server 8000
# เปิด http://localhost:8000
```

### วิธีที่ 3: ใช้ Node.js Server
```bash
npx serve .
# หรือ
npx live-server .
```

## โครงสร้างไฟล์

```
projgem/
├── index.html              # หน้าหลัก
├── package.json           # ข้อมูลโปรเจค
├── README.md             # คู่มือนี้
├── css/
│   ├── style.css         # สไตล์หลัก
│   ├── modal.css         # สไตล์ Modal
│   └── animations.css    # สไตล์ Animation
├── js/
│   ├── main.js          # JavaScript หลัก
│   ├── systems.js       # ข้อมูลระบบร่างกาย
│   └── animations.js    # ระบบ Animation
└── images/
    ├── human-body-outline.svg
    ├── skin-diagram.svg
    ├── muscles-diagram.svg
    ├── bones-diagram.svg
    ├── organs-diagram.svg
    ├── circulatory-diagram.svg
    └── placeholder-diagram.svg
```

## การใช้งาน

1. **หน้าแรก** - ดูภาพรวมและคลิกเริ่มการสำรวจ
2. **ส่วน Hero** - hover หรือคลิกที่ชั้นต่างๆ ของร่างกาย
3. **ส่วนระบบ** - คลิกที่การ์ดแต่ละระบบเพื่อเรียนรู้
4. **Modal ข้อมูล** - อ่านข้อมูล ดูรูปภาพ และทำแบบทดสอบ
5. **Quiz** - ทดสอบความเข้าใจและดูผลคะแนน

## ข้อควรระวัง

- ต้องใช้ Modern Browser ที่รองรับ ES6+
- ต้องมีการเชื่อมต่ออินเทอร์เน็ตสำหรับโหลด GSAP และ Font Awesome
- ไฟล์ภาพ SVG ต้องอยู่ในโฟลเดอร์ images/

## การแก้ไขปัญหา

### ถ้า Animation ไม่ทำงาน
- ตรวจสอบการโหลด GSAP
- ดู Console สำหรับข้อผิดพลาด

### ถ้า Modal ไม่เปิด
- ตรวจสอบ JavaScript errors
- ลองรีเฟรชหน้า

### ถ้าภาพไม่โหลด
- ตรวจสอบ path ของไฟล์ภาพ
- ตรวจสอบว่าไฟล์ SVG อยู่ในโฟลเดอร์ images/

## การพัฒนาต่อ

- เพิ่มระบบร่างกายเพิ่มเติม
- เพิ่ม 3D visualization
- เพิ่มระบบ user authentication
- เพิ่มการบันทึกความคืบหน้า
- เพิ่มเสียงประกอบ

## License

MIT License - สามารถใช้งานและแก้ไขได้อย่างอิสระ

## ผู้พัฒนา

พัฒนาโดยนักเรียนชั้นมัธยมศึกษา เพื่อการศึกษาและการเรียนรู้

---

**หมายเหตุ:** นี่คือเวอร์ชันที่แก้ไขข้อบกพร่องแล้วจากตัวอย่างเดิม ทำงานได้อย่างสมบูรณ์และมีการจัดการข้อผิดพลาดที่ดีขึ้น
