# Microsoft.ReportingServices.Interfaces.FolderOperationsCollection::Add

- ea: `0xf70`
- end: `0xf82`
- name: `Microsoft.ReportingServices.Interfaces.FolderOperationsCollection::Add`
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
0xf70  ldarg.0
0xf71  call     instance class [mscorlib]System.Collections.ArrayList [mscorlib]System.Collections.CollectionBase::get_InnerList()
0xf76  ldarg.1
0xf77  box      Microsoft.ReportingServices.Interfaces.FolderOperation
0xf7c  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xf81  ret
```
