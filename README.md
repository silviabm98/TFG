# TFG
Las redes generativas adversarias, llamadas habitualmente GANs, son modelos de apren-
dizaje profundo especializados en la generación de contenidos sintéticos realistas, como
imágenes, audios y vídeos, a partir de ejemplos reales. Este trabajo se centra en el estudio de
los fundamentos matemáticos e informáticos de las GANs, así como en su aplicación para la
generación de ultrafalsificaciones de imágenes (deep fakes).

Las GANs son un tipo de redes neuronales con dos partes diferenciadas, una red genera-
dora y otra red discriminadora, que compiten en un juego de suma cero. La red generadora
produce muestras, con la intención de engañar a la red discriminadora para que crea que son
muestras reales, y la red discriminadora debe distinguir las muestras reales de las producidas
por el generador. Ambas redes se entrenan de forma simultánea con el objetivo de construir
un buen generador que se capaz de producir ejemplos sintéticos indistinguibles de los reales.
Según su creador Ian Goodfellow, “es un proceso donde cada una de las redes va mejorando
y aprende de su oponente”.

El procesamiento en las GANs tiene diferencias relevantes respecto a las redes neuronales
habituales. Inicialmente, disponemos de un conjunto de entrenamiento con ejemplos reales
y de vectores de ruido aleatorio con la misma estructura. Para cada vector de ruido, la red
generadora construye un ejemplo falso. A continuación, estos ejemplos falsos, junto a los
ejemplos reales, constituyen la entrada de la red discriminadora, cuya misión es asignar a ca-
da ejemplo la probabilidad de que que pertenezca al conjunto de ejemplos de entrenamiento;
esto es, de que sea verdadero. La formulación y la implementación de las GANs presentan
características de interés, que se estudian en la parte de este trabajo más cercana al ámbito
de la informática.

En cuanto al entrenamiento, las dos redes neuronales se ajustan al mismo tiempo aplicando
gradiente descendente y retropropagación. La clave del entrenamiento de las GANs es de-
terminar cuándo finalizar este entrenamiento. Puesto que se trata de un juego de suma cero,
también conocido como problema minmax, el objetivo teórico es alcanzar un equilibrio de
Nash, esto es, un punto donde ningún jugador mejore su situación aunque el entrenamiento
continúe. No obstante, este equilibrio es muy difícil de alcanzar en la práctica y presenta un
problema para las GANs. En la parte de matemática del trabajo, se analiza la formulación de
este problema minmax y de sus implicaciones en la convergencia del entrenamiento de las
GANs, así como las diferentes alternativas dependiendo de la formulación de la función de
pérdida de las redes basada en teoría de la probabilidad.

Finalmente, se realizan diversos experimentos con varios tipos de GANs (arquitectura
y función de pérdida) en dos problemas de procesamiento de imágenes: la generación de
dígitos, basada en el conjunto de datos MNIST, y la ultrafalsificación de caras, con el conjunto
de datos CelebA. Este segundo caso de uso es especialmente relevante en la actualidad, ya
que las GANs se utilizan cada vez más para la manipulación de contenidos audiovisuales
con el propósito de propagar desinformación. Por ello, previamente se revisa el estado del
arte de las deep fakes con GANs en este contexto.


En conclusión, este trabajo proporciona una introducción formal a las GANs, describien-
do los principios fundamentos matemáticos que subyacen a esta técnica y explicando su
materialización en una implementación con herramientas de aprendizaje profundo. La expe-
rimentación demuestra que es posible generar contenidos falsos y potencialmente realistas
