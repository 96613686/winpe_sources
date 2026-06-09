# Microsoft.ReportingServices.Library.Native::GetSystemSid

- ea: `0x4260`
- end: `0x42cb`
- name: `Microsoft.ReportingServices.Library.Native::GetSystemSid`
- size: `107`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x4140`

## callees

- `0x3ec0`
- `0x4260`

## string_xrefs

- `0x4282`: `AllocateAndInitializeSid: Win32 error:{0}`

## pseudocode

```c

```

## disassembly

```asm
0x4260  ldnull
0x4261  stloc.0
0x4262  ldnull
0x4263  stloc.1
0x4264  ldc.i4.1
0x4265  ldc.i4.s 0x12
0x4267  ldc.i4.0
0x4268  ldc.i4.0
0x4269  ldc.i4.0
0x426a  ldc.i4.0
0x426b  ldc.i4.0
0x426c  ldc.i4.0
0x426d  ldc.i4.0
0x426e  ldloca.s 1
0x4270  call     bool [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SafeSidPtr::AllocateAndInitializeSid(unsigned int8, unsigned int32, unsigned int32, unsigned int32, unsigned int32, unsigned int32, unsigned int32, unsigned int32, unsigned int32, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SafeSidPtr&)
0x4275  brtrue.s loc_4298
0x4277  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x427c  stloc.3
0x427d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4282  ldstr    aAllocateandini// "AllocateAndInitializeSid: Win32 error:{"...
0x4287  ldloc.3
0x4288  box      [mscorlib]System.Int32
0x428d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x4292  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x4297  throw
0x4298  ldloc.1
0x4299  callvirt instance native int [mscorlib]System.Runtime.InteropServices.SafeHandle::DangerousGetHandle()
0x429e  call     int32 Microsoft.ReportingServices.Library.Native::GetLengthSid(native int pSid)
0x42a3  stloc.2
0x42a4  ldloc.2
0x42a5  newarr   [mscorlib]System.Byte
0x42aa  stloc.0
0x42ab  ldloc.1
0x42ac  callvirt instance native int [mscorlib]System.Runtime.InteropServices.SafeHandle::DangerousGetHandle()
0x42b1  ldloc.0
0x42b2  ldc.i4.0
0x42b3  ldloc.2
0x42b4  call     void [mscorlib]System.Runtime.InteropServices.Marshal::Copy(native int, unsigned int8[], int32, int32)
0x42b9  ldloc.0
0x42ba  stloc.s  4
0x42bc  leave.s  loc_42C8
0x42be  ldloc.1
0x42bf  brfalse.s loc_42C7
0x42c1  ldloc.1
0x42c2  callvirt instance void [mscorlib]System.Runtime.InteropServices.SafeHandle::Close()
0x42c7  endfinally
0x42c8  ldloc.s  4
0x42ca  ret
```
