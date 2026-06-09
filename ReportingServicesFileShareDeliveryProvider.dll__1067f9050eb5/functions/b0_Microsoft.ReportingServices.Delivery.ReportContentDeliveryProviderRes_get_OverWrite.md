# Microsoft.ReportingServices.Delivery.ReportContentDeliveryProviderRes::get_OverWrite

- ea: `0xb0`
- end: `0xbb`
- name: `Microsoft.ReportingServices.Delivery.ReportContentDeliveryProviderRes::get_OverWrite`
- size: `11`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x460`
- `0xa30`

## callees

- `0x3ed0`

## string_xrefs

- `0xb0`: `OverWrite`

## pseudocode

```c

```

## disassembly

```asm
0xb0  ldstr    aOverwrite// "OverWrite"
0xb5  call     string Keys::GetString(string key)
0xba  ret
```
