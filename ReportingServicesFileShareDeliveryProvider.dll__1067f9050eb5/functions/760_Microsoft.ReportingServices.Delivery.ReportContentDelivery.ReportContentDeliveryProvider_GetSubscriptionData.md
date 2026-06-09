# Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::GetSubscriptionData

- ea: `0x760`
- end: `0x76d`
- name: `Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::GetSubscriptionData`
- size: `13`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x2a0`

## callees

- `0x8c0`
- `0x9f0`

## pseudocode

```c

```

## disassembly

```asm
0x760  newobj   instance void Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::.ctor()
0x765  dup
0x766  ldarg.1
0x767  callvirt instance void Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::FromSettings(class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] settings)
0x76c  ret
```
