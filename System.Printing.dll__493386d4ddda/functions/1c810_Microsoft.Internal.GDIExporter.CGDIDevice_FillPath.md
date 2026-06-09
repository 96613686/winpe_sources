# Microsoft.Internal.GDIExporter.CGDIDevice::FillPath

- ea: `0x1c810`
- end: `0x1c827`
- name: `Microsoft.Internal.GDIExporter.CGDIDevice::FillPath`
- size: `23`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1d0b0`

## callees

- `0x240`
- `0x1bc00`

## pseudocode

```c

```

## disassembly

```asm
0x1c810  ldarg.0
0x1c811  ldfld    class Microsoft.Internal.GDIExporter.GdiSafeDCHandle Microsoft.Internal.GDIExporter.CGDIDevice::m_hDC
0x1c816  call     int32 Microsoft.Internal.GDIExporter.CNativeMethods::FillPath(class Microsoft.Internal.GDIExporter.GdiSafeDCHandle hdc)
0x1c81b  call     modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 Microsoft.Internal.GDIExporter.ErrorCode(int32 rslt)
0x1c820  ldarg.0
0x1c821  call     void [mscorlib]System.GC::KeepAlive(object)
0x1c826  ret
```
