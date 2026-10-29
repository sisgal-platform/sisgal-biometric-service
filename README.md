# SISGAL Biometric Service

Microservicio NestJS para recibir lecturas biométricas, identificar al empleado y registrar marcaciones de asistencia. La implementación inicial mantiene el lector simulado existente.

## Requisitos

- Node.js
- npm
- PostgreSQL accesible mediante `SUPABASE_DB_URL`
- URL de Supabase Auth en `SUPABASE_URL`

## Configuración

Crea un archivo `.env` con:

```env
PORT=3001
SUPABASE_DB_URL=postgresql://usuario:clave@host:5432/base
SUPABASE_URL=https://proyecto.supabase.co
CORS_ORIGINS=http://localhost:5173
```

El servicio usa las entidades y migraciones actuales de SISGAL y las tablas compartidas con core. `synchronize` permanece deshabilitado.

## Ejecución

```bash
npm ci
npm run start:dev
```

La documentación Swagger queda disponible en `/api`. El endpoint del lector simulado es `POST /integracion/lector-simulado/marcaciones` y requiere JWT de administrador.
