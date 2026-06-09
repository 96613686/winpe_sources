# Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::CreateSetting

- ea: `0x9d0`
- end: `0x9e4`
- name: `Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::CreateSetting`
- size: `20`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x950`
- `0x3910`

## pseudocode

```c

```

## disassembly

```asm
0x9d0  newobj   instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::.ctor()
0x9d5  dup
0x9d6  ldarg.1
0x9d7  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_Name(string)
0x9dc  dup
0x9dd  ldarg.2
0x9de  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::set_Value(string)
0x9e3  ret
```
