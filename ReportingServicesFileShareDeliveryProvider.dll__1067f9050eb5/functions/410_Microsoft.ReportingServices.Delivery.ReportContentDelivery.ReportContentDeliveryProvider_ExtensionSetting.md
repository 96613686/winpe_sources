# Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::ExtensionSetting

- ea: `0x410`
- end: `0x41e`
- name: `Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::ExtensionSetting`
- size: `14`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x3a0`

## callees

- `0x420`
- `0x460`

## pseudocode

```c

```

## disassembly

```asm
0x410  ldarg.0
0x411  ldarg.1
0x412  ldarg.0
0x413  callvirt instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::get_ExtensionSettings()
0x418  call     instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::GetSetting(string name, class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] settings)
0x41d  ret
```
