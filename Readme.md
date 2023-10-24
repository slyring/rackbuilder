# Racks Builder Toolkit

Contains tools/generators that help in building context-based levels with ease.

![End Result](/.res/overview.png)

## How to use

- Place the `BP_Cluster_Racks` actor into the level

![Drop actor](/.res/drop_actor.png)

- Set suitable values for parameters under `Cluster`, `Rack`, and `Palette`. The breakdown of each section will be
  explained below.

![All settings](/.res/settings_overview.png)

- After setting/modifying the parameter click on `Generate Rack Cluster`.
  It's the call-in editor function that will use the above config and generate racks and palettes with boxes.

![Control buttons](/.res/control_buttons.png)

## Settings Breakdown

### Cluster Config

![Cluster Config](/.res/cluster_settings.png)

- `Box Extents:` Defines the spread and distribution of racks to be spawned.
- `Spaceing X & Spaceing Y:` controls the spacing BETWEEN the spawned racks
- `Padding X & Padding Y:` controls the padding between `BoxExtent`and Racks

The result with the above settings are as shown in the image below

- The red line represents `Box Extents` and the blue line represents `Padded Box Extents`.

![Control buttons](/.res/box_extents.png)

### Rack Config

![Rack Config](/.res/rack_settings.png)

- `Columns:` controls how many columns each rack should have.
- `ShelfHeight:`controls the vertical spacing <b>BETWEEN</b> trays of each rack. Frames supporting the Trays will automatically
  adjust based on the selected `ShelfHeight`.
- `Frame_Bottom, Frame_Mid, Frame_Top, Tray_Bottom, Tray_Mid & Tray_Top:` are the meshes to be assigned for the rack to
  be generated.<br/> `NOTE: The pivots of the meshes should be same as the pivots mesh in the example.`

### Palette Config

![Palette Config](/.res/palette_settings.png)

- `Seed:` Controls`RandomStream`of palette rotations, box types, rotation, and spacing.
- `Palette Mesh:`Sets Palette mesh. The pivot has to be the same as the mesh provided in the example.
- `Boxes:` Array of boxes that will spawn on the palette that are picked randomly.
- `MinPadding & MaxPadding:` Controls the random padding between boxes. Selected padding will be the same per palette actor.
- `TraceLocationOffsetX:` This is mainly to adjust trace offset for different rack meshes.
  This allows to configure the starting point of the placement.
- `MinPaletteOffset & MaxPaletteOffset:`Controls random location offsets per palette actor.
- `MinPaletteRotation & MaxPaletteRotation:`Controls random location offsets per palette actor.
- `MinFillPercentage & MaxFillPercentage:` Controls the random fill percentage of palette actors per shelf.

### Outliner

- The below image is the hierarchy that will be generated.
- Each `Palette` will be spawned as an actor with attached `Static Mesh Actors` of palette and boxes
- Each `Rack` will spawn as an actor. Frames and Trays will be `Static Mesh Components` inside it.

![Hierarchy](/.res/hierarchy.png)
