# Microsoft.ReportingServices.Interfaces.ReportOperationsCollection::Add

- ea: `0xfd0`
- end: `0xfe2`
- name: `Microsoft.ReportingServices.Interfaces.ReportOperationsCollection::Add`
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
0xfd0  ldarg.0
0xfd1  call     instance class [mscorlib]System.Collections.ArrayList [mscorlib]System.Collections.CollectionBase::get_InnerList()
0xfd6  ldarg.1
0xfd7  box      Microsoft.ReportingServices.Interfaces.ReportOperation
0xfdc  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xfe1  ret
```
