# Backporch

Backporch is a board to connect many classic gaming consoles with widely
available and easily made cables with no components inside.  Backporch can then
be connected to PVMs (via HD15), Extron matrices, SCART TVs or OSSC / Retrotink
devices.

PVMs and Extron matrices can be connected with a simple VGA to BNC or VGA to
VGA cable. SCART TVs can be connected with a component-free Mini-DIN 8 to SCART
cable.

It includes the necessary resistors, coupling caps and a sync stripper / sync
booster.

## Inputs

There are two inputs:

* The (mini) DIN 9 connector is suitable for consoles that output directly from
  a video amplifier to the back of the console.  Cables for such consoles
typically have impedence matching resistors as well as coupling capacitors.

* The (mini) DIN 8 connector (also usable as output) is suitable for consoles
  that have adequate components inside the console and are ready to be
connected to a SCART. This mainly include retro mods such as the NES RGB.

## Outputs

There are two video outputs:

* The DE-15/HD-15 ("VGA") connector is suitable for PVMs (or the DE-15 input on
  the OSSC) and is best used with widely available HD15 to BNC cables. It will
output composite sync or separate H-SYNC and V-SYNC depending on the JP3
jumper.

* The (mini) DIN 8 connector (also usable as input) is suitable for SCART
  output using a widely available mini DIN 8 to SCART cable. This output can
also be used to connect to a fFramemeister with a simple mini DIN 8 cable.

Jumpers:

* JP1: Solder pad 1 and 2 together (keep the 2-3 connection open)
* JP2: keep open
* JP3: Solder pad 2 and 3 together for composite sync (CSYNC), or pad 1 and 2
  instead for separate HSYNC / VSYNC output

## Supported consoles

### NES RGB mod

* If your mod uses the mini DIN 8 output, simply use a mini DIN 8 to mini DIN 8
  cable
* If your mod uses the multi-av output, solder a simpler passive cable from the
  multi AV to mini DIN 8

### Sega Mega-Drive / Genesis 2

* Use a simple mini DIN 9 to mini DIN 9 cable. Sega 32X cables work well, but
  all pints need to be connected. Note that *proper* 32X cables don't have PIN
2 (5V) connected. Most "cheap" cables on Ebay have all pins connected.

### Sega Mega-Drive / Genesis 1

* There are many model 1 to model 2 adapters available

### Super Nintendo

* If your super Nintendo is modded with an RGB bypass mod, you can build a
  simple cable from MultiAV to mini-din 8.  Wire sync (Pin 3) from either
composite or Luma (better!). This will work for either PAL or NTSC consoles! If
you have CSYNC wired, you can use that instead, but ideally configure your RGB
bypass board to output 75 Ohm CSYNC.

* Unmodded Super Nintendo are not supported at this time as they require
  coupling capacitors (things will work without them, but this setup might draw
excessive current from the video amplifiers).

### PC Engine with SSDS3: same as Mega-Drive / Genesis 2.

### Neo Geo AES

* Build a simple passive cable from the Neo geo DIN8 to standard Mini DIN 8

### Neo Geo MVS

* If you use the [Minigun
  Supergun](https://www.arcade-projects.com/threads/minigun-supergun-an-open-source-supergun.9408/),
you can simply use a Mini DIN8 to Mini DIN8 cable between them.

## Proper cable hygiene

Ideally proper analog video transmission should happens over 75 Ohm coaxial.
[Proper impedence
matching](https://en.wikipedia.org/wiki/Impedance_matching#Transmission_lines)
requires a 75 Ohm resistor at the source and a 75 Ohm resistor at the
destination. This is why many retro gaming cables that have resistors inside
the SCART (near the destination) are not proper. At the frequencies used in
classic gaming console signals, this only starts to matter for very long cables
though.

You should strive to use high quality shielded cables to Backporch and keep
them very short. Proper VGA cables used from Backporch output can be long.

## FAQ

* What does the name mean?

It's a small deck at the back of your console (back porch). It's also a
reference to the blanking interval after the sync pulse in video signals.

* Do I need all those components?

Probably not. For many inputs, if you know what you're doing, you can remove
all components related to sync stripping and use JP1 to send sync directly to
HSYNC on the HD-15 port. For THS737X mods ("RGB bypass"), coupling capacitors
are not needed. Remove the big electrolytic capacitors and bridge the footprint
of the small ones.

* There is "noise" when connecting to an OSSC via DE-15: the DE-15 input on the
  OSSC does not have a proper low-pass filter.  You can use the SCART input
instead, or you can route the RGB lines to AV2 instead (via BNC/RCA adaptors
and VGA/BNC breakout cables) and use the "AV3 use alt. RGB" option on the OSSC.
