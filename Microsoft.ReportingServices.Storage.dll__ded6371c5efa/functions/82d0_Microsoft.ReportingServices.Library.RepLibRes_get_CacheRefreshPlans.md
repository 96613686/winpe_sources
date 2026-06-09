# Microsoft.ReportingServices.Library.RepLibRes::get_CacheRefreshPlans

- ea: `0x82d0`
- end: `0x82db`
- name: `Microsoft.ReportingServices.Library.RepLibRes::get_CacheRefreshPlans`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x9870`

## string_xrefs

- `0x82d0`: `CacheRefreshPlans`

## pseudocode

```c

```

## disassembly

```asm
0x82d0  ldstr    aCacherefreshpl// "CacheRefreshPlans"
0x82d5  call     string Keys::GetString(string key)
0x82da  ret
```
