# Microsoft.ManagementConsole.ScopeNode::RequestSharedDataUpdate

- ea: `0x1b00`
- end: `0x1b34`
- name: `Microsoft.ManagementConsole.ScopeNode::RequestSharedDataUpdate`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0xe00`

## callees

- `0x16c0`
- `0x1b00`
- `0x5550`
- `0x5810`

## pseudocode

```c

```

## disassembly

```asm
0x1b00  ldarg.0
0x1b01  call     instance class Microsoft.ManagementConsole.WritableSharedData Microsoft.ManagementConsole.ScopeNode::get_SharedData()
0x1b06  ldarg.1
0x1b07  callvirt instance valuetype [MMCFxCommon]Microsoft.ManagementConsole.Internal.ClipboardData [MMCFxCommon]Microsoft.ManagementConsole.Internal.UpdateDataChangeNodeRequestInfo::get_RequestedValue()
0x1b0c  stloc.1
0x1b0d  ldloca.s 1
0x1b0f  call     instance string [MMCFxCommon]Microsoft.ManagementConsole.Internal.ClipboardData::get_ClipboardFormatId()
0x1b14  callvirt instance class Microsoft.ManagementConsole.WritableSharedDataItem Microsoft.ManagementConsole.WritableSharedData::GetItem(string clipboardFormatId)
0x1b19  stloc.0
0x1b1a  ldloc.0
0x1b1b  brtrue.s loc_1B1E
0x1b1d  ret
0x1b1e  ldloc.0
0x1b1f  ldarg.1
0x1b20  callvirt instance valuetype [MMCFxCommon]Microsoft.ManagementConsole.Internal.ClipboardData [MMCFxCommon]Microsoft.ManagementConsole.Internal.UpdateDataChangeNodeRequestInfo::get_RequestedValue()
0x1b25  stloc.2
0x1b26  ldloca.s 2
0x1b28  call     instance unsigned int8[] [MMCFxCommon]Microsoft.ManagementConsole.Internal.ClipboardData::GetValue()
0x1b2d  ldarg.2
0x1b2e  callvirt instance void Microsoft.ManagementConsole.WritableSharedDataItem::OnPropertyUpdateRequested(unsigned int8[] value, class [MMCFxCommon]Microsoft.ManagementConsole.Internal.IRequestStatus status)
0x1b33  ret
```
