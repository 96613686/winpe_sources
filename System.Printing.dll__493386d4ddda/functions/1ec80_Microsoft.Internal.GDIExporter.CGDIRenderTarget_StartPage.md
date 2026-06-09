# Microsoft.Internal.GDIExporter.CGDIRenderTarget::StartPage

- ea: `0x1ec80`
- end: `0x1ecf2`
- name: `Microsoft.Internal.GDIExporter.CGDIRenderTarget::StartPage`
- size: `114`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1bc80`
- `0x1c9d0`
- `0x1cf70`
- `0x1ec80`
- `0x1ee40`
- `0x1f030`

## string_xrefs

- `0x1ec93`: `EndPage already called.`

## pseudocode

```c

```

## disassembly

```asm
0x1ec80  ldarg.0
0x1ec81  call     instance bool Microsoft.Internal.GDIExporter.CGDIDevice::get_HasDC()
0x1ec86  brfalse.s loc_1ECF1
0x1ec88  ldarg.0
0x1ec89  ldfld    bool Microsoft.Internal.GDIExporter.CGDIRenderTarget::m_startPage
0x1ec8e  ldc.i4.0
0x1ec8f  ceq
0x1ec91  stloc.1
0x1ec92  ldloc.1
0x1ec93  ldstr    aEndpageAlready// "EndPage already called."
0x1ec98  call     void [System]System.Diagnostics.Debug::Assert(bool, string)
0x1ec9d  ldarg.0
0x1ec9e  ldarg.1
0x1ec9f  call     instance modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 Microsoft.Internal.GDIExporter.CGDIDevice::HrStartPage(unsigned int8[] pDevmode)
0x1eca4  stloc.0
0x1eca5  ldarg.0
0x1eca6  ldloc.0
0x1eca7  call     instance void Microsoft.Internal.GDIExporter.CGDIRenderTarget::ThrowOnFailure(modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 hr)
0x1ecac  ldarg.0
0x1ecad  dup
0x1ecae  ldfld    class Microsoft.Internal.GDIExporter.GdiSafeDCHandle Microsoft.Internal.GDIExporter.CGDIDevice::m_hDC
0x1ecb3  ldc.i4.8
0x1ecb4  call     int32 Microsoft.Internal.GDIExporter.CNativeMethods::GetDeviceCaps(class Microsoft.Internal.GDIExporter.GdiSafeHandle hdc, int32 nIndex)
0x1ecb9  stfld    int32 Microsoft.Internal.GDIExporter.CGDIRenderTarget::m_nWidth
0x1ecbe  ldarg.0
0x1ecbf  dup
0x1ecc0  ldfld    class Microsoft.Internal.GDIExporter.GdiSafeDCHandle Microsoft.Internal.GDIExporter.CGDIDevice::m_hDC
0x1ecc5  ldc.i4.s 0xA
0x1ecc7  call     int32 Microsoft.Internal.GDIExporter.CNativeMethods::GetDeviceCaps(class Microsoft.Internal.GDIExporter.GdiSafeHandle hdc, int32 nIndex)
0x1eccc  stfld    int32 Microsoft.Internal.GDIExporter.CGDIRenderTarget::m_nHeight
0x1ecd1  ldarg.0
0x1ecd2  ldarg.2
0x1ecd3  conv.r8
0x1ecd4  stfld    float64 Microsoft.Internal.GDIExporter.CGDIDevice::m_RasterizationDPI
0x1ecd9  ldarg.0
0x1ecda  ldc.i4.1
0x1ecdb  stfld    bool Microsoft.Internal.GDIExporter.CGDIRenderTarget::m_startPage
0x1ece0  ldarg.0
0x1ece1  dup
0x1ece2  ldflda   valuetype [WindowsBase]System.Windows.Media.Matrix Microsoft.Internal.GDIExporter.CGDIRenderTarget::m_DeviceTransform
0x1ece7  ldobj    [WindowsBase]System.Windows.Media.Matrix
0x1ecec  callvirt instance void Microsoft.Internal.GDIExporter.CGDIRenderTarget::PushTransform(valuetype [WindowsBase]System.Windows.Media.Matrix transform)
0x1ecf1  ret
```
