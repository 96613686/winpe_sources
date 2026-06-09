# Microsoft.EventViewer.SnapIn.MMCEventsFolderView::ScopeNodeChanged

- ea: `0x4e80`
- end: `0x4e91`
- name: `Microsoft.EventViewer.SnapIn.MMCEventsFolderView::ScopeNodeChanged`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x4dc0`
- `0x4e80`

## pseudocode

```c

```

## disassembly

```asm
0x4e80  ldarg.1
0x4e81  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Identifier()
0x4e86  ldc.i4.s 0xA
0x4e88  bne.un.s loc_4E90
0x4e8a  ldarg.0
0x4e8b  call     instance void Microsoft.EventViewer.SnapIn.MMCEventsFolderView::InitializeResultsView()
0x4e90  ret
```
