# Microsoft.ReportingServices.Portal.Services.SR::get_Error_CatalogItemAlreadyExists

- ea: `0xa870`
- end: `0xa87b`
- name: `Microsoft.ReportingServices.Portal.Services.SR::get_Error_CatalogItemAlreadyExists`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x20b30`

## string_xrefs

- `0xa870`: `Error_CatalogItemAlreadyExists`

## pseudocode

```c

```

## disassembly

```asm
0xa870  ldstr    aErrorCatalogit_3// "Error_CatalogItemAlreadyExists"
0xa875  call     string Keys::GetString(string key)
0xa87a  ret
```
