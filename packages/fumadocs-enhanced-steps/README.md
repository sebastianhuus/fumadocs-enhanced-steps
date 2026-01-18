# fumadocs-enhanced-steps

Enhanced Steps component for [Fumadocs](https://fumadocs.dev) with support for lettered increments, custom icons, and step titles.

## Features

- **Multiple counter types**: decimal (1, 2, 3), letters (a, b, c or A, B, C), roman numerals (i, ii, iii or I, II, III)
- **Custom icons**: Replace numbers/letters with any React node
- **Step titles**: Add titles with configurable heading levels
- **Fumadocs theming**: Seamless integration with fumadocs color variables
- **Dark mode**: Automatic dark mode support
- **Accessible**: Proper ARIA roles for screen readers

## Installation

```bash
npm install fumadocs-enhanced-steps
# or
pnpm add fumadocs-enhanced-steps
# or
yarn add fumadocs-enhanced-steps
```

## Usage

### Basic Usage

```tsx
import { Steps, Step } from 'fumadocs-enhanced-steps';
import 'fumadocs-enhanced-steps/styles/steps.css';

<Steps>
  <Step title="First Step">
    Content for the first step.
  </Step>
  <Step title="Second Step">
    Content for the second step.
  </Step>
  <Step title="Third Step">
    Content for the third step.
  </Step>
</Steps>
```

### Lettered Steps

```tsx
<Steps type="lower-alpha">
  <Step title="Step A">First step content.</Step>
  <Step title="Step B">Second step content.</Step>
  <Step title="Step C">Third step content.</Step>
</Steps>
```

### Counter Types

| Type | Output |
|------|--------|
| `decimal` (default) | 1, 2, 3... |
| `lower-alpha` | a, b, c... |
| `upper-alpha` | A, B, C... |
| `lower-roman` | i, ii, iii... |
| `upper-roman` | I, II, III... |

### Custom Icons

```tsx
import { CheckIcon } from 'lucide-react';

<Steps>
  <Step title="Completed" icon={<CheckIcon />}>
    This step is complete!
  </Step>
  <Step title="In Progress">
    Working on this...
  </Step>
</Steps>
```

### Title Heading Levels

```tsx
<Steps titleSize="h3">
  <Step title="Important Step">
    The title will render as an h3 element.
  </Step>
</Steps>
```

## Props

### Steps

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| `type` | `'decimal' \| 'lower-alpha' \| 'upper-alpha' \| 'lower-roman' \| 'upper-roman'` | `'decimal'` | Counter style for step indicators |
| `titleSize` | `'p' \| 'h2' \| 'h3'` | `'p'` | Default heading level for titles |
| `className` | `string` | - | Additional CSS classes |

### Step

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| `title` | `ReactNode` | - | Title displayed next to the indicator |
| `icon` | `ReactNode` | - | Custom icon (replaces number/letter) |
| `titleSize` | `'p' \| 'h2' \| 'h3'` | inherited | Heading level for this step's title |
| `className` | `string` | - | Additional CSS classes |

## Styling

The component uses fumadocs CSS variables for theming:

- `--color-fd-secondary` - Indicator background
- `--color-fd-secondary-foreground` - Indicator text
- `--color-fd-border` - Connecting line
- `--color-fd-foreground` - Title text
- `--color-fd-muted-foreground` - Body text

If these variables aren't defined, sensible fallback colors are used.

## License

MIT
