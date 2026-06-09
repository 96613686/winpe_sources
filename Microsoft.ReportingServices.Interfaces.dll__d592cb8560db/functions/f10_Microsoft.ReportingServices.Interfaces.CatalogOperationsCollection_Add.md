# Microsoft.ReportingServices.Interfaces.CatalogOperationsCollection::Add

- ea: `0xf10`
- end: `0xf22`
- name: `Microsoft.ReportingServices.Interfaces.CatalogOperationsCollection::Add`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0xf10  ldarg.0
0xf11  call     instance class [mscorlib]System.Collections.ArrayList [mscorlib]System.Collections.CollectionBase::get_InnerList()
0xf16  ldarg.1
0xf17  box      Microsoft.ReportingServices.Interfaces.CatalogOperation
0xf1c  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xf21  ret
```
