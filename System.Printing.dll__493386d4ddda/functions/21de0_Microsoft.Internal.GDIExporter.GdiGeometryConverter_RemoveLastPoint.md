# Microsoft.Internal.GDIExporter.GdiGeometryConverter::RemoveLastPoint

- ea: `0x21de0`
- end: `0x21e3d`
- name: `Microsoft.Internal.GDIExporter.GdiGeometryConverter::RemoveLastPoint`
- size: `93`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x21a30`
- `0x21b90`

## callees

- `0x21de0`

## pseudocode

```c

```

## disassembly

```asm
0x21de0  ldarg.0
0x21de1  ldfld    int32 Microsoft.Internal.GDIExporter.GdiGeometryConverter::_pointCount
0x21de6  ldc.i4.0
0x21de7  cgt
0x21de9  stloc.2
0x21dea  ldloc.2
0x21deb  call     void [System]System.Diagnostics.Debug::Assert(bool)
0x21df0  ldarg.0
0x21df1  ldfld    int32 Microsoft.Internal.GDIExporter.GdiGeometryConverter::_pointCount
0x21df6  ldc.i4.1
0x21df7  sub
0x21df8  stloc.0
0x21df9  ldarg.0
0x21dfa  ldfld    unsigned int8[] Microsoft.Internal.GDIExporter.GdiGeometryConverter::_types
0x21dff  ldloc.0
0x21e00  ldelem.u1
0x21e01  ldc.i4.6
0x21e02  and
0x21e03  conv.u1
0x21e04  ldc.i4.6
0x21e05  bne.un.s loc_21E15
0x21e07  ldarg.0
0x21e08  dup
0x21e09  ldfld    int32 Microsoft.Internal.GDIExporter.GdiGeometryConverter::_figureCount
0x21e0e  ldc.i4.1
0x21e0f  sub
0x21e10  stfld    int32 Microsoft.Internal.GDIExporter.GdiGeometryConverter::_figureCount
0x21e15  ldarg.0
0x21e16  ldloc.0
0x21e17  stfld    int32 Microsoft.Internal.GDIExporter.GdiGeometryConverter::_pointCount
0x21e1c  ldloca.s 1
0x21e1e  ldc.r8   NaN
0x21e27  ldc.r8   NaN
0x21e30  call     instance void [WindowsBase]System.Windows.Point::.ctor(float64, float64)
0x21e35  ldarg.0
0x21e36  ldloc.1
0x21e37  stfld    valuetype [WindowsBase]System.Windows.Point Microsoft.Internal.GDIExporter.GdiGeometryConverter::_lastPoint
0x21e3c  ret
```
