# South Pole Lander

A browser-based lunar landing simulator set in the Moon's south polar region. Fly the lander yourself or watch a guidance autopilot bring it down, then take over mid-descent.

## Play

Open `index.html` in any browser. No install or build step.

| Key | Action |
| --- | --- |
| ↑ / W | Fire engine at the throttle setting |
| ← → / A D | Rotate the lander |
| P | Switch autopilot on or off mid-flight |
| R | Restart |

Touch buttons below the flight view work on phones.

**Touchdown limits:** under 2 m/s vertical, under 1 m/s horizontal, tilt under 8°, between the two beacons.

## Physics

- Lunar gravity: 1.62 m/s²
- Lander: 1,500 kg dry mass, one 7,000 N throttleable engine
- Specific impulse: 311 s (close to the Apollo descent engine)
- Propellant flow: `ṁ = T / (Isp · g₀)`, so the lander gets lighter as it burns
- Remaining Δv from the rocket equation: `Δv = Isp · g₀ · ln(m_wet / m_dry)`
- Fixed 120 Hz physics step

## Guidance

The autopilot sets a target descent rate that shrinks with altitude and a target horizontal speed that shrinks with distance to the pad. The difference between target and actual velocity becomes a desired acceleration vector, which sets the tilt angle and throttle every step.

Program modes follow Apollo naming: **P63** braking, **P64** approach, **P66** terminal descent.

## Terrain

Procedurally generated craters and ridges, lit by a sun 2° above the horizon. Slopes facing the sun are bright; the rest sits in permanent shadow, as it does near the real lunar south pole.
