# Microsoft.Internal.GDIExporter.CGDIRenderTarget::CreateDeviceContext

- ea: `0x1eac0`
- end: `0x1eb20`
- name: `Microsoft.Internal.GDIExporter.CGDIRenderTarget::CreateDeviceContext`
- size: `96`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1bb30`
- `0x1cf70`
- `0x1eac0`
- `0x1f030`
- `0x1f080`

## string_xrefs

- `0x1eacb`: `HDC already created.`

## pseudocode

```c

```

## disassembly

```asm
0x1eac0  ldarg.0
0x1eac1  call     instance bool Microsoft.Internal.GDIExporter.CGDIDevice::get_HasDC()
0x1eac6  ldc.i4.0
0x1eac7  ceq
0x1eac9  stloc.1
0x1eaca  ldloc.1
0x1eacb  ldstr    aHdcAlreadyCrea// "HDC already created."
0x1ead0  call     void [System]System.Diagnostics.Debug::Assert(bool, string)
0x1ead5  ldarg.1
0x1ead6  ldnull
0x1ead7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1eadc  brfalse.s loc_1EAE9
0x1eade  ldstr    aPrintername_0// "printerName"
0x1eae3  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1eae8  throw
0x1eae9  ldarg.0
0x1eaea  ldarg.3
0x1eaeb  stfld    unsigned int8[] Microsoft.Internal.GDIExporter.CGDIDevice::m_lastDevmode
0x1eaf0  ldarg.0
0x1eaf1  ldnull
0x1eaf2  ldarg.1
0x1eaf3  ldnull
0x1eaf4  ldarg.3
0x1eaf5  call     class Microsoft.Internal.GDIExporter.GdiSafeDCHandle Microsoft.Internal.GDIExporter.CNativeMethods::CreateDCW([hasfieldmarshal] modopt([mscorlib]System.Runtime.CompilerServices.IsConst) string pDriver, [hasfieldmarshal] modopt([mscorlib]System.Runtime.CompilerServices.IsConst) string pDevice, [hasfieldmarshal] modopt([mscorlib]System.Runtime.CompilerServices.IsConst) string pPort, [hasfieldmarshal] unsigned int8[] devmode)
0x1eafa  stfld    class Microsoft.Internal.GDIExporter.GdiSafeDCHandle Microsoft.Internal.GDIExporter.CGDIDevice::m_hDC
0x1eaff  ldarg.0
0x1eb00  call     instance bool Microsoft.Internal.GDIExporter.CGDIDevice::get_HasDC()
0x1eb05  brtrue.s loc_1EB11
0x1eb07  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetHRForLastWin32Error()
0x1eb0c  stloc.0
0x1eb0d  ldloc.0
0x1eb0e  ldc.i4.0
0x1eb0f  blt.s    loc_1EB18
0x1eb11  ldarg.0
0x1eb12  call     instance modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 Microsoft.Internal.GDIExporter.CGDIRenderTarget::Initialize()
0x1eb17  stloc.0
0x1eb18  ldarg.0
0x1eb19  ldloc.0
0x1eb1a  call     instance void Microsoft.Internal.GDIExporter.CGDIRenderTarget::ThrowOnFailure(modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 hr)
0x1eb1f  ret
```
