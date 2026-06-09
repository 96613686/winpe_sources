# Microsoft.ReportingServices.Portal.Services.SR::get_Error_CatalogItemPropertyInvalid

- ea: `0xa840`
- end: `0xa84b`
- name: `Microsoft.ReportingServices.Portal.Services.SR::get_Error_CatalogItemPropertyInvalid`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x45a0`

## callees

- `0x20b30`

## string_xrefs

- `0xa840`: `Error_CatalogItemPropertyInvalid`

## pseudocode

```c

```

## disassembly

```asm
0xa840  ldstr    aErrorCatalogit_1// "Error_CatalogItemPropertyInvalid"
0xa845  call     string Keys::GetString(string key)
0xa84a  ret
```
