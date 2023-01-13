<template>
  <div class="form">
    <label class="toggle" for="flex-grow">
      <span class="toggle__label">flex-grow: 1</span>
      <input
        type="checkbox"
        role="switch"
        class="toggle__element"
        id="flex-grow"
        checked
      />
      <div class="toggle__decor" aria-hidden="true">
        <div class="toggle__thumb"></div>
      </div>
    </label>
  </div>
  <div class="cards">
    <div class="card">
      <figure>
        <img src="https://loremflickr.com/640/480?random=1" alt="" />
      </figure>
      <h3>Bandwidth responsive web design.</h3>
      <p>
        Twitter stock equity vesting period learning curve launch party pitch
        innovator series A financing churn rate handshake.
      </p>
      <button>Read more</button>
    </div>
    <div class="card">
      <figure>
        <img src="https://loremflickr.com/640/480?random=3" alt="" />
      </figure>
      <h3>Social media accelerator.</h3>
      <p contenteditable>
        Churn rate non-disclosure agreement buyer focus ecosystem iPad.(Please
        click on me to add content！ )
      </p>
      <button>Read more</button>
    </div>
    <div class="card">
      <figure>
        <img src="https://loremflickr.com/640/480?random=2" alt="" />
      </figure>
      <h3>Marketing iPad angel investor.</h3>
      <p>
        Funding influencer partner network metrics bandwidth leverage traction
        buzz virality.
      </p>
      <button>Read more</button>
    </div>
  </div>
</template>

<script setup lang="ts"></script>

<style lang="less" scoped>
// @import url("https://fonts.googleapis.com/css2?family=Exo:wght@600&display=swap");

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  width: 100vw;
  min-height: 100vh;
  font-family: "Exo", Arial, sans-serif;
  background-color: #557;
  color: #fff;
  display: grid;
  gap: 10px;
  place-content: center;
  justify-items: center;
  padding: 1rem;
}

:root {
  --color-primary: #3740ff;
  --color-primary-dark: #272eb5;
  --color-primary-light: #3740ff;
  --color-primary-x-light: #e8f0fe;
  --color-light: #ffffff;
  --color-dark: #202124;
  --color-off-white: #f3f4f4;
  --color-mid: #5f6368;
  --color-mid-dark: #3c4043;
  --color-stroke: #dadce0;
  --metric-gutter: 1.5rem;
  --metric-box-spacing: 1rem;
  --metric-radius: 3px;
  --generic-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3),
    0px 2px 6px 2px rgba(60, 64, 67, 0.15);
  --font-mono: SFMono-Regular, Consolas, "Liberation Mono", Menlo, monospace;
}

.toggle {
  --metric-toggle-thumb-size: 1rem;
  --metric-toggle-thumb-space: 0.25rem;
  position: relative;
  display: inline-flex;
  align-items: center;
}
.toggle__element {
  opacity: 0;
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  right: var(--metric-toggle-thumb-size);
  width: 1em;
  height: 1em;
}

.toggle__decor {
  display: block;
  position: relative;
  overflow: hidden;
  width: calc(
    (var(--metric-toggle-thumb-size) * 2) +
      (var(--metric-toggle-thumb-space) * 2)
  );
  height: calc(
    var(--metric-toggle-thumb-size) + (var(--metric-toggle-thumb-space) * 2)
  );
  background: var(--color-mid);
  margin-left: 0.5rem;
  border-radius: var(--metric-toggle-thumb-size);
  box-sizing: content-box;
  border: 1px solid var(--color-light);
}
:checked + .toggle__decor {
  background: var(--color-primary-light);
}

label::after {
  content: "\A";
  white-space: pre;
}

.toggle__thumb {
  display: grid;
  place-items: center;
  width: var(--metric-toggle-thumb-size);
  height: var(--metric-toggle-thumb-size);
  border-radius: var(--metric-toggle-thumb-size);
  background: linear-gradient(
      229.84deg,
      rgba(255, 255, 255, 0) 14.29%,
      rgba(48, 48, 48, 0.15) 81.82%
    ),
    #ffffff;
  box-shadow: var(--generic-shadow);
  position: absolute;
  top: var(--metric-toggle-thumb-space);
  left: var(--metric-toggle-thumb-space);
  transform: none;
  transition: transform 200ms cubic-bezier(1, 0, 0.55, 0.85);
  will-change: transform;
  z-index: 1;
}

.toggle__thumb::before {
  content: "";
  display: none;
  width: calc(
    var(--metric-toggle-thumb-size) - var(--metric-toggle-thumb-space)
  );
  height: calc(
    var(--metric-toggle-thumb-size) - var(--metric-toggle-thumb-space)
  );
  border: 1px solid var(--color-primary-light);
  border-radius: calc(
    var(--metric-toggle-thumb-size) - var(--metric-toggle-thumb-space)
  );
}

:checked + .toggle__decor .toggle__thumb {
  transform: translateX(var(--metric-toggle-thumb-size)) rotate(270deg);
}

.cards {
  background-color: #009788;
  color: #009788;
  border-radius: 6px;
  box-shadow: 0 1px 3px 0 rgb(0 0 0 / 10%), 0 6px 12px 0 rgb(0 0 0 / 10%);
  padding: 40px;
  width: min(1024px, 100%);
}

.card {
  border-radius: 4px;
  background-color: #fff;
}

figure {
  margin: 0;
  background-color: #b1dfdb;
  border-radius: 4px 4px 0 0;
  display: flex;
  justify-content: center;
  margin-bottom: 16px;
  overflow: hidden;
}

figure img {
  max-width: 100%;
  aspect-ratio: 16 / 9;
  object-fit: cover;
  object-position: center;
  border-radius: 4px 4px 0 0;
  mix-blend-mode: multiply;
  transform-origin: center;
  transform: scale3d(1, 1, 1);
  transition: all 0.2s ease-in-out;
}

.card:hover img {
  transform: scale3d(1.01, 1.02, 1.1);
}

.card > *:not(figure, button) {
  padding: 0 1rem;
}

.card h3 {
  font-size: 1.25em;
  line-height: 1.5;
  font-weight: 500;
  letter-spacing: -0.02em;
  margin-bottom: 1rem;
}

.card p {
  font-size: 12px;
  line-height: 1.625;
  color: #467570;
  font-weight: 300;
  margin-bottom: 1rem;
}

.card button {
  padding: 10px 18px 8px;
  min-height: 44px;
  font-size: 0.865em;
  letter-spacing: 0.1em;
  font-weight: bold;
  text-transform: uppercase;
  text-decoration: none;
  color: #fff;
  border-radius: 3px;
  background: #009888;
  transition: all 0.275s;
  display: inline-flex;
  justify-content: center;
  align-items: center;
  border: none 0;
  margin: 1rem;
}

.card button:hover {
  background: #095c53;
  color: #fff;
  text-shadow: 1px 1px 0 rgb(0 0 0 / 50%);
  cursor: pointer;
}

.cards {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
}

.card {
  display: flex;
  flex-direction: column;
  flex: 1 1 300px;
}

:root {
  --flex-grow: 1;
}

.card p {
  flex-grow: var(--flex-grow);
}
</style>
