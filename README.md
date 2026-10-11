# Bent Light

A black hole drawn live in the browser by tracing the path of light for every pixel.

**Live:** https://trainedon-mercy.github.io/bent-light/

Drag to orbit. Two switches let you turn the physics off to see what it was doing:

- **Bend light** turns off gravitational lensing, so you see the flat disc and the event horizon at its true size.
- **Doppler boost** turns off the brightening of the side of the disc that moves toward you.

## How it works

A WebGL fragment shader fires one ray per pixel and steps it a few hundred times through the gravity of a non-spinning (Schwarzschild) black hole, using the acceleration `a = -1.5 h² x / r⁵` with the Schwarzschild radius set to 1. Each time a ray crosses the disc plane it picks up light from the disc. Rays that escape sample a procedural star field. Rays that fall inside the horizon stay black.

## What is real and what is not

- The light paths follow the real equation of motion, integrated with a simple fixed-order stepper, so fine detail in the photon ring is approximate.
- The disc starts at 3 Schwarzschild radii, the innermost stable circular orbit.
- Doppler and gravitational shifts use the orbital speed a static observer would measure.
- Disc colour, temperature and texture are artistic. A real disc this close to a black hole shines mostly in X-rays.

## Run it locally

Open `index.html` in a browser with WebGL.
