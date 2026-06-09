# Microsoft.Internal.GDIExporter.GdiGeometryConverter::AddPoint

- ea: `0x21b90`
- end: `0x21ddc`
- name: `Microsoft.Internal.GDIExporter.GdiGeometryConverter::AddPoint`
- size: `588`
- prototype: ``
- caller_count: `9`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x219c0`
- `0x21a30`
- `0x21ac0`
- `0x21e80`
- `0x21f60`
- `0x22060`
- `0x220a0`
- `0x220d0`
- `0x22180`

## callees

- `0x21970`
- `0x21990`
- `0x21b20`
- `0x21b90`
- `0x21de0`

## string_xrefs

- `0x21dca`: `Invalid path input: NaN encountered`

## pseudocode

```c

```

## disassembly

```asm
0x21b90  ldarg.0
0x21b91  ldflda   valuetype [WindowsBase]System.Windows.Media.Matrix Microsoft.Internal.GDIExporter.GdiGeometryConverter::_transform
0x21b96  ldarg.1
0x21b97  call     instance valuetype [WindowsBase]System.Windows.Point [WindowsBase]System.Windows.Media.Matrix::Transform(valuetype [WindowsBase]System.Windows.Point)
0x21b9c  stloc.s  0xC
0x21b9e  ldloca.s 0xC
0x21ba0  call     instance float64 [WindowsBase]System.Windows.Point::get_X()
0x21ba5  call     bool [mscorlib]System.Double::IsNaN(float64)
0x21baa  brtrue   loc_21DC9
0x21baf  ldloca.s 0xC
0x21bb1  call     instance float64 [WindowsBase]System.Windows.Point::get_Y()
0x21bb6  call     bool [mscorlib]System.Double::IsNaN(float64)
0x21bbb  brtrue   loc_21DC9
0x21bc0  ldloca.s 0xB
0x21bc2  initobj  Microsoft.Internal.GDIExporter.PointI
0x21bc8  ldloca.s 0xB
0x21bca  ldloca.s 0xC
0x21bcc  call     instance float64 [WindowsBase]System.Windows.Point::get_X()
0x21bd1  call     float64 [mscorlib]System.Math::Round(float64)
0x21bd6  conv.i4
0x21bd7  stfld    int32 Microsoft.Internal.GDIExporter.PointI::x
0x21bdc  ldloca.s 0xC
0x21bde  call     instance float64 [WindowsBase]System.Windows.Point::get_Y()
0x21be3  call     float64 [mscorlib]System.Math::Round(float64)
0x21be8  conv.i4
0x21be9  stloc.s  9
0x21beb  ldloca.s 0xB
0x21bed  ldloc.s  9
0x21bef  stfld    int32 Microsoft.Internal.GDIExporter.PointI::y
0x21bf4  ldc.i4.0
0x21bf5  stloc.2
0x21bf6  ldc.i4.0
0x21bf7  stloc.1
0x21bf8  ldarg.0
0x21bf9  ldfld    int32 Microsoft.Internal.GDIExporter.GdiGeometryConverter::_pointCount
0x21bfe  stloc.0
0x21bff  ldloc.0
0x21c00  ldc.i4.0
0x21c01  ble.s    loc_21C36
0x21c03  ldarg.0
0x21c04  ldfld    valuetype Microsoft.Internal.GDIExporter.PointI[] Microsoft.Internal.GDIExporter.GdiGeometryConverter::_points
0x21c09  stloc.s  8
0x21c0b  ldloca.s 0xB
0x21c0d  ldfld    int32 Microsoft.Internal.GDIExporter.PointI::x
0x21c12  ldloc.s  8
0x21c14  ldloc.0
0x21c15  ldc.i4.1
0x21c16  sub
0x21c17  ldelema  Microsoft.Internal.GDIExporter.PointI
0x21c1c  ldfld    int32 Microsoft.Internal.GDIExporter.PointI::x
0x21c21  sub
0x21c22  stloc.2
0x21c23  ldloc.s  9
0x21c25  ldloc.s  8
0x21c27  ldloc.0
0x21c28  ldc.i4.1
0x21c29  sub
0x21c2a  ldelema  Microsoft.Internal.GDIExporter.PointI
0x21c2f  ldfld    int32 Microsoft.Internal.GDIExporter.PointI::y
0x21c34  sub
0x21c35  stloc.1
0x21c36  ldloc.0
0x21c37  ldc.i4.0
0x21c38  ble.s    loc_21C57
0x21c3a  ldarg.0
0x21c3b  ldfld    bool Microsoft.Internal.GDIExporter.GdiGeometryConverter::_stroking
0x21c40  brfalse.s loc_21C57
0x21c42  ldloc.2
0x21c43  brtrue.s loc_21C57
0x21c45  ldloc.1
0x21c46  brtrue.s loc_21C57
0x21c48  ldarg.2
0x21c49  ldc.i4.6
0x21c4a  and
0x21c4b  conv.u1
0x21c4c  ldc.i4.6
0x21c4d  beq.s    loc_21C57
0x21c4f  ldarg.0
0x21c50  call     instance void Microsoft.Internal.GDIExporter.GdiGeometryConverter::FailGeometry()
0x21c55  ldc.i4.m1
0x21c56  ret
0x21c57  ldarg.2
0x21c58  ldc.i4.6
0x21c59  and
0x21c5a  stloc.3
0x21c5b  ldloc.3
0x21c5c  ldc.i4.2
0x21c5d  beq      loc_21D32
0x21c62  ldloc.3
0x21c63  ldc.i4.4
0x21c64  beq.s    loc_21CA7
0x21c66  ldloc.3
0x21c67  ldc.i4.6
0x21c68  bne.un   loc_21D5F
0x21c6d  ldarg.0
0x21c6e  dup
0x21c6f  ldfld    int32 Microsoft.Internal.GDIExporter.GdiGeometryConverter::_figureCount
0x21c74  ldc.i4.1
0x21c75  add
0x21c76  stfld    int32 Microsoft.Internal.GDIExporter.GdiGeometryConverter::_figureCount
0x21c7b  ldarg.0
0x21c7c  ldc.i4.1
0x21c7d  stfld    bool Microsoft.Internal.GDIExporter.GdiGeometryConverter::_figureHasGaps
0x21c82  ldloc.0
0x21c83  ldc.i4.0
0x21c84  ble      loc_21D5F
0x21c89  ldarg.0
0x21c8a  ldfld    unsigned int8[] Microsoft.Internal.GDIExporter.GdiGeometryConverter::_types
0x21c8f  ldloc.0
0x21c90  ldc.i4.1
0x21c91  sub
0x21c92  ldelem.u1
0x21c93  ldc.i4.6
0x21c94  and
0x21c95  conv.u1
0x21c96  ldc.i4.6
0x21c97  bne.un   loc_21D5F
0x21c9c  ldarg.0
0x21c9d  call     instance void Microsoft.Internal.GDIExporter.GdiGeometryConverter::RemoveLastPoint()
0x21ca2  br       loc_21D5F
0x21ca7  ldarg.0
0x21ca8  ldfld    int32 Microsoft.Internal.GDIExporter.GdiGeometryConverter::_bezierIndex
0x21cad  ldc.i4.2
0x21cae  bne.un.s loc_21D20
0x21cb0  ldloc.0
0x21cb1  ldc.i4.3
0x21cb2  blt.s    loc_21D20
0x21cb4  ldarg.0
0x21cb5  ldfld    unsigned int8[] Microsoft.Internal.GDIExporter.GdiGeometryConverter::_types
0x21cba  stloc.s  7
0x21cbc  ldloc.s  7
0x21cbe  ldloc.0
0x21cbf  ldc.i4.1
0x21cc0  sub
0x21cc1  ldelem.u1
0x21cc2  ldc.i4.6
0x21cc3  and
0x21cc4  conv.u1
0x21cc5  ldc.i4.4
0x21cc6  bne.un.s loc_21CD9
0x21cc8  ldloc.s  7
0x21cca  ldloc.0
0x21ccb  ldc.i4.2
0x21ccc  sub
0x21ccd  ldelem.u1
0x21cce  ldc.i4.6
0x21ccf  and
0x21cd0  conv.u1
0x21cd1  ldc.i4.4
0x21cd2  bne.un.s loc_21CD9
0x21cd4  ldc.i4.1
0x21cd5  stloc.s  6
0x21cd7  br.s     loc_21CDC
0x21cd9  ldc.i4.0
0x21cda  stloc.s  6
0x21cdc  ldloc.s  6
0x21cde  call     void [System]System.Diagnostics.Debug::Assert(bool)
0x21ce3  ldarg.0
0x21ce4  ldfld    int32 Microsoft.Internal.GDIExporter.GdiGeometryConverter::_pointCount
0x21ce9  stloc.0
0x21cea  ldarg.0
0x21ceb  ldloc.2
0x21cec  ldloc.1
0x21ced  ldloc.0
0x21cee  ldc.i4.2
0x21cef  sub
0x21cf0  ldloc.0
0x21cf1  ldc.i4.1
0x21cf2  sub
0x21cf3  call     instance bool Microsoft.Internal.GDIExporter.GdiGeometryConverter::Colinear([hasfieldmarshal] int32 value, int32 dx, int32 dy, int32 p1)
0x21cf8  brfalse.s loc_21D20
0x21cfa  ldarg.0
0x21cfb  ldfld    int32 Microsoft.Internal.GDIExporter.GdiGeometryConverter::_pointCount
0x21d00  stloc.0
0x21d01  ldarg.0
0x21d02  ldloc.2
0x21d03  ldloc.1
0x21d04  ldloc.0
0x21d05  ldc.i4.3
0x21d06  sub
0x21d07  ldloc.0
0x21d08  ldc.i4.1
0x21d09  sub
0x21d0a  call     instance bool Microsoft.Internal.GDIExporter.GdiGeometryConverter::Colinear([hasfieldmarshal] int32 value, int32 dx, int32 dy, int32 p1)
0x21d0f  brfalse.s loc_21D20
0x21d11  ldarg.0
0x21d12  call     instance void Microsoft.Internal.GDIExporter.GdiGeometryConverter::RemoveLastPoint()
0x21d17  ldarg.0
0x21d18  call     instance void Microsoft.Internal.GDIExporter.GdiGeometryConverter::RemoveLastPoint()
0x21d1d  ldc.i4.2
0x21d1e  starg.s  2
0x21d20  ldarg.0
0x21d21  dup
0x21d22  ldfld    int32 Microsoft.Internal.GDIExporter.GdiGeometryConverter::_bezierIndex
0x21d27  ldc.i4.1
0x21d28  add
0x21d29  ldc.i4.3
0x21d2a  rem
0x21d2b  stfld    int32 Microsoft.Internal.GDIExporter.GdiGeometryConverter::_bezierIndex
0x21d30  br.s     loc_21D5F
0x21d32  ldloc.0
0x21d33  ldc.i4.2
0x21d34  blt.s    loc_21D5F
0x21d36  ldloc.0
0x21d37  ldc.i4.1
0x21d38  sub
0x21d39  stloc.s  5
0x21d3b  ldarg.0
0x21d3c  ldfld    unsigned int8[] Microsoft.Internal.GDIExporter.GdiGeometryConverter::_types
0x21d41  ldloc.s  5
0x21d43  ldelem.u1
0x21d44  ldc.i4.6
0x21d45  and
0x21d46  conv.u1
0x21d47  ldc.i4.2
0x21d48  bne.un.s loc_21D5F
0x21d4a  ldarg.0
0x21d4b  ldloc.2
0x21d4c  ldloc.1
0x21d4d  ldloc.0
0x21d4e  ldc.i4.2
0x21d4f  sub
0x21d50  ldloc.s  5
0x21d52  call     instance bool Microsoft.Internal.GDIExporter.GdiGeometryConverter::Colinear([hasfieldmarshal] int32 value, int32 dx, int32 dy, int32 p1)
0x21d57  brfalse.s loc_21D5F
0x21d59  ldarg.0
0x21d5a  call     instance void Microsoft.Internal.GDIExporter.GdiGeometryConverter::RemoveLastPoint()
0x21d5f  ldarg.0
0x21d60  ldfld    int32 Microsoft.Internal.GDIExporter.GdiGeometryConverter::_pointCount
0x21d65  ldarg.0
0x21d66  ldfld    valuetype Microsoft.Internal.GDIExporter.PointI[] Microsoft.Internal.GDIExporter.GdiGeometryConverter::_points
0x21d6b  ldlen
0x21d6c  ble.s    loc_21D71
0x21d6e  ldc.i4.0
0x21d6f  br.s     loc_21D72
0x21d71  ldc.i4.1
0x21d72  stloc.s  0xA
0x21d74  ldloc.s  0xA
0x21d76  ldstr    aPointCountEsti// "Point count estimation too small"
0x21d7b  call     void [System]System.Diagnostics.Debug::Assert(bool, string)
0x21d80  ldarg.0
0x21d81  ldarg.1
0x21d82  stfld    valuetype [WindowsBase]System.Windows.Point Microsoft.Internal.GDIExporter.GdiGeometryConverter::_lastPoint
0x21d87  ldarg.0
0x21d88  ldfld    valuetype Microsoft.Internal.GDIExporter.PointI[] Microsoft.Internal.GDIExporter.GdiGeometryConverter::_points
0x21d8d  ldarg.0
0x21d8e  ldfld    int32 Microsoft.Internal.GDIExporter.GdiGeometryConverter::_pointCount
0x21d93  ldelema  Microsoft.Internal.GDIExporter.PointI
0x21d98  ldloca.s 0xB
0x21d9a  cpobj    Microsoft.Internal.GDIExporter.PointI
0x21d9f  ldarg.0
0x21da0  ldfld    unsigned int8[] Microsoft.Internal.GDIExporter.GdiGeometryConverter::_types
0x21da5  ldarg.0
0x21da6  ldfld    int32 Microsoft.Internal.GDIExporter.GdiGeometryConverter::_pointCount
0x21dab  ldelema  [mscorlib]System.Byte
0x21db0  ldarg.2
0x21db1  stind.i1
0x21db2  ldarg.0
0x21db3  ldfld    int32 Microsoft.Internal.GDIExporter.GdiGeometryConverter::_pointCount
0x21db8  ldc.i4.1
0x21db9  add
0x21dba  stloc.s  4
0x21dbc  ldarg.0
0x21dbd  ldloc.s  4
0x21dbf  stfld    int32 Microsoft.Internal.GDIExporter.GdiGeometryConverter::_pointCount
0x21dc4  ldloc.s  4
0x21dc6  ldc.i4.1
0x21dc7  sub
0x21dc8  ret
0x21dc9  ldc.i4.0
0x21dca  ldstr    aInvalidPathInp// "Invalid path input: NaN encountered"
0x21dcf  call     void [System]System.Diagnostics.Debug::Assert(bool, string)
0x21dd4  ldarg.0
0x21dd5  call     instance void Microsoft.Internal.GDIExporter.GdiGeometryConverter::ForceGeometryEmpty()
0x21dda  ldc.i4.m1
0x21ddb  ret
```
