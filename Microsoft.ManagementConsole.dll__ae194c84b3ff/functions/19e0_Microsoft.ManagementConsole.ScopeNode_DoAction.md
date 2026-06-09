# Microsoft.ManagementConsole.ScopeNode::DoAction

- ea: `0x19e0`
- end: `0x1a7a`
- name: `Microsoft.ManagementConsole.ScopeNode::DoAction`
- size: `154`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0xe00`

## callees

- `0x670`
- `0x14e0`
- `0x1520`
- `0x19e0`
- `0x1a80`
- `0x1a90`
- `0x2920`
- `0x2a60`
- `0x30e0`
- `0x73b0`
- `0x73d0`

## pseudocode

```c

```

## disassembly

```asm
0x19e0  ldarg.0
0x19e1  call     instance class Microsoft.ManagementConsole.ActionsPaneItemCollection Microsoft.ManagementConsole.ScopeNode::get_ActionsPaneItems()
0x19e6  ldarg.1
0x19e7  callvirt instance class Microsoft.ManagementConsole.ActionsPaneItem Microsoft.ManagementConsole.ActionsPaneItemCollection::GetItemById(int32 itemId)
0x19ec  stloc.0
0x19ed  ldloc.0
0x19ee  brtrue.s loc_19FD
0x19f0  ldarg.0
0x19f1  call     instance class Microsoft.ManagementConsole.ActionsPaneItemCollection Microsoft.ManagementConsole.ScopeNode::get_ActionsPaneHelpItems()
0x19f6  ldarg.1
0x19f7  callvirt instance class Microsoft.ManagementConsole.ActionsPaneItem Microsoft.ManagementConsole.ActionsPaneItemCollection::GetItemById(int32 itemId)
0x19fc  stloc.0
0x19fd  ldloc.0
0x19fe  isinst   Microsoft.ManagementConsole.Action
0x1a03  stloc.1
0x1a04  ldloc.1
0x1a05  brfalse.s loc_1A1F
0x1a07  ldarg.2
0x1a08  newobj   instance void Microsoft.ManagementConsole.AsyncStatus::.ctor(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.IRequestStatus requestStatus)
0x1a0d  stloc.2
0x1a0e  ldloc.1
0x1a0f  ldarg.0
0x1a10  ldloc.2
0x1a11  callvirt instance void Microsoft.ManagementConsole.Action::RaiseTriggeredEvent(object sender, class Microsoft.ManagementConsole.AsyncStatus status)
0x1a16  ldarg.0
0x1a17  ldloc.1
0x1a18  ldloc.2
0x1a19  callvirt instance void Microsoft.ManagementConsole.ScopeNode::OnAction(class Microsoft.ManagementConsole.Action action, class Microsoft.ManagementConsole.AsyncStatus status)
0x1a1e  ret
0x1a1f  ldloc.0
0x1a20  isinst   Microsoft.ManagementConsole.SyncAction
0x1a25  stloc.3
0x1a26  ldloc.3
0x1a27  brfalse.s loc_1A44
0x1a29  ldarg.2
0x1a2a  newobj   instance void Microsoft.ManagementConsole.SyncStatus::.ctor(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.IRequestStatus requestStatus)
0x1a2f  stloc.s  4
0x1a31  ldloc.3
0x1a32  ldarg.0
0x1a33  ldloc.s  4
0x1a35  callvirt instance void Microsoft.ManagementConsole.SyncAction::RaiseTriggeredEvent(object sender, class Microsoft.ManagementConsole.SyncStatus status)
0x1a3a  ldarg.0
0x1a3b  ldloc.3
0x1a3c  ldloc.s  4
0x1a3e  callvirt instance void Microsoft.ManagementConsole.ScopeNode::OnSyncAction(class Microsoft.ManagementConsole.SyncAction action, class Microsoft.ManagementConsole.SyncStatus status)
0x1a43  ret
0x1a44  call     class [System]System.Diagnostics.TraceSource [MMCFxCommon]Microsoft.ManagementConsole.TraceSources::get_ExecutiveSource()
0x1a49  ldc.i4.2
0x1a4a  ldc.i4.s 0xC
0x1a4c  ldstr    aActionWithId0N// "action with Id {0} no longer exists on "...
0x1a51  ldc.i4.2
0x1a52  newarr   [mscorlib]System.Object
0x1a57  stloc.s  5
0x1a59  ldloc.s  5
0x1a5b  ldc.i4.0
0x1a5c  ldarg.1
0x1a5d  box      [mscorlib]System.Int32
0x1a62  stelem.ref
0x1a63  ldloc.s  5
0x1a65  ldc.i4.1
0x1a66  ldarg.0
0x1a67  call     instance int32 Microsoft.ManagementConsole.Node::get_Id()
0x1a6c  box      [mscorlib]System.Int32
0x1a71  stelem.ref
0x1a72  ldloc.s  5
0x1a74  callvirt instance void [System]System.Diagnostics.TraceSource::TraceEvent(valuetype [System]System.Diagnostics.TraceEventType, int32, string, object[])
0x1a79  ret
```
