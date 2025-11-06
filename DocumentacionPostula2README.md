# Postula2

**Creado por:**
### Simón Tabares Arias

**Postula2** es un sistema web que permite la postulación a diferentes cargos u ofertas laborales, la gestión y publicación de dichas oportunidades. Los usuarios pueden registrarse, postularse y consultar ofertas disponibles, mientras que las empresas o administradores pueden crear, gestionar y validar los procesos de selección de manera centralizada y eficiente.
El sistema tiene un enfoque basado en una arquitectura modular la cual nos permite tener una baja cohesion y un alto acoplamiento. Priorizando temas como la **seguridad**, **escalabilidad** y **disponibilidad**

La documentacion describe tecnicamente lo siguente:

- **Despliegue:** Componentes adoptados y desarrollados, asi como su ubicación en la infraestructura.
- **Componentes:** Módulos lógicos del backend y frontend, y sus funciones.
- **Paquetes:** Organización interna bajo capas y dependencias controladas.
- **Secuencias:** Flujos de interacción de casos de uso típicos (UI ↔ API ↔ servicios).

## **1. Diagrama de Despliegue**

**Descripción General**
El diagrama de despliegque representa la arquitectura física y lógica de Postula2, mostrando los servicios adoptados y desarrollados, así como su interacción dentro del entorno.  
La solución está diseñada bajo un enfoque **cloud-agnostic**, escalables y desplegados en servicios administrados, garantizando **alta disponibilidad** y **seguridad** 

### **1.1 Componentes del Despliegue**

### **1.2 Componentes Principales**

| Componente | Tipo de Componente | Descripción | Justificación | ¿Es Bloque de Construcción? | Tipo de Bloque |
|-----------|-------------------|-------------|--------------|-----------------------------|----------------|
| **CDN** | Componente Adoptado | Entrega contenido estático del Frontend con baja latencia. | Aumenta el rendimiento y disponibilidad. | Sí | Genérico |
| **Blob Storage** | Componente Adoptado | Almacena imágenes y archivos asociados al catálogo y pedidos. | Evita sobrecargar el backend y facilita escalabilidad. | Sí | Genérico |
| **WAF** | Componente Adoptado | Filtra y bloquea tráfico malicioso (SQLi, XSS, CSRF). | Protege la infraestructura y datos. | Sí | Genérico |
| **Identity Management** | Componente Adoptado | Administración centralizada de autenticación y roles. | Garantiza seguridad en el acceso. | Sí | Genérico |
| **API Gateway** | Componente Adoptado | Punto de acceso unificado al backend. | Facilita enrutamiento y políticas de seguridad. | Sí | Genérico |
| **Traceability and Monitoring Platform** | Componente Adoptado | Observabilidad y detección temprana de fallos. | Mantiene la estabilidad del servicio. | Sí | Genérico |
| **Database** | Componente Adoptado | Persistencia de datos críticos del negocio. | Garantiza consistencia y disponibilidad. | Sí | Genérico |
| **Parameters Catalog** | Desarrollo Propio | Configuración dinámica del sistema. | Permite ajustes sin redeploy. | Sí | Soporte |
| **Messages Catalog** | Desarrollo Propio | Gestión centralizada de mensajes del sistema. | Mejora mantenibilidad y soporte multiidioma. | Sí | Soporte |
| **Key Vault** | Componente Adoptado | Almacenamiento seguro de llaves y secretos. | Previene exposición de credenciales. | Sí | Genérico |
| **Notification Gateway** | Componente Adoptado | Envío centralizado de notificaciones. | Evita construir infraestructura propia. | Sí | Soporte |
| **Postula2 Back End** | Desarrollo Propio | Núcleo funcional del negocio. | Procesa operaciones críticas del sistema. | No | Core |
| **Postula2 Front End** | Desarrollo Propio | Interfaz de usuario final. | Facilita acceso y experiencia de usuario. | No | Core |

### **1.2.2 Bloques de Construcción Adoptados**

| Componente | ¿Es de Pago? | Fabricante | Producto | Versión | Protocolo | Justificación | Tipo de Bloque |
|-----------|--------------|------------|----------|---------|-----------|--------------|----------------|
| CDN | No | Cloudflare | Cloudflare CDN | Latest | HTTPS | Baja latencia y optimización automática. | Genérico |
| Blob Storage | Sí | Cloudflare | Cloudflare R2 Storage | Latest | HTTPS | Integrado y escalable con despliegue. | Genérico |
| WAF | No | Cloudflare | Cloudflare WAF | Latest | HTTPS | Protección perimetral, DDoS mitigation y firewall inteligente. | Genérico |
| Identity Management | Sí | Cloudflare | Cloudflare Access | Latest | HTTPS | Seguridad y manejo de roles centralizado. | Genérico |
| API Gateway | Sí | AWS | AWS API Gateway | V2 | HTTPS | Facilita la creación, gestión y protección de APIs,a cualquier escala. | Genérico |
| Traceability and Monitoring Platform | Sí | AWS | Cloudwatch | Latest | HTTPS | Trazabilidad y deteccion de errores en tiempo real. | Genérico |
| Database | No | PostgreSQL | PostgreSQL | 16+ | TCP/IP | Base de datos confiable y libre de licencias. | Genérico |
| Key Vault | Sí | Cloudflare | Workers KV | Latest | HTTPS | Protección de datos con auditoría y control de acceso. | Genérico |
| Notification Gateway | No | NotificationAPI | NotificationAPI | Latest | HTTPS | Comunicación confiable multicanal. | Soporte |


## Estructura de documentación

Toda la documentación relevante se encontrará en la carpeta `Documentacion Postula2`, por ejemplo:

```
Documentacion Postula2/
    README.md  # Índice y guía de la documentación del proyecto
```

## Acerca de

Bienvenido a la documentación oficial del proyecto **Postula2**.  
Aquí encontrarás información relevante sobre el proyecto, su instalación, uso y contribución.

---

¡Puedes comenzar añadiendo archivos o más secciones de documentación dentro de la carpeta Documentacion Postula2!
