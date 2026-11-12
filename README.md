# Panchayat Lauki

> **SOOCHNA — Gram Panchayat Phulera**
> Sabhi gaon waalon ko soochit kiya jaata hai ki panchayat office mein ek nayi lauki aayi hai.
> Isse 5 barabar-ish tukdon mein kaatna hai. Chaaku apne aap chalega, aapko bas sahi time pe muh kholna hai.
> — *Aadesh anusaar, Pradhan ji*

**Khelo yahan:** https://panchayat-lauki.teeaarbee.com (phone pe kholo, front camera chahiye)

| Shuru | Jeet | Haar |
|---|---|---|
| ![Home screen](docs/start.png) | ![Jeet gaye](docs/win.png) | ![Chook gaye](docs/miss.png) |

---

## Khel ke niyam

1. Camera on karo. Lauki seedha aapke chehre pe, naak ke level pe aa jaayegi, aur aapke saath hilegi.
2. Neeche chaaku left-right chalta rahega, upar dotted line ke saath.
3. **Muh kholo** (ya screen pe **tap** karo) toh chaaku lauki pe girega aur ek tukda kat ke gir jaayega.
4. **5 tukde** kaat liye toh *JEET GAYE!* Pradhan ji khush.
5. Chaaku lauki ke bahar gira toh *CHOOK GAYE!* Arre Sachiv ji, ek galti aur khel khatam.
6. Har tukde ke baad chaaku thoda tez ho jaata hai. Sar hila ke lauki ko chaaku ke neeche laao.

## Video record karna

Neeche laal button dabao. Camera, lauki, chaaku, text, chop ki awaaz aur aapki awaaz, sab record hota hai.
Stop karte hi preview aata hai. **Save / Share** se seedha Instagram ya WhatsApp pe bhej sakte ho.
Kuch bhi upload nahi hota, sab phone pe hi banta hai.

## Andar ka maamla (tech)

- Ek hi file: [`public/index.html`](public/index.html), koi build step nahi.
- Chehra track karne ke liye Google ka [MediaPipe Face Landmarker](https://ai.google.dev/edge/mediapipe/solutions/vision/face_landmarker). Model (`face_landmarker.task`) isi repo mein rakha hai, aur `jawOpen` se pata chalta hai ki muh khula ya nahi.
- Lauki, chaaku aur tukde sab `<canvas>` pe code se bante hain, koi image nahi.
- Recording `MediaRecorder` se: iPhone pe MP4, baaki jagah MP4 ya WebM.
- Hosting: Cloudflare Workers (static assets), domain `panchayat-lauki.teeaarbee.com`.

## Apne computer pe chalao

Camera sirf `https` ya `localhost` pe chalta hai.

```sh
cd public
python3 -m http.server 8000
# phir browser mein kholo: http://localhost:8000
```

## Deploy

```sh
npx wrangler deploy
```

`wrangler.toml` mein custom domain pehle se set hai.

## Shukriya

- Idea: Snapchat ka [Bread Cut Game lens](https://www.snapchat.com/lens/8fdc8899da3d4f04a9e5a6e1cadcace3) by Vaibhav. Humne bread ki jagah lauki rakh di.
- Face model: Google MediaPipe (Apache 2.0).

---

*Is repo ko Phulera panchayat office ki file mein darj kar liya gaya hai. Mohar baad mein lagegi.*
