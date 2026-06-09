# Microsoft.Internal.GDIExporter.CachedGDIObject::.ctor

- ea: `0x1c220`
- end: `0x1c261`
- name: `Microsoft.Internal.GDIExporter.CachedGDIObject::.ctor`
- size: `65`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1cb60`

## callees

- `0x1c220`

## pseudocode

```c

```

## disassembly

```asm
0x1c220  ldarg.0
0x1c221  call     instance void [mscorlib]System.Object::.ctor()
0x1c226  ldarg.0
0x1c227  ldarg.2
0x1c228  newarr   [mscorlib]System.Byte
0x1c22d  stfld    unsigned int8[] Microsoft.Internal.GDIExporter.CachedGDIObject::m_RawData
0x1c232  ldc.i4.0
0x1c233  stloc.0
0x1c234  ldc.i4.0
0x1c235  ldarg.2
0x1c236  bge.s    loc_1C259
0x1c238  ldc.i4.0
0x1c239  conv.i8
0x1c23a  stloc.1
0x1c23b  ldarg.0
0x1c23c  ldfld    unsigned int8[] Microsoft.Internal.GDIExporter.CachedGDIObject::m_RawData
0x1c241  ldloc.0
0x1c242  ldelema  [mscorlib]System.Byte
0x1c247  ldloc.1
0x1c248  ldarg.1
0x1c249  add
0x1c24a  ldind.u1
0x1c24b  stind.i1
0x1c24c  ldloc.0
0x1c24d  ldc.i4.1
0x1c24e  add
0x1c24f  stloc.0
0x1c250  ldloc.1
0x1c251  ldc.i4.1
0x1c252  conv.i8
0x1c253  add
0x1c254  stloc.1
0x1c255  ldloc.0
0x1c256  ldarg.2
0x1c257  blt.s    loc_1C23B
0x1c259  ldarg.0
0x1c25a  ldarg.3
0x1c25b  stfld    class Microsoft.Internal.GDIExporter.GdiSafeHandle Microsoft.Internal.GDIExporter.CachedGDIObject::m_handle
0x1c260  ret
```
