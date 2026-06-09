# Microsoft.ReportingServices.Library.RepLibRes::get_SharedDatasetCacheUpdatePlans

- ea: `0x82e0`
- end: `0x82eb`
- name: `Microsoft.ReportingServices.Library.RepLibRes::get_SharedDatasetCacheUpdatePlans`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x9870`

## string_xrefs

- `0x82e0`: `SharedDatasetCacheUpdatePlans`

## pseudocode

```c

```

## disassembly

```asm
0x82e0  ldstr    aShareddatasetc_0// "SharedDatasetCacheUpdatePlans"
0x82e5  call     string Keys::GetString(string key)
0x82ea  ret
```
