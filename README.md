# Como instalar yt-dlp en Android con Termux
Vómo instalar yt-dlp para descargar videos de YouTube, etc

2024 Octubre

Termux es como un emulador de terminal y entorno Linux y gracias a él en Android podemos instalar programas como: `yt-dlp` para descargar videos de YouTube y otros sitios.

## yt-dlp

`yt-dlp` es una bifurcación (fork) de `youtube-dl`, una popular herramienta de línea de comandos (terminal) utilizada para descargar videos de YouTube y otros sitios web. `yt-dlp` agrega características adicionales y mejoras a la funcionalidad original de `youtube-dl`, abordando problemas de mantenimiento y añadiendo soporte para más sitios web, opciones avanzadas de configuración, y mejores métodos de extracción y descarga. Es una herramienta poderosa para aquellos que desean descargar y gestionar contenido multimedia de diversas plataformas en línea de manera eficiente y flexible.


Vea el siguiente tutorial:

## Cómo instalar git en Android con Termux
https://youtu.be/QoWkTVlEB1k?si=06nXIyJP48bA1aBD

Para esta instalación elija un repositorio, ejemplo grimler

en el vídeo cuando esté en la parte de instalar git, en vez de instalarlo escriba:

```
pkg install python ffmpeg -y
```

y luego:

```
python -m pip install yt-dlp
```

En Termux 0.119 no use: `pkg upgrade` porque le cambiará el repositorio y además no es necesario porque `pkg update` es una especie de híbrido que hace las dos funciones.

En Termux 0.118 si use `pkg upgrade` después de haber usado `pkg update` y si le cambia el repositorio use el comando para volver a elegir el que va a usar: 

```
termux-change-repo
```

## ACCEDER AL ALMACENAMIENTO INTERNO
En Termux poner:

```
termux-setup-storage
```

Y aceptar los permisos y poner:

```
cd storage
```

luego poner:

```
ls 
```

para ver las rutas  disponibles y elegir la memoria compartida:

```
cd shared
```

**COMANDO ESPECIAL**.- También se pueden abreviar esos 2 pasos solo con:

```
cd /sdcard
```

Con cualquiera de los dos métoos llegará a la memoria interna compartida.

Para saber en qué ruta está ponga en Termux:

```
pwd
```

y de Enter

**Nota**: Si es la 1ra vez k abre Termux estará en:

```
/data/data/com.termux/files/home
```

y si ya está en la memoria interna aparece:

```
/sdcard $
```

## DESCARGANDO CON yt-dlp
Una vez que esté en el Almacenamiento Interno Compartido  allí puede usar los comandos para descargar multimedias con yt-dlp y se descargarán allí, pero si quiere descargar en una carpeta especial cree una ejemplo: 

```
mkdir descargas-yt
```

claro Ud puede ponerle otro nombre, y ejem entrar con:

```
cd descargas-yt
```

## COMANDOS PARA DESCARGAR CON YT-DLP
Basado en el siguiente comando:

```
yt-dlp "https://www.youtube.com/watch?v=VIDEO_ID"
```
  
 Reemplace `VIDEO_ID` con el ID  del vídeo de YouTube (El ID de un vídeo de YouTube es un identificador único k permite localizar y reproducir ese vídeo específico en la plataforma. Cada vídeo tiene un ID único compuesto por una cadena de 11 caracteres, letras y números).

### DESCARGAR FORMATOS DE VIDEO
 Para elegir un formato de video específico, use la opción `-f` seguida del formato.  Por ejemplo:

```
yt-dlp -f best "https://www.youtube.com/watch?v=VIDEO_ID"
```

Reemplace "best" con el formato deseado (por ejemplo, "mp4", "webm", etc.)

Según esto:

#### DESCARGAR MP4

```
yt-dlp -f mp4 https://youtu.be/bGhshJ4c2Mw?si=Wzix5jAlefvpY4Hz
```

### DESCARGAR FORMATOS DE AUDIO 

#### DESCARGAR MP3
Para esto hay k user opciones especificas:

```
yt-dlp -x --audio-format mp3 https://youtu.be/jWIW8sSvxSc?si=C25l9yKM4YqjHEBg

yt-dlp -x --audio-format mp3 https://youtu.be/y3LYzZvURfI?si=Mk2hBJnvkkXIWbsi

yt-dlp -x --audio-format mp3 https://youtu.be/-jhxYZIzrkE?si=zxBdRd_LUESIqbic
```

#### DESCARGAR M4A

```
yt-dlp -x --audio-format m4a https://youtu.be/jWIW8sSvxSc?si=C25l9yKM4YqjHEBg
```

y otro formato solo cambien la extensión, ejem: aac, alac, flac, opus, vorbis, wav.

### DESCARGAR VIDEOS DE OTROS SITIOS WEB
 También puedes utilizar yt-dlp para descargar vídeos de otros sitios web.  Simplemente cambie la URL en el comando al sitio deseado:

```
yt-dlp -o "%(title)s.%(ext)s" "https://www.example.com/video"
```

Mas información:

```
yt-dlp -help
```

## CONSULTAS

[Termux Setup Storage](https://wiki.termux.com/wiki/Termux-setup-storage)

[yt-dlp on Termux](https://www.reddit.com/r/youtubedl/comments/pr7ruk/ytdlp_on_termux/)
