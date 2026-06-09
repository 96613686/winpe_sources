# Microsoft.ManagementConsole.BaseCollection::OnClearComplete

- ea: `0x2d60`
- end: `0x2d7b`
- name: `Microsoft.ManagementConsole.BaseCollection::OnClearComplete`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x2bf0`

## pseudocode

```c

```

## disassembly

```asm
0x2d60  ldarg.0
0x2d61  call     instance void [mscorlib]System.Collections.CollectionBase::OnClearComplete()
0x2d66  ldarg.0
0x2d67  ldc.i4.0
0x2d68  ldarg.0
0x2d69  ldfld    object[] Microsoft.ManagementConsole.BaseCollection::_itemsBeingCleared
0x2d6e  callvirt instance void Microsoft.ManagementConsole.BaseCollection::OnItemsRemoved(int32 index, object[] items)
0x2d73  ldarg.0
0x2d74  ldnull
0x2d75  stfld    object[] Microsoft.ManagementConsole.BaseCollection::_itemsBeingCleared
0x2d7a  ret
```
