# Microsoft.Internal.GDIExporter.CGDIDevice::EndPath

- ea: `0x1c7f0`
- end: `0x1c807`
- name: `Microsoft.Internal.GDIExporter.CGDIDevice::EndPath`
- size: `23`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1d0b0`
- `0x1d4b0`

## callees

- `0x240`
- `0x1bbf0`

## pseudocode

```c

```

## disassembly

```asm
0x1c7f0  ldarg.0
0x1c7f1  ldfld    class Microsoft.Internal.GDIExporter.GdiSafeDCHandle Microsoft.Internal.GDIExporter.CGDIDevice::m_hDC
0x1c7f6  call     int32 Microsoft.Internal.GDIExporter.CNativeMethods::EndPath(class Microsoft.Internal.GDIExporter.GdiSafeDCHandle hdc)
0x1c7fb  call     modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 Microsoft.Internal.GDIExporter.ErrorCode(int32 rslt)
0x1c800  ldarg.0
0x1c801  call     void [mscorlib]System.GC::KeepAlive(object)
0x1c806  ret
```
