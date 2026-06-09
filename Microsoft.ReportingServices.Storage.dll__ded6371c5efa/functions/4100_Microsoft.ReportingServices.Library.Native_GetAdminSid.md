# Microsoft.ReportingServices.Library.Native::GetAdminSid

- ea: `0x4100`
- end: `0x413c`
- name: `Microsoft.ReportingServices.Library.Native::GetAdminSid`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x3f40`

## callees

- `0x4100`

## string_xrefs

- `0x4124`: `AllocateAndInitializeSid: Win32 error:{0}`

## pseudocode

```c

```

## disassembly

```asm
0x4100  ldnull
0x4101  stloc.0
0x4102  ldc.i4.2
0x4103  ldc.i4.s 0x20
0x4105  ldc.i4   0x220
0x410a  ldc.i4.0
0x410b  ldc.i4.0
0x410c  ldc.i4.0
0x410d  ldc.i4.0
0x410e  ldc.i4.0
0x410f  ldc.i4.0
0x4110  ldloca.s 0
0x4112  call     bool [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SafeSidPtr::AllocateAndInitializeSid(unsigned int8, unsigned int32, unsigned int32, unsigned int32, unsigned int32, unsigned int32, unsigned int32, unsigned int32, unsigned int32, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SafeSidPtr&)
0x4117  brtrue.s loc_413A
0x4119  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x411e  stloc.1
0x411f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4124  ldstr    aAllocateandini// "AllocateAndInitializeSid: Win32 error:{"...
0x4129  ldloc.1
0x412a  box      [mscorlib]System.Int32
0x412f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x4134  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x4139  throw
0x413a  ldloc.0
0x413b  ret
```
