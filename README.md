# Manual Básico de Git

### ¿Qué es Git?

Git es un sistema de control de versiones distribuido. Sirve para llevar un seguimiento de los

cambios realizados en el código fuente de un proyecto. Te permite trabajar en equipo, mantener un

historial de versiones y volver a estados anteriores si algo sale mal.

### ¿Qué es una rama (branch)?

Una rama en Git es una línea paralela de desarrollo. Permite trabajar en una nueva funcionalidad,

bugfix o idea sin afectar el código principal (por lo general llamado main o master).

Ejemplo de flujo:

1. Estás en la rama main, que está estable.

2. Creás una rama feature/login para desarrollar el login.

3. Trabajás en esa rama y hacés tus commits.

4. Cuando terminás, unís esa rama con main mediante un merge.

### Comandos Esenciales de Git

`git init`

Inicializa un repositorio Git en el directorio actual.

`git init`

`git clone <url>`

Clona un repositorio remoto a tu máquina.

`git clone https://github.com/usuario/repositorio.gitCommit`

Guardar cambios

`git add <archivo>`

Agrega archivos al área de preparación (staging).

`git add index.js`

`git add .`

`git commit -m "Mensaje"`

Guarda un snapshot de los cambios con un mensaje.

`git commit -m "Agrega formulario de login"`

Push: Enviar cambios al repositorio remoto

`git push origin <rama>`

Envía los commits de la rama local al repositorio remoto.

`git push origin main`

Pull: Traer cambios del remoto

`git pull origin <rama>`

Trae los cambios más recientes del repositorio remoto y los mezcla con tu rama actual.

`git pull origin main`

Branch: Crear y trabajar con ramas

`git branch`

Lista las ramas disponibles.

`git branch`

`git branch <nombre-rama>`

Crea una nueva rama.

`git checkout -b <nombre-rama>`

Cambia a otra rama.

`git checkout feature/login`

Merge: Unir ramas

`git merge <rama>`

Une los cambios de otra rama a la actual.

`git checkout main`

`git merge feature/login`

Otros comandos útiles

`git status`

Muestra los archivos modificados y el estado actual del repo.

`git status`
`git log`

Muestra el historial de commits.

`git log`

Buenas prácticas con ramas

- Usá nombres descriptivos: feature/navbar, bugfix/footer, hotfix/api-error.

- No trabajes directamente en main, usá ramas para desarrollar y luego mergeá.

- Hacé commits frecuentemente y con mensajes claros.

- Antes de hacer merge, actualizá tu rama con pull.

### Resolver Conflictos en un Merge

A veces, cuando hacés un merge entre ramas, Git no puede decidir automáticamente qué cambios

conservar.

Esto se llama un "conflicto de merge".

Pasos para resolver un conflicto:

1. Git te va a mostrar qué archivos tienen conflictos.

Podés verlos con:

`git status`

2. Abrí los archivos en conflicto. Vas a ver algo como esto:
```
<<<<<<< HEAD

Código de tu rama actual

=======

Código de la rama que estás mergeando

>>>>>>> feature/login
```
3. Editá el archivo y dejá solo el código que querés conservar.

4. Una vez resueltos todos los conflictos, marcá los archivos como resueltos:
`git add <archivo-resuelto>`

5. Completá el merge con:
`git commit`

¡Listo! El conflicto está resuelto.
