# Microsoft.ReportingServices.Interfaces.AceCollection::get_Item

- ea: `0x12a0`
- end: `0x12b2`
- name: `Microsoft.ReportingServices.Interfaces.AceCollection::get_Item`
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
0x12a0  ldarg.0
0x12a1  call     instance class [mscorlib]System.Collections.ArrayList [mscorlib]System.Collections.CollectionBase::get_InnerList()
0x12a6  ldarg.1
0x12a7  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x12ac  castclass Microsoft.ReportingServices.Interfaces.AceStruct
0x12b1  ret
```
