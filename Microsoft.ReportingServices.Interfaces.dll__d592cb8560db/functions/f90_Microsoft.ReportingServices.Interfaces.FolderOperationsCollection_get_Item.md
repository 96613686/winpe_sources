# Microsoft.ReportingServices.Interfaces.FolderOperationsCollection::get_Item

- ea: `0xf90`
- end: `0xfa2`
- name: `Microsoft.ReportingServices.Interfaces.FolderOperationsCollection::get_Item`
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
0xf90  ldarg.0
0xf91  call     instance class [mscorlib]System.Collections.ArrayList [mscorlib]System.Collections.CollectionBase::get_InnerList()
0xf96  ldarg.1
0xf97  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0xf9c  unbox.any Microsoft.ReportingServices.Interfaces.FolderOperation
0xfa1  ret
```
