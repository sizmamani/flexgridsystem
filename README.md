# react-flex-grid-system

Set of React components that implement [`flexboxgrid.css`](https://github.com/kristoferjoseph/flexboxgrid) but with [`styled-components`](https://github.com/styled-components/styled-components)/[`emotion`](https://github.com/emotion-js/emotion). Furthermore, it allows to customize grid configuration like gutter width...

Highly inspired by the excellent [`react-flexbox-grid`](https://github.com/roylee0704/react-flexbox-grid) which the API is nearly the same than this module.

## Usage

### Installation

```
npm i -S react-flex-grid-system
```

`react-flex-grid-system` depends on 2 **peer** dependencies:

- `react@^0.14.0 || ^15.0.0-0 || ^16.0.0-0 || ^17.0.0-0`
- `prop-types@^15.0.0-0`
- `styled-components@2`

You should install them in your project.

### Basic

```JSX
import React from 'react'

import {Grid, Col, Row} from 'reac-flex-grid-system'

const App = props =>
  <Grid>
    <Row>
      <Col xs={6} md={3}>Hello, world!</Col>
    </Row>
  </Grid>
```

### Grid

The `<Grid>` component is optional and can help to wrap children in a fixed/fluid container. Use the configuration `container` for fixed width value.

##### Props

- `fluid` _(Boolean)_: Create a responsive fixed width container or a full width container, spanning the entire width of your viewport. Default: false

### Row

##### Props

- `reverse` _(Boolean)_: Use `flex-direction: row-reverse`. Default: false
- `start`
- `center`
- `end`
- `top`
- `middle`
- `bottom`
- `around`
- `between`
- `first`
- `last` _(String(xs|sm|md|lg)_: Align elements to the start or end of row as well as the top, bottom, or center of a column.

### Col

##### Props

- `reverse` _(Boolean)_: Use `flex-direction: column-reverse`. Default: false
- `xs`
- `sm`
- `md`
- `lg` _(Boolean|Integer)_:
  - When `true`, enable auto sizing column.
  - When `false`, hide colomn for the breakpoint.
  - When `integer` value, it specify the column size on the grid. (1 to 12)
- `xsOffset`
- `smOffset`
- `mdOffset`
- `lgOffset` _(Integer)_: Offset the column.

### Configuration

The grid use same defaults than [`flexboxgrid.css`](https://github.com/kristoferjoseph/flexboxgrid).

You can customize values using [`<ThemeProvider>`](https://github.com/styled-components/styled-components#theming) component from styled-components.
`reac-flex-grid-system` will looks at the `flexboxgrid` property in the theme.

```JSX
import React from 'react'

import {ThemeProvider} from 'styled-components'
import {Grid, Col, Row} from 'reac-flex-grid-system'

const theme = {
  flexboxgrid: {
    // Defaults
    gridSize: 12, // columns
    gutterWidth: 1, // rem
    outerMargin: 2, // rem
    mediaQuery: 'only screen',
    container: {
      sm: 46, // rem
      md: 61, // rem
      lg: 76  // rem
    },
    breakpoints: {
      xs: 0,  // em
      sm: 48, // em
      md: 64, // em
      lg: 75  // em
    }
  }
}

const App = props =>
  <ThemeProvider theme={theme}>
    <Grid>
      <Row>
        <Col xs={6} md={3}>Hello, world!</Col>
      </Row>
    </Grid>
  </ThemeProvider>
```

## Use with Emotion

To use reac-flex-grid-system with emotion, import from 'reac-flex-grid-system/emotion':

```jsx
import { Grid, Col, Row } from "reac-flex-grid-system/emotion";
```

## Related projects

- [styled-components](https://github.com/styled-components/styled-components)
- [hedron](https://github.com/JSBros/hedron)

## License

MIT
