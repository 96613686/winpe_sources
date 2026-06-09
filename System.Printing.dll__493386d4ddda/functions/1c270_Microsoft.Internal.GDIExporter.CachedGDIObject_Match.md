# Microsoft.Internal.GDIExporter.CachedGDIObject::Match

- ea: `0x1c270`
- end: `0x1c2a8`
- name: `Microsoft.Internal.GDIExporter.CachedGDIObject::Match`
- size: `56`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1cb20`

## callees

- `0x1c270`

## pseudocode

```c

```

## disassembly

```asm
0x1c270  ldarg.0
0x1c271  ldfld    unsigned int8[] Microsoft.Internal.GDIExporter.CachedGDIObject::m_RawData
0x1c276  stloc.2
0x1c277  ldarg.2
0x1c278  ldloc.2
0x1c279  ldlen
0x1c27a  beq.s    loc_1C27E
0x1c27c  ldnull
0x1c27d  ret
0x1c27e  ldc.i4.0
0x1c27f  stloc.0
0x1c280  ldc.i4.0
0x1c281  ldarg.2
0x1c282  bge.s    loc_1C2A1
0x1c284  ldc.i4.0
0x1c285  conv.i8
0x1c286  stloc.1
0x1c287  ldloc.2
0x1c288  ldloc.0
0x1c289  ldelem.u1
0x1c28a  ldloc.1
0x1c28b  ldarg.1
0x1c28c  add
0x1c28d  ldind.u1
0x1c28e  bne.un.s loc_1C29F
0x1c290  ldloc.0
0x1c291  ldc.i4.1
0x1c292  add
0x1c293  stloc.0
0x1c294  ldloc.1
0x1c295  ldc.i4.1
0x1c296  conv.i8
0x1c297  add
0x1c298  stloc.1
0x1c299  ldloc.0
0x1c29a  ldarg.2
0x1c29b  blt.s    loc_1C287
0x1c29d  br.s     loc_1C2A1
0x1c29f  ldnull
0x1c2a0  ret
0x1c2a1  ldarg.0
0x1c2a2  ldfld    class Microsoft.Internal.GDIExporter.GdiSafeHandle Microsoft.Internal.GDIExporter.CachedGDIObject::m_handle
0x1c2a7  ret
```
