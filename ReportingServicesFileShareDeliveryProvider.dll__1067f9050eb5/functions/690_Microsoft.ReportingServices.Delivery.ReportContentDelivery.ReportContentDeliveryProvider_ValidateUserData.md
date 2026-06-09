# Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::ValidateUserData

- ea: `0x690`
- end: `0x69c`
- name: `Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::ValidateUserData`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x770`

## pseudocode

```c

```

## disassembly

```asm
0x690  ldarg.0
0x691  ldarg.1
0x692  ldloca.s 0
0x694  callvirt instance bool Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::IsValidSettingsData(class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] settings, [out] class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[]& outputSettings)
0x699  pop
0x69a  ldloc.0
0x69b  ret
```
