# Microsoft.Internal.GDIExporter.CGDIDevice::BeginPath

- ea: `0x1c7d0`
- end: `0x1c7e7`
- name: `Microsoft.Internal.GDIExporter.CGDIDevice::BeginPath`
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
- `0x1bbe0`

## pseudocode

```c

```

## disassembly

```asm
0x1c7d0  ldarg.0
0x1c7d1  ldfld    class Microsoft.Internal.GDIExporter.GdiSafeDCHandle Microsoft.Internal.GDIExporter.CGDIDevice::m_hDC
0x1c7d6  call     int32 Microsoft.Internal.GDIExporter.CNativeMethods::BeginPath(class Microsoft.Internal.GDIExporter.GdiSafeDCHandle hdc)
0x1c7db  call     modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 Microsoft.Internal.GDIExporter.ErrorCode(int32 rslt)
0x1c7e0  ldarg.0
0x1c7e1  call     void [mscorlib]System.GC::KeepAlive(object)
0x1c7e6  ret
```
