## AP2 Übungen

[Sommer 2014](https://forms.gle/cnHbXsF3wFqMStEe7)

[Winter 2015/2016](https://forms.gle/y8cEytWb87R44QwY9)


### Alte Abschlussprüfungen:

[Sommer 2012](https://ts13b.github.io/sozialkunde_pdf/sozialkunde_sommer_2012.pdf)

[Sommer 2013](https://ts13b.github.io/sozialkunde_pdf/sozialkunde_sommer_2013.pdf)

[Sommer 2014](https://ts13b.github.io/sozialkunde_pdf/sozialkunde_sommer_2014.pdf)

[Winter 2014/2015](https://ts13b.github.io/sozialkunde_pdf/sozialkunde_winter_2014_2015.pdf)

[Sommer 2015](https://ts13b.github.io/sozialkunde_pdf/sozialkunde_sommer_2015.pdf)

[Winter 2015/2016](https://ts13b.github.io/sozialkunde_pdf/sozialkunde_winter_2016_2016.pdf)

[Winter 2017/2018](https://ts13b.github.io/sozialkunde_pdf/sozialkunde_winter_2017_2018.pdf)

[Sommer 2019](https://ts13b.github.io/sozialkunde_pdf/sozialkunde_sommer_2019.pdf)

### Abschlussprüfungen hochladen:

[`zum Upload`](https://forms.gle/GqEd1L56UDE3HVfDA)

```diff
- [Sommer 2019](https://ts13b.github.io/sozialkunde_pdf/sozialkunde_sommer_2019.pdf)
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```

---
title: Colors
description: 'Immutable, atomic CSS classes to rapidly build product'
status: Stable
status_issue: 'https://github.com/github/design-systems/issues/97'
---

import {Box, BorderBox} from '@primer/components'
import {palettes, allColors} from '../../src/color-variables'
import {PaletteTable, PaletteTableFragment, PaletteHeading, PaletteCell, PaletteValue} from '../../src/color-system'

Use color utilities to apply color to the background of elements, text, and borders.

## Background colors

Background colors are most commonly used for filling large blocks of content or areas with a color. When selecting a background color, make sure the foreground color contrast passes a minimum WCAG accessibility rating of [level AA](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-contrast.html). Meeting these standards ensures that content is accessible by everyone, regardless of disability or user device. You can [check your color combination with this demo site](https://colorable.jxnblk.com/). For more information, read our [accessibility standards](../principles/accessibility).

### Background utilities

<PaletteTable>
  {palettes.map(({name, title, value}) => (
    <PaletteTableFragment name={name} type="bg" sparse key={name}>
      <tr>
        <PaletteHeading indicatorColor={value} colSpan="4">
          {title}
        </PaletteHeading>
      </tr>
    </PaletteTableFragment>
  ))}
</PaletteTable>

## Text colors

Use text color utilities to set text or [Octicons](https://octicons.github.com) to a specific color. Color contrast must pass a minimum WCAG accessibility rating of [level AA](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-contrast.html). This ensures that viewers who cannot see the full color spectrum are able to read the text. To customize outside of the suggested combinations below, we recommend using this [color contrast testing tool](https://colorable.jxnblk.com/). For more information, read our [accessibility standards](../principles/accessibility).

These are our most common text with background color combinations. They don't all pass accessibility standards currently, but will be updated in the future. **⚠️ Any of the combinations with a warning icon must be used with caution**.

### Text color inheritance

You can set the color inheritance on an element by using the `text-inherit` class.

```html live
<div class="text-purple">This text is purple, <a href="#" class="text-inherit">including the link</a></div>
```

### Text on white background

```html live
<div class="text-blue mb-2">
  .text-blue
</div>
<div class="text-gray-dark mb-2">
  .text-gray-dark
</div>
<div class="text-gray mb-2">
  .text-gray
</div>
<div class="text-gray-light mb-2">
  .text-gray-light
</div>
<div class="text-red mb-2">
  .text-red
</div>
<div class="text-orange mb-2">
  .text-orange
</div>
<div class="text-orange-light mb-2">
  .text-orange-light
  <span class="tooltipped tooltipped-n" aria-label="Does not meet accessibility standards">⚠️</span>
</div>
<div class="text-yellow mb-2">
  .text-yellow
  <span class="tooltipped tooltipped-n" aria-label="Does not meet accessibility standards">⚠️</span>
</div>
<div class="text-green mb-2">
  .text-green
</div>
<div class="text-purple mb-2">
  .text-purple
</div>
```

### Text on colored backgrounds

```html live
<div class="text-white bg-blue mb-2">
  .text-white on .bg-blue
</div>
<div class="bg-blue-light mb-2">
  .text-gray-dark on .bg-blue-light
</div>
<div class="text-white bg-red mb-2">
  .text-white on .bg-red
</div>
<div class="text-red bg-red-light mb-2">
  .text-red on .bg-red-light
</div>
<div class="bg-green-light mb-2">
  .text-gray-dark on .bg-green-light
</div>
<div class="bg-yellow-dark mb-2">
  .text-gray-dark on .bg-yellow-dark
</div>
<div class="bg-yellow mb-2">
  .text-gray-dark on .bg-yellow
</div>
<div class="bg-yellow-light mb-2">
  .text-gray-dark on .bg-yellow-light
</div>
<div class="text-white bg-purple mb-2">
  .text-white on .bg-purple
</div>
<div class="text-white bg-gray-dark mb-2">
  .text-white on .bg-gray-dark
</div>
<div class="bg-gray">
  .text-gray-dark on .bg-gray
</div>
```

### Text color utilities

<PaletteTable columns={[
  {
    title: 'Alias',
    Cell: props => <PaletteCell.Alias {...props} style={{borderBottom: `1px solid ${props.value} !important`}} />
  },
  'variable',
  {title: 'Value', Cell: PaletteCell.Background, Value: PaletteValue.Value}
]}>
  {palettes.map(({name, title, value}) => (
    <PaletteTableFragment name={name} type="text" sparse prefix="color" columns={[
  {
    title: 'Alias',
    Cell: props => <PaletteCell.Alias {...props} style={{borderBottom: `1px solid ${props.value} !important`}} />
  },
  'variable',
  {title: 'Value', Cell: PaletteCell.Background, Value: PaletteValue.Value}
]}>
      <tr>
        <PaletteHeading indicatorColor={value} colSpan="4">
          {title}
        </PaletteHeading>
      </tr>
    </PaletteTableFragment>
  ))}
</PaletteTable>

## White background

You can make a background explicitly white (`#fff`) with the `bg-white` utility:

```html live
<div class="bg-gray-dark p-2">
  <span class="bg-white">.bg-white over .bg-gray-dark</span>
</div>
```

## Link colors

Base link styles turn links blue and apply an underline on hover. You can override the base link styles with text color utilities and the following link utilities. **Bear in mind that link styles are easier for more people to see and interact with when the changes in styles do not rely on color alone.**

Use `link-gray` to turn the link color to `$text-gray` and remain hover on blue.

```html live
<a class="link-gray" href="#url">link-gray</a>
```

Use `link-gray-dark` to turn the link color to `$text-gray-dark` and remain hover on blue.

```html live
<a class="link-gray-dark" href="#url">link-gray-dark</a>
```

Use `.muted-link` to turn the link light gray in color, and blue on hover or focus with no underline.

```html live
<a class="muted-link" href="#url">muted-link</a>
```

Use `link-hover-blue` to make any text color used with links to turn blue on hover. This is useful when you want only part of a link to turn blue on hover.

```html live
<a class="text-gray-dark no-underline" href="#url">
  A link with only part of it is <span class="link-hover-blue">blue on hover</span>.
</a>
```

## Border colors

Border colors are documented on the [border utilities page](../utilities/borders#border-width-style-and-color-utilities).
