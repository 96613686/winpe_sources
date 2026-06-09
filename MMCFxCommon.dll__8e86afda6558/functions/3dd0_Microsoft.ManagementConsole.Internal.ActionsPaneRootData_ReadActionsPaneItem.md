# Microsoft.ManagementConsole.Internal.ActionsPaneRootData::ReadActionsPaneItem

- ea: `0x3dd0`
- end: `0x3df5`
- name: `Microsoft.ManagementConsole.Internal.ActionsPaneRootData::ReadActionsPaneItem`
- size: `37`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x3d50`

## callees

- `0x37a0`
- `0x37c0`

## pseudocode

```c

```

## disassembly

```asm
0x3dd0  ldarg.1
0x3dd1  ldarg.0
0x3dd2  ldfld    int32[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::_id
0x3dd7  ldarg.2
0x3dd8  ldind.i4
0x3dd9  ldelem.i4
0x3dda  callvirt instance void Microsoft.ManagementConsole.Internal.ActionsPaneItemData::set_Id(int32 value)
0x3ddf  ldarg.1
0x3de0  ldarg.0
0x3de1  ldfld    valuetype Microsoft.ManagementConsole.Internal.ActionsInsertionLocation[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::_insertionLocation
0x3de6  ldarg.2
0x3de7  ldind.i4
0x3de8  ldelem.i4
0x3de9  callvirt instance void Microsoft.ManagementConsole.Internal.ActionsPaneItemData::set_InsertionLocation(valuetype Microsoft.ManagementConsole.Internal.ActionsInsertionLocation value)
0x3dee  ldarg.2
0x3def  dup
0x3df0  ldind.i4
0x3df1  ldc.i4.1
0x3df2  add
0x3df3  stind.i4
0x3df4  ret
```
