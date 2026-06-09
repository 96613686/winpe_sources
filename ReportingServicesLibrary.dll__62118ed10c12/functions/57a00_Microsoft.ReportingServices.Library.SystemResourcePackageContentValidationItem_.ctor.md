# Microsoft.ReportingServices.Library.SystemResourcePackageContentValidationItem::.ctor

- ea: `0x57a00`
- end: `0x57a73`
- name: `Microsoft.ReportingServices.Library.SystemResourcePackageContentValidationItem::.ctor`
- size: `115`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x57a00`

## string_xrefs

- `0x57a48`: `extension`
- `0x57a52`: `extension`

## pseudocode

```c

```

## disassembly

```asm
0x57a00  ldarg.0
0x57a01  call     instance void [mscorlib]System.Object::.ctor()
0x57a06  ldarg.1
0x57a07  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x57a0c  brfalse.s loc_57A23
0x57a0e  ldstr    aKey_1// "key"
0x57a13  call     string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStringsWrapper::rsMissingParameter(string)
0x57a18  ldstr    aKey_1// "key"
0x57a1d  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x57a22  throw
0x57a23  ldarg.2
0x57a24  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x57a29  brfalse.s loc_57A40
0x57a2b  ldstr    aContenttype_0// "contentType"
0x57a30  call     string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStringsWrapper::rsMissingParameter(string)
0x57a35  ldstr    aContenttype_0// "contentType"
0x57a3a  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x57a3f  throw
0x57a40  ldarg.3
0x57a41  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x57a46  brfalse.s loc_57A5D
0x57a48  ldstr    aExtension_1// "extension"
0x57a4d  call     string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStringsWrapper::rsMissingParameter(string)
0x57a52  ldstr    aExtension_1// "extension"
0x57a57  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x57a5c  throw
0x57a5d  ldarg.0
0x57a5e  ldarg.1
0x57a5f  stfld    string Microsoft.ReportingServices.Library.SystemResourcePackageContentValidationItem::_key
0x57a64  ldarg.0
0x57a65  ldarg.2
0x57a66  stfld    string Microsoft.ReportingServices.Library.SystemResourcePackageContentValidationItem::_contentType
0x57a6b  ldarg.0
0x57a6c  ldarg.3
0x57a6d  stfld    string Microsoft.ReportingServices.Library.SystemResourcePackageContentValidationItem::_extension
0x57a72  ret
```
