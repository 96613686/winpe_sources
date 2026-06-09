# Microsoft.EventViewer.SnapIn.FormControlBase::GetAction

- ea: `0x8010`
- end: `0x8045`
- name: `Microsoft.EventViewer.SnapIn.FormControlBase::GetAction`
- size: `53`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x4c40`
- `0x5d60`
- `0x8120`
- `0x99a0`

## callees

- `0x7fb0`
- `0x8010`
- `0x8380`

## pseudocode

```c

```

## disassembly

```asm
0x8010  ldarg.2
0x8011  ldnull
0x8012  stind.ref
0x8013  ldc.i4.0
0x8014  stloc.0
0x8015  ldnull
0x8016  stloc.1
0x8017  ldarg.1
0x8018  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Identifier()
0x801d  ldc.i4.s 0x1E
0x801f  bne.un.s loc_802B
0x8021  ldarg.1
0x8022  ldloca.s 1
0x8024  call     void Microsoft.EventViewer.SnapIn.FormControlBase::GetShowDirectChannelAction(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction action, [out] class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionsPaneItem& actionOut)
0x8029  ldc.i4.1
0x802a  stloc.0
0x802b  ldloc.0
0x802c  brfalse.s loc_8043
0x802e  ldloc.1
0x802f  brfalse.s loc_8043
0x8031  ldloc.1
0x8032  isinst   [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase
0x8037  stloc.2
0x8038  ldarg.0
0x8039  ldloca.s 2
0x803b  call     instance void Microsoft.EventViewer.SnapIn.FormControlBase::SetTriggeredForAction(class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase& actBase)
0x8040  ldarg.2
0x8041  ldloc.1
0x8042  stind.ref
0x8043  ldloc.0
0x8044  ret
```
