# Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::WriteNextUpdatedData

- ea: `0x7310`
- end: `0x7347`
- name: `Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::WriteNextUpdatedData`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x71b0`

## callees

- `0xc10`
- `0xc30`
- `0x7130`
- `0x7310`
- `0x8440`
- `0x8530`

## pseudocode

```c

```

## disassembly

```asm
0x7310  ldarg.0
0x7311  ldarga.s 1
0x7313  call     instance string Microsoft.ManagementConsole.Internal.ClipboardData::get_ClipboardFormatId()
0x7318  call     instance void Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::WriteString(string value)
0x731d  ldarga.s 1
0x731f  call     instance unsigned int8[] Microsoft.ManagementConsole.Internal.ClipboardData::GetValue()
0x7324  stloc.0
0x7325  ldc.i4.m1
0x7326  stloc.1
0x7327  ldloc.0
0x7328  brfalse.s loc_733A
0x732a  ldarg.0
0x732b  ldfld    class Microsoft.ManagementConsole.Internal.ByteList Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_InitialSharedData_UpdatedData_Value
0x7330  ldloc.0
0x7331  callvirt instance void Microsoft.ManagementConsole.Internal.ByteList::AddRange(unsigned int8[] items)
0x7336  ldloc.0
0x7337  ldlen
0x7338  conv.i4
0x7339  stloc.1
0x733a  ldarg.0
0x733b  ldfld    class Microsoft.ManagementConsole.Internal.Int32List Microsoft.ManagementConsole.Internal.InsertScopeNodesCommandWriter::_InitialSharedData_UpdatedData_Value_Count
0x7340  ldloc.1
0x7341  callvirt instance void Microsoft.ManagementConsole.Internal.Int32List::Add(int32 item)
0x7346  ret
```
