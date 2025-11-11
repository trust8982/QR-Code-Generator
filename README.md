# 📱 QR Code Generator in Python

This project is a simple **Python script** that generates a QR code from any text or URL you provide.  
It uses the `qrcode` library to create and save the QR code as an image file.

---

## 🚀 Features

- Converts any **text or URL** into a QR code  
- Saves the generated QR code as a **PNG image**  
- Minimal and beginner-friendly script  
- Customizable box size, border, and colors  

---

## 🧠 How It Works

1. The user inputs a URL or text.
2. The script uses the `qrcode` library to generate a QR code.
3. The QR code is saved locally as an image file named **`qrimg.png`**.

---

## 💻 Code Overview

```python
import qrcode

def generate_qrcode(text):
    
    qr = qrcode.QRCode(
        version=1,
        error_correction=qrcode.constants.ERROR_CORRECT_L,
        box_size=10,
        border=4,
    )

    qr.add_data(text)
    qr.make(fit=True)
    img = qr.make_image(fill_color="black", back_color="white")
    img.save("qrimg.png")

url = input("Enter your url: ") 
generate_qrcode(url)
