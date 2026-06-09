# Microsoft.EventViewer.SnapIn.FormControlBase::UpdateActions

- ea: `0x7cf0`
- end: `0x7cfc`
- name: `Microsoft.EventViewer.SnapIn.FormControlBase::UpdateActions`
- size: `12`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x4d70`
- `0x4f30`
- `0x57a0`
- `0x6420`
- `0x80a0`
- `0x9670`
- `0x97f0`
- `0x9c80`
- `0x9d10`

## callees

- `0x8120`

## pseudocode

```c

```

## disassembly

```asm
0x7cf0  ldarg.0
0x7cf1  call     class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_DirectChannelVisibleAction()
0x7cf6  call     instance void Microsoft.EventViewer.SnapIn.FormControlBase::AddOrModifyAction(class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction action)
0x7cfb  ret
```
