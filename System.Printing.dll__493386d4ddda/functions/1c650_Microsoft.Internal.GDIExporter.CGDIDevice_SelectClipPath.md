# Microsoft.Internal.GDIExporter.CGDIDevice::SelectClipPath

- ea: `0x1c650`
- end: `0x1c65d`
- name: `Microsoft.Internal.GDIExporter.CGDIDevice::SelectClipPath`
- size: `13`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1d4b0`

## callees

- `0x1bcc0`

## pseudocode

```c

```

## disassembly

```asm
0x1c650  ldarg.0
0x1c651  ldfld    class Microsoft.Internal.GDIExporter.GdiSafeDCHandle Microsoft.Internal.GDIExporter.CGDIDevice::m_hDC
0x1c656  ldarg.1
0x1c657  call     int32 Microsoft.Internal.GDIExporter.CNativeMethods::SelectClipPath(class Microsoft.Internal.GDIExporter.GdiSafeHandle hdc, int32 iMode)
0x1c65c  ret
```
