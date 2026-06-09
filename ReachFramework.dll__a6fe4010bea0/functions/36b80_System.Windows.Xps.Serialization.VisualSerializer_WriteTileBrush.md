# System.Windows.Xps.Serialization.VisualSerializer::WriteTileBrush

- ea: `0x36b80`
- end: `0x36e89`
- name: `System.Windows.Xps.Serialization.VisualSerializer::WriteTileBrush`
- size: `777`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x37110`

## callees

- `0x37a0`
- `0x36950`
- `0x36b30`
- `0x36b80`

## pseudocode

```c

```

## disassembly

```asm
0x36b80  ldarg.0
0x36b81  ldarg.1
0x36b82  ldarg.2
0x36b83  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteBrushHeader(string element, class [PresentationCore]System.Windows.Media.Brush brush)
0x36b88  ldarg.2
0x36b89  callvirt instance valuetype [PresentationCore]System.Windows.Media.BrushMappingMode [PresentationCore]System.Windows.Media.TileBrush::get_ViewportUnits()
0x36b8e  stloc.0
0x36b8f  ldloc.0
0x36b90  brtrue.s loc_36B99
0x36b92  ldsfld   valuetype [WindowsBase]System.Windows.Rect System.Windows.Xps.Serialization.VisualSerializer::UnitRect
0x36b97  starg.s  3
0x36b99  ldc.i4.0
0x36b9a  stloc.0
0x36b9b  ldarg.0
0x36b9c  ldstr    aViewportunits// "ViewportUnits"
0x36ba1  ldloc.0
0x36ba2  box      [PresentationCore]System.Windows.Media.BrushMappingMode
0x36ba7  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteAttr(string attribute, object val)
0x36bac  ldarg.0
0x36bad  ldstr    aTilemode// "TileMode"
0x36bb2  ldarg.2
0x36bb3  callvirt instance valuetype [PresentationCore]System.Windows.Media.TileMode [PresentationCore]System.Windows.Media.TileBrush::get_TileMode()
0x36bb8  box      [PresentationCore]System.Windows.Media.TileMode
0x36bbd  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteAttr(string attribute, object val)
0x36bc2  ldarg.2
0x36bc3  callvirt instance valuetype [WindowsBase]System.Windows.Rect [PresentationCore]System.Windows.Media.TileBrush::get_Viewport()
0x36bc8  stloc.s  0x10
0x36bca  ldloca.s 0x10
0x36bcc  call     instance float64 [WindowsBase]System.Windows.Rect::get_Width()
0x36bd1  ldarga.s 3
0x36bd3  call     instance float64 [WindowsBase]System.Windows.Rect::get_Width()
0x36bd8  mul
0x36bd9  stloc.1
0x36bda  ldarg.2
0x36bdb  callvirt instance valuetype [WindowsBase]System.Windows.Rect [PresentationCore]System.Windows.Media.TileBrush::get_Viewport()
0x36be0  stloc.s  0x10
0x36be2  ldloca.s 0x10
0x36be4  call     instance float64 [WindowsBase]System.Windows.Rect::get_Height()
0x36be9  ldarga.s 3
0x36beb  call     instance float64 [WindowsBase]System.Windows.Rect::get_Height()
0x36bf0  mul
0x36bf1  stloc.2
0x36bf2  ldarg.2
0x36bf3  call     valuetype [WindowsBase]System.Windows.Rect Microsoft.Internal.AlphaFlattener.Utility::GetTileAbsoluteViewbox(class [PresentationCore]System.Windows.Media.TileBrush brush)
0x36bf8  stloc.3
0x36bf9  ldloca.s 3
0x36bfb  call     instance float64 [WindowsBase]System.Windows.Rect::get_Width()
0x36c00  stloc.s  4
0x36c02  ldloca.s 3
0x36c04  call     instance float64 [WindowsBase]System.Windows.Rect::get_Height()
0x36c09  stloc.s  5
0x36c0b  ldc.i4.1
0x36c0c  stloc.s  8
0x36c0e  ldarg.2
0x36c0f  callvirt instance valuetype [PresentationCore]System.Windows.Media.Stretch [PresentationCore]System.Windows.Media.TileBrush::get_Stretch()
0x36c14  stloc.s  0x11
0x36c16  ldloc.s  0x11
0x36c18  switch   loc_36C2F, loc_36C81, loc_36C54, loc_36C69
0x36c2d  br.s     loc_36C81
0x36c2f  ldc.r8   1.0
0x36c38  stloc.s  6
0x36c3a  ldc.r8   1.0
0x36c43  stloc.s  7
0x36c45  ldloc.s  4
0x36c47  ldloc.1
0x36c48  bgt.s    loc_36C4F
0x36c4a  ldloc.s  5
0x36c4c  ldloc.2
0x36c4d  ble.un.s loc_36C8D
0x36c4f  ldc.i4.0
0x36c50  stloc.s  8
0x36c52  br.s     loc_36C8D
0x36c54  ldloc.1
0x36c55  ldloc.s  4
0x36c57  div
0x36c58  ldloc.2
0x36c59  ldloc.s  5
0x36c5b  div
0x36c5c  call     float64 [mscorlib]System.Math::Min(float64, float64)
0x36c61  stloc.s  6
0x36c63  ldloc.s  6
0x36c65  stloc.s  7
0x36c67  br.s     loc_36C8D
0x36c69  ldloc.1
0x36c6a  ldloc.s  4
0x36c6c  div
0x36c6d  ldloc.2
0x36c6e  ldloc.s  5
0x36c70  div
0x36c71  call     float64 [mscorlib]System.Math::Max(float64, float64)
0x36c76  stloc.s  6
0x36c78  ldloc.s  6
0x36c7a  stloc.s  7
0x36c7c  ldc.i4.0
0x36c7d  stloc.s  8
0x36c7f  br.s     loc_36C8D
0x36c81  ldloc.1
0x36c82  ldloc.s  4
0x36c84  div
0x36c85  stloc.s  6
0x36c87  ldloc.2
0x36c88  ldloc.s  5
0x36c8a  div
0x36c8b  stloc.s  7
0x36c8d  ldloc.s  4
0x36c8f  ldloc.s  6
0x36c91  mul
0x36c92  stloc.s  9
0x36c94  ldloc.s  5
0x36c96  ldloc.s  7
0x36c98  mul
0x36c99  stloc.s  0xA
0x36c9b  ldarg.2
0x36c9c  callvirt instance valuetype [PresentationCore]System.Windows.Media.AlignmentX [PresentationCore]System.Windows.Media.TileBrush::get_AlignmentX()
0x36ca1  stloc.s  0x12
0x36ca3  ldloc.s  0x12
0x36ca5  switch   loc_36CB8, loc_36CDD, loc_36CCB
0x36cb6  br.s     loc_36CDD
0x36cb8  ldloc.1
0x36cb9  ldloc.s  9
0x36cbb  sub
0x36cbc  neg
0x36cbd  ldc.r8   2.0
0x36cc6  div
0x36cc7  stloc.s  0xB
0x36cc9  br.s     loc_36CE8
0x36ccb  ldloc.1
0x36ccc  ldloc.s  9
0x36cce  sub
0x36ccf  ldc.r8   2.0
0x36cd8  div
0x36cd9  stloc.s  0xB
0x36cdb  br.s     loc_36CE8
0x36cdd  ldc.r8   0.0
0x36ce6  stloc.s  0xB
0x36ce8  ldarg.2
0x36ce9  callvirt instance valuetype [PresentationCore]System.Windows.Media.AlignmentY [PresentationCore]System.Windows.Media.TileBrush::get_AlignmentY()
0x36cee  stloc.s  0x13
0x36cf0  ldloc.s  0x13
0x36cf2  switch   loc_36D05, loc_36D2A, loc_36D18
0x36d03  br.s     loc_36D2A
0x36d05  ldloc.2
0x36d06  ldloc.s  0xA
0x36d08  sub
0x36d09  neg
0x36d0a  ldc.r8   2.0
0x36d13  div
0x36d14  stloc.s  0xC
0x36d16  br.s     loc_36D35
0x36d18  ldloc.2
0x36d19  ldloc.s  0xA
0x36d1b  sub
0x36d1c  ldc.r8   2.0
0x36d25  div
0x36d26  stloc.s  0xC
0x36d28  br.s     loc_36D35
0x36d2a  ldc.r8   0.0
0x36d33  stloc.s  0xC
0x36d35  ldarg.0
0x36d36  ldstr    aViewboxunits// "ViewboxUnits"
0x36d3b  ldc.i4.0
0x36d3c  box      [PresentationCore]System.Windows.Media.BrushMappingMode
0x36d41  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteAttr(string attribute, object val)
0x36d46  ldarg.2
0x36d47  callvirt instance valuetype [WindowsBase]System.Windows.Rect [PresentationCore]System.Windows.Media.TileBrush::get_Viewport()
0x36d4c  stloc.s  0xD
0x36d4e  ldloca.s 0xD
0x36d50  ldarga.s 3
0x36d52  call     instance float64 [WindowsBase]System.Windows.Rect::get_X()
0x36d57  ldloca.s 0xD
0x36d59  call     instance float64 [WindowsBase]System.Windows.Rect::get_X()
0x36d5e  ldarga.s 3
0x36d60  call     instance float64 [WindowsBase]System.Windows.Rect::get_Width()
0x36d65  mul
0x36d66  add
0x36d67  ldarga.s 3
0x36d69  call     instance float64 [WindowsBase]System.Windows.Rect::get_Y()
0x36d6e  ldloca.s 0xD
0x36d70  call     instance float64 [WindowsBase]System.Windows.Rect::get_Y()
0x36d75  ldarga.s 3
0x36d77  call     instance float64 [WindowsBase]System.Windows.Rect::get_Height()
0x36d7c  mul
0x36d7d  add
0x36d7e  ldloca.s 0xD
0x36d80  call     instance float64 [WindowsBase]System.Windows.Rect::get_Width()
0x36d85  ldarga.s 3
0x36d87  call     instance float64 [WindowsBase]System.Windows.Rect::get_Width()
0x36d8c  mul
0x36d8d  ldloca.s 0xD
0x36d8f  call     instance float64 [WindowsBase]System.Windows.Rect::get_Height()
0x36d94  ldarga.s 3
0x36d96  call     instance float64 [WindowsBase]System.Windows.Rect::get_Height()
0x36d9b  mul
0x36d9c  call     instance void [WindowsBase]System.Windows.Rect::.ctor(float64, float64, float64, float64)
0x36da1  ldloc.s  8
0x36da3  brfalse.s loc_36DD0
0x36da5  ldloca.s 0xD
0x36da7  ldloca.s 0xD
0x36da9  call     instance float64 [WindowsBase]System.Windows.Rect::get_Left()
0x36dae  ldloc.s  0xB
0x36db0  add
0x36db1  ldloca.s 0xD
0x36db3  call     instance float64 [WindowsBase]System.Windows.Rect::get_Top()
0x36db8  ldloc.s  0xC
0x36dba  add
0x36dbb  ldloca.s 0xD
0x36dbd  call     instance float64 [WindowsBase]System.Windows.Rect::get_Width()
0x36dc2  ldloca.s 0xD
0x36dc4  call     instance float64 [WindowsBase]System.Windows.Rect::get_Height()
0x36dc9  call     instance void [WindowsBase]System.Windows.Rect::.ctor(float64, float64, float64, float64)
0x36dce  br.s     loc_36DFF
0x36dd0  ldloca.s 3
0x36dd2  ldloca.s 3
0x36dd4  call     instance float64 [WindowsBase]System.Windows.Rect::get_Left()
0x36dd9  ldloc.s  0xB
0x36ddb  ldloc.s  6
0x36ddd  div
0x36dde  sub
0x36ddf  ldloca.s 3
0x36de1  call     instance float64 [WindowsBase]System.Windows.Rect::get_Top()
0x36de6  ldloc.s  0xC
0x36de8  ldloc.s  7
0x36dea  div
0x36deb  sub
0x36dec  ldloca.s 3
0x36dee  call     instance float64 [WindowsBase]System.Windows.Rect::get_Width()
0x36df3  ldloca.s 3
0x36df5  call     instance float64 [WindowsBase]System.Windows.Rect::get_Height()
0x36dfa  call     instance void [WindowsBase]System.Windows.Rect::.ctor(float64, float64, float64, float64)
0x36dff  ldloca.s 0xD
0x36e01  call     instance float64 [WindowsBase]System.Windows.Rect::get_Width()
0x36e06  ldloc.s  6
0x36e08  div
0x36e09  stloc.s  0xE
0x36e0b  ldloca.s 0xD
0x36e0d  call     instance float64 [WindowsBase]System.Windows.Rect::get_Height()
0x36e12  ldloc.s  7
0x36e14  div
0x36e15  stloc.s  0xF
0x36e17  ldloca.s 3
0x36e19  ldloca.s 3
0x36e1b  call     instance float64 [WindowsBase]System.Windows.Rect::get_Left()
0x36e20  ldloca.s 3
0x36e22  call     instance float64 [WindowsBase]System.Windows.Rect::get_Width()
0x36e27  ldloc.s  0xE
0x36e29  sub
0x36e2a  ldc.r8   2.0
0x36e33  div
0x36e34  add
0x36e35  ldloca.s 3
0x36e37  call     instance float64 [WindowsBase]System.Windows.Rect::get_Top()
0x36e3c  ldloca.s 3
0x36e3e  call     instance float64 [WindowsBase]System.Windows.Rect::get_Height()
0x36e43  ldloc.s  0xF
0x36e45  sub
0x36e46  ldc.r8   2.0
0x36e4f  div
0x36e50  add
0x36e51  ldloc.s  0xE
0x36e53  ldloc.s  0xF
0x36e55  call     instance void [WindowsBase]System.Windows.Rect::.ctor(float64, float64, float64, float64)
0x36e5a  ldarg.0
0x36e5b  ldstr    aViewbox// "Viewbox"
0x36e60  ldloca.s 3
0x36e62  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x36e67  call     instance string [WindowsBase]System.Windows.Rect::ToString(class [mscorlib]System.IFormatProvider)
0x36e6c  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteAttr(string attribute, object val)
0x36e71  ldarg.0
0x36e72  ldstr    aViewport// "Viewport"
0x36e77  ldloca.s 0xD
0x36e79  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x36e7e  call     instance string [WindowsBase]System.Windows.Rect::ToString(class [mscorlib]System.IFormatProvider)
0x36e83  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteAttr(string attribute, object val)
0x36e88  ret
```
