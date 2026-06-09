# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::GetSubscriptionData

- ea: `0xe00`
- end: `0xe0d`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::GetSubscriptionData`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x8c0`
- `0x3860`

## pseudocode

```c

```

## disassembly

```asm
0xe00  newobj   instance void Microsoft.ReportingServices.FileShareDeliveryProvider.SubscriptionData::.ctor()
0xe05  dup
0xe06  ldarg.1
0xe07  callvirt instance void Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::FromSettings(class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] settings)
0xe0c  ret
```
