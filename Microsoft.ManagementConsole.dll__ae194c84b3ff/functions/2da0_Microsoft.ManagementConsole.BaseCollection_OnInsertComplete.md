# Microsoft.ManagementConsole.BaseCollection::OnInsertComplete

- ea: `0x2da0`
- end: `0x2dbc`
- name: `Microsoft.ManagementConsole.BaseCollection::OnInsertComplete`
- size: `28`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x2be0`

## pseudocode

```c

```

## disassembly

```asm
0x2da0  ldarg.0
0x2da1  ldarg.1
0x2da2  ldarg.2
0x2da3  call     instance void [mscorlib]System.Collections.CollectionBase::OnInsertComplete(int32, object)
0x2da8  ldarg.0
0x2da9  ldarg.1
0x2daa  ldc.i4.1
0x2dab  newarr   [mscorlib]System.Object
0x2db0  stloc.0
0x2db1  ldloc.0
0x2db2  ldc.i4.0
0x2db3  ldarg.2
0x2db4  stelem.ref
0x2db5  ldloc.0
0x2db6  callvirt instance void Microsoft.ManagementConsole.BaseCollection::OnItemsAdded(int32 index, object[] items)
0x2dbb  ret
```
