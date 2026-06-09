# Microsoft.Internal.GDIExporter.CGDIDevice::ConvertBrush

- ea: `0x1cdf0`
- end: `0x1ce39`
- name: `Microsoft.Internal.GDIExporter.CGDIDevice::ConvertBrush`
- size: `73`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1c830`
- `0x1ce40`

## callees

- `0x1bd50`
- `0x1cb20`
- `0x1cb60`
- `0x1cdf0`

## string_xrefs

- `0x1ce2d`: `CreateSolidBrush failed`

## pseudocode

```c

```

## disassembly

```asm
0x1cdf0  ldarg.1
0x1cdf1  ldc.i4   0xFFFFFF
0x1cdf6  bne.un.s loc_1CDFF
0x1cdf8  ldarg.0
0x1cdf9  ldfld    class Microsoft.Internal.GDIExporter.GdiSafeHandle Microsoft.Internal.GDIExporter.CGDIDevice::m_whiteBrush
0x1cdfe  ret
0x1cdff  ldarg.1
0x1ce00  brtrue.s loc_1CE09
0x1ce02  ldarg.0
0x1ce03  ldfld    class Microsoft.Internal.GDIExporter.GdiSafeHandle Microsoft.Internal.GDIExporter.CGDIDevice::m_blackBrush
0x1ce08  ret
0x1ce09  ldarg.0
0x1ce0a  ldarga.s 1
0x1ce0c  ldc.i4.4
0x1ce0d  call     instance class Microsoft.Internal.GDIExporter.GdiSafeHandle Microsoft.Internal.GDIExporter.CGDIDevice::CacheMatch(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsExplicitlyDereferenced) unsigned int8& pData, int32 size)
0x1ce12  stloc.0
0x1ce13  ldloc.0
0x1ce14  brtrue.s loc_1CE37
0x1ce16  ldarg.1
0x1ce17  call     class Microsoft.Internal.GDIExporter.GdiSafeHandle Microsoft.Internal.GDIExporter.CNativeMethods::CreateSolidBrush(modopt([mscorlib]System.Runtime.CompilerServices.IsLong) unsigned int32 crColor)
0x1ce1c  stloc.0
0x1ce1d  ldloc.0
0x1ce1e  brfalse.s loc_1CE2C
0x1ce20  ldarg.0
0x1ce21  ldarga.s 1
0x1ce23  ldc.i4.4
0x1ce24  ldloc.0
0x1ce25  call     instance void Microsoft.Internal.GDIExporter.CGDIDevice::CacheObject(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsExplicitlyDereferenced) unsigned int8& pData, int32 size, class Microsoft.Internal.GDIExporter.GdiSafeHandle handle)
0x1ce2a  br.s     loc_1CE37
0x1ce2c  ldc.i4.0
0x1ce2d  ldstr    aCreatesolidbru// "CreateSolidBrush failed"
0x1ce32  call     void [System]System.Diagnostics.Debug::Assert(bool, string)
0x1ce37  ldloc.0
0x1ce38  ret
```
