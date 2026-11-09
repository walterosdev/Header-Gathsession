# GathSession – Header & Hero

Maquetación de la página de inicio de **GathSession** (header con navegación, sección hero y footer de características), hecha con **HTML + Tailwind CSS v4** y empaquetada con **Vite**.

![Vite](https://img.shields.io/badge/Vite-8-646CFF?logo=vite&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-4-06B6D4?logo=tailwindcss&logoColor=white)

---

## 🚀 Cómo ver la página

Hay dos formas de acceder a la página web:

| | Forma sencilla | Forma completa |
|---|---|---|
| **Requisitos** | Solo un navegador | Node.js + npm |
| **Qué abres** | La versión ya compilada (`dist/`) | El código fuente, con un servidor de desarrollo |
| **Ideal para** | Ver el resultado final | Editar el proyecto y ver los cambios al instante |

---

### 1️⃣ Forma sencilla (sin instalar nada)

La carpeta `dist/` contiene la página ya compilada: HTML, CSS final e imágenes.

1. Abre la carpeta `dist/` del proyecto.
2. Haz doble clic en **`dist/index.html`** (o arrástralo a tu navegador).

Listo, la página se abre directamente.

> [!NOTE]
> La carpeta `dist/` está en el `.gitignore`, así que **no se sube al repositorio**. Si descargaste el proyecto desde Git y no tienes `dist/`, genérala con la forma completa (`npm run build`).

> [!WARNING]
> **No abras el `index.html` de la raíz** con doble clic: ese es el código fuente y sus estilos de Tailwind (`src/style.css`) necesitan pasar por Vite para funcionar. Verás la página sin estilos.

<details>
<summary>¿La página se ve sin estilos al abrir <code>dist/index.html</code>?</summary>

Algunos navegadores (como Chrome) bloquean ciertos archivos cuando la página se abre como `file://`. En ese caso, sirve la carpeta con un servidor local muy simple:

```bash
npx serve dist
```

y abre la URL que aparece en la terminal (normalmente http://localhost:3000).

</details>

---

### 2️⃣ Forma completa (entorno de desarrollo)

#### Requisitos

- [Node.js](https://nodejs.org/) **20.19 o superior** (incluye npm)

Comprueba que lo tienes instalado:

```bash
node -v
npm -v
```

#### Pasos

**1. Instala las dependencias** (solo la primera vez):

```bash
npm install
```

**2. Inicia el servidor de desarrollo:**

```bash
npm run dev
```

**3. Abre la URL que aparece en la terminal**, normalmente:

```
http://localhost:5173
```

Cualquier cambio que hagas en `index.html` o `src/style.css` se verá al instante en el navegador, sin recargar.

Para detener el servidor pulsa `Ctrl + C` en la terminal.

#### Generar la versión final (`dist/`)

```bash
npm run build     # compila el proyecto en la carpeta dist/
npm run preview   # sirve dist/ en http://localhost:4173 para revisarla
```

Después de `npm run build` ya puedes usar la **forma sencilla** abriendo `dist/index.html`.

---

## 📜 Scripts disponibles

| Comando | Descripción |
|---|---|
| `npm run dev` | Servidor de desarrollo con recarga en vivo |
| `npm run build` | Compila la versión de producción en `dist/` |
| `npm run preview` | Sirve la versión compilada para revisarla |

---

## 📁 Estructura del proyecto

```
Header-Gathsession/
├── index.html        # Página principal (código fuente)
├── src/
│   ├── style.css     # Tailwind + tema (colores, fuentes) y utilities propias
│   └── assets/       # Logo e imágenes SVG
├── public/           # Archivos que se copian tal cual (favicon, iconos)
├── dist/             # Versión compilada (se genera con npm run build)
├── vite.config.js    # Configuración de Vite + plugin de Tailwind
└── package.json
```

---

## 🎨 Personalización

Los colores y fuentes están definidos en el bloque `@theme` de `src/style.css`:

| Variable | Valor | Clase de Tailwind |
|---|---|---|
| `--color-bg-primary` | `#2B2D38` | `bg-bg-primary` |
| `--color-bg-secondary` | `#3D3F4B` | `bg-bg-secondary` |
| `--color-text-primary` | `#FFFFFF` | `text-text-primary` |
| `--color-text-secondary` | `#9597A1` | `text-text-secondary` |
| `--color-text-rose` | `#DB2A6B` | `text-text-rose`, `bg-text-rose` |
| `--font-poppins` | Poppins | `font-poppins` |
| `--font-merriweather` | Merriweather | `font-merriweather` |

Utilities propias:

- **`nav-link`**: enlace con una línea rosa animada al hacer hover. Añade `aria-current="page"` para dejar la línea fija en la página actual.
- **`button-primary`**: botón principal rosa y redondeado.

Las fuentes se cargan desde [Google Fonts](https://fonts.google.com/) en el `<head>` de `index.html`, por lo que se necesita conexión a internet para verlas.

