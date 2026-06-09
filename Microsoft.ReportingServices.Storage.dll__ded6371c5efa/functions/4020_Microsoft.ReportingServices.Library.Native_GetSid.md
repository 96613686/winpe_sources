# Microsoft.ReportingServices.Library.Native::GetSid

- ea: `0x4020`
- end: `0x40f3`
- name: `Microsoft.ReportingServices.Library.Native::GetSid`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x3fa0`

## callees

- `0x3e60`
- `0x3ff0`
- `0x4020`

## pseudocode

```c

```

## disassembly

```asm
0x4020  ldc.i4.0
0x4021  stloc.0
0x4022  ldarg.1
0x4023  ldc.i4.0
0x4024  stind.i4
0x4025  ldnull
0x4026  stloc.1
0x4027  ldnull
0x4028  stloc.2
0x4029  ldc.i4.0
0x402a  stloc.3
0x402b  ldc.i4.0
0x402c  stloc.s  4
0x402e  ldc.i4.0
0x402f  stloc.s  5
0x4031  ldnull
0x4032  ldarg.0
0x4033  ldsfld   class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SafeLocalFree [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SafeLocalFree::Zero
0x4038  ldloca.s 3
0x403a  ldsfld   class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SafeLocalFree [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SafeLocalFree::Zero
0x403f  ldloca.s 4
0x4041  ldloca.s 5
0x4043  call     bool Microsoft.ReportingServices.Library.Native::LookupAccountName(string lpSystemName, string lpAccountName, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SafeLocalFree Sid, [in] [out] unsigned int32& cbSid, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SafeLocalFree DomainName, [in] [out] unsigned int32& cbDomainName, [out] unsigned int32& peUse)
0x4048  brtrue.s loc_4085
0x404a  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x404f  stloc.0
0x4050  ldloc.0
0x4051  ldc.i4.s 0x7A
0x4053  beq.s    loc_4078
0x4055  ldloc.0
0x4056  call     bool Microsoft.ReportingServices.Library.Native::ExpectedLookupAccountError(int32 err)
0x405b  brtrue.s loc_4078
0x405d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4062  ldstr    aLookupaccountn// "LookupAccountName: Win32 error:{0}"
0x4067  ldloc.0
0x4068  box      [mscorlib]System.Int32
0x406d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x4072  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x4077  throw
0x4078  ldloc.0
0x4079  call     bool Microsoft.ReportingServices.Library.Native::ExpectedLookupAccountError(int32 err)
0x407e  brfalse.s loc_4085
0x4080  ldnull
0x4081  stloc.s  6
0x4083  leave.s  loc_40F0
0x4085  ldloc.s  4
0x4087  ldc.i4.2
0x4088  mul
0x4089  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SafeLocalFree [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SafeLocalFree::LocalAlloc(int32)
0x408e  stloc.1
0x408f  ldloc.3
0x4090  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SafeLocalFree [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SafeLocalFree::LocalAlloc(int32)
0x4095  stloc.2
0x4096  ldnull
0x4097  ldarg.0
0x4098  ldloc.2
0x4099  ldloca.s 3
0x409b  ldloc.1
0x409c  ldloca.s 4
0x409e  ldloca.s 5
0x40a0  call     bool Microsoft.ReportingServices.Library.Native::LookupAccountName(string lpSystemName, string lpAccountName, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SafeLocalFree Sid, [in] [out] unsigned int32& cbSid, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SafeLocalFree DomainName, [in] [out] unsigned int32& cbDomainName, [out] unsigned int32& peUse)
0x40a5  brtrue.s loc_40DE
0x40a7  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x40ac  stloc.0
0x40ad  ldloc.2
0x40ae  brfalse.s loc_40B6
0x40b0  ldloc.2
0x40b1  callvirt instance void [mscorlib]System.Runtime.InteropServices.SafeHandle::Close()
0x40b6  ldloc.0
0x40b7  call     bool Microsoft.ReportingServices.Library.Native::ExpectedLookupAccountError(int32 err)
0x40bc  brfalse.s loc_40C3
0x40be  ldnull
0x40bf  stloc.s  6
0x40c1  leave.s  loc_40F0
0x40c3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x40c8  ldstr    aLookupaccountn// "LookupAccountName: Win32 error:{0}"
0x40cd  ldloc.0
0x40ce  box      [mscorlib]System.Int32
0x40d3  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x40d8  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x40dd  throw
0x40de  ldarg.1
0x40df  ldloc.3
0x40e0  stind.i4
0x40e1  ldloc.2
0x40e2  stloc.s  6
0x40e4  leave.s  loc_40F0
0x40e6  ldloc.1
0x40e7  brfalse.s loc_40EF
0x40e9  ldloc.1
0x40ea  callvirt instance void [mscorlib]System.Runtime.InteropServices.SafeHandle::Close()
0x40ef  endfinally
0x40f0  ldloc.s  6
0x40f2  ret
```
