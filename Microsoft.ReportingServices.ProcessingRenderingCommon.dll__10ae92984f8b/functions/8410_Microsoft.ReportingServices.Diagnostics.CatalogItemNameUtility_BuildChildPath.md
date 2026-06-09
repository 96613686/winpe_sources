# Microsoft.ReportingServices.Diagnostics.CatalogItemNameUtility::BuildChildPath

- ea: `0x8410`
- end: `0x844b`
- name: `Microsoft.ReportingServices.Diagnostics.CatalogItemNameUtility::BuildChildPath`
- size: `59`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path, service_task, broker_com_uri`

## callees

- `0x3a20`
- `0x82e0`
- `0x8410`

## string_xrefs

- `0x841d`: `parentPath = '/' on BuildChildPath`

## pseudocode

```c

```

## disassembly

```asm
0x8410  ldarg.0
0x8411  ldsfld   string Microsoft.ReportingServices.Diagnostics.CatalogItemNameUtility::PathSeparatorString
0x8416  call     int32 Microsoft.ReportingServices.Diagnostics.Localization::CatalogCultureCompare(string a, string b)
0x841b  brtrue.s loc_8428
0x841d  ldstr    aParentpathOnBu// "parentPath = '/' on BuildChildPath"
0x8422  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x8427  throw
0x8428  ldarg.0
0x8429  ldstr    asc_1F13A// "/"
0x842e  ldarg.1
0x842f  call     string [mscorlib]System.String::Concat(string, string, string)
0x8434  stloc.0
0x8435  ldloc.0
0x8436  callvirt instance int32 [mscorlib]System.String::get_Length()
0x843b  call     int32 Microsoft.ReportingServices.Diagnostics.CatalogItemNameUtility::get_MaxItemPathLength()
0x8440  ble.s    loc_8449
0x8442  ldloc.0
0x8443  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ItemPathLengthExceededException::.ctor(string)
0x8448  throw
0x8449  ldloc.0
0x844a  ret
```
