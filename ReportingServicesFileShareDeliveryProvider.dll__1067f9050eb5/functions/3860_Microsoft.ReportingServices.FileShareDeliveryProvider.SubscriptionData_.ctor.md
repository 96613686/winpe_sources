# Microsoft.ReportingServices.FileShareDeliveryProvider.SubscriptionData::.ctor

- ea: `0x3860`
- end: `0x386e`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.SubscriptionData::.ctor`
- size: `14`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xe00`
- `0x2430`
- `0x2500`

## callees

- `0x9f0`

## pseudocode

```c

```

## disassembly

```asm
0x3860  ldarg.0
0x3861  ldc.i4.1
0x3862  stfld    bool Microsoft.ReportingServices.FileShareDeliveryProvider.SubscriptionData::m_FileExtn
0x3867  ldarg.0
0x3868  call     instance void Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::.ctor()
0x386d  ret
```
