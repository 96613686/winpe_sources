# Microsoft.ReportingServices.Library.RepLibRes::get_SubscriptionReady

- ea: `0x8360`
- end: `0x836b`
- name: `Microsoft.ReportingServices.Library.RepLibRes::get_SubscriptionReady`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x9870`

## string_xrefs

- `0x8360`: `SubscriptionReady`

## pseudocode

```c

```

## disassembly

```asm
0x8360  ldstr    aSubscriptionre// "SubscriptionReady"
0x8365  call     string Keys::GetString(string key)
0x836a  ret
```
