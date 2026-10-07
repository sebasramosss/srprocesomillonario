# Analizador de Perfil — el que usamos

> **Estado: funcionando.** `index.html` es la herramienta real, no un ejemplo.
> Un solo archivo, sin backend, sin base de datos.
> Se entrega a Carlos para montar en la landing.

## Qué hace

El lead pone 9 datos y recibe su diagnóstico al instante, comparado contra
los **75 videos reales** de `nichos/data/`.

## Lo que pide

| Campo | Para qué |
|---|---|
| Usuario de IG | Personalizar el encabezado |
| Qué vende | La bio y la palabra clave del CTA |
| Precio | El camino a los $10K |
| Clientes al mes | La facturación actual y los que faltan |
| Seguidores | El color: rojo, amarillo o verde |
| Videos al mes | Contra el estándar de 14 |
| Vistas promedio | El multiplicador contra seguidores |
| Likes promedio | La base de la tasa de conversación |
| **Comentarios promedio** | **La métrica central** |
| Bio actual | Para reescribirla |

## El motor

Calcula y encuentra **el primer eslabón que se corta**:

```
videos < 7              → VOLUMEN
vistas/seguidores < 1   → GANCHO (rojo)
conversación < 3.11%    → PUENTE   ← el caso más común
conversación ok, 0 clientes → OFERTA
todo bien               → ESCALA
```

Cada rama tiene su propio titular, su número protagonista y su diagnóstico.

## Los benchmarks (medidos, no inventados)

- **Mediana de conversación: 3.11%** — de los 75 videos
- **Estándar de volumen: 14 videos/mes** — el de la agencia
- **Color:** verde ≥5×, amarillo ≥1×, rojo <1× contra seguidores
- Los 4 ganchos y sus tasas salen de `nichos/ganchos.md`

## Para Carlos

- Un archivo HTML. Sin dependencias salvo Google Fonts (Montserrat).
- Mobile-first: todo el tráfico viene de Instagram.
- El botón del CTA final apunta a `#agendar` — hay que cambiarlo por el
  link real de la agenda.
- Toda la lógica está en el `<script>` del final. Los benchmarks son
  constantes nombradas arriba (`MEDIANA`, `ESTANDAR_VIDEOS`, `META`).

## Lo que falta

- **La bio se genera con fórmulas**, no con IA. Son plantillas armadas con
  los datos del lead. Funcionan, pero no son tan finas como las que
  escribiría Sebastián a mano. Si se quiere subir el nivel, hay que
  conectar una API.
- El link de agenda.
- El audio de seguimiento va aparte, en ManyChat.
