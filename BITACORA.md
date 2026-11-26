 
# Bitácora del laboratorio de rescate.

para el punto 1:

git log: Muestra el historial completo y detallado de todos los commits (código identificador completo, autor, fecha, hora y mensaje del commit).

git log --oneline: Muestra una versión resumida del historial, donde cada commit ocupa una sola línea con su código corto y su mensaje.

git log --oneline --graph --all: Muestra el historial resumido en una línea junto con un gráfico visual en texto (líneas y asteriscos) de todas las ramas y bifurcaciones del proyecto.

¿Qué es el código al inicio de cada commit?
 Es el hash SHA-1, un identificador único generado por Git para cada commit (por ejemplo, 2f6d5a6 en su versión corta) que permite rastrear o volver a esa versión exacta del proyecto.

 para el punto 2:

¿Por qué el segundo git diff no mostró nada?
 Porque git diff sin opciones solo compara el directorio de trabajo (working directory) contra el área de preparación (staging area). Al ejecutar git add notas.txt, los cambios pasaron al staging area, por lo que ya no quedaban diferencias sin preparar.

¿Qué muestra --staged?
 Muestra exactamente las diferencias entre los archivos que ya fueron agregados al área de preparación (staging area con git add) y el último commit guardado, es decir, lo que está listo para incluirse en el próximo commit.

 para el punto 3:

¿Qué hace git restore?
 Descarta los cambios no confirmados en el directorio de trabajo (working directory) y restaura el archivo exactamente al estado en que estaba en el último commit guardado.

¿Funcionaría si nunca hubieras hecho commit de ese archivo?
 No. Si el archivo nunca fue rastreado ni guardado en un commit previo, Git no tiene ninguna copia de respaldo en su historial de dónde recuperarlo.

 para el punto 4:

¿Qué diferencia hay entre git restore y git restore --staged?
 git restore <archivo> descarta las modificaciones hechas en el archivo dentro de tu carpeta local (volviéndolo al estado del último commit), mientras que git restore --staged <archivo> únicamente saca el archivo del área de preparación (staging area) sin borrar los cambios que hiciste en tu carpeta.

  para el punto 6
  ¿git revert borró el commit equivocado o creó uno nuevo?
   Creó un commit nuevo que deshace los cambios del commit anterior sin eliminarlo del historial.  
    ¿Por qué es la opción segura cuando ya se hizo push?
     Porque conserva intacto el historial público ya subido a GitHub, evitando conflictos o historiales desincronizados para otras personas que ya hayan descargado los cambios. 