# learn.svelte.dev

Интерактивный учебник по супам на орехах о том, как создавать приложения с Svelte.

## Setup

Это репо использует [pnpm](https://pnpm.io/).

## Разработка приложения

Прежде всего, запустите `node scripts/create-common-bundle`. Это упаковывает все, что нужно для запуска приложения Sveltekit (Vite, esbuild, SvelteKit, Svelte compiler, etc.) который впоследствии может быть распакован на сервере для создания и запуска экземпляра Sveltekit Application (которое питает окно вывода учебника). Затем запустите, `dev`:

```bash
node scripts/create-common-bundle
pnpm dev
```

Сборка для продакшн и работы локально:

```bash
pnpm build
pnpm preview
```

## Создание нового туториала

Туториалы живут внутри `content`. Каждый туториал состоит из `README.md`, который является текстом слева, и `app-a` и `app-b` папок, которые представляют исходное и решенное состояние. Файлы, которые остаются такими же, могут быть опущены из `app-b`. Файлы помечены как удаленные в `app-b` если они начинаются с `__delete`. Папки, которые отмечены как удаленные в `app-b` если они содержат файл с именем `__delete`.

## Bumping tutorial dependencies

Bump the dependency (for example Svelte) in both the root and the `content/common` `package.json`. In the root do `pnpm i` (to update `pnpm-lock.yaml`), in `content/common` do `npm i` (to update `package-lock.json`).