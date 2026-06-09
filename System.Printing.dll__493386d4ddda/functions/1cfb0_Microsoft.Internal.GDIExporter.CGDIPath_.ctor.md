# Microsoft.Internal.GDIExporter.CGDIPath::.ctor

- ea: `0x1cfb0`
- end: `0x1d08c`
- name: `Microsoft.Internal.GDIExporter.CGDIPath::.ctor`
- size: `220`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1d090`
- `0x1d0a0`

## callees

- `0x1c0f0`
- `0x1c120`
- `0x1cfb0`
- `0x1d880`
- `0x1d920`
- `0x21890`
- `0x21900`
- `0x21910`
- `0x21920`
- `0x21930`
- `0x21940`

## pseudocode

```c

```

## disassembly

```asm
0x1cfb0  ldarg.0
0x1cfb1  call     instance void [mscorlib]System.Object::.ctor()
0x1cfb6  ldarg.3
0x1cfb7  brtrue.s loc_1CFC1
0x1cfb9  ldarg.s  4
0x1cfbb  brtrue.s loc_1CFC1
0x1cfbd  ldc.i4.0
0x1cfbe  stloc.2
0x1cfbf  br.s     loc_1CFC3
0x1cfc1  ldc.i4.1
0x1cfc2  stloc.2
0x1cfc3  ldloc.2
0x1cfc4  call     void [System]System.Diagnostics.Debug::Assert(bool)
0x1cfc9  ldarg.1
0x1cfca  call     instance valuetype [PresentationCore]System.Windows.Media.FillRule Microsoft.Internal.GDIExporter.GeometryProxy::GetFillRule()
0x1cfcf  ldc.i4.0
0x1cfd0  beq.s    loc_1CFD5
0x1cfd2  ldc.i4.2
0x1cfd3  br.s     loc_1CFD6
0x1cfd5  ldc.i4.1
0x1cfd6  stloc.s  4
0x1cfd8  ldarg.0
0x1cfd9  ldloc.s  4
0x1cfdb  stfld    int32 Microsoft.Internal.GDIExporter.CGDIPath::m_PathFillMode
0x1cfe0  ldarg.0
0x1cfe1  ldflda   valuetype [WindowsBase]System.Windows.Int32Rect Microsoft.Internal.GDIExporter.CGDIPath::m_DeviceBounds
0x1cfe6  ldc.i4.0
0x1cfe7  call     instance void [WindowsBase]System.Windows.Int32Rect::set_X(int32)
0x1cfec  ldarg.0
0x1cfed  ldflda   valuetype [WindowsBase]System.Windows.Int32Rect Microsoft.Internal.GDIExporter.CGDIPath::m_DeviceBounds
0x1cff2  ldc.i4.0
0x1cff3  call     instance void [WindowsBase]System.Windows.Int32Rect::set_Y(int32)
0x1cff8  ldarg.0
0x1cff9  ldflda   valuetype [WindowsBase]System.Windows.Int32Rect Microsoft.Internal.GDIExporter.CGDIPath::m_DeviceBounds
0x1cffe  ldc.i4.0
0x1cfff  call     instance void [WindowsBase]System.Windows.Int32Rect::set_Width(int32)
0x1d004  ldarg.0
0x1d005  ldflda   valuetype [WindowsBase]System.Windows.Int32Rect Microsoft.Internal.GDIExporter.CGDIPath::m_DeviceBounds
0x1d00a  ldc.i4.0
0x1d00b  call     instance void [WindowsBase]System.Windows.Int32Rect::set_Height(int32)
0x1d010  ldarg.0
0x1d011  ldc.i4.1
0x1d012  stfld    int32 Microsoft.Internal.GDIExporter.CGDIPath::m_ResolutionScale
0x1d017  ldarg.3
0x1d018  ldc.i4.0
0x1d019  ceq
0x1d01b  stloc.3
0x1d01c  ldarg.1
0x1d01d  ldarg.2
0x1d01e  ldloc.3
0x1d01f  call     class Microsoft.Internal.GDIExporter.GdiGeometryConverter Microsoft.Internal.GDIExporter.GdiGeometryConverter::Convert(modreq([mscorlib]System.Runtime.CompilerServices.IsImplicitlyDereferenced) class Microsoft.Internal.GDIExporter.GeometryProxy geometry, valuetype [WindowsBase]System.Windows.Media.Matrix geometryToWorldTransform, [hasfieldmarshal] bool stroking)
0x1d024  stloc.0
0x1d025  ldloc.0
0x1d026  brfalse.s loc_1D08B
0x1d028  ldarg.0
0x1d029  ldloc.0
0x1d02a  call     instance valuetype Microsoft.Internal.GDIExporter.PointI[] Microsoft.Internal.GDIExporter.GdiGeometryConverter::get_Points()
0x1d02f  stfld    valuetype Microsoft.Internal.GDIExporter.PointI[] Microsoft.Internal.GDIExporter.CGDIPath::m_Points
0x1d034  ldarg.0
0x1d035  ldloc.0
0x1d036  call     instance unsigned int8[] Microsoft.Internal.GDIExporter.GdiGeometryConverter::get_Types()
0x1d03b  stfld    unsigned int8[] Microsoft.Internal.GDIExporter.CGDIPath::m_Types
0x1d040  ldarg.0
0x1d041  ldarg.1
0x1d042  call     instance bool Microsoft.Internal.GDIExporter.GeometryProxy::MayHaveCurves()
0x1d047  stfld    bool Microsoft.Internal.GDIExporter.CGDIPath::m_HasCurve
0x1d04c  ldarg.0
0x1d04d  ldloc.0
0x1d04e  call     instance int32 Microsoft.Internal.GDIExporter.GdiGeometryConverter::get_ResolutionScale()
0x1d053  stfld    int32 Microsoft.Internal.GDIExporter.CGDIPath::m_ResolutionScale
0x1d058  ldloc.0
0x1d059  call     instance int32 Microsoft.Internal.GDIExporter.GdiGeometryConverter::get_PointCount()
0x1d05e  stloc.1
0x1d05f  ldloc.1
0x1d060  brtrue.s loc_1D06B
0x1d062  ldarg.0
0x1d063  ldc.i4.1
0x1d064  stfld    bool Microsoft.Internal.GDIExporter.CGDIPath::m_IsValid
0x1d069  br.s     loc_1D08B
0x1d06b  ldarg.0
0x1d06c  ldfld    bool Microsoft.Internal.GDIExporter.CGDIPath::m_HasCurve
0x1d071  brfalse.s loc_1D07D
0x1d073  ldarg.0
0x1d074  ldloc.1
0x1d075  ldarg.3
0x1d076  call     instance void Microsoft.Internal.GDIExporter.CGDIPath::ProcessCurve(int32 count, [hasfieldmarshal] bool ForFill)
0x1d07b  br.s     loc_1D08B
0x1d07d  ldarg.0
0x1d07e  ldloc.1
0x1d07f  ldarg.3
0x1d080  ldloc.0
0x1d081  call     instance int32 Microsoft.Internal.GDIExporter.GdiGeometryConverter::get_FigureCount()
0x1d086  call     instance void Microsoft.Internal.GDIExporter.CGDIPath::ProcessPolygon(int32 count, [hasfieldmarshal] bool ForFill, int32 figureCount)
0x1d08b  ret
```
