# ro-portafolio

Portafolio personal de Rodrigo Gaete (destino: ro.vientonorte.io).

Contenido: build dedicado de la ficha `/sobre-mi/` de `vientonorte/mi-portafolio` @ `e1413d694d9da1e73c1a1467d4a97d4a5d569c46` (main), sin rediseño.
Salida: `npm run build:ro` → `dist-ro/` → `public/`.
`public/index.html` es la ficha prerenderizada; `public/assets`, fonts, imágenes referenciadas y `public/ar/` se copian desde ese build.
Cualquier otra ruta redirige (308) a https://vientonorte.io/ (ver `vercel.json`).

## Actualizar

En `vientonorte/mi-portafolio` en el SHA de arriba:

    env | grep VITE_APP_ENV   # debe estar vacío; no heredar qa
    npm run build:ro

`scripts/build-ro.mjs` fija `VITE_BASE=/` y los `VITE_*` públicos (GTM `GTM-PM5LBQRP`, action y `entry.*` del Google Form, `VITE_A11Y_FREE_SCHEDULE_URL`). No usa `VITE_FORM_SUBMIT_INBOX`. No setea `VITE_APP_ENV`.

Copiar el contenido de `dist-ro/` a `public/`. No cambiar `vercel.json`.
