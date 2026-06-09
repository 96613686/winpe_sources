# Microsoft.ReportingServices.Interfaces.ModelItemOperationsCollection::Add

- ea: `0x1150`
- end: `0x1162`
- name: `Microsoft.ReportingServices.Interfaces.ModelItemOperationsCollection::Add`
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
0x1150  ldarg.0
0x1151  call     instance class [mscorlib]System.Collections.ArrayList [mscorlib]System.Collections.CollectionBase::get_InnerList()
0x1156  ldarg.1
0x1157  box      Microsoft.ReportingServices.Interfaces.ModelItemOperation
0x115c  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x1161  ret
```
