# Microsoft.ReportingServices.Interfaces.ReportOperationsCollection::get_Item

- ea: `0xff0`
- end: `0x1002`
- name: `Microsoft.ReportingServices.Interfaces.ReportOperationsCollection::get_Item`
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
0xff0  ldarg.0
0xff1  call     instance class [mscorlib]System.Collections.ArrayList [mscorlib]System.Collections.CollectionBase::get_InnerList()
0xff6  ldarg.1
0xff7  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0xffc  unbox.any Microsoft.ReportingServices.Interfaces.ReportOperation
0x1001  ret
```
