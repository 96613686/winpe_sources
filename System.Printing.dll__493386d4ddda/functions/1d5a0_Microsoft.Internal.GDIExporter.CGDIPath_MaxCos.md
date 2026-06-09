# Microsoft.Internal.GDIExporter.CGDIPath::MaxCos

- ea: `0x1d5a0`
- end: `0x1d7ac`
- name: `Microsoft.Internal.GDIExporter.CGDIPath::MaxCos`
- size: `524`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1cc10`

## callees

- `0x1d5a0`

## pseudocode

```c

```

## disassembly

```asm
0x1d5a0  ldc.r8   -1.0
0x1d5a9  stloc.s  0xA
0x1d5ab  ldarg.0
0x1d5ac  ldfld    int32 Microsoft.Internal.GDIExporter.CGDIPath::m_NumPoints
0x1d5b1  stloc.s  7
0x1d5b3  ldarg.0
0x1d5b4  ldfld    valuetype Microsoft.Internal.GDIExporter.PointI[] Microsoft.Internal.GDIExporter.CGDIPath::m_Points
0x1d5b9  stloc.s  6
0x1d5bb  ldarg.0
0x1d5bc  ldfld    unsigned int8[] Microsoft.Internal.GDIExporter.CGDIPath::m_Types
0x1d5c1  stloc.s  0x19
0x1d5c3  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<int32>::.ctor()
0x1d5c8  stloc.s  5
0x1d5ca  ldc.i4.m1
0x1d5cb  stloc.s  9
0x1d5cd  ldc.i4.0
0x1d5ce  stloc.3
0x1d5cf  ldc.i4.0
0x1d5d0  ldloc.s  7
0x1d5d2  bge.s    loc_1D61A
0x1d5d4  ldloc.s  0x19
0x1d5d6  ldloc.3
0x1d5d7  ldelem.u1
0x1d5d8  stloc.s  0x17
0x1d5da  ldloc.s  0x17
0x1d5dc  ldc.i4.6
0x1d5dd  and
0x1d5de  conv.u1
0x1d5df  ldc.i4.6
0x1d5e0  bne.un.s loc_1D5E7
0x1d5e2  ldloc.3
0x1d5e3  stloc.s  9
0x1d5e5  br.s     loc_1D611
0x1d5e7  ldloc.s  0x17
0x1d5e9  ldc.i4.1
0x1d5ea  and
0x1d5eb  conv.u1
0x1d5ec  brfalse.s loc_1D611
0x1d5ee  ldloc.s  9
0x1d5f0  ldc.i4.m1
0x1d5f1  bne.un.s loc_1D5F6
0x1d5f3  ldc.i4.0
0x1d5f4  br.s     loc_1D5F7
0x1d5f6  ldc.i4.1
0x1d5f7  stloc.s  0x18
0x1d5f9  ldloc.s  0x18
0x1d5fb  call     void [System]System.Diagnostics.Debug::Assert(bool)
0x1d600  ldloc.s  5
0x1d602  ldloc.s  9
0x1d604  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x1d609  ldloc.s  5
0x1d60b  ldloc.3
0x1d60c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x1d611  ldloc.3
0x1d612  ldc.i4.1
0x1d613  add
0x1d614  stloc.3
0x1d615  ldloc.3
0x1d616  ldloc.s  7
0x1d618  blt.s    loc_1D5D4
0x1d61a  ldc.i4.m1
0x1d61b  stloc.2
0x1d61c  ldc.i4.m1
0x1d61d  stloc.1
0x1d61e  ldc.i4.0
0x1d61f  ldloc.s  7
0x1d621  bge      loc_1D7A9
0x1d626  ldc.i4.1
0x1d627  stloc.0
0x1d628  ldc.i4.1
0x1d629  stloc.s  4
0x1d62b  ldloc.0
0x1d62c  ldc.i4.1
0x1d62d  sub
0x1d62e  ldloc.1
0x1d62f  ble.s    loc_1D658
0x1d631  ldloc.s  4
0x1d633  ldloc.s  5
0x1d635  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<int32>::get_Count()
0x1d63a  bge.s    loc_1D658
0x1d63c  ldloc.s  5
0x1d63e  ldloc.s  4
0x1d640  ldc.i4.1
0x1d641  sub
0x1d642  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<int32>::get_Item(!!T0)
0x1d647  stloc.2
0x1d648  ldloc.s  5
0x1d64a  ldloc.s  4
0x1d64c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<int32>::get_Item(!!T0)
0x1d651  stloc.1
0x1d652  ldloc.s  4
0x1d654  ldc.i4.2
0x1d655  add
0x1d656  stloc.s  4
0x1d658  ldloc.0
0x1d659  ldc.i4.2
0x1d65a  sub
0x1d65b  stloc.s  8
0x1d65d  ldloc.0
0x1d65e  stloc.s  0x16
0x1d660  ldloc.2
0x1d661  ldc.i4.m1
0x1d662  beq.s    loc_1D6C3
0x1d664  ldloc.1
0x1d665  ldc.i4.m1
0x1d666  beq.s    loc_1D6C3
0x1d668  ldloc.0
0x1d669  ldc.i4.2
0x1d66a  sub
0x1d66b  ldloc.2
0x1d66c  bge.s    loc_1D6BA
0x1d66e  ldloc.s  6
0x1d670  ldloc.2
0x1d671  ldelema  Microsoft.Internal.GDIExporter.PointI
0x1d676  ldobj    Microsoft.Internal.GDIExporter.PointI
0x1d67b  stloc.s  0x1E
0x1d67d  ldloc.s  6
0x1d67f  ldloc.1
0x1d680  ldelema  Microsoft.Internal.GDIExporter.PointI
0x1d685  ldobj    Microsoft.Internal.GDIExporter.PointI
0x1d68a  stloc.s  0x1D
0x1d68c  ldloc.1
0x1d68d  ldloc.2
0x1d68e  ble.s    loc_1D6B7
0x1d690  ldloca.s 0x1E
0x1d692  ldfld    int32 Microsoft.Internal.GDIExporter.PointI::x
0x1d697  ldloca.s 0x1D
0x1d699  ldfld    int32 Microsoft.Internal.GDIExporter.PointI::x
0x1d69e  bne.un.s loc_1D6B7
0x1d6a0  ldloca.s 0x1E
0x1d6a2  ldfld    int32 Microsoft.Internal.GDIExporter.PointI::y
0x1d6a7  ldloca.s 0x1D
0x1d6a9  ldfld    int32 Microsoft.Internal.GDIExporter.PointI::y
0x1d6ae  bne.un.s loc_1D6B7
0x1d6b0  ldloc.1
0x1d6b1  ldc.i4.1
0x1d6b2  sub
0x1d6b3  stloc.s  8
0x1d6b5  br.s     loc_1D6BA
0x1d6b7  ldloc.1
0x1d6b8  stloc.s  8
0x1d6ba  ldloc.0
0x1d6bb  ldloc.1
0x1d6bc  ble.s    loc_1D6D4
0x1d6be  ldloc.2
0x1d6bf  stloc.s  0x16
0x1d6c1  br.s     loc_1D6D4
0x1d6c3  ldloc.0
0x1d6c4  ldc.i4.2
0x1d6c5  sub
0x1d6c6  ldc.i4.0
0x1d6c7  blt      loc_1D79B
0x1d6cc  ldloc.0
0x1d6cd  ldloc.s  7
0x1d6cf  bge      loc_1D79B
0x1d6d4  ldloc.s  6
0x1d6d6  ldloc.s  8
0x1d6d8  ldelema  Microsoft.Internal.GDIExporter.PointI
0x1d6dd  ldobj    Microsoft.Internal.GDIExporter.PointI
0x1d6e2  stloc.s  0x1C
0x1d6e4  ldloc.s  6
0x1d6e6  ldloc.0
0x1d6e7  ldc.i4.1
0x1d6e8  sub
0x1d6e9  ldelema  Microsoft.Internal.GDIExporter.PointI
0x1d6ee  ldobj    Microsoft.Internal.GDIExporter.PointI
0x1d6f3  stloc.s  0x1B
0x1d6f5  ldloc.s  6
0x1d6f7  ldloc.s  0x16
0x1d6f9  ldelema  Microsoft.Internal.GDIExporter.PointI
0x1d6fe  ldobj    Microsoft.Internal.GDIExporter.PointI
0x1d703  stloc.s  0x1A
0x1d705  ldloca.s 0x1B
0x1d707  ldfld    int32 Microsoft.Internal.GDIExporter.PointI::x
0x1d70c  stloc.s  0x15
0x1d70e  ldloca.s 0x1C
0x1d710  ldfld    int32 Microsoft.Internal.GDIExporter.PointI::x
0x1d715  ldloc.s  0x15
0x1d717  sub
0x1d718  stloc.s  0x14
0x1d71a  ldloca.s 0x1B
0x1d71c  ldfld    int32 Microsoft.Internal.GDIExporter.PointI::y
0x1d721  stloc.s  0x13
0x1d723  ldloca.s 0x1C
0x1d725  ldfld    int32 Microsoft.Internal.GDIExporter.PointI::y
0x1d72a  ldloc.s  0x13
0x1d72c  sub
0x1d72d  stloc.s  0x12
0x1d72f  ldloca.s 0x1A
0x1d731  ldfld    int32 Microsoft.Internal.GDIExporter.PointI::x
0x1d736  ldloc.s  0x15
0x1d738  sub
0x1d739  stloc.s  0x11
0x1d73b  ldloca.s 0x1A
0x1d73d  ldfld    int32 Microsoft.Internal.GDIExporter.PointI::y
0x1d742  ldloc.s  0x13
0x1d744  sub
0x1d745  stloc.s  0x10
0x1d747  ldloc.s  0x14
0x1d749  brtrue.s loc_1D74F
0x1d74b  ldloc.s  0x12
0x1d74d  brfalse.s loc_1D79B
0x1d74f  ldloc.s  0x11
0x1d751  brtrue.s loc_1D757
0x1d753  ldloc.s  0x10
0x1d755  brfalse.s loc_1D79B
0x1d757  ldloc.s  0x10
0x1d759  conv.r8
0x1d75a  stloc.s  0xF
0x1d75c  ldloc.s  0x12
0x1d75e  conv.r8
0x1d75f  stloc.s  0xE
0x1d761  ldloc.s  0x11
0x1d763  conv.r8
0x1d764  stloc.s  0xD
0x1d766  ldloc.s  0x14
0x1d768  conv.r8
0x1d769  stloc.s  0xC
0x1d76b  ldloc.s  0xC
0x1d76d  ldloc.s  0xD
0x1d76f  mul
0x1d770  ldloc.s  0xE
0x1d772  ldloc.s  0xF
0x1d774  mul
0x1d775  add
0x1d776  ldloc.s  0xC
0x1d778  dup
0x1d779  mul
0x1d77a  ldloc.s  0xE
0x1d77c  dup
0x1d77d  mul
0x1d77e  add
0x1d77f  ldloc.s  0xD
0x1d781  dup
0x1d782  mul
0x1d783  ldloc.s  0xF
0x1d785  dup
0x1d786  mul
0x1d787  add
0x1d788  mul
0x1d789  call     float64 [mscorlib]System.Math::Sqrt(float64)
0x1d78e  div
0x1d78f  stloc.s  0xB
0x1d791  ldloc.s  0xB
0x1d793  ldloc.s  0xA
0x1d795  ble.un.s loc_1D79B
0x1d797  ldloc.s  0xB
0x1d799  stloc.s  0xA
0x1d79b  ldloc.0
0x1d79c  ldc.i4.1
0x1d79d  add
0x1d79e  stloc.0
0x1d79f  ldloc.0
0x1d7a0  ldc.i4.1
0x1d7a1  sub
0x1d7a2  ldloc.s  7
0x1d7a4  blt      loc_1D62B
0x1d7a9  ldloc.s  0xA
0x1d7ab  ret
```
