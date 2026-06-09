# Microsoft.ManagementConsole.BaseCollection::OnRemoveComplete

- ea: `0x2de0`
- end: `0x2dfc`
- name: `Microsoft.ManagementConsole.BaseCollection::OnRemoveComplete`
- size: `28`
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
0x2de0  ldarg.0
0x2de1  ldarg.1
0x2de2  ldarg.2
0x2de3  call     instance void [mscorlib]System.Collections.CollectionBase::OnRemoveComplete(int32, object)
0x2de8  ldarg.0
0x2de9  ldarg.1
0x2dea  ldc.i4.1
0x2deb  newarr   [mscorlib]System.Object
0x2df0  stloc.0
0x2df1  ldloc.0
0x2df2  ldc.i4.0
0x2df3  ldarg.2
0x2df4  stelem.ref
0x2df5  ldloc.0
0x2df6  callvirt instance void Microsoft.ManagementConsole.BaseCollection::OnItemsRemoved(int32 index, object[] items)
0x2dfb  ret
```
