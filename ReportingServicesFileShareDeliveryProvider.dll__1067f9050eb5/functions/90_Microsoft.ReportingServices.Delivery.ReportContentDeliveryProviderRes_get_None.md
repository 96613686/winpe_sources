# Microsoft.ReportingServices.Delivery.ReportContentDeliveryProviderRes::get_None

- ea: `0x90`
- end: `0x9b`
- name: `Microsoft.ReportingServices.Delivery.ReportContentDeliveryProviderRes::get_None`
- size: `11`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x460`
- `0xa30`

## callees

- `0x3ed0`

## pseudocode

```c

```

## disassembly

```asm
0x90  ldstr    aNone// "None"
0x95  call     string Keys::GetString(string key)
0x9a  ret
```
