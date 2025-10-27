##  
 Universidad CENFOTEC  
Desarrollado por **Esteban Rojas Herrera**

#  Demo CRUD Frontend (Angular 17 + TypeScript)

Frontend del sistema CRUD con autenticación JWT, control de roles (SUPER_ADMIN, USER) y consumo del backend desarrollado en Spring Boot.

---

##  Tecnologías utilizadas
- **Angular 17**
- **TypeScript**
- **Bootstrap 5**
- **RxJS**
- **Angular Material (opcional)**
- **Interceptors (JWT + manejo de errores)**

---

##  Configuración del entorno

1. Instala Node.js 18+ y Angular CLI globalmente:
   ```bash
   npm install -g @angular/cli
   ```

2. Clona el repositorio y entra en la carpeta del proyecto:
   ```bash
   git clone https://github.com/TU_USUARIO/demo-crud-frontend.git
   cd demo-crud-frontend
   ```

3. Instala dependencias:
   ```bash
   npm install
   ```

4. Asegúrate de que el backend esté corriendo en:
   ```
   http://localhost:8080
   ```

5. Inicia el servidor Angular:
   ```bash
   ng serve
   ```

6. Abre en el navegador:
   ```
   http://localhost:4200
   ```

---

##  Credenciales para pruebas

| Rol | Email | Contraseña |
|------|----------------------|----------------|
| SUPER_ADMIN | **superadmin@demo.com** | **sopadepollo** |
| USER | **user@demo.com** | **123456** |

---

##  Estructura de navegación

| Página | Ruta | Acceso |
|---------|------|--------|
| Login | `/login` | Público |
| Registro | `/signup` | Público |
| Dashboard | `/app/dashboard` | Autenticado |
| Productos | `/app/productos` | USER / SUPER_ADMIN |
| Categorías | `/app/categorias` | USER / SUPER_ADMIN |
| Usuarios | `/app/users` | Solo SUPER_ADMIN |

---

##  Componentes principales

- `AuthService` → Manejo de sesión, tokens y roles.
- `ProductoService` → CRUD de productos.
- `CategoriaService` → CRUD de categorías.
- `AuthGuard` / `AdminRoleGuard` → Protección de rutas.
- `SidebarComponent` → Navegación dinámica según rol.
- `ModalService` → Control centralizado de modales.

---

##  Comandos útiles

### Compilar para producción
```bash
ng build --configuration production
```

### Ejecutar pruebas unitarias
```bash
ng test
```

---

##  Notas importantes
- El `environment.ts` o `base-url.interceptor.ts` debe apuntar al backend:
  ```ts
  export const environment = {
    apiUrl: 'http://localhost:8080/api'
  };
  ```
- El token JWT se almacena en `localStorage`.
- Los roles determinan la visibilidad de las opciones en el sidebar.

---

##  Estructura del proyecto

```
src/
 ├── app/
 │   ├── pages/
 │   │   ├── auth/
 │   │   ├── productos/
 │   │   ├── categorias/
 │   │   └── users/
 │   ├── services/
 │   ├── guards/
 │   ├── components/
 │   └── app.routes.ts
 ├── assets/
 └── environments/
```

---


