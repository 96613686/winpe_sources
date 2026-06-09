# System.Windows.Xps.Serialization.VisualSerializer::WriteTCO

- ea: `0x38ca0`
- end: `0x38d57`
- name: `System.Windows.Xps.Serialization.VisualSerializer::WriteTCO`
- size: `183`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x385c0`
- `0x38840`
- `0x38ea0`

## callees

- `0x2180`
- `0x40a0`
- `0x70e0`
- `0x36950`
- `0x37510`
- `0x38130`
- `0x38200`
- `0x38ca0`

## pseudocode

```c

```

## disassembly

```asm
0x38ca0  ldarg.s  6
0x38ca2  brfalse.s loc_38CD8
0x38ca4  ldarg.s  6
0x38ca6  isinst   [PresentationCore]System.Windows.Media.SolidColorBrush
0x38cab  stloc.1
0x38cac  ldloc.1
0x38cad  brfalse.s loc_38CD8
0x38caf  ldarg.s  5
0x38cb1  ldloc.1
0x38cb2  callvirt instance valuetype [PresentationCore]System.Windows.Media.Color [PresentationCore]System.Windows.Media.SolidColorBrush::get_Color()
0x38cb7  stloc.2
0x38cb8  ldloca.s 2
0x38cba  call     instance float32 [PresentationCore]System.Windows.Media.Color::get_ScA()
0x38cbf  conv.r8
0x38cc0  call     float64 Microsoft.Internal.AlphaFlattener.Utility::NormalizeOpacity(float64 value)
0x38cc5  ldarg.s  6
0x38cc7  callvirt instance float64 [PresentationCore]System.Windows.Media.Brush::get_Opacity()
0x38ccc  call     float64 Microsoft.Internal.AlphaFlattener.Utility::NormalizeOpacity(float64 value)
0x38cd1  mul
0x38cd2  mul
0x38cd3  starg.s  5
0x38cd5  ldnull
0x38cd6  starg.s  6
0x38cd8  ldarg.s  5
0x38cda  call     bool Microsoft.Internal.AlphaFlattener.Utility::IsOne(float64 value)
0x38cdf  brtrue.s loc_38D0F
0x38ce1  ldarg.0
0x38ce2  ldstr    aOpacity// "Opacity"
0x38ce7  ldarg.s  5
0x38ce9  ldc.r8   0.0
0x38cf2  call     float64 [mscorlib]System.Math::Max(float64, float64)
0x38cf7  ldc.r8   1.0
0x38d00  call     float64 [mscorlib]System.Math::Min(float64, float64)
0x38d05  box      [mscorlib]System.Double
0x38d0a  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteAttr(string attribute, object val)
0x38d0f  ldarg.s  6
0x38d11  brfalse.s loc_38D2B
0x38d13  ldarg.s  6
0x38d15  call     bool Microsoft.Internal.AlphaFlattener.BrushProxy::IsEmpty(class [PresentationCore]System.Windows.Media.Brush brush)
0x38d1a  brtrue.s loc_38D2B
0x38d1c  ldarg.0
0x38d1d  ldstr    aOpacitymask// "OpacityMask"
0x38d22  ldarg.s  6
0x38d24  ldarg.s  7
0x38d26  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteBrush(string attribute, class [PresentationCore]System.Windows.Media.Brush brush, valuetype [WindowsBase]System.Windows.Rect bounds)
0x38d2b  ldarg.0
0x38d2c  ldstr    aRendertransfor// "RenderTransform"
0x38d31  ldarg.2
0x38d32  ldnull
0x38d33  call     valuetype [WindowsBase]System.Windows.Rect [WindowsBase]System.Windows.Rect::get_Empty()
0x38d38  call     instance void System.Windows.Xps.Serialization.VisualSerializer::WriteTransform(string attribute, class [PresentationCore]System.Windows.Media.Transform trans, class [PresentationCore]System.Windows.Media.Transform relative, valuetype [WindowsBase]System.Windows.Rect bounds)
0x38d3d  ldc.i4.0
0x38d3e  stloc.0
0x38d3f  ldarg.3
0x38d40  brfalse.s loc_38D55
0x38d42  ldarg.0
0x38d43  ldarg.1
0x38d44  ldstr    aClip// "Clip"
0x38d49  ldarg.3
0x38d4a  ldarg.s  4
0x38d4c  ldc.i4.0
0x38d4d  ldc.i4.1
0x38d4e  ldc.i4.0
0x38d4f  call     instance bool System.Windows.Xps.Serialization.VisualSerializer::WriteGeometry(string element, string attribute, class [PresentationCore]System.Windows.Media.Geometry geo, valuetype [WindowsBase]System.Windows.Media.Matrix map, bool asElement, bool forFill, bool forStroke)
0x38d54  stloc.0
0x38d55  ldloc.0
0x38d56  ret
```
