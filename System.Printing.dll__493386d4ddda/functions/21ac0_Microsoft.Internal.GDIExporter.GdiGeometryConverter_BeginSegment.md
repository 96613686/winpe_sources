# Microsoft.Internal.GDIExporter.GdiGeometryConverter::BeginSegment

- ea: `0x21ac0`
- end: `0x21b1d`
- name: `Microsoft.Internal.GDIExporter.GdiGeometryConverter::BeginSegment`
- size: `93`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x22060`
- `0x22080`
- `0x220a0`
- `0x220d0`
- `0x22120`
- `0x22180`
- `0x221d0`

## callees

- `0x21970`
- `0x21ac0`
- `0x21b90`

## string_xrefs

- `0x21ae3`: `Non-multiple of 3 PT_BEZIER points added during previous segment`

## pseudocode

```c

```

## disassembly

```asm
0x21ac0  ldarg.0
0x21ac1  ldfld    bool Microsoft.Internal.GDIExporter.GdiGeometryConverter::_isValid
0x21ac6  brfalse.s loc_21B1B
0x21ac8  ldarg.0
0x21ac9  ldfld    bool Microsoft.Internal.GDIExporter.GdiGeometryConverter::_forceEmpty
0x21ace  brtrue.s loc_21B1B
0x21ad0  ldarg.0
0x21ad1  ldfld    bool Microsoft.Internal.GDIExporter.GdiGeometryConverter::_figureVisible
0x21ad6  brfalse.s loc_21B1B
0x21ad8  ldarg.0
0x21ad9  ldfld    int32 Microsoft.Internal.GDIExporter.GdiGeometryConverter::_bezierIndex
0x21ade  ldc.i4.0
0x21adf  ceq
0x21ae1  stloc.2
0x21ae2  ldloc.2
0x21ae3  ldstr    aNonMultipleOf3// "Non-multiple of 3 PT_BEZIER points adde"...
0x21ae8  call     void [System]System.Diagnostics.Debug::Assert(bool, string)
0x21aed  ldc.i4.0
0x21aee  stloc.0
0x21aef  ldarg.0
0x21af0  ldfld    bool Microsoft.Internal.GDIExporter.GdiGeometryConverter::_stroking
0x21af5  stloc.1
0x21af6  ldloc.1
0x21af7  brfalse.s loc_21B04
0x21af9  ldarg.2
0x21afa  brfalse.s loc_21B04
0x21afc  ldarg.0
0x21afd  call     instance void Microsoft.Internal.GDIExporter.GdiGeometryConverter::FailGeometry()
0x21b02  br.s     loc_21B19
0x21b04  ldloc.1
0x21b05  brfalse.s loc_21B17
0x21b07  ldarg.1
0x21b08  brtrue.s loc_21B17
0x21b0a  ldc.i4.0
0x21b0b  stloc.0
0x21b0c  ldarg.0
0x21b0d  ldarg.3
0x21b0e  ldc.i4.6
0x21b0f  call     instance int32 Microsoft.Internal.GDIExporter.GdiGeometryConverter::AddPoint(valuetype [WindowsBase]System.Windows.Point point, unsigned int8 type)
0x21b14  pop
0x21b15  br.s     loc_21B19
0x21b17  ldc.i4.1
0x21b18  stloc.0
0x21b19  ldloc.0
0x21b1a  ret
0x21b1b  ldc.i4.0
0x21b1c  ret
```
