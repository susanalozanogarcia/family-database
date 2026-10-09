# family-database
Datos familiares y parentesco
Este proyecto consiste en el diseño conceptual de una base de datos para organizar la estructura de una familia, sus domicilios y sus mascotas. Desarrollado como práctica en el primer bloque de la asignatura de **Base de datos (1º sw DAM)**.
Decisiones de diseño y arquitectura: para evitar la **redundancia de datos** y optimizar la flexibilidad del sistema, se han tomado las siguientes decisiones de modelado:
* **Relaciones Recursivas con Roles**  En lugar de crear entidades rígidas para cada tipo de parentesco (¨tío¨, äbuel¨, ¨primo¨), el sistema modela la familia mediante dos relaciones recursivas sobre la entidad ´MIEMBRO´: *´<progenitor>´: con cardinalidad ´(0.2)´para registrar  los enlaces directos de padre/madre biológicos. El valor ´0´actúa como tope dinámico para permitir el registro de ancestros sin obligar a la recursividad infinita. *´<pareja>´: con cardinalidad ´(0.1)´para las relaciones conyugales.
* **Cálculo Dinámico: **Gracias a este enfoque, el sistema es capaz de deducir automáticamente cualquier parentesco biológico o político mediante consultas jerárquicas en el código, manteniendo la base de datos limpia de duplicidad.
## 📊 Diagrama Entidad-Relación
<img width="552" height="422" alt="Diagrama FAMILIA drawio" src="https://github.com/user-attachments/assets/d2cb8246-5233-4652-b1e9-e823b67780bf" />
