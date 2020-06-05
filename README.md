# cursos-platzi
notas de los cursos en platzi

en este curso aprederemos comandos git para elcontrol de versiones

PASOS PARA CREAR UN PROYECTO

#1. creamos un repositorio en google drive

mkdir "C:\Users\ASUS\Google Drive (ronesprograms@gmail.com)\platzi-cursos\curso-git"

git init


#2. Clonamos en la laptop el repositorio de google

git clone "C:\Users\ASUS\Google Drive (ronesprograms@gmail.com)\platzi-cursos\curso-git"

cd curso-git


#3. Creamos un repositorio en github cursos-platzi

https://github.com/ronesprograms/cursos-platzi.git


#4. Agregamos el repositorio github al proyecto en la laptop

git remote add github-origin https://github.com/ronesprograms/cursos-platzi.git

$ git remote
github-origin
origin

$ git remote -v
github-origin   https://github.com/ronesprograms/cursos-platzi.git (fetch)
github-origin   https://github.com/ronesprograms/cursos-platzi.git (push)
origin  C:\Users\ASUS\Google Drive (ronesprograms@gmail.com)\platzi-cursos\curso-git (fetch)
origin  C:\Users\ASUS\Google Drive (ronesprograms@gmail.com)\platzi-cursos\curso-git (push)

#5. enviamos el proyecto a github

$ git push github-origin master
To https://github.com/ronesprograms/cursos-platzi.git
 ! [rejected]        master -> master (fetch first)
error: failed to push some refs to 'https://github.com/ronesprograms/cursos-platzi.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.

Primero tenemos que hacer un git pull$ git pull github-origin
warning: no common commits
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), 620 bytes | 2.00 KiB/s, done.
From https://github.com/ronesprograms/cursos-platzi
 * [new branch]      master     -> github-origin/master
You asked to pull from the remote 'github-origin', but did not specify
a branch. Because this is not the default configured remote
for your current branch, you must specify a branch on the command line.

ASUS@DESKTOP-LQC4BQI MINGW64 /d/workspace/platzi-cursos/curso-git (master)
$  git pull github-origin master
From https://github.com/ronesprograms/cursos-platzi
 * branch            master     -> FETCH_HEAD
fatal: refusing to merge unrelated histories

!!!PERO DA ERROR NO SE PUEDEN MESCLAR LAS HISTORIAS NO RELACIONADAS
Hay que utilizar el comando:

git pull github-origin master --allow-unrelated-histories
$ git pull github-origin master --allow-unrelated-histories
From https://github.com/ronesprograms/cursos-platzi
 * branch            master     -> FETCH_HEAD
error: Your local changes to the following files would be overwritten by merge:
        README.md
Please commit your changes or stash them before you merge.
Aborting
!!! primero hay que hacer commit a todos los archivos del master antes de hacer el pull.

git add .
git commit -m "commit a todos los archivos"

FINALMENTE HACEMOS EL PULL
$ git pull github-origin master --allow-unrelated-histories
remote: Enumerating objects: 5, done.
remote: Counting objects: 100% (5/5), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), 1.84 KiB | 14.00 KiB/s, done.
From https://github.com/ronesprograms/cursos-platzi
 * branch            master     -> FETCH_HEAD
   750e8c4..e932537  master     -> github-origin/master
hint: Waiting for your editor to close the file...
Merge made by the 'recursive' strategy.


#6 Hcemos commit en nuestro master para guardar los ultimos cambios
 git commit -am "guardamos los ultimos cambios en el master-local"


#07 Hacemos un push al remoto github-origin desde master para sincronizar los repositorio.

git push github-origin master


