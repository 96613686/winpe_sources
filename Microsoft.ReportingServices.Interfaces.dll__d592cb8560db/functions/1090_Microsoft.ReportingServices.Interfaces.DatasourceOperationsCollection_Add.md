# Microsoft.ReportingServices.Interfaces.DatasourceOperationsCollection::Add

- ea: `0x1090`
- end: `0x10a2`
- name: `Microsoft.ReportingServices.Interfaces.DatasourceOperationsCollection::Add`
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
0x1090  ldarg.0
0x1091  call     instance class [mscorlib]System.Collections.ArrayList [mscorlib]System.Collections.CollectionBase::get_InnerList()
0x1096  ldarg.1
0x1097  box      Microsoft.ReportingServices.Interfaces.DatasourceOperation
0x109c  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x10a1  ret
```
