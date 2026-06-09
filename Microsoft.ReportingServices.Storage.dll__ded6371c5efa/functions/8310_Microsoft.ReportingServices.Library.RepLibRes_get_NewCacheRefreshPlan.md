# Microsoft.ReportingServices.Library.RepLibRes::get_NewCacheRefreshPlan

- ea: `0x8310`
- end: `0x831b`
- name: `Microsoft.ReportingServices.Library.RepLibRes::get_NewCacheRefreshPlan`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x9870`

## string_xrefs

- `0x8310`: `NewCacheRefreshPlan`

## pseudocode

```c

```

## disassembly

```asm
0x8310  ldstr    aNewcacherefres// "NewCacheRefreshPlan"
0x8315  call     string Keys::GetString(string key)
0x831a  ret
```
