# Microsoft.ManagementConsole.ScopeNode::DoVerb

- ea: `0x1b40`
- end: `0x1c26`
- name: `Microsoft.ManagementConsole.ScopeNode::DoVerb`
- size: `230`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0xe00`

## callees

- `0x550`
- `0x1b40`
- `0x1e00`
- `0x1e10`
- `0x1e20`
- `0x1e30`
- `0x1e40`
- `0x1e50`
- `0x4230`
- `0x4570`
- `0x45b0`
- `0x4ec0`
- `0x4ee0`
- `0x73b0`
- `0x73d0`
- `0x7ec0`

## pseudocode

```c

```

## disassembly

```asm
0x1b40  ldarg.1
0x1b41  isinst   [MMCFxCommon]Microsoft.ManagementConsole.Internal.DeleteNodeRequestInfo
0x1b46  brfalse.s loc_1B55
0x1b48  ldarg.0
0x1b49  ldarg.2
0x1b4a  newobj   instance void Microsoft.ManagementConsole.SyncStatus::.ctor(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.IRequestStatus requestStatus)
0x1b4f  callvirt instance void Microsoft.ManagementConsole.ScopeNode::OnDelete(class Microsoft.ManagementConsole.SyncStatus status)
0x1b54  ret
0x1b55  ldarg.1
0x1b56  isinst   [MMCFxCommon]Microsoft.ManagementConsole.Internal.RefreshNodeRequestInfo
0x1b5b  brfalse.s loc_1B6A
0x1b5d  ldarg.0
0x1b5e  ldarg.2
0x1b5f  newobj   instance void Microsoft.ManagementConsole.AsyncStatus::.ctor(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.IRequestStatus requestStatus)
0x1b64  callvirt instance void Microsoft.ManagementConsole.ScopeNode::OnRefresh(class Microsoft.ManagementConsole.AsyncStatus status)
0x1b69  ret
0x1b6a  ldarg.1
0x1b6b  isinst   [MMCFxCommon]Microsoft.ManagementConsole.Internal.PrintNodeRequestInfo
0x1b70  brfalse.s loc_1B7F
0x1b72  ldarg.0
0x1b73  ldarg.2
0x1b74  newobj   instance void Microsoft.ManagementConsole.SyncStatus::.ctor(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.IRequestStatus requestStatus)
0x1b79  callvirt instance void Microsoft.ManagementConsole.ScopeNode::OnPrint(class Microsoft.ManagementConsole.SyncStatus status)
0x1b7e  ret
0x1b7f  ldarg.1
0x1b80  isinst   [MMCFxCommon]Microsoft.ManagementConsole.Internal.RenameNodeRequestInfo
0x1b85  brfalse.s loc_1B9F
0x1b87  ldarg.0
0x1b88  ldarg.1
0x1b89  castclass [MMCFxCommon]Microsoft.ManagementConsole.Internal.RenameNodeRequestInfo
0x1b8e  callvirt instance string [MMCFxCommon]Microsoft.ManagementConsole.Internal.RenameNodeRequestInfo::get_NewDisplayName()
0x1b93  ldarg.2
0x1b94  newobj   instance void Microsoft.ManagementConsole.SyncStatus::.ctor(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.IRequestStatus requestStatus)
0x1b99  callvirt instance void Microsoft.ManagementConsole.ScopeNode::OnRename(string newText, class Microsoft.ManagementConsole.SyncStatus status)
0x1b9e  ret
0x1b9f  ldarg.1
0x1ba0  isinst   [MMCFxCommon]Microsoft.ManagementConsole.Internal.PasteNodeRequestInfo
0x1ba5  brfalse.s loc_1C11
0x1ba7  ldarg.1
0x1ba8  castclass [MMCFxCommon]Microsoft.ManagementConsole.Internal.PasteNodeRequestInfo
0x1bad  stloc.0
0x1bae  ldloc.0
0x1baf  callvirt instance int32 [MMCFxCommon]Microsoft.ManagementConsole.Internal.PasteNodeRequestInfo::get_DataObjectId()
0x1bb4  newobj   instance void Microsoft.ManagementConsole.SharedData::.ctor(int32 dataObjectId)
0x1bb9  stloc.1
0x1bba  ldarg.0
0x1bbb  call     instance class Microsoft.ManagementConsole.NamespaceSnapInBase Microsoft.ManagementConsole.Node::get_SnapIn()
0x1bc0  ldloc.1
0x1bc1  callvirt instance void Microsoft.ManagementConsole.SnapInBase::AddSharedData(class Microsoft.ManagementConsole.SharedData sharedData)
0x1bc6  ldloc.1
0x1bc7  ldarg.0
0x1bc8  call     instance class Microsoft.ManagementConsole.NamespaceSnapInBase Microsoft.ManagementConsole.Node::get_SnapIn()
0x1bcd  callvirt instance class Microsoft.ManagementConsole.Internal.SnapInClient Microsoft.ManagementConsole.SnapInBase::get_SnapInClient()
0x1bd2  callvirt instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ISnapInPlatform Microsoft.ManagementConsole.Internal.SnapInClient::get_SnapInPlatform()
0x1bd7  callvirt instance void Microsoft.ManagementConsole.SharedData::SetSnapInPlatform(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ISnapInPlatform snapInPlatform)
0x1bdc  newobj   instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.PasteResponse::.ctor()
0x1be1  stloc.2
0x1be2  ldloc.2
0x1be3  ldarg.0
0x1be4  ldloc.1
0x1be5  ldloc.0
0x1be6  callvirt instance valuetype [MMCFxCommon]Microsoft.ManagementConsole.Internal.DragAndDropVerb [MMCFxCommon]Microsoft.ManagementConsole.Internal.PasteNodeRequestInfo::get_PasteType()
0x1beb  ldarg.2
0x1bec  newobj   instance void Microsoft.ManagementConsole.SyncStatus::.ctor(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.IRequestStatus requestStatus)
0x1bf1  callvirt instance bool Microsoft.ManagementConsole.ScopeNode::OnPaste(class Microsoft.ManagementConsole.SharedData data, valuetype Microsoft.ManagementConsole.DragAndDropVerb pasteType, class Microsoft.ManagementConsole.SyncStatus status)
0x1bf6  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.PasteResponse::set_AcceptPaste(bool)
0x1bfb  ldarg.2
0x1bfc  ldloc.2
0x1bfd  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.IRequestStatus::ProcessResponse(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.RequestResponse)
0x1c02  leave.s  loc_1C25
0x1c04  ldarg.0
0x1c05  call     instance class Microsoft.ManagementConsole.NamespaceSnapInBase Microsoft.ManagementConsole.Node::get_SnapIn()
0x1c0a  ldloc.1
0x1c0b  callvirt instance void Microsoft.ManagementConsole.SnapInBase::RemoveSharedData(class Microsoft.ManagementConsole.SharedData sharedData)
0x1c10  endfinally
0x1c11  ldarg.1
0x1c12  isinst   [MMCFxCommon]Microsoft.ManagementConsole.Internal.CutOrMoveNodeRequestInfo
0x1c17  brfalse.s loc_1C25
0x1c19  ldarg.0
0x1c1a  ldarg.2
0x1c1b  newobj   instance void Microsoft.ManagementConsole.AsyncStatus::.ctor(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.IRequestStatus requestStatus)
0x1c20  callvirt instance void Microsoft.ManagementConsole.ScopeNode::OnCut(class Microsoft.ManagementConsole.AsyncStatus status)
0x1c25  ret
```
