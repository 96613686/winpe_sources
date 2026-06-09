# Microsoft.ReportingServices.Library.RepLibRes::get_NewScheduledRefreshPlan

- ea: `0x8320`
- end: `0x832b`
- name: `Microsoft.ReportingServices.Library.RepLibRes::get_NewScheduledRefreshPlan`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x9870`

## string_xrefs

- `0x8320`: `NewScheduledRefreshPlan`

## pseudocode

```c

```

## disassembly

```asm
0x8320  ldstr    aNewscheduledre// "NewScheduledRefreshPlan"
0x8325  call     string Keys::GetString(string key)
0x832a  ret
```
