# Microsoft.Internal.GDIExporter.CGDIRenderTarget::StartDocument

- ea: `0x1e8b0`
- end: `0x1ea0f`
- name: `Microsoft.Internal.GDIExporter.CGDIRenderTarget::StartDocument`
- size: `351`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x240`
- `0x1bad0`
- `0x1bb30`
- `0x1bba0`
- `0x1be70`
- `0x1cf70`
- `0x1e8b0`
- `0x1f030`
- `0x1f080`

## string_xrefs

- `0x1e8bf`: `HDC already created.`

## pseudocode

```c

```

## disassembly

```asm
0x1e8b0  ldnull
0x1e8b1  stloc.3
0x1e8b2  ldarg.0
0x1e8b3  call     instance bool Microsoft.Internal.GDIExporter.CGDIDevice::get_HasDC()
0x1e8b8  ldc.i4.0
0x1e8b9  ceq
0x1e8bb  stloc.s  8
0x1e8bd  ldloc.s  8
0x1e8bf  ldstr    aHdcAlreadyCrea// "HDC already created."
0x1e8c4  call     void [System]System.Diagnostics.Debug::Assert(bool, string)
0x1e8c9  ldarg.1
0x1e8ca  ldnull
0x1e8cb  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1e8d0  brfalse.s loc_1E8DD
0x1e8d2  ldstr    aPrintername_0// "printerName"
0x1e8d7  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1e8dc  throw
0x1e8dd  ldsfld   class [mscorlib]System.Collections.ArrayList Microsoft.Internal.GDIExporter.CGDIDevice::s_oldPrivateFonts
0x1e8e2  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x1e8e7  brfalse  loc_1E96C
0x1e8ec  ldsfld   object Microsoft.Internal.GDIExporter.CGDIDevice::s_lockObject
0x1e8f1  call     void [mscorlib]System.Threading.Monitor::Enter(object)
0x1e8f6  ldc.r8   10.0
0x1e8ff  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMinutes(float64)
0x1e904  stloc.s  7
0x1e906  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x1e90b  ldloc.s  7
0x1e90d  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x1e912  stloc.s  6
0x1e914  ldc.i4.0
0x1e915  stloc.2
0x1e916  ldloc.2
0x1e917  ldsfld   class [mscorlib]System.Collections.ArrayList Microsoft.Internal.GDIExporter.CGDIDevice::s_oldPrivateFonts
0x1e91c  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x1e921  bge.s    loc_1E95F
0x1e923  ldsfld   class [mscorlib]System.Collections.ArrayList Microsoft.Internal.GDIExporter.CGDIDevice::s_oldPrivateFonts
0x1e928  ldloc.2
0x1e929  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x1e92e  isinst   Microsoft.Internal.GDIExporter.GdiFontResourceSafeHandle
0x1e933  stloc.3
0x1e934  ldloc.3
0x1e935  brfalse.s loc_1E959
0x1e937  ldloc.3
0x1e938  call     instance valuetype [mscorlib]System.DateTime Microsoft.Internal.GDIExporter.GdiFontResourceSafeHandle::get_TimeStamp()
0x1e93d  ldloc.s  6
0x1e93f  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x1e944  brfalse.s loc_1E959
0x1e946  ldloc.3
0x1e947  call     instance void [mscorlib]System.Runtime.InteropServices.SafeHandle::Close()
0x1e94c  ldsfld   class [mscorlib]System.Collections.ArrayList Microsoft.Internal.GDIExporter.CGDIDevice::s_oldPrivateFonts
0x1e951  ldloc.2
0x1e952  callvirt instance void [mscorlib]System.Collections.ArrayList::RemoveAt(int32)
0x1e957  br.s     loc_1E916
0x1e959  ldloc.2
0x1e95a  ldc.i4.1
0x1e95b  add
0x1e95c  stloc.2
0x1e95d  br.s     loc_1E916
0x1e95f  leave.s  loc_1E96C
0x1e961  ldsfld   object Microsoft.Internal.GDIExporter.CGDIDevice::s_lockObject
0x1e966  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x1e96b  endfinally
0x1e96c  ldc.i4.0
0x1e96d  stloc.s  4
0x1e96f  ldarg.0
0x1e970  ldarg.s  4
0x1e972  stfld    unsigned int8[] Microsoft.Internal.GDIExporter.CGDIDevice::m_lastDevmode
0x1e977  ldarg.0
0x1e978  ldnull
0x1e979  ldarg.1
0x1e97a  ldnull
0x1e97b  ldarg.s  4
0x1e97d  call     class Microsoft.Internal.GDIExporter.GdiSafeDCHandle Microsoft.Internal.GDIExporter.CNativeMethods::CreateDCW([hasfieldmarshal] modopt([mscorlib]System.Runtime.CompilerServices.IsConst) string pDriver, [hasfieldmarshal] modopt([mscorlib]System.Runtime.CompilerServices.IsConst) string pDevice, [hasfieldmarshal] modopt([mscorlib]System.Runtime.CompilerServices.IsConst) string pPort, [hasfieldmarshal] unsigned int8[] devmode)
0x1e982  stfld    class Microsoft.Internal.GDIExporter.GdiSafeDCHandle Microsoft.Internal.GDIExporter.CGDIDevice::m_hDC
0x1e987  ldarg.0
0x1e988  call     instance bool Microsoft.Internal.GDIExporter.CGDIDevice::get_HasDC()
0x1e98d  call     modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 Microsoft.Internal.GDIExporter.ErrorCode(int32 rslt)
0x1e992  stloc.1
0x1e993  ldloc.1
0x1e994  ldc.i4.0
0x1e995  blt.s    loc_1E99E
0x1e997  ldarg.0
0x1e998  call     instance modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 Microsoft.Internal.GDIExporter.CGDIRenderTarget::Initialize()
0x1e99d  stloc.1
0x1e99e  ldloc.1
0x1e99f  ldc.i4.0
0x1e9a0  blt.s    loc_1E9FF
0x1e9a2  newobj   instance void GdiDocInfoW::.ctor()
0x1e9a7  stloc.0
0x1e9a8  ldloc.0
0x1e9a9  dup
0x1e9aa  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::SizeOf(object)
0x1e9af  stfld    int32 GdiDocInfoW::cbSize
0x1e9b4  ldarg.2
0x1e9b5  ldnull
0x1e9b6  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x1e9bb  brfalse.s loc_1E9C2
0x1e9bd  ldarg.2
0x1e9be  stloc.s  5
0x1e9c0  br.s     loc_1E9C9
0x1e9c2  ldsfld   string [mscorlib]System.String::Empty
0x1e9c7  stloc.s  5
0x1e9c9  ldloc.0
0x1e9ca  ldloc.s  5
0x1e9cc  stfld    string GdiDocInfoW::DocName
0x1e9d1  ldloc.0
0x1e9d2  ldarg.3
0x1e9d3  stfld    string GdiDocInfoW::Output
0x1e9d8  ldloc.0
0x1e9d9  ldnull
0x1e9da  stfld    string GdiDocInfoW::DataType
0x1e9df  ldloc.0
0x1e9e0  ldc.i4.0
0x1e9e1  stfld    int32 GdiDocInfoW::Types
0x1e9e6  ldarg.0
0x1e9e7  ldfld    class Microsoft.Internal.GDIExporter.GdiSafeDCHandle Microsoft.Internal.GDIExporter.CGDIDevice::m_hDC
0x1e9ec  ldloc.0
0x1e9ed  call     int32 Microsoft.Internal.GDIExporter.CNativeMethods::StartDocW(class Microsoft.Internal.GDIExporter.GdiSafeDCHandle hdc, modopt([mscorlib]System.Runtime.CompilerServices.IsConst) class GdiDocInfoW docinfo)
0x1e9f2  stloc.s  4
0x1e9f4  ldloc.s  4
0x1e9f6  ldc.i4.0
0x1e9f7  cgt
0x1e9f9  call     modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 Microsoft.Internal.GDIExporter.ErrorCode(int32 rslt)
0x1e9fe  stloc.1
0x1e9ff  ldarg.0
0x1ea00  ldloc.1
0x1ea01  call     instance void Microsoft.Internal.GDIExporter.CGDIRenderTarget::ThrowOnFailure(modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 hr)
0x1ea06  ldarg.0
0x1ea07  call     void [mscorlib]System.GC::KeepAlive(object)
0x1ea0c  ldloc.s  4
0x1ea0e  ret
```
