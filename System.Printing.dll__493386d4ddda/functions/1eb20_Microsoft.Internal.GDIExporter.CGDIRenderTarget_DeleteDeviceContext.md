# Microsoft.Internal.GDIExporter.CGDIRenderTarget::DeleteDeviceContext

- ea: `0x1eb20`
- end: `0x1eb42`
- name: `Microsoft.Internal.GDIExporter.CGDIRenderTarget::DeleteDeviceContext`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1cf70`
- `0x1eb20`

## pseudocode

```c

```

## disassembly

```asm
0x1eb20  ldarg.0
0x1eb21  call     instance bool Microsoft.Internal.GDIExporter.CGDIDevice::get_HasDC()
0x1eb26  brfalse.s loc_1EB3A
0x1eb28  ldarg.0
0x1eb29  ldfld    class Microsoft.Internal.GDIExporter.GdiSafeDCHandle Microsoft.Internal.GDIExporter.CGDIDevice::m_hDC
0x1eb2e  call     instance void [mscorlib]System.Runtime.InteropServices.SafeHandle::Close()
0x1eb33  ldarg.0
0x1eb34  ldnull
0x1eb35  stfld    class Microsoft.Internal.GDIExporter.GdiSafeDCHandle Microsoft.Internal.GDIExporter.CGDIDevice::m_hDC
0x1eb3a  ldarg.0
0x1eb3b  ldnull
0x1eb3c  stfld    class Microsoft.Internal.GDIExporter.GdiSafeDCHandle Microsoft.Internal.GDIExporter.CGDIDevice::m_hDC
0x1eb41  ret
```
