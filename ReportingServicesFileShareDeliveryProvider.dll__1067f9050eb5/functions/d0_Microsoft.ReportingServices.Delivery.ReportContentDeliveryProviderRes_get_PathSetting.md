# Microsoft.ReportingServices.Delivery.ReportContentDeliveryProviderRes::get_PathSetting

- ea: `0xd0`
- end: `0xdb`
- name: `Microsoft.ReportingServices.Delivery.ReportContentDeliveryProviderRes::get_PathSetting`
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

- `0xd0`: `PathSetting`

## pseudocode

```c

```

## disassembly

```asm
0xd0  ldstr    aPathsetting// "PathSetting"
0xd5  call     string Keys::GetString(string key)
0xda  ret
```
