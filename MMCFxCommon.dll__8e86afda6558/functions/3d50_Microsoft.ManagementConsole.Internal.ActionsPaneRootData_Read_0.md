# Microsoft.ManagementConsole.Internal.ActionsPaneRootData::Read_0

- ea: `0x3d50`
- end: `0x3dc7`
- name: `Microsoft.ManagementConsole.Internal.ActionsPaneRootData::Read_0`
- size: `119`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x3ce0`
- `0x3eb0`

## callees

- `0x3800`
- `0x3a20`
- `0x3a80`
- `0x3d50`
- `0x3dd0`
- `0x3e00`
- `0x3e80`
- `0x3eb0`

## pseudocode

```c

```

## disassembly

```asm
0x3d50  ldnull
0x3d51  stloc.0
0x3d52  ldarg.0
0x3d53  ldfld    valuetype Microsoft.ManagementConsole.Internal.ActionsPaneRootItemType[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::_type
0x3d58  ldarg.1
0x3d59  ldind.i4
0x3d5a  ldelem.i4
0x3d5b  stloc.3
0x3d5c  ldloc.3
0x3d5d  switch   loc_3D70, loc_3D80, loc_3D78
0x3d6e  br.s     loc_3D86
0x3d70  newobj   instance void Microsoft.ManagementConsole.Internal.ActionSeparatorItemData::.ctor()
0x3d75  stloc.0
0x3d76  br.s     loc_3D86
0x3d78  newobj   instance void Microsoft.ManagementConsole.Internal.ActionsPaneItemCollectionData::.ctor()
0x3d7d  stloc.0
0x3d7e  br.s     loc_3D86
0x3d80  newobj   instance void Microsoft.ManagementConsole.Internal.ActionData::.ctor()
0x3d85  stloc.0
0x3d86  ldarg.0
0x3d87  ldloc.0
0x3d88  ldarg.1
0x3d89  call     instance void Microsoft.ManagementConsole.Internal.ActionsPaneRootData::ReadActionsPaneItem(class Microsoft.ManagementConsole.Internal.ActionsPaneItemData data, int32& index)
0x3d8e  ldloc.0
0x3d8f  isinst   Microsoft.ManagementConsole.Internal.ActionsPaneExtendedItemData
0x3d94  stloc.1
0x3d95  ldloc.1
0x3d96  brfalse.s loc_3DC5
0x3d98  ldarg.0
0x3d99  ldloc.1
0x3d9a  ldarg.2
0x3d9b  call     instance void Microsoft.ManagementConsole.Internal.ActionsPaneRootData::ReadExtendedActionsPaneItem(class Microsoft.ManagementConsole.Internal.ActionsPaneExtendedItemData data, int32& exItemIndex)
0x3da0  ldloc.1
0x3da1  isinst   Microsoft.ManagementConsole.Internal.ActionData
0x3da6  stloc.2
0x3da7  ldloc.2
0x3da8  brfalse.s loc_3DB4
0x3daa  ldarg.0
0x3dab  ldloc.2
0x3dac  ldarg.3
0x3dad  call     instance void Microsoft.ManagementConsole.Internal.ActionsPaneRootData::ReadAction(class Microsoft.ManagementConsole.Internal.ActionData data, int32& actionIndex)
0x3db2  br.s     loc_3DC5
0x3db4  ldarg.0
0x3db5  ldloc.1
0x3db6  castclass Microsoft.ManagementConsole.Internal.ActionsPaneItemCollectionData
0x3dbb  ldarg.1
0x3dbc  ldarg.2
0x3dbd  ldarg.3
0x3dbe  ldarg.s  4
0x3dc0  call     instance void Microsoft.ManagementConsole.Internal.ActionsPaneRootData::ReadCollection(class Microsoft.ManagementConsole.Internal.ActionsPaneItemCollectionData data, int32& index, int32& exItemIndex, int32& actionIndex, int32& colIndex)
0x3dc5  ldloc.0
0x3dc6  ret
```
