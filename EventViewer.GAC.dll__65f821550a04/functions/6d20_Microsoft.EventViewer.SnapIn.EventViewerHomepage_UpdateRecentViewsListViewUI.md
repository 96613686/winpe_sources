# Microsoft.EventViewer.SnapIn.EventViewerHomepage::UpdateRecentViewsListViewUI

- ea: `0x6d20`
- end: `0x6d39`
- name: `Microsoft.EventViewer.SnapIn.EventViewerHomepage::UpdateRecentViewsListViewUI`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x68d0`

## callees

- `0x6d20`

## pseudocode

```c

```

## disassembly

```asm
0x6d20  ldarg.1
0x6d21  brfalse.s loc_6D38
0x6d23  ldarg.1
0x6d24  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.RecentViewsData>::get_Count()
0x6d29  ldc.i4.0
0x6d2a  ble.s    loc_6D38
0x6d2c  ldarg.0
0x6d2d  ldfld    class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl Microsoft.EventViewer.SnapIn.EventViewerHomepage::eventHomeControl
0x6d32  ldarg.1
0x6d33  callvirt instance void [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventHomeControl::UpdateRecentViewsListViewUI(class [mscorlib]System.Collections.Generic.List`1<class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.RecentViewsData>)
0x6d38  ret
```
