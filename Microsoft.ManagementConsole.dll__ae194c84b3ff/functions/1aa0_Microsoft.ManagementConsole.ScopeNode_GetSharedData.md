# Microsoft.ManagementConsole.ScopeNode::GetSharedData

- ea: `0x1aa0`
- end: `0x1afb`
- name: `Microsoft.ManagementConsole.ScopeNode::GetSharedData`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0xe00`

## callees

- `0x16c0`
- `0x1aa0`
- `0x1de0`
- `0x5200`
- `0x5550`
- `0x73b0`

## pseudocode

```c

```

## disassembly

```asm
0x1aa0  ldarg.0
0x1aa1  call     instance class Microsoft.ManagementConsole.WritableSharedData Microsoft.ManagementConsole.ScopeNode::get_SharedData()
0x1aa6  ldarg.1
0x1aa7  callvirt instance string [MMCFxCommon]Microsoft.ManagementConsole.Internal.ReadSharedDataNodeRequestInfo::get_RequestedClipboardFormatId()
0x1aac  callvirt instance class Microsoft.ManagementConsole.WritableSharedDataItem Microsoft.ManagementConsole.WritableSharedData::GetItem(string clipboardFormatId)
0x1ab1  stloc.0
0x1ab2  ldloc.0
0x1ab3  brtrue.s loc_1AB6
0x1ab5  ret
0x1ab6  ldarg.2
0x1ab7  newobj   instance void Microsoft.ManagementConsole.SyncStatus::.ctor(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.IRequestStatus requestStatus)
0x1abc  stloc.1
0x1abd  ldarg.0
0x1abe  ldloc.0
0x1abf  ldloc.1
0x1ac0  callvirt instance unsigned int8[] Microsoft.ManagementConsole.ScopeNode::OnGetSharedData(class Microsoft.ManagementConsole.WritableSharedDataItem item, class Microsoft.ManagementConsole.SyncStatus status)
0x1ac5  stloc.2
0x1ac6  ldloca.s 3
0x1ac8  initobj  [MMCFxCommon]Microsoft.ManagementConsole.Internal.ClipboardData
0x1ace  ldloca.s 3
0x1ad0  ldloc.0
0x1ad1  callvirt instance string Microsoft.ManagementConsole.SharedDataItemBase::get_ClipboardFormatId()
0x1ad6  call     instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.ClipboardData::set_ClipboardFormatId(string)
0x1adb  ldloca.s 3
0x1add  ldloc.2
0x1ade  call     instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.ClipboardData::SetValue(unsigned int8[])
0x1ae3  newobj   instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.ReadSharedDataResponse::.ctor()
0x1ae8  stloc.s  4
0x1aea  ldloc.s  4
0x1aec  ldloc.3
0x1aed  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.ReadSharedDataResponse::set_RequestedClipboardData(valuetype [MMCFxCommon]Microsoft.ManagementConsole.Internal.ClipboardData)
0x1af2  ldarg.2
0x1af3  ldloc.s  4
0x1af5  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.IRequestStatus::ProcessResponse(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.RequestResponse)
0x1afa  ret
```
