# Microsoft.EventViewer.SnapIn.FormControlBase::SetTriggeredForAction

- ea: `0x8380`
- end: `0x83c2`
- name: `Microsoft.EventViewer.SnapIn.FormControlBase::SetTriggeredForAction`
- size: `66`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4c40`
- `0x5d60`
- `0x8010`
- `0x99a0`

## callees

- `0x8380`

## pseudocode

```c

```

## disassembly

```asm
0x8380  ldarg.1
0x8381  ldind.ref
0x8382  isinst   [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Action
0x8387  stloc.0
0x8388  ldloc.0
0x8389  brfalse.s loc_83A1
0x838b  ldloc.0
0x838c  ldarg.0
0x838d  ldftn    instance void Microsoft.EventViewer.SnapIn.FormControlBase::OnAction(object sender, class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionEventArgs e)
0x8393  newobj   instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Action/ActionEventHandler::.ctor(object, native int)
0x8398  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Action::add_Triggered(class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.Action/ActionEventHandler)
0x839d  ldarg.1
0x839e  ldloc.0
0x839f  stind.ref
0x83a0  ret
0x83a1  ldarg.1
0x83a2  ldind.ref
0x83a3  isinst   [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SyncAction
0x83a8  stloc.1
0x83a9  ldloc.1
0x83aa  brfalse.s loc_83C1
0x83ac  ldloc.1
0x83ad  ldarg.0
0x83ae  ldftn    instance void Microsoft.EventViewer.SnapIn.FormControlBase::OnAction(object sender, class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SyncActionEventArgs e)
0x83b4  newobj   instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SyncAction/SyncActionEventHandler::.ctor(object, native int)
0x83b9  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SyncAction::add_Triggered(class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SyncAction/SyncActionEventHandler)
0x83be  ldarg.1
0x83bf  ldloc.1
0x83c0  stind.ref
0x83c1  ret
```
