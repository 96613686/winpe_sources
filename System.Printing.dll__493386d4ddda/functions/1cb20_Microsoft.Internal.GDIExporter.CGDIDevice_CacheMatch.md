# Microsoft.Internal.GDIExporter.CGDIDevice::CacheMatch

- ea: `0x1cb20`
- end: `0x1cb5c`
- name: `Microsoft.Internal.GDIExporter.CGDIDevice::CacheMatch`
- size: `60`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1cc10`
- `0x1cdf0`
- `0x207b0`

## callees

- `0x1c270`
- `0x1cb20`

## pseudocode

```c

```

## disassembly

```asm
0x1cb20  ldarg.0
0x1cb21  ldfld    class Microsoft.Internal.GDIExporter.CachedGDIObject[] Microsoft.Internal.GDIExporter.CGDIDevice::m_Cache
0x1cb26  stloc.0
0x1cb27  ldloc.0
0x1cb28  brtrue.s loc_1CB2C
0x1cb2a  ldnull
0x1cb2b  ret
0x1cb2c  ldc.i4.0
0x1cb2d  stloc.1
0x1cb2e  ldc.i4.0
0x1cb2f  ldloc.0
0x1cb30  ldlen
0x1cb31  bge.s    loc_1CB5A
0x1cb33  ldloc.0
0x1cb34  ldloc.1
0x1cb35  ldelem.ref
0x1cb36  stloc.3
0x1cb37  ldloc.3
0x1cb38  brfalse.s loc_1CB46
0x1cb3a  ldloc.3
0x1cb3b  ldarg.1
0x1cb3c  ldarg.2
0x1cb3d  call     instance class Microsoft.Internal.GDIExporter.GdiSafeHandle Microsoft.Internal.GDIExporter.CachedGDIObject::Match(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsExplicitlyDereferenced) unsigned int8& pData, int32 size)
0x1cb42  stloc.2
0x1cb43  ldloc.2
0x1cb44  brtrue.s loc_1CB58
0x1cb46  ldloc.1
0x1cb47  ldc.i4.1
0x1cb48  add
0x1cb49  stloc.1
0x1cb4a  ldarg.0
0x1cb4b  ldfld    class Microsoft.Internal.GDIExporter.CachedGDIObject[] Microsoft.Internal.GDIExporter.CGDIDevice::m_Cache
0x1cb50  stloc.0
0x1cb51  ldloc.1
0x1cb52  ldloc.0
0x1cb53  ldlen
0x1cb54  bge.s    loc_1CB5A
0x1cb56  br.s     loc_1CB33
0x1cb58  ldloc.2
0x1cb59  ret
0x1cb5a  ldnull
0x1cb5b  ret
```
