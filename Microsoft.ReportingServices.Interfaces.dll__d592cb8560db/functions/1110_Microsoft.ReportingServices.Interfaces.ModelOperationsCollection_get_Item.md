# Microsoft.ReportingServices.Interfaces.ModelOperationsCollection::get_Item

- ea: `0x1110`
- end: `0x1122`
- name: `Microsoft.ReportingServices.Interfaces.ModelOperationsCollection::get_Item`
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
0x1110  ldarg.0
0x1111  call     instance class [mscorlib]System.Collections.ArrayList [mscorlib]System.Collections.CollectionBase::get_InnerList()
0x1116  ldarg.1
0x1117  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x111c  unbox.any Microsoft.ReportingServices.Interfaces.ModelOperation
0x1121  ret
```
