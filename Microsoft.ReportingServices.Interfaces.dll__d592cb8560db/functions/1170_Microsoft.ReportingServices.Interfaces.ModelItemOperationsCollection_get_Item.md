# Microsoft.ReportingServices.Interfaces.ModelItemOperationsCollection::get_Item

- ea: `0x1170`
- end: `0x1182`
- name: `Microsoft.ReportingServices.Interfaces.ModelItemOperationsCollection::get_Item`
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
0x1170  ldarg.0
0x1171  call     instance class [mscorlib]System.Collections.ArrayList [mscorlib]System.Collections.CollectionBase::get_InnerList()
0x1176  ldarg.1
0x1177  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x117c  unbox.any Microsoft.ReportingServices.Interfaces.ModelItemOperation
0x1181  ret
```
