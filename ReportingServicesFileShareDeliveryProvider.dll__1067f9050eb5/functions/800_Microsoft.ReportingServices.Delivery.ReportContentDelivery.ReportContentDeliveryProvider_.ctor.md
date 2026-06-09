# Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::.ctor

- ea: `0x800`
- end: `0x817`
- name: `Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::.ctor`
- size: `23`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x1c50`

## pseudocode

```c

```

## disassembly

```asm
0x800  ldarg.0
0x801  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x806  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor(class [mscorlib]System.Collections.IEqualityComparer)
0x80b  stfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::m_excludedRenderFormats
0x810  ldarg.0
0x811  call     instance void [mscorlib]System.Object::.ctor()
0x816  ret
```
