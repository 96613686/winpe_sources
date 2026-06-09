# Microsoft.ManagementConsole.Internal.ActionsPaneRootData::ReadCollection

- ea: `0x3eb0`
- end: `0x3efc`
- name: `Microsoft.ManagementConsole.Internal.ActionsPaneRootData::ReadCollection`
- size: `76`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x3d50`

## callees

- `0x3a50`
- `0x3a70`
- `0x3d50`
- `0x3eb0`

## pseudocode

```c

```

## disassembly

```asm
0x3eb0  ldarg.1
0x3eb1  ldarg.0
0x3eb2  ldfld    bool[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::_renderAsRegion
0x3eb7  ldarg.s  5
0x3eb9  ldind.i4
0x3eba  ldelem.i1
0x3ebb  callvirt instance void Microsoft.ManagementConsole.Internal.ActionsPaneItemCollectionData::set_RenderAsRegion(bool value)
0x3ec0  ldarg.0
0x3ec1  ldfld    int32[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::_itemsCount
0x3ec6  ldarg.s  5
0x3ec8  ldind.i4
0x3ec9  ldelem.i4
0x3eca  stloc.0
0x3ecb  ldarg.s  5
0x3ecd  dup
0x3ece  ldind.i4
0x3ecf  ldc.i4.1
0x3ed0  add
0x3ed1  stind.i4
0x3ed2  ldloc.0
0x3ed3  newarr   Microsoft.ManagementConsole.Internal.ActionsPaneItemData
0x3ed8  stloc.1
0x3ed9  ldc.i4.0
0x3eda  stloc.2
0x3edb  br.s     loc_3EF0
0x3edd  ldloc.1
0x3ede  ldloc.2
0x3edf  ldarg.0
0x3ee0  ldarg.2
0x3ee1  ldarg.3
0x3ee2  ldarg.s  4
0x3ee4  ldarg.s  5
0x3ee6  call     instance class Microsoft.ManagementConsole.Internal.ActionsPaneItemData Microsoft.ManagementConsole.Internal.ActionsPaneRootData::Read(int32& index, int32& exItemIndex, int32& actionIndex, int32& colIndex)
0x3eeb  stelem.ref
0x3eec  ldloc.2
0x3eed  ldc.i4.1
0x3eee  add
0x3eef  stloc.2
0x3ef0  ldloc.2
0x3ef1  ldloc.0
0x3ef2  blt.s    loc_3EDD
0x3ef4  ldarg.1
0x3ef5  ldloc.1
0x3ef6  callvirt instance void Microsoft.ManagementConsole.Internal.ActionsPaneItemCollectionData::SetItems(class Microsoft.ManagementConsole.Internal.ActionsPaneItemData[] items)
0x3efb  ret
```
