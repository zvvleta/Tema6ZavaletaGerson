```mermaid
flowchart TD
A([Inicio]) --> B[Usuario inicia sesión]
B --> C{Ingesar contraseña}
C -- contraseña correcta --> R[Ingreso al dashboard] --> B
C -- Sí --> D[Elige especialidad, fecha y horario]
D --> E{¿Horario libre?}
E -- No --> F[Mostrar horarios alternativos] --> D
E -- Sí --> G[Bloquear horario y registrar cita]
G --> H{¿Confirmación enviada?}
H -- No --> I[Reintentar 3 veces; si falla, estado Pendiente] --> J
H -- Sí --> J([Fin: cita registrada])
