# Microsoft.ReportingServices.Interfaces.CatalogOperationsCollection::get_Item

- ea: `0xf30`
- end: `0xf42`
- name: `Microsoft.ReportingServices.Interfaces.CatalogOperationsCollection::get_Item`
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
0xf30  ldarg.0
0xf31  call     instance class [mscorlib]System.Collections.ArrayList [mscorlib]System.Collections.CollectionBase::get_InnerList()
0xf36  ldarg.1
0xf37  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0xf3c  unbox.any Microsoft.ReportingServices.Interfaces.CatalogOperation
0xf41  ret
```
