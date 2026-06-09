# Microsoft.ReportingServices.Diagnostics.ExternalItemPath::ConvertToCatalogPath

- ea: `0x8e30`
- end: `0x8e5d`
- name: `Microsoft.ReportingServices.Diagnostics.ExternalItemPath::ConvertToCatalogPath`
- size: `45`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x9470`

## callees

- `0x7890`
- `0x8b50`
- `0x8b60`
- `0x8d70`
- `0x8da0`
- `0x8e30`

## pseudocode

```c

```

## disassembly

```asm
0x8e30  ldarg.1
0x8e31  brtrue.s loc_8E45
0x8e33  ldarg.0
0x8e34  call     instance string Microsoft.ReportingServices.Diagnostics.ExternalItemPath::get_NativeCatalogPath()
0x8e39  ldarg.0
0x8e3a  call     instance string Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_EditSessionID()
0x8e3f  newobj   instance void Microsoft.ReportingServices.Diagnostics.CatalogItemPath::.ctor(string value, string editSessionID)
0x8e44  ret
0x8e45  ldarg.1
0x8e46  ldarg.0
0x8e47  call     instance string Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x8e4c  callvirt instance string Microsoft.ReportingServices.Diagnostics.IPathTranslator::ExternalToCatalog(string source)
0x8e51  ldarg.0
0x8e52  call     instance string Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_EditSessionID()
0x8e57  newobj   instance void Microsoft.ReportingServices.Diagnostics.CatalogItemPath::.ctor(string value, string editSessionID)
0x8e5c  ret
```
