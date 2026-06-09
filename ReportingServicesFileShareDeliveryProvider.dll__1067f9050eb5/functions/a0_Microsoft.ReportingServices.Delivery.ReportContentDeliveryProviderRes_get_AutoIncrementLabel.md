# Microsoft.ReportingServices.Delivery.ReportContentDeliveryProviderRes::get_AutoIncrementLabel

- ea: `0xa0`
- end: `0xab`
- name: `Microsoft.ReportingServices.Delivery.ReportContentDeliveryProviderRes::get_AutoIncrementLabel`
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
0xa0  ldstr    aAutoincrementl// "AutoIncrementLabel"
0xa5  call     string Keys::GetString(string key)
0xaa  ret
```
