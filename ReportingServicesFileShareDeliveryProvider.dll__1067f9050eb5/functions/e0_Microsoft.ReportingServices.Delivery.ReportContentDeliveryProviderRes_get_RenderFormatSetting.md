# Microsoft.ReportingServices.Delivery.ReportContentDeliveryProviderRes::get_RenderFormatSetting

- ea: `0xe0`
- end: `0xeb`
- name: `Microsoft.ReportingServices.Delivery.ReportContentDeliveryProviderRes::get_RenderFormatSetting`
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
0xe0  ldstr    aRenderformatse// "RenderFormatSetting"
0xe5  call     string Keys::GetString(string key)
0xea  ret
```
