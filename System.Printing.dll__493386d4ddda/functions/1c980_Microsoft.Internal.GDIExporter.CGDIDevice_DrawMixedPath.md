# Microsoft.Internal.GDIExporter.CGDIDevice::DrawMixedPath

- ea: `0x1c980`
- end: `0x1c9aa`
- name: `Microsoft.Internal.GDIExporter.CGDIDevice::DrawMixedPath`
- size: `42`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1d0b0`
- `0x1d230`
- `0x1d4b0`

## callees

- `0x240`
- `0x1bcb0`

## pseudocode

```c

```

## disassembly

```asm
0x1c980  ldarg.1
0x1c981  ldc.i4.0
0x1c982  ldelema  Microsoft.Internal.GDIExporter.PointI
0x1c987  stloc.1
0x1c988  ldarg.2
0x1c989  ldc.i4.0
0x1c98a  ldelema  [mscorlib]System.Byte
0x1c98f  stloc.0
0x1c990  ldarg.0
0x1c991  ldfld    class Microsoft.Internal.GDIExporter.GdiSafeDCHandle Microsoft.Internal.GDIExporter.CGDIDevice::m_hDC
0x1c996  ldloc.1
0x1c997  ldloc.0
0x1c998  ldarg.3
0x1c999  call     int32 Microsoft.Internal.GDIExporter.CNativeMethods::PolyDraw(class Microsoft.Internal.GDIExporter.GdiSafeDCHandle hdc, modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype Microsoft.Internal.GDIExporter.PointI* ppt, modopt([mscorlib]System.Runtime.CompilerServices.IsConst) unsigned int8* pbTypes, int32 cCount)
0x1c99e  call     modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 Microsoft.Internal.GDIExporter.ErrorCode(int32 rslt)
0x1c9a3  ldarg.0
0x1c9a4  call     void [mscorlib]System.GC::KeepAlive(object)
0x1c9a9  ret
```
