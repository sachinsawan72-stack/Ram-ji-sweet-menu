# Restaurant Digital Menu

Restaurant ke liye simple digital menu. Do pages hain:

- **Customer view** (`index.html`): customer sirf menu dekh sakta hai. Photo, rate aur category dikhte hain. Not available items dhundhle dikhte hain.
- **Admin panel** (`admin.html`): yahan se poora control hota hai. Item jodna, photo upload, rate likhna, Available / Not available karna, edit aur delete.

Pure HTML, CSS aur JavaScript hai. Koi build ya install nahi chahiye.

## Files

| File | Kaam |
|------|------|
| `index.html` | Customer ka menu page |
| `admin.html` | Admin panel (login ke saath) |
| `menu-data.json` | Menu ka data (admin se export hota hai) |
| `README.md` | Ye guide |

## Computer par chalana

1. Teeno files ek hi folder me rakhein.
2. `admin.html` ko browser me kholein. Default password: `admin123`.
3. Items jodein. Customer page `index.html` usi browser me khulega aur menu dikhayega.

## Password badalna

`admin.html` kholkar ye line dhundhein aur apna password likhein:

```js
const ADMIN_PASSWORD = "admin123";
```

> Password page ke code me hi likha hota hai, isliye ye sirf halki suraksha hai. Admin ka link kisi ko na dein.

## GitHub par upload karna

1. GitHub par naya **Public** repository banayein, jaise `restaurant-menu`.
2. **Add file → Upload files** se `index.html`, `admin.html` (aur `menu-data.json`) daalein.
3. **Commit changes** dabayein.

## Render par deploy karna

1. [render.com](https://render.com) par GitHub se login karein.
2. **New + → Static Site** chunein aur apna repo connect karein.
3. Settings:
   - **Build Command:** khaali chhodein
   - **Publish Directory:** `.`
4. **Create Static Site** dabayein.

Live links:

- Customer: `https://your-site.onrender.com`
- Admin: `https://your-site.onrender.com/admin.html`

## Menu update karne ka tareeka

Data har browser ki `localStorage` me save hota hai, isliye dusre phone par menu `menu-data.json` se pahunchta hai:

1. Live site ke `/admin.html` par login karein.
2. Menu me badlav karein.
3. **menu-data.json export** dabayein.
4. GitHub repo me `menu-data.json` ko dobara upload (replace) karein.
5. Render khud 1-2 minute me naya version deploy kar dega.

Naya data import karna ho to admin me **Import** button se purani `menu-data.json` daal sakte hain.

## Zaroori baatein

- Jis browser me admin badlav karta hai, wahan customer page turant naya menu dikhata hai. Baaki devices ko naya menu `menu-data.json` upload karne ke baad milta hai.
- Photo upload hote waqt apne aap chhoti (max 640px) ho jaati hai. Jyada photos hone par browser ka storage bhar sakta hai.
- Free Render plan par site kabhi-kabhi pehli baar kholne par thodi der leti hai.

## Aage kya ho sakta hai

Agar admin se badlav karte hi sabke phone par turant dikhana ho aur asli login chahiye, to Firebase ya Supabase jodkar real database wala version banaya ja sakta hai.
