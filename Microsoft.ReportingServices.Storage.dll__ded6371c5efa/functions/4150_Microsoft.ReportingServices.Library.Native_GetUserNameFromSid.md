# Microsoft.ReportingServices.Library.Native::GetUserNameFromSid

- ea: `0x4150`
- end: `0x4258`
- name: `Microsoft.ReportingServices.Library.Native::GetUserNameFromSid`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x4140`

## callees

- `0x3e70`
- `0x3ff0`
- `0x4150`

## string_xrefs

- `0x418f`: `LookupAccountSid: Win32 error:{0}`

## pseudocode

```c

```

## disassembly

```asm
0x4150  ldc.i4.0
0x4151  stloc.0
0x4152  ldnull
0x4153  stloc.1
0x4154  ldnull
0x4155  stloc.2
0x4156  ldc.i4.0
0x4157  stloc.3
0x4158  ldc.i4.0
0x4159  stloc.s  4
0x415b  ldc.i4.0
0x415c  stloc.s  5
0x415e  ldnull
0x415f  ldarg.0
0x4160  ldsfld   class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SafeLocalFree [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SafeLocalFree::Zero
0x4165  ldloca.s 4
0x4167  ldsfld   class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SafeLocalFree [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SafeLocalFree::Zero
0x416c  ldloca.s 3
0x416e  ldloca.s 5
0x4170  call     bool Microsoft.ReportingServices.Library.Native::LookupAccountSid(string lpSystemName, unsigned int8[] pSid, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SafeLocalFree lpAccountName, [in] [out] unsigned int32& cchName, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SafeLocalFree DomainName, [in] [out] unsigned int32& cchDomainName, [out] unsigned int32& peUse)
0x4175  brtrue.s loc_41B5
0x4177  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x417c  stloc.0
0x417d  ldloc.0
0x417e  ldc.i4.s 0x7A
0x4180  beq.s    loc_41A5
0x4182  ldloc.0
0x4183  call     bool Microsoft.ReportingServices.Library.Native::ExpectedLookupAccountError(int32 err)
0x4188  brtrue.s loc_41A5
0x418a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x418f  ldstr    aLookupaccounts// "LookupAccountSid: Win32 error:{0}"
0x4194  ldloc.0
0x4195  box      [mscorlib]System.Int32
0x419a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x419f  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x41a4  throw
0x41a5  ldloc.0
0x41a6  call     bool Microsoft.ReportingServices.Library.Native::ExpectedLookupAccountError(int32 err)
0x41ab  brfalse.s loc_41B5
0x41ad  ldnull
0x41ae  stloc.s  6
0x41b0  leave    loc_4255
0x41b5  ldloc.3
0x41b6  ldc.i4.2
0x41b7  mul
0x41b8  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SafeLocalFree [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SafeLocalFree::LocalAlloc(int32)
0x41bd  stloc.1
0x41be  ldloc.s  4
0x41c0  ldc.i4.2
0x41c1  mul
0x41c2  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SafeLocalFree [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SafeLocalFree::LocalAlloc(int32)
0x41c7  stloc.2
0x41c8  ldnull
0x41c9  ldarg.0
0x41ca  ldloc.2
0x41cb  ldloca.s 4
0x41cd  ldloc.1
0x41ce  ldloca.s 3
0x41d0  ldloca.s 5
0x41d2  call     bool Microsoft.ReportingServices.Library.Native::LookupAccountSid(string lpSystemName, unsigned int8[] pSid, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SafeLocalFree lpAccountName, [in] [out] unsigned int32& cchName, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SafeLocalFree DomainName, [in] [out] unsigned int32& cchDomainName, [out] unsigned int32& peUse)
0x41d7  brtrue.s loc_4207
0x41d9  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x41de  stloc.0
0x41df  ldloc.0
0x41e0  call     bool Microsoft.ReportingServices.Library.Native::ExpectedLookupAccountError(int32 err)
0x41e5  brfalse.s loc_41EC
0x41e7  ldnull
0x41e8  stloc.s  6
0x41ea  leave.s  loc_4255
0x41ec  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x41f1  ldstr    aLookupaccountn// "LookupAccountName: Win32 error:{0}"
0x41f6  ldloc.0
0x41f7  box      [mscorlib]System.Int32
0x41fc  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x4201  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x4206  throw
0x4207  ldloc.2
0x4208  callvirt instance native int [mscorlib]System.Runtime.InteropServices.SafeHandle::DangerousGetHandle()
0x420d  call     string [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStringUni(native int)
0x4212  stloc.s  7
0x4214  ldloc.1
0x4215  callvirt instance native int [mscorlib]System.Runtime.InteropServices.SafeHandle::DangerousGetHandle()
0x421a  call     string [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStringUni(native int)
0x421f  stloc.s  8
0x4221  ldloc.s  8
0x4223  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4228  brfalse.s loc_4230
0x422a  ldloc.s  7
0x422c  stloc.s  6
0x422e  leave.s  loc_4255
0x4230  ldloc.s  8
0x4232  ldstr    asc_E63C// "\\"
0x4237  ldloc.s  7
0x4239  call     string [mscorlib]System.String::Concat(string, string, string)
0x423e  stloc.s  6
0x4240  leave.s  loc_4255
0x4242  ldloc.1
0x4243  brfalse.s loc_424B
0x4245  ldloc.1
0x4246  callvirt instance void [mscorlib]System.Runtime.InteropServices.SafeHandle::Close()
0x424b  ldloc.2
0x424c  brfalse.s loc_4254
0x424e  ldloc.2
0x424f  callvirt instance void [mscorlib]System.Runtime.InteropServices.SafeHandle::Close()
0x4254  endfinally
0x4255  ldloc.s  6
0x4257  ret
```
