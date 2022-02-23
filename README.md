# 🚀 Astro theme utilities

### [📘 Documentation →](https://astros.warps.it/documentation)

### [🧑‍🚀 Astro website →](https://astro.build/)

This component should includes various utilities for helping handle theming with astro.

You can find a live usage at [astros.warps.it](https://astros.warps.it/).

Utilities included in the package

| Name          | Description                   |
| ------------- | ----------------------------- |
| ThemeSwitcher | Switch between choosen themes |

## ThemeSwitcher

Note: Work in progress. for now specifiy only dark, light and dimmed theme names (check below).
### How To Use

In any of your Astro pages, import the utility you need:

```astro
---
...
/* Import the components you need */
import { ThemeSwitcher } from "astro-theme";
---

<html lang="en">
	<head>
	</head>
	<head>
		<body>
			<header>
				<ThemeSwitcher />
			</header>
		</body>
	</head>
</html>
```

Now in your global css/scss use css variables like so:

```scss
:root {
	--color-bg: white;
	--color-text-primary: black;

	&[data-theme="dark"] {
		--color-bg: black;
		--color-text-primary: white;
	}

	&[data-theme="dimmed"] {
		--color-bg: gray;
		--color-text-primary: white;
	}

	&[data-theme="any-other-theme-you-want"] {
		--color-bg: gray;
		--color-text-primary: white;
	}
}

```

### Supported Props

| Propname     | Type    | Default                                                                           | Required | Description                                                                                   |
| ------------ | ------- | --------------------------------------------------------------------------------- | -------- | --------------------------------------------------------------------------------------------- |
| themes       | theme[] | `[{ name: "dark", icon: "ph:moon-thin" },{ name: "light", icon: "ph:sun-thin" }]` |          | Themes name and icons to use, objects with name and [icon](https://icon-sets.iconify.design/) |
| defaultDark  | string  | null                                                                              |          | Name of the theme to use as default for dark (will check prefers-color-scheme)                |
| defaultLight | string  | null                                                                              |          | Name of the theme to use as default for light (will check prefers-color-scheme)               |
| type         | string  | rotate                                                                            |          | Type of switcher, for now only rotate is supported                                            |
