# Microsoft.Internal.GDIExporter.CGDIPath::ProcessCurve

- ea: `0x1d880`
- end: `0x1d918`
- name: `Microsoft.Internal.GDIExporter.CGDIPath::ProcessCurve`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1cfb0`

## callees

- `0x1d7b0`
- `0x1d880`

## pseudocode

```c

```

## disassembly

```asm
0x1d880  ldarg.0
0x1d881  dup
0x1d882  ldfld    valuetype Microsoft.Internal.GDIExporter.PointI[] Microsoft.Internal.GDIExporter.CGDIPath::m_Points
0x1d887  ldarg.1
0x1d888  call     instance void Microsoft.Internal.GDIExporter.CGDIPath::GetDeviceBounds(valuetype Microsoft.Internal.GDIExporter.PointI[] p, int32 count)
0x1d88d  ldarg.0
0x1d88e  ldarg.1
0x1d88f  stfld    int32 Microsoft.Internal.GDIExporter.CGDIPath::m_NumPoints
0x1d894  ldc.i4.1
0x1d895  stloc.1
0x1d896  ldc.i4.1
0x1d897  ldarg.1
0x1d898  bge.s    loc_1D8B2
0x1d89a  ldarg.0
0x1d89b  ldfld    unsigned int8[] Microsoft.Internal.GDIExporter.CGDIPath::m_Types
0x1d8a0  stloc.3
0x1d8a1  ldloc.3
0x1d8a2  ldloc.1
0x1d8a3  ldelem.u1
0x1d8a4  ldc.i4.6
0x1d8a5  and
0x1d8a6  conv.u1
0x1d8a7  ldc.i4.4
0x1d8a8  bne.un.s loc_1D910
0x1d8aa  ldloc.1
0x1d8ab  ldc.i4.1
0x1d8ac  add
0x1d8ad  stloc.1
0x1d8ae  ldloc.1
0x1d8af  ldarg.1
0x1d8b0  blt.s    loc_1D8A1
0x1d8b2  ldarg.2
0x1d8b3  brtrue.s loc_1D901
0x1d8b5  ldarg.1
0x1d8b6  ldc.i4.1
0x1d8b7  sub
0x1d8b8  stloc.2
0x1d8b9  ldarg.0
0x1d8ba  ldfld    unsigned int8[] Microsoft.Internal.GDIExporter.CGDIPath::m_Types
0x1d8bf  ldloc.2
0x1d8c0  ldelem.u1
0x1d8c1  ldc.i4.1
0x1d8c2  and
0x1d8c3  conv.u1
0x1d8c4  brfalse.s loc_1D901
0x1d8c6  ldarg.0
0x1d8c7  ldfld    valuetype Microsoft.Internal.GDIExporter.PointI[] Microsoft.Internal.GDIExporter.CGDIPath::m_Points
0x1d8cc  stloc.0
0x1d8cd  ldloc.0
0x1d8ce  ldc.i4.0
0x1d8cf  ldelema  Microsoft.Internal.GDIExporter.PointI
0x1d8d4  ldfld    int32 Microsoft.Internal.GDIExporter.PointI::x
0x1d8d9  ldloc.0
0x1d8da  ldloc.2
0x1d8db  ldelema  Microsoft.Internal.GDIExporter.PointI
0x1d8e0  ldfld    int32 Microsoft.Internal.GDIExporter.PointI::x
0x1d8e5  bne.un.s loc_1D910
0x1d8e7  ldloc.0
0x1d8e8  ldc.i4.0
0x1d8e9  ldelema  Microsoft.Internal.GDIExporter.PointI
0x1d8ee  ldfld    int32 Microsoft.Internal.GDIExporter.PointI::y
0x1d8f3  ldloc.0
0x1d8f4  ldloc.2
0x1d8f5  ldelema  Microsoft.Internal.GDIExporter.PointI
0x1d8fa  ldfld    int32 Microsoft.Internal.GDIExporter.PointI::y
0x1d8ff  bne.un.s loc_1D910
0x1d901  ldarg.0
0x1d902  dup
0x1d903  ldfld    modopt([mscorlib]System.Runtime.CompilerServices.IsLong) unsigned int32 Microsoft.Internal.GDIExporter.CGDIPath::m_Flags
0x1d908  ldc.i4.s 0x10
0x1d90a  or
0x1d90b  stfld    modopt([mscorlib]System.Runtime.CompilerServices.IsLong) unsigned int32 Microsoft.Internal.GDIExporter.CGDIPath::m_Flags
0x1d910  ldarg.0
0x1d911  ldc.i4.1
0x1d912  stfld    bool Microsoft.Internal.GDIExporter.CGDIPath::m_IsValid
0x1d917  ret
```
