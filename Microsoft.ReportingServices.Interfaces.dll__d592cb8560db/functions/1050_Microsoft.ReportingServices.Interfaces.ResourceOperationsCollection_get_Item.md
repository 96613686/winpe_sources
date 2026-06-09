# Microsoft.ReportingServices.Interfaces.ResourceOperationsCollection::get_Item

- ea: `0x1050`
- end: `0x1062`
- name: `Microsoft.ReportingServices.Interfaces.ResourceOperationsCollection::get_Item`
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
0x1050  ldarg.0
0x1051  call     instance class [mscorlib]System.Collections.ArrayList [mscorlib]System.Collections.CollectionBase::get_InnerList()
0x1056  ldarg.1
0x1057  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x105c  unbox.any Microsoft.ReportingServices.Interfaces.ResourceOperation
0x1061  ret
```
