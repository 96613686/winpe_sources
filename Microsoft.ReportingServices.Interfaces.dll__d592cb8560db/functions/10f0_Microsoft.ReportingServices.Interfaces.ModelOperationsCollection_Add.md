# Microsoft.ReportingServices.Interfaces.ModelOperationsCollection::Add

- ea: `0x10f0`
- end: `0x1102`
- name: `Microsoft.ReportingServices.Interfaces.ModelOperationsCollection::Add`
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
0x10f0  ldarg.0
0x10f1  call     instance class [mscorlib]System.Collections.ArrayList [mscorlib]System.Collections.CollectionBase::get_InnerList()
0x10f6  ldarg.1
0x10f7  box      Microsoft.ReportingServices.Interfaces.ModelOperation
0x10fc  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x1101  ret
```
