# Microsoft.ReportingServices.Interfaces.ResourceOperationsCollection::Add

- ea: `0x1030`
- end: `0x1042`
- name: `Microsoft.ReportingServices.Interfaces.ResourceOperationsCollection::Add`
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
0x1030  ldarg.0
0x1031  call     instance class [mscorlib]System.Collections.ArrayList [mscorlib]System.Collections.CollectionBase::get_InnerList()
0x1036  ldarg.1
0x1037  box      Microsoft.ReportingServices.Interfaces.ResourceOperation
0x103c  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x1041  ret
```
