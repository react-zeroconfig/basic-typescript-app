# Start development

```bash
npm start
```

# Build

```bash
npm run build
```

# Source Import Sample

## Jest 
<!-- import src/__tests__/*.{js,jsx,ts,tsx} --title-tag h3 -->
<h3>src/__tests__/e2e.ts</h3>
```ts
import puppeteer, { Browser, Page } from 'puppeteer';

describe('E2E Sample', () => {
  test('Test', async () => {
    const browser: Browser = await puppeteer.launch({headless: true});
    const page: Page = await browser.newPage();
    
    await page.goto('http://localhost:3100');
    await page.waitForSelector('#app > h1');
    
    await expect(page.$eval('#app > h1', e => e.innerHTML)).resolves.toEqual('Hello World!');
    
    await browser.close();
  });
});
```
<h3>src/__tests__/sample.ts</h3>
```ts
describe('Sample', () => {
  test('Test', () => {
    expect('text').toEqual('text');
  });
});
```
<!-- importend -->

<!-- import src/**/*.test.{js,jsx,ts,tsx} --title-tag h3 -->
<!-- importend -->

## Storybook
<!-- import src/**/*.stories.{js,jsx,ts,tsx} --title-tag h3 -->
<h3>src/app/components/Title.stories.tsx</h3>
```tsx
import { storiesOf } from '@storybook/react';
import React from 'react';
import { Title } from './Title';

storiesOf('Title', module)
  .add('text=Hello?', () => (
    <Title text="Hello?"/>
  ))
  .add('text=World?', () => (
    <Title text="World?"/>
  ));
```
<!-- importend -->