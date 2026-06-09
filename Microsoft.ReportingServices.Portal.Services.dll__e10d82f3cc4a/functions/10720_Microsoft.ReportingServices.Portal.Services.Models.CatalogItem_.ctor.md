# Microsoft.ReportingServices.Portal.Services.Models.CatalogItem::.ctor

- ea: `0x10720`
- end: `0x1072e`
- name: `Microsoft.ReportingServices.Portal.Services.Models.CatalogItem::.ctor`
- size: `14`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x10440`
- `0x10650`
- `0x10690`
- `0x106f0`
- `0x108a0`

## callees

- `0x107a0`

## pseudocode

```c

```

## disassembly

```asm
0x10720  ldarg.0
0x10721  call     instance void [mscorlib]System.Object::.ctor()
0x10726  ldarg.0
0x10727  ldarg.1
0x10728  call     instance void Microsoft.ReportingServices.Portal.Services.Models.CatalogItem::set_Type(valuetype [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.CatalogItemType value)
0x1072d  ret
```
