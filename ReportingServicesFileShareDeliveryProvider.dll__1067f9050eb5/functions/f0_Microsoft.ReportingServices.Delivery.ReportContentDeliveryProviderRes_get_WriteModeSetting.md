# Microsoft.ReportingServices.Delivery.ReportContentDeliveryProviderRes::get_WriteModeSetting

- ea: `0xf0`
- end: `0xfb`
- name: `Microsoft.ReportingServices.Delivery.ReportContentDeliveryProviderRes::get_WriteModeSetting`
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

## string_xrefs

- `0xf0`: `WriteModeSetting`

## pseudocode

```c

```

## disassembly

```asm
0xf0  ldstr    aWritemodesetti// "WriteModeSetting"
0xf5  call     string Keys::GetString(string key)
0xfa  ret
```
