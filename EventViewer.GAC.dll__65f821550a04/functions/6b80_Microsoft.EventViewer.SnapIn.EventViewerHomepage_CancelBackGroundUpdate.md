# Microsoft.EventViewer.SnapIn.EventViewerHomepage::CancelBackGroundUpdate

- ea: `0x6b80`
- end: `0x6b94`
- name: `Microsoft.EventViewer.SnapIn.EventViewerHomepage::CancelBackGroundUpdate`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x6b30`

## callees

- `0x6b80`

## pseudocode

```c

```

## disassembly

```asm
0x6b80  ldarg.0
0x6b81  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl Microsoft.EventViewer.SnapIn.EventViewerHomepage::eventHomeControl
0x6b86  brfalse.s loc_6B93
0x6b88  ldarg.0
0x6b89  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl Microsoft.EventViewer.SnapIn.EventViewerHomepage::eventHomeControl
0x6b8e  callvirt instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::CancelReading()
0x6b93  ret
```
