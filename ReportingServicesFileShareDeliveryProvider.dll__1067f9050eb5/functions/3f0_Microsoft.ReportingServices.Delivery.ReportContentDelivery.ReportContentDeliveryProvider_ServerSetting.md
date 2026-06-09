# Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::ServerSetting

- ea: `0x3f0`
- end: `0x403`
- name: `Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::ServerSetting`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x420`
- `0x670`

## pseudocode

```c

```

## disassembly

```asm
0x3f0  ldarg.0
0x3f1  ldarg.1
0x3f2  ldarg.0
0x3f3  call     instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.IDeliveryReportServerInformation Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::get_ReportServerInformation()
0x3f8  callvirt instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.IDeliveryReportServerInformation::get_ServerSettings()
0x3fd  call     instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::GetSetting(string name, class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] settings)
0x402  ret
```
