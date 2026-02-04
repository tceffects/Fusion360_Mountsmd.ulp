# TCFX_Mountsmd.ulp

Fusion 360 migrated from the old Eagle layer numbering to their own system. In classic Eagle, top copper was 1 and bottom copper was 16. When Autodesk integrated Eagle into Fusion, they started remapping internal layer numbers—304 is their new bottom copper ID.

That's exactly why the stock mountsmd ULP broke too. It was still checking for layer 16, which doesn't exist anymore in newer Fusion versions. So it found all the top components on layer 1 (unchanged) but never matched anything on the bottom because it was looking for 16 instead of 304.
