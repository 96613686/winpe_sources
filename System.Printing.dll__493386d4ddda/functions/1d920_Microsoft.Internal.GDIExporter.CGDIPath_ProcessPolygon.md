# Microsoft.Internal.GDIExporter.CGDIPath::ProcessPolygon

- ea: `0x1d920`
- end: `0x1dac6`
- name: `Microsoft.Internal.GDIExporter.CGDIPath::ProcessPolygon`
- size: `422`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1cfb0`

## callees

- `0x1d7b0`
- `0x1d920`

## pseudocode

```c

```

## disassembly

```asm
0x1d920  ldarg.0
0x1d921  dup
0x1d922  ldfld    modopt([mscorlib]System.Runtime.CompilerServices.IsLong) unsigned int32 Microsoft.Internal.GDIExporter.CGDIPath::m_Flags
0x1d927  ldc.i4.1
0x1d928  or
0x1d929  stfld    modopt([mscorlib]System.Runtime.CompilerServices.IsLong) unsigned int32 Microsoft.Internal.GDIExporter.CGDIPath::m_Flags
0x1d92e  ldarg.0
0x1d92f  ldfld    unsigned int8[] Microsoft.Internal.GDIExporter.CGDIPath::m_Types
0x1d934  stloc.s  5
0x1d936  ldarg.3
0x1d937  ldc.i4.1
0x1d938  bne.un   loc_1D9B7
0x1d93d  ldc.i4.1
0x1d93e  stloc.2
0x1d93f  ldc.i4.1
0x1d940  ldarg.1
0x1d941  bge.s    loc_1D955
0x1d943  ldloc.s  5
0x1d945  ldloc.2
0x1d946  ldelem.u1
0x1d947  ldc.i4.6
0x1d948  and
0x1d949  conv.u1
0x1d94a  ldc.i4.2
0x1d94b  bne.un.s loc_1D9B7
0x1d94d  ldloc.2
0x1d94e  ldc.i4.1
0x1d94f  add
0x1d950  stloc.2
0x1d951  ldloc.2
0x1d952  ldarg.1
0x1d953  blt.s    loc_1D943
0x1d955  ldarg.0
0x1d956  dup
0x1d957  ldfld    valuetype Microsoft.Internal.GDIExporter.PointI[] Microsoft.Internal.GDIExporter.CGDIPath::m_Points
0x1d95c  ldarg.1
0x1d95d  call     instance void Microsoft.Internal.GDIExporter.CGDIPath::GetDeviceBounds(valuetype Microsoft.Internal.GDIExporter.PointI[] p, int32 count)
0x1d962  ldarg.0
0x1d963  ldarg.1
0x1d964  stfld    int32 Microsoft.Internal.GDIExporter.CGDIPath::m_NumPoints
0x1d969  ldarg.0
0x1d96a  ldc.i4.1
0x1d96b  stfld    int32 Microsoft.Internal.GDIExporter.CGDIPath::m_NumPolygons
0x1d970  ldc.i4.1
0x1d971  newarr   [mscorlib]System.UInt32
0x1d976  stloc.s  8
0x1d978  ldarg.0
0x1d979  ldloc.s  8
0x1d97b  stfld    unsigned int32[] Microsoft.Internal.GDIExporter.CGDIPath::m_PolyCounts
0x1d980  ldloc.s  8
0x1d982  ldc.i4.0
0x1d983  ldarg.1
0x1d984  stelem.i4
0x1d985  ldarg.2
0x1d986  brtrue.s loc_1D99C
0x1d988  ldarg.0
0x1d989  ldfld    unsigned int8[] Microsoft.Internal.GDIExporter.CGDIPath::m_Types
0x1d98e  ldarg.0
0x1d98f  ldfld    int32 Microsoft.Internal.GDIExporter.CGDIPath::m_NumPoints
0x1d994  ldc.i4.1
0x1d995  sub
0x1d996  ldelem.u1
0x1d997  ldc.i4.1
0x1d998  and
0x1d999  conv.u1
0x1d99a  brfalse.s loc_1D9AB
0x1d99c  ldarg.0
0x1d99d  dup
0x1d99e  ldfld    modopt([mscorlib]System.Runtime.CompilerServices.IsLong) unsigned int32 Microsoft.Internal.GDIExporter.CGDIPath::m_Flags
0x1d9a3  ldc.i4.s 0x20
0x1d9a5  or
0x1d9a6  stfld    modopt([mscorlib]System.Runtime.CompilerServices.IsLong) unsigned int32 Microsoft.Internal.GDIExporter.CGDIPath::m_Flags
0x1d9ab  ldarg.0
0x1d9ac  ldc.i4.1
0x1d9ad  stfld    bool Microsoft.Internal.GDIExporter.CGDIPath::m_IsValid
0x1d9b2  br       loc_1DAC5
0x1d9b7  ldarg.0
0x1d9b8  ldarg.3
0x1d9b9  newarr   [mscorlib]System.UInt32
0x1d9be  stfld    unsigned int32[] Microsoft.Internal.GDIExporter.CGDIPath::m_PolyCounts
0x1d9c3  ldc.i4.s 0xF8
0x1d9c5  stloc.s  4
0x1d9c7  ldc.i4.0
0x1d9c8  stloc.3
0x1d9c9  ldc.i4.m1
0x1d9ca  stloc.1
0x1d9cb  ldc.i4.0
0x1d9cc  stloc.0
0x1d9cd  ldc.i4.0
0x1d9ce  ldarg.1
0x1d9cf  bge      loc_1DA5F
0x1d9d4  ldloc.s  5
0x1d9d6  ldloc.0
0x1d9d7  ldelem.u1
0x1d9d8  ldc.i4.6
0x1d9d9  and
0x1d9da  stloc.s  7
0x1d9dc  ldloc.s  7
0x1d9de  ldc.i4.2
0x1d9df  beq.s    loc_1DA4E
0x1d9e1  ldloc.s  7
0x1d9e3  ldc.i4.6
0x1d9e4  beq.s    loc_1D9EE
0x1d9e6  ldc.i4.0
0x1d9e7  call     void [System]System.Diagnostics.Debug::Assert(bool)
0x1d9ec  br.s     loc_1DA4E
0x1d9ee  ldloc.s  4
0x1d9f0  ldc.i4.6
0x1d9f1  and
0x1d9f2  ldc.i4.6
0x1d9f3  beq.s    loc_1DA4C
0x1d9f5  ldloc.1
0x1d9f6  ldc.i4.0
0x1d9f7  blt.s    loc_1DA48
0x1d9f9  ldarg.2
0x1d9fa  brtrue.s loc_1DA13
0x1d9fc  ldloc.s  4
0x1d9fe  ldc.i4.1
0x1d9ff  and
0x1da00  brtrue.s loc_1DA13
0x1da02  ldarg.0
0x1da03  dup
0x1da04  ldfld    modopt([mscorlib]System.Runtime.CompilerServices.IsLong) unsigned int32 Microsoft.Internal.GDIExporter.CGDIPath::m_Flags
0x1da09  ldc.i4.s 0x40
0x1da0b  or
0x1da0c  stfld    modopt([mscorlib]System.Runtime.CompilerServices.IsLong) unsigned int32 Microsoft.Internal.GDIExporter.CGDIPath::m_Flags
0x1da11  br.s     loc_1DA22
0x1da13  ldarg.0
0x1da14  dup
0x1da15  ldfld    modopt([mscorlib]System.Runtime.CompilerServices.IsLong) unsigned int32 Microsoft.Internal.GDIExporter.CGDIPath::m_Flags
0x1da1a  ldc.i4.s 0x20
0x1da1c  or
0x1da1d  stfld    modopt([mscorlib]System.Runtime.CompilerServices.IsLong) unsigned int32 Microsoft.Internal.GDIExporter.CGDIPath::m_Flags
0x1da22  ldloc.0
0x1da23  ldloc.3
0x1da24  sub
0x1da25  stloc.s  6
0x1da27  ldloc.s  6
0x1da29  ldc.i4.2
0x1da2a  bge.s    loc_1DA2F
0x1da2c  ldc.i4.0
0x1da2d  br.s     loc_1DA30
0x1da2f  ldc.i4.1
0x1da30  stloc.s  9
0x1da32  ldloc.s  9
0x1da34  call     void [System]System.Diagnostics.Debug::Assert(bool)
0x1da39  ldarg.0
0x1da3a  ldfld    unsigned int32[] Microsoft.Internal.GDIExporter.CGDIPath::m_PolyCounts
0x1da3f  ldloc.1
0x1da40  ldelema  [mscorlib]System.UInt32
0x1da45  ldloc.s  6
0x1da47  stind.i4
0x1da48  ldloc.1
0x1da49  ldc.i4.1
0x1da4a  add
0x1da4b  stloc.1
0x1da4c  ldloc.0
0x1da4d  stloc.3
0x1da4e  ldloc.s  5
0x1da50  ldloc.0
0x1da51  ldelem.u1
0x1da52  stloc.s  4
0x1da54  ldloc.0
0x1da55  ldc.i4.1
0x1da56  add
0x1da57  stloc.0
0x1da58  ldloc.0
0x1da59  ldarg.1
0x1da5a  blt      loc_1D9D4
0x1da5f  ldarg.2
0x1da60  brtrue.s loc_1DA82
0x1da62  ldarg.0
0x1da63  ldfld    unsigned int8[] Microsoft.Internal.GDIExporter.CGDIPath::m_Types
0x1da68  ldarg.1
0x1da69  ldc.i4.1
0x1da6a  sub
0x1da6b  ldelem.u1
0x1da6c  ldc.i4.1
0x1da6d  and
0x1da6e  conv.u1
0x1da6f  brtrue.s loc_1DA82
0x1da71  ldarg.0
0x1da72  dup
0x1da73  ldfld    modopt([mscorlib]System.Runtime.CompilerServices.IsLong) unsigned int32 Microsoft.Internal.GDIExporter.CGDIPath::m_Flags
0x1da78  ldc.i4.s 0x40
0x1da7a  or
0x1da7b  stfld    modopt([mscorlib]System.Runtime.CompilerServices.IsLong) unsigned int32 Microsoft.Internal.GDIExporter.CGDIPath::m_Flags
0x1da80  br.s     loc_1DA91
0x1da82  ldarg.0
0x1da83  dup
0x1da84  ldfld    modopt([mscorlib]System.Runtime.CompilerServices.IsLong) unsigned int32 Microsoft.Internal.GDIExporter.CGDIPath::m_Flags
0x1da89  ldc.i4.s 0x20
0x1da8b  or
0x1da8c  stfld    modopt([mscorlib]System.Runtime.CompilerServices.IsLong) unsigned int32 Microsoft.Internal.GDIExporter.CGDIPath::m_Flags
0x1da91  ldarg.0
0x1da92  ldfld    unsigned int32[] Microsoft.Internal.GDIExporter.CGDIPath::m_PolyCounts
0x1da97  ldloc.1
0x1da98  ldelema  [mscorlib]System.UInt32
0x1da9d  ldarg.1
0x1da9e  ldloc.3
0x1da9f  sub
0x1daa0  stind.i4
0x1daa1  ldarg.0
0x1daa2  ldloc.1
0x1daa3  ldc.i4.1
0x1daa4  add
0x1daa5  stfld    int32 Microsoft.Internal.GDIExporter.CGDIPath::m_NumPolygons
0x1daaa  ldarg.0
0x1daab  dup
0x1daac  ldfld    valuetype Microsoft.Internal.GDIExporter.PointI[] Microsoft.Internal.GDIExporter.CGDIPath::m_Points
0x1dab1  ldarg.1
0x1dab2  call     instance void Microsoft.Internal.GDIExporter.CGDIPath::GetDeviceBounds(valuetype Microsoft.Internal.GDIExporter.PointI[] p, int32 count)
0x1dab7  ldarg.0
0x1dab8  ldarg.1
0x1dab9  stfld    int32 Microsoft.Internal.GDIExporter.CGDIPath::m_NumPoints
0x1dabe  ldarg.0
0x1dabf  ldc.i4.1
0x1dac0  stfld    bool Microsoft.Internal.GDIExporter.CGDIPath::m_IsValid
0x1dac5  ret
```
