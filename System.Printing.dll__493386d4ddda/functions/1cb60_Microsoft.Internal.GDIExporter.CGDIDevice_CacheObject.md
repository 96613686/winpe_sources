# Microsoft.Internal.GDIExporter.CGDIDevice::CacheObject

- ea: `0x1cb60`
- end: `0x1cc01`
- name: `Microsoft.Internal.GDIExporter.CGDIDevice::CacheObject`
- size: `161`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1cc10`
- `0x1cdf0`
- `0x207b0`

## callees

- `0x1c210`
- `0x1c220`
- `0x1cb60`

## pseudocode

```c

```

## disassembly

```asm
0x1cb60  ldarg.0
0x1cb61  ldfld    class Microsoft.Internal.GDIExporter.CachedGDIObject[] Microsoft.Internal.GDIExporter.CGDIDevice::m_Cache
0x1cb66  stloc.0
0x1cb67  ldloc.0
0x1cb68  brfalse  loc_1CC00
0x1cb6d  ldloc.0
0x1cb6e  ldarg.0
0x1cb6f  ldfld    int32 Microsoft.Internal.GDIExporter.CGDIDevice::m_CacheFirst
0x1cb74  ldelem.ref
0x1cb75  brfalse.s loc_1CBD5
0x1cb77  ldloc.0
0x1cb78  ldarg.0
0x1cb79  ldfld    int32 Microsoft.Internal.GDIExporter.CGDIDevice::m_CacheFirst
0x1cb7e  ldelem.ref
0x1cb7f  call     instance class Microsoft.Internal.GDIExporter.GdiSafeHandle Microsoft.Internal.GDIExporter.CachedGDIObject::get_Handle()
0x1cb84  stloc.1
0x1cb85  ldloc.1
0x1cb86  ldarg.0
0x1cb87  ldfld    class Microsoft.Internal.GDIExporter.GdiSafeHandle Microsoft.Internal.GDIExporter.CGDIDevice::m_lastFont
0x1cb8c  beq.s    loc_1CBA0
0x1cb8e  ldloc.1
0x1cb8f  ldarg.0
0x1cb90  ldfld    class Microsoft.Internal.GDIExporter.GdiSafeHandle Microsoft.Internal.GDIExporter.CGDIDevice::m_lastBrush
0x1cb95  beq.s    loc_1CBA0
0x1cb97  ldloc.1
0x1cb98  ldarg.0
0x1cb99  ldfld    class Microsoft.Internal.GDIExporter.GdiSafeHandle Microsoft.Internal.GDIExporter.CGDIDevice::m_lastPen
0x1cb9e  bne.un.s loc_1CBC1
0x1cba0  ldarg.0
0x1cba1  ldfld    class Microsoft.Internal.GDIExporter.CachedGDIObject[] Microsoft.Internal.GDIExporter.CGDIDevice::m_Cache
0x1cba6  stloc.0
0x1cba7  ldarg.0
0x1cba8  ldfld    int32 Microsoft.Internal.GDIExporter.CGDIDevice::m_CacheFirst
0x1cbad  ldc.i4.1
0x1cbae  add
0x1cbaf  ldloc.0
0x1cbb0  ldlen
0x1cbb1  rem
0x1cbb2  stloc.2
0x1cbb3  ldarg.0
0x1cbb4  ldloc.2
0x1cbb5  stfld    int32 Microsoft.Internal.GDIExporter.CGDIDevice::m_CacheFirst
0x1cbba  ldloc.0
0x1cbbb  ldloc.2
0x1cbbc  ldelem.ref
0x1cbbd  brfalse.s loc_1CBD5
0x1cbbf  br.s     loc_1CB77
0x1cbc1  ldloc.1
0x1cbc2  call     instance void [mscorlib]System.Runtime.InteropServices.SafeHandle::Close()
0x1cbc7  ldarg.0
0x1cbc8  ldfld    class Microsoft.Internal.GDIExporter.CachedGDIObject[] Microsoft.Internal.GDIExporter.CGDIDevice::m_Cache
0x1cbcd  ldarg.0
0x1cbce  ldfld    int32 Microsoft.Internal.GDIExporter.CGDIDevice::m_CacheFirst
0x1cbd3  ldnull
0x1cbd4  stelem.ref
0x1cbd5  ldarg.0
0x1cbd6  ldfld    class Microsoft.Internal.GDIExporter.CachedGDIObject[] Microsoft.Internal.GDIExporter.CGDIDevice::m_Cache
0x1cbdb  ldarg.0
0x1cbdc  ldfld    int32 Microsoft.Internal.GDIExporter.CGDIDevice::m_CacheFirst
0x1cbe1  ldarg.1
0x1cbe2  ldarg.2
0x1cbe3  ldarg.3
0x1cbe4  newobj   instance void Microsoft.Internal.GDIExporter.CachedGDIObject::.ctor(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsExplicitlyDereferenced) unsigned int8& pData, int32 size, class Microsoft.Internal.GDIExporter.GdiSafeHandle handle)
0x1cbe9  stelem.ref
0x1cbea  ldarg.0
0x1cbeb  dup
0x1cbec  ldfld    int32 Microsoft.Internal.GDIExporter.CGDIDevice::m_CacheFirst
0x1cbf1  ldc.i4.1
0x1cbf2  add
0x1cbf3  ldarg.0
0x1cbf4  ldfld    class Microsoft.Internal.GDIExporter.CachedGDIObject[] Microsoft.Internal.GDIExporter.CGDIDevice::m_Cache
0x1cbf9  ldlen
0x1cbfa  rem
0x1cbfb  stfld    int32 Microsoft.Internal.GDIExporter.CGDIDevice::m_CacheFirst
0x1cc00  ret
```
