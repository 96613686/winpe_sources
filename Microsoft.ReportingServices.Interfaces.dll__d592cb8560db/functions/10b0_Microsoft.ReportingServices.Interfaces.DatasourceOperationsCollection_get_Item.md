# Microsoft.ReportingServices.Interfaces.DatasourceOperationsCollection::get_Item

- ea: `0x10b0`
- end: `0x10c2`
- name: `Microsoft.ReportingServices.Interfaces.DatasourceOperationsCollection::get_Item`
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
0x10b0  ldarg.0
0x10b1  call     instance class [mscorlib]System.Collections.ArrayList [mscorlib]System.Collections.CollectionBase::get_InnerList()
0x10b6  ldarg.1
0x10b7  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x10bc  unbox.any Microsoft.ReportingServices.Interfaces.DatasourceOperation
0x10c1  ret
```
