# Microsoft.Internal.GDIExporter.CGDIRenderTarget::FillLinearGradient

- ea: `0x20d40`
- end: `0x21182`
- name: `Microsoft.Internal.GDIExporter.CGDIRenderTarget::FillLinearGradient`
- size: `1090`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1f8d0`

## callees

- `0x240`
- `0x2a0`
- `0x7e0`
- `0x1020`
- `0x10f0`
- `0x11b0`
- `0x1260`
- `0x12b0`
- `0x1bde0`
- `0x1bf80`
- `0x1bfe0`
- `0x1ed40`
- `0x1f490`
- `0x1f8d0`
- `0x20d40`

## string_xrefs

- `0x20e4a`: `Unknown GradientSpreadMethod`

## pseudocode

```c

```

## disassembly

```asm
0x20d40  ldarg.2
0x20d41  isinst   [PresentationCore]System.Windows.Media.LinearGradientBrush
0x20d46  stloc.0
0x20d47  ldloc.0
0x20d48  brfalse  loc_2117C
0x20d4d  ldloc.0
0x20d4e  call     instance valuetype [PresentationCore]System.Windows.Media.ColorInterpolationMode [PresentationCore]System.Windows.Media.GradientBrush::get_ColorInterpolationMode()
0x20d53  ldc.i4.1
0x20d54  bne.un   loc_2117C
0x20d59  ldloc.0
0x20d5a  call     instance class [PresentationCore]System.Windows.Media.GradientStopCollection [PresentationCore]System.Windows.Media.GradientBrush::get_GradientStops()
0x20d5f  brfalse  loc_2116F
0x20d64  ldloc.0
0x20d65  call     instance class [PresentationCore]System.Windows.Media.GradientStopCollection [PresentationCore]System.Windows.Media.GradientBrush::get_GradientStops()
0x20d6a  callvirt instance int32 [PresentationCore]System.Windows.Media.GradientStopCollection::get_Count()
0x20d6f  brfalse  loc_2116F
0x20d74  ldloc.0
0x20d75  call     instance class [PresentationCore]System.Windows.Media.GradientStopCollection [PresentationCore]System.Windows.Media.GradientBrush::get_GradientStops()
0x20d7a  callvirt instance int32 [PresentationCore]System.Windows.Media.GradientStopCollection::get_Count()
0x20d7f  ldc.i4.1
0x20d80  bne.un.s loc_20DAF
0x20d82  ldc.i4.0
0x20d83  ldstr    aSingleStopLine// "Single-stop LinearGradientBrush, should"...
0x20d88  call     void [System]System.Diagnostics.Debug::Assert(bool, string)
0x20d8d  ldloc.0
0x20d8e  call     instance class [PresentationCore]System.Windows.Media.GradientStopCollection [PresentationCore]System.Windows.Media.GradientBrush::get_GradientStops()
0x20d93  ldc.i4.0
0x20d94  callvirt instance class [PresentationCore]System.Windows.Media.GradientStop [PresentationCore]System.Windows.Media.GradientStopCollection::get_Item(int32)
0x20d99  call     instance valuetype [PresentationCore]System.Windows.Media.Color [PresentationCore]System.Windows.Media.GradientStop::get_Color()
0x20d9e  stloc.s  0x1C
0x20da0  ldarg.0
0x20da1  ldarg.1
0x20da2  ldloc.s  0x1C
0x20da4  newobj   instance void [PresentationCore]System.Windows.Media.SolidColorBrush::.ctor(valuetype [PresentationCore]System.Windows.Media.Color)
0x20da9  call     instance modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 Microsoft.Internal.GDIExporter.CGDIRenderTarget::FillPath(modreq([mscorlib]System.Runtime.CompilerServices.IsImplicitlyDereferenced) class Microsoft.Internal.GDIExporter.GeometryProxy geometry, class [PresentationCore]System.Windows.Media.Brush pFillBrush)
0x20dae  ret
0x20daf  ldloc.0
0x20db0  call     instance valuetype [PresentationCore]System.Windows.Media.BrushMappingMode [PresentationCore]System.Windows.Media.GradientBrush::get_MappingMode()
0x20db5  ldc.i4.0
0x20db6  ceq
0x20db8  stloc.s  0x1B
0x20dba  ldloc.s  0x1B
0x20dbc  ldstr    aBrushShouldVeB// "Brush should've been made absolute"
0x20dc1  call     void [System]System.Diagnostics.Debug::Assert(bool, string)
0x20dc6  ldloc.0
0x20dc7  call     instance class [PresentationCore]System.Windows.Media.GradientStopCollection [PresentationCore]System.Windows.Media.GradientBrush::get_GradientStops()
0x20dcc  call     class [mscorlib]System.Collections.SortedList Microsoft.Internal.GDIExporter.GetSortedGradientStops(class [PresentationCore]System.Windows.Media.GradientStopCollection stopCollection)
0x20dd1  stloc.1
0x20dd2  ldloc.0
0x20dd3  call     valuetype [WindowsBase]System.Windows.Media.Matrix Microsoft.Internal.GDIExporter.GetGradientWorldToXTransform(class [PresentationCore]System.Windows.Media.LinearGradientBrush brush)
0x20dd8  stloc.s  0x16
0x20dda  ldarg.1
0x20ddb  call     instance class [PresentationCore]System.Windows.Media.Geometry Microsoft.Internal.GDIExporter.GeometryProxy::get_Geometry()
0x20de0  ldloc.s  0x16
0x20de2  call     class [PresentationCore]System.Windows.Media.Geometry Microsoft.Internal.GDIExporter.TransformGeometry(class [PresentationCore]System.Windows.Media.Geometry geometry, valuetype [WindowsBase]System.Windows.Media.Matrix transform)
0x20de7  callvirt instance valuetype [WindowsBase]System.Windows.Rect [PresentationCore]System.Windows.Media.Geometry::get_Bounds()
0x20dec  stloc.s  0x24
0x20dee  ldloca.s 0x24
0x20df0  ldc.r8   0.0
0x20df9  ldc.r8   1.0
0x20e02  call     instance void [WindowsBase]System.Windows.Rect::Inflate(float64, float64)
0x20e07  ldloc.s  0x16
0x20e09  stloc.s  0x23
0x20e0b  ldloca.s 0x23
0x20e0d  call     instance void [WindowsBase]System.Windows.Media.Matrix::Invert()
0x20e12  ldloca.s 0x23
0x20e14  ldarg.0
0x20e15  ldflda   valuetype [WindowsBase]System.Windows.Media.Matrix Microsoft.Internal.GDIExporter.CGDIRenderTarget::m_transform
0x20e1a  ldobj    [WindowsBase]System.Windows.Media.Matrix
0x20e1f  call     instance void [WindowsBase]System.Windows.Media.Matrix::Append(valuetype [WindowsBase]System.Windows.Media.Matrix)
0x20e24  ldc.i4.0
0x20e25  stloc.s  0x10
0x20e27  ldc.i4.0
0x20e28  stloc.s  0xF
0x20e2a  ldc.i4.0
0x20e2b  stloc.s  7
0x20e2d  ldc.i4.0
0x20e2e  stloc.s  6
0x20e30  ldloc.0
0x20e31  call     instance valuetype [PresentationCore]System.Windows.Media.GradientSpreadMethod [PresentationCore]System.Windows.Media.GradientBrush::get_SpreadMethod()
0x20e36  stloc.s  0x22
0x20e38  ldloca.s 0x22
0x20e3a  ldind.i4
0x20e3b  brfalse.s loc_20E89
0x20e3d  ldloca.s 0x22
0x20e3f  ldind.i4
0x20e40  ldc.i4.1
0x20e41  beq.s    loc_20E60
0x20e43  ldloca.s 0x22
0x20e45  ldind.i4
0x20e46  ldc.i4.2
0x20e47  beq.s    loc_20E60
0x20e49  ldc.i4.0
0x20e4a  ldstr    aUnknownGradien// "Unknown GradientSpreadMethod"
0x20e4f  call     void [System]System.Diagnostics.Debug::Assert(bool, string)
0x20e54  ldarg.0
0x20e55  call     void [mscorlib]System.GC::KeepAlive(object)
0x20e5a  ldc.i4   0x80004001
0x20e5f  ret
0x20e60  ldloca.s 0x24
0x20e62  call     instance float64 [WindowsBase]System.Windows.Rect::get_Left()
0x20e67  call     float64 [mscorlib]System.Math::Floor(float64)
0x20e6c  conv.i4
0x20e6d  stloc.s  7
0x20e6f  ldloca.s 0x24
0x20e71  call     instance float64 [WindowsBase]System.Windows.Rect::get_Right()
0x20e76  call     float64 [mscorlib]System.Math::Floor(float64)
0x20e7b  conv.i4
0x20e7c  stloc.s  6
0x20e7e  ldloc.s  6
0x20e80  ldloc.s  7
0x20e82  bge.s    loc_20EB3
0x20e84  ldc.i4.0
0x20e85  stloc.s  0x15
0x20e87  br.s     loc_20EB6
0x20e89  ldloca.s 0x24
0x20e8b  call     instance float64 [WindowsBase]System.Windows.Rect::get_Left()
0x20e90  ldc.r8   0.0
0x20e99  bge.un.s loc_20E9E
0x20e9b  ldc.i4.1
0x20e9c  stloc.s  0x10
0x20e9e  ldloca.s 0x24
0x20ea0  call     instance float64 [WindowsBase]System.Windows.Rect::get_Right()
0x20ea5  ldc.r8   1.0
0x20eae  ble.un.s loc_20EB3
0x20eb0  ldc.i4.1
0x20eb1  stloc.s  0xF
0x20eb3  ldc.i4.1
0x20eb4  stloc.s  0x15
0x20eb6  ldloc.s  0x15
0x20eb8  call     void [System]System.Diagnostics.Debug::Assert(bool)
0x20ebd  ldloc.1
0x20ebe  callvirt instance int32 [mscorlib]System.Collections.SortedList::get_Count()
0x20ec3  ldc.i4.1
0x20ec4  sub
0x20ec5  ldloc.s  6
0x20ec7  ldloc.s  7
0x20ec9  sub
0x20eca  ldc.i4.1
0x20ecb  add
0x20ecc  mul
0x20ecd  stloc.2
0x20ece  ldloc.2
0x20ecf  ldc.i4.0
0x20ed0  cgt
0x20ed2  stloc.s  0x1A
0x20ed4  ldloc.s  0x1A
0x20ed6  ldstr    a0GradientBands// "0 gradient bands in FillLinearGradient"
0x20edb  call     void [System]System.Diagnostics.Debug::Assert(bool, string)
0x20ee0  ldloc.s  0x10
0x20ee2  ldc.i4.0
0x20ee3  bne.un.s loc_20EE8
0x20ee5  ldc.i4.0
0x20ee6  br.s     loc_20EE9
0x20ee8  ldc.i4.1
0x20ee9  stloc.s  0x19
0x20eeb  ldloc.2
0x20eec  ldloc.s  0x19
0x20eee  add
0x20eef  stloc.2
0x20ef0  ldloc.s  0xF
0x20ef2  ldc.i4.0
0x20ef3  bne.un.s loc_20EF8
0x20ef5  ldc.i4.0
0x20ef6  br.s     loc_20EF9
0x20ef8  ldc.i4.1
0x20ef9  stloc.s  0x18
0x20efb  ldloc.2
0x20efc  ldloc.s  0x18
0x20efe  add
0x20eff  stloc.2
0x20f00  ldloc.2
0x20f01  ldc.i4.4
0x20f02  mul
0x20f03  stloc.s  0xE
0x20f05  ldloc.2
0x20f06  ldc.i4.2
0x20f07  mul
0x20f08  stloc.s  0x14
0x20f0a  ldloc.s  0x14
0x20f0c  ldc.i4.3
0x20f0d  mul
0x20f0e  stloc.s  0x13
0x20f10  ldarg.0
0x20f11  ldflda   valuetype [WindowsBase]System.Windows.Media.Matrix Microsoft.Internal.GDIExporter.CGDIRenderTarget::m_transform
0x20f16  ldobj    [WindowsBase]System.Windows.Media.Matrix
0x20f1b  call     bool Microsoft.Internal.GDIExporter.IsTranslateOrScale([hasfieldmarshal] valuetype [WindowsBase]System.Windows.Media.Matrix value)
0x20f20  brfalse  loc_20FA9
0x20f25  ldloc.0
0x20f26  ldloca.s 0x12
0x20f28  ldloca.s 0x11
0x20f2a  call     void Microsoft.Internal.GDIExporter.GetLinearGradientAxisAligned(class [PresentationCore]System.Windows.Media.LinearGradientBrush brush, [out] bool& isVertical, [out] bool& isHorizontal)
0x20f2f  ldloc.s  0x12
0x20f31  brtrue.s loc_20F37
0x20f33  ldloc.s  0x11
0x20f35  brfalse.s loc_20FA9
0x20f37  ldarg.1
0x20f38  ldnull
0x20f39  call     instance valuetype [WindowsBase]System.Windows.Rect Microsoft.Internal.GDIExporter.GeometryProxy::GetBounds(class [PresentationCore]System.Windows.Media.Pen pen)
0x20f3e  stloc.s  0x21
0x20f40  ldloca.s 0x21
0x20f42  ldarg.0
0x20f43  ldflda   valuetype [WindowsBase]System.Windows.Media.Matrix Microsoft.Internal.GDIExporter.CGDIRenderTarget::m_transform
0x20f48  ldobj    [WindowsBase]System.Windows.Media.Matrix
0x20f4d  call     instance void [WindowsBase]System.Windows.Rect::Transform(valuetype [WindowsBase]System.Windows.Media.Matrix)
0x20f52  ldloc.s  0x12
0x20f54  brfalse.s loc_20F62
0x20f56  ldloca.s 0x21
0x20f58  call     instance float64 [WindowsBase]System.Windows.Rect::get_Height()
0x20f5d  conv.i4
0x20f5e  stloc.s  0xD
0x20f60  br.s     loc_20F84
0x20f62  ldloc.s  0x11
0x20f64  brfalse.s loc_20F72
0x20f66  ldloca.s 0x21
0x20f68  call     instance float64 [WindowsBase]System.Windows.Rect::get_Width()
0x20f6d  conv.i4
0x20f6e  stloc.s  0xD
0x20f70  br.s     loc_20F84
0x20f72  ldloca.s 0x21
0x20f74  call     instance float64 [WindowsBase]System.Windows.Rect::get_Width()
0x20f79  ldloca.s 0x21
0x20f7b  call     instance float64 [WindowsBase]System.Windows.Rect::get_Height()
0x20f80  mul
0x20f81  conv.i4
0x20f82  stloc.s  0xD
0x20f84  ldloc.s  0xD
0x20f86  ldc.i4.4
0x20f87  mul
0x20f88  sizeof   TriVertex
0x20f8e  conv.u8
0x20f8f  ldloc.s  0xE
0x20f91  conv.i8
0x20f92  mul
0x20f93  ldloc.s  0x13
0x20f95  conv.i8
0x20f96  ldc.i4.4
0x20f97  conv.i8
0x20f98  mul
0x20f99  add
0x20f9a  conv.i4
0x20f9b  bge.s    loc_20FA9
0x20f9d  ldarg.0
0x20f9e  call     void [mscorlib]System.GC::KeepAlive(object)
0x20fa3  ldc.i4   0x80004001
0x20fa8  ret
0x20fa9  ldloc.s  0xE
0x20fab  newarr   TriVertex
0x20fb0  stloc.s  0xA
0x20fb2  ldloc.s  0x13
0x20fb4  newarr   [mscorlib]System.UInt32
0x20fb9  stloc.s  9
0x20fbb  ldc.i4.0
0x20fbc  stloc.s  0xC
0x20fbe  ldc.i4.0
0x20fbf  stloc.s  0x20
0x20fc1  ldloc.s  0x10
0x20fc3  brfalse.s loc_21012
0x20fc5  ldloc.1
0x20fc6  ldc.r8   0.0
0x20fcf  box      [mscorlib]System.Double
0x20fd4  callvirt instance object [mscorlib]System.Collections.SortedList::get_Item(object)
0x20fd9  unbox    [PresentationCore]System.Windows.Media.Color
0x20fde  ldobj    [PresentationCore]System.Windows.Media.Color
0x20fe3  stloc.s  0x1F
0x20fe5  ldloc.s  9
0x20fe7  ldloca.s 0x20
0x20fe9  ldloc.s  0xC
0x20feb  call     void Microsoft.Internal.GDIExporter.GenerateGradientBandTriangles(modopt([mscorlib]System.Runtime.CompilerServices.IsLong) unsigned int32[] indices, int32& indexOffset, int32 vertexOffset)
0x20ff0  ldloc.s  0xA
0x20ff2  ldloca.s 0xC
0x20ff4  ldloca.s 0x23
0x20ff6  ldloca.s 0x24
0x20ff8  call     instance float64 [WindowsBase]System.Windows.Rect::get_Left()
0x20ffd  ldloca.s 0x24
0x20fff  call     instance float64 [WindowsBase]System.Windows.Rect::get_Top()
0x21004  ldloca.s 0x24
0x21006  call     instance float64 [WindowsBase]System.Windows.Rect::get_Bottom()
0x2100b  ldloca.s 0x1F
0x2100d  call     void Microsoft.Internal.GDIExporter.GenerateGradientBandVertices(valuetype TriVertex[] vertices, int32& vertexOffset, valuetype [WindowsBase]System.Windows.Media.Matrix& transform, float64 x, float64 top, float64 bottom, valuetype [PresentationCore]System.Windows.Media.Color& color)
0x21012  ldloc.s  7
0x21014  stloc.s  5
0x21016  ldloc.s  7
0x21018  ldloc.s  6
0x2101a  bgt      loc_210EF
0x2101f  ldc.i4.0
0x21020  stloc.s  8
0x21022  ldloc.s  5
0x21024  ldc.i4.2
0x21025  rem
0x21026  brfalse.s loc_21038
0x21028  ldloc.0
0x21029  call     instance valuetype [PresentationCore]System.Windows.Media.GradientSpreadMethod [PresentationCore]System.Windows.Media.GradientBrush::get_SpreadMethod()
0x2102e  ldc.i4.1
0x2102f  beq.s    loc_21035
0x21031  ldloc.s  8
0x21033  br.s     loc_21036
0x21035  ldc.i4.1
0x21036  stloc.s  8
0x21038  ldc.i4.0
  ... truncated ...
```
