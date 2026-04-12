# RepositorioJenkins

Pipeline declarativo de Jenkins conectado a GitHub.

## Descripción

Este repositorio contiene un `Jenkinsfile` con un pipeline declarativo que se ejecuta automáticamente cada minuto mediante un cron trigger. El pipeline incluye:

- **Parámetro configurable**: `MOSTRAR_STEP` (booleano) para controlar la ejecución del primer stage.
- **Primer Stage**: Muestra un saludo personalizado. Solo se ejecuta si el parámetro `MOSTRAR_STEP` es `true`.
- **Segundo Stage**: Ejecuta los steps 2 y 3.
- **Post**: Imprime un mensaje de finalización en todas las ejecuciones.

## Configuración

| Propiedad | Valor |
|-----------|-------|
| Trigger | Cron cada minuto (`* * * * *`) |
| Timeout | 5 minutos |
| Agente | `any` |

## Parámetros

| Nombre | Tipo | Default | Descripción |
|--------|------|---------|-------------|
| `MOSTRAR_STEP` | boolean | `true` | Controla si se ejecuta el primer stage |

## Estructura

```
Jenkinsfile   # Pipeline declarativo
README.md     # Este archivo
```

## Uso

1. Configura este repositorio como fuente en un job de tipo **Pipeline** en Jenkins.
2. Selecciona **Pipeline script from SCM** y apunta a este repositorio.
3. Jenkins ejecutará el pipeline automáticamente cada minuto o de forma manual con el parámetro `MOSTRAR_STEP`.
