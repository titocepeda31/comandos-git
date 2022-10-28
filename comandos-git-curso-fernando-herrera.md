# CONFIGURACIONES GLOBALES

Se usa para que git tome la decisión de unir los cambios cuando haya conflicto, si la decisión es imposible. se deben hacer los cambios de manera manual

`git config --global pull.ff only` 

Se usa para que realizar los cambios de manera manual 

`git config --global pull.rebase true`

# CREAR ALIAS

### GIT LOG

`git config --global alias.lg "log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(bold yellow)%d%C(reset)' --all"`

### GIT STATUS

`git config --global alias.s status --short`

# GIT

### Agregar archivos al Stage

`git add nombre_archivo.algo`

### **Agregar todos los archivos al Stage**

`git add .`

### Realizar un commit o sacar un screentshoot de nuestro proyecto

`git commit -m “comentario”`

### Agregar archivos al stage + commit

`git commit -am “comentario”`

### Reestablece los archivos al commit anterior manteniendo los otro cambios efectuados

`git reset --soft HEAD~1`

### Reestablece los archivos al último commit, borrando todos los cambios realizados

`git reset --hard HEAD~1` 

### Elimina commit pusheado

`git revert (Hash commit)`

### Modificar un commit no pusheado

`git commit —amend` 

### Reconstruir todo lo borrado (vuelve al ultimo commit)

`git checkout — .`

### Volver al estado inicial de un archivo en específico

`git checkout — nombre-del-archivo.algo`

### Ver historial de commits

`git reflog`

Este comando muestra todos los logs que han ocurrido en el stage , incluso los archivos que se han eliminado

### Recuperar un commit en el tiempo

`git reset —hard ( numero de commit )`

### Recuperar un archivo mediante el  hash de un commit

`git checkout ( hash commit) nombre-archivo.algo`

### Eliminar un Archivo

`git rm archivo.algo`

### Renombrar un archivo ( si se encuentra en la misma ruta )

`git mv nombre_que_no_me_gusta.algo (ESPACIO) nuevo_nombre.algo`

### Ignorar arhivos o directorios que no deseamos darle seguimiento

Se debe crear un archivo llamado **.gitignore**

debe estar en la carpeta raiz

### Crear Rama

`git branch (nombre de la rama)`

### Cambiarse de rama

`git checkout ( nombre de la rama)`

### Unir cambios

`git merge (nombre de la rama)`

***Para el caso de querer traer los cambios a la rama master , debemos estar en master y hacer el merge de la rama que queremos unir.***

### Borrar rama

`git branch -d ( nombre de la rama)`

las ramas se deben borrar para cuando no queremos hacer mas seguimiento  a dicha rama debido a que a la unión de ramas o a que nuestros cambios fueron agregados con éxito y ya no es necesario continuar con esa rama.

-d = delete

### Borrar rama de manera forzada

`git branch -d (nombre rama) -f`

### Crear Rama y moverme a la rama creada

`git checkout -b (nombre de la rama)`

### Creación de tags

git tag (nombre del tag)

***Los tags se utilizan para marcar o señalar puntos importantes a lo largo del tiempo , ya sea para señalar que nuestro proyecto se convierte en una versión estable o de prueba ( ejemplo)***

### Listar tags

`git tag`

### Eliminar Tags

`git tag -d (nombre del tags)`

### Versionamiento Semántico con Tag

`git tag -a v1.0.0 -m “versión 1.0.0 lista”`

### Agregar tag a un commit en específico

`git tag -a v0.1.0 ( hash de commit) -m “mensaje de tag“`

### Información de un tag

`git show (nombre tag)`

### Almacenar o guardar cambios o mejoras que aún no han sido probadas ni agregadas al stage

`git stash`

***Sirve como bóbeda para dejar cambios que aún no ha sido puestos en el stage o que aún no son un commit , quiero decir que e sun almacen para dejar cambios que no han sido probados en el proyecto y que por abc motivos , se nos pide desplegar la versión del ultimo commit.***

****No se debería trabajar con stash si trabajamos con ramas y no manipulamos la rama master***

### Listar los Stash

`git stash list`

### Traer el último Stash y borra del stash ( posición 0 siempre es el último)

`git stash pop`

Ignorar cambios en el stash

### Borrar todos los stash

`git stash clear`

### Recuperar un stash en particular

`git stash apply stash@{NUMERO STASH}`

### Borrar un stash específico

`git stash drop stash@{NUMERO STASH}`

### Agregar descripción al guardar un stash

`git stash save “comentario”`

### Ver Stash con mas información

`git stash list —stat`

### Unificar Commit

`git rebase -i HEAD~4` ( el 4 espeficica cuantos commit quieres listar desde el commit actual)

usar rebase solo y cuando no hayamos realizado push 

Reebase Squash unir commits

Rebase Reword Sirve para renombrar los commit 

Rebase Edit  

# GITHUB

### Tags

### Corroborar y comprobar tags origen remoto - local

`git push -tags`

### Comprobar la ruta de nuestro repositorio remoto

`git remote -v`

### Empujar cambios remotos

`git pull origin (nombre de la rama)`

### Configuración cambios globales

`git config —global pull.ff only`

### Para comprobar o revisar la configuración global

`git config —global -e`

### Si queremos traer nuestor repositorio remoto desactualizado con nuestro proyecto local , debemos configurar lo siguiente para poder hacer el pull.

`git pull.rebase true` ( si a continuación hacemos el git pull , nos mostrará las diferencias entre los archivos) *dejar esta configuración

**Luego de decidir que cambios dejar , debemos agregar los archivos y crear el commit.**

**Para terminar el rebease debemos tipear** 

`git rebase —continue`

### UNIONES PULL REQUEST

`git pull request` sirve para bajar los cambios del repositorio de github a nuestro repositorio local

### Actualizar nuestro repositorio local con el repositorio remoto sin hacer merge ni entrar en conflicto  , solo traer cambios y actualizar repositorio local manteniendo nuestro commit actual.

`git fetch` 

****Se deben agregar comentarios en los commit de github para poder entender el flujo de github***
