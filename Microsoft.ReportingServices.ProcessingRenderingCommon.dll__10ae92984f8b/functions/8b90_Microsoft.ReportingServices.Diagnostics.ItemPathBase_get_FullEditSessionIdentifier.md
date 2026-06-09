# Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_FullEditSessionIdentifier

- ea: `0x8b90`
- end: `0x8bea`
- name: `Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_FullEditSessionIdentifier`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x94c0`

## callees

- `0x8b50`
- `0x8b60`
- `0x8b80`
- `0x8b90`

## string_xrefs

- `0x8bbc`: `Unexpected character in ItemPath or EditSessionID`

## pseudocode

```c

```

## disassembly

```asm
0x8b90  ldarg.0
0x8b91  call     instance bool Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_IsEditSession()
0x8b96  brfalse.s loc_8BE3
0x8b98  ldarg.0
0x8b99  call     instance string Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x8b9e  ldstr    asc_1F320// "|"
0x8ba3  callvirt instance bool [mscorlib]System.String::Contains(string)
0x8ba8  brtrue.s loc_8BBC
0x8baa  ldarg.0
0x8bab  call     instance string Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_EditSessionID()
0x8bb0  ldstr    asc_1F320// "|"
0x8bb5  callvirt instance bool [mscorlib]System.String::Contains(string)
0x8bba  brfalse.s loc_8BC7
0x8bbc  ldstr    aUnexpectedChar// "Unexpected character in ItemPath or Edi"...
0x8bc1  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x8bc6  throw
0x8bc7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8bcc  ldstr    a01// "|{0}|@|{1}|"
0x8bd1  ldarg.0
0x8bd2  call     instance string Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_EditSessionID()
0x8bd7  ldarg.0
0x8bd8  call     instance string Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x8bdd  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object)
0x8be2  ret
0x8be3  ldarg.0
0x8be4  call     instance string Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x8be9  ret
```
