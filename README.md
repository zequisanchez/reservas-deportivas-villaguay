# ⚽ Reservas Deportivas · Villaguay

App móvil para reservar los espacios deportivos municipales de Villaguay (Entre Ríos). Permite ver la disponibilidad de cada cancha, reservar un turno y mostrar el QR en la entrada. El personal de la Dirección de Deportes, además, puede administrar la agenda, los bloqueos y las reservas fijas.

Es el **Trabajo Final de Desarrollo para Móviles** (2026) de la Tecnicatura Universitaria en Desarrollo Web (FCAD · UNER). Lo desarrollé **en equipo** con otros tres compañeros: Grupo 67.

> 📌 Esta es una copia en mi cuenta personal del repositorio original del grupo: [moviles-grupo67/movil_67](https://github.com/moviles-grupo67/movil_67). El historial de commits completo está incluido.

📱 **[Descargar APK para Android](https://expo.dev/accounts/grupo57/projects/movil_67/builds/e0148ea3-6118-4943-81d8-0c8905ad15fd)** · 🎬 **[Video de la app](https://www.youtube.com/watch?v=w6FvLAL-obk)** · 🎨 **[Diseño en Figma](https://www.figma.com/design/v3dhnYBRumf4wkCJdekvdv/Desarrollo-Moviles---Grupo-67?node-id=0-1)**

---

## 🛠️ Tecnologías

![React Native](https://img.shields.io/badge/React_Native-61DAFB?style=flat&logo=react&logoColor=black)
![Expo](https://img.shields.io/badge/Expo_SDK_54-000020?style=flat&logo=expo&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat&logo=typescript&logoColor=white)
![Firebase](https://img.shields.io/badge/Firebase-FFCA28?style=flat&logo=firebase&logoColor=black)
![Google Maps](https://img.shields.io/badge/Google_Maps-4285F4?style=flat&logo=googlemaps&logoColor=white)
![Figma](https://img.shields.io/badge/Figma-F24E1E?style=flat&logo=figma&logoColor=white)

- **React Native + Expo** (SDK 54) con **TypeScript**
- **Expo Router** para la navegación por pestañas y stacks
- **Axios** como cliente HTTP, con el token JWT en cada request
- **react-native-maps** + **expo-location** para el mapa, la ubicación y "cómo llegar"
- **expo-notifications** + **Firebase Cloud Messaging** para las notificaciones push
- **expo-camera** para escanear QR y **react-native-qrcode-svg** para generarlos
- **expo-local-authentication** (huella o PIN) y **expo-secure-store** para la sesión
- **expo-sqlite** para guardar reservas en el dispositivo
- **react-native-reanimated** para el carrusel de fotos y video y las animaciones
- **EAS Build** para generar el APK

## ✨ Funcionalidades

**Jugador**
- Lista de espacios deportivos con filtros por deporte y complejo, favoritos y carrusel de fotos y video.
- Mapa con todos los espacios, ubicación actual y botón "cómo llegar".
- Grilla de disponibilidad de turnos y reserva.
- QR de la reserva para presentar en la entrada.
- Avisos push 2 horas antes del turno y cuando se suspende por lluvia.
- Ingreso con email y desbloqueo con huella o PIN.
- Tema claro y oscuro.

**Personal de la Dirección de Deportes**
- Agenda de turnos, bloqueos de espacios, reservas fijas y precios.
- Escáner de QR para validar las reservas en la entrada.

## 👥 Grupo 67

| Integrante | Parte de la app |
|---|---|
| Demian Nehuen Diak Prediger | Gestión: agenda, bloqueos, reservas fijas, precios |
| Andres Labra | Reservas y código QR |
| Micaela Giselle Ortiz | Cuenta, ingreso y conexión con la API |
| **Ezequiel Eduardo Sanchez** | **Espacios, mapa y notificaciones** |

## 🙋‍♂️ Mi aporte

- **Creé el proyecto** con Expo y la estructura de navegación por pestañas.
- Armé la **identidad visual**: logo, paleta de colores, tipografía Inter y el componente de encabezado.
- Desarrollé el **módulo de Espacios**: catálogo de los 11 espacios, filtros por deporte y complejo, favoritos, carrusel de fotos y video, y la conexión con la API de espacios y deportes.
- Implementé el **mapa** con Google Maps, la ubicación del usuario y "cómo llegar".
- Implementé las **notificaciones push**: registro del token del dispositivo, configuración de Firebase y avisos antes del turno y por suspensión por lluvia.
- Escribí el **README** del proyecto.

## 🔌 API

La app usa la API de la cátedra. Para las notificaciones push hicimos un fork, en el que programamos el guardado de los tokens de Expo y el envío de las push (`src/student-notifications/`):

- Fork del grupo: https://github.com/moviles-grupo67/api-reservas-deportivas-grupo67
- API original de la cátedra: https://github.com/franco-ruisdias-uner/api-proyectos-mobile

## 📋 Cómo correrla

1. Clonar e instalar dependencias:
   ```bash
   git clone https://github.com/zequisanchez/reservas-deportivas-villaguay.git
   cd reservas-deportivas-villaguay
   npm install
   ```
2. Copiar `.env.example` como `.env` y poner la URL de la API en `EXPO_PUBLIC_API_URL`.
3. Iniciar con Expo:
   ```bash
   npx expo start
   ```
   Se puede abrir en un emulador de Android o en el celular con la app **Expo Go**. El mapa y las notificaciones push funcionan completos solo en el APK.
