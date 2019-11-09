# ga-ec-posts-wordpress
Plugin para implementar impresiones y clics del comercio avanzado de Analytics en los posts de WordPress


Por ahora es necesario insertar en los enlaces del archivo donde se llama al loop de los posts, el siguiente evento onclick:
```
onclick="productObject('<?php the_title(); ?>','<?php the_ID(); ?>','<?php echo get_the_author_meta('ID'); ?>','<?php  $cat = get_the_category(); echo $cat[0]->cat_name; ?>','<?php $posttags = get_the_tags();
					if ($posttags) {i
					  foreach($posttags as $tag) {
						echo $tag->name . ', '; 
					  }
					} ?>','<?php wp_title(); ?>','<?php the_permalink(); ?>')"
```

El fichero cambia según el tema, en el tema flymag de WordPress por ejemplo, es el content.php


## REQUISITOS

- Necesitas tener instalado Google Analytics en WordPress para que funcione el plugin
- Necesitas tener activada la parte de Comercio Avanzado de Google Analytics
	- Para activar esto accede a la **Administrar** de Google Analytics, en la columna de **Vistas** en **Configuración del Comercio Electrónico** activar las dos opciones y guardar.
- Insertar el código del *onclick* arriba dado en los enlaces a los artículos
