# Microsoft.EventViewer.SnapIn.EventViewerHomepage::UpdateSelectionDataDisplayName

- ea: `0x79f0`
- end: `0x7a7c`
- name: `Microsoft.EventViewer.SnapIn.EventViewerHomepage::UpdateSelectionDataDisplayName`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x7950`

## callees

- `0x79f0`

## pseudocode

```c

```

## disassembly

```asm
0x79f0  ldarg.1
0x79f1  isinst   [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventSummaryListViewTag
0x79f6  brfalse.s loc_7A35
0x79f8  ldarg.1
0x79f9  isinst   [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventSummaryListViewTag
0x79fe  stloc.0
0x79ff  ldloc.0
0x7a00  callvirt instance bool [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventSummaryListViewTag::get_IsGroupedBySeverityItem()
0x7a05  brfalse.s loc_7A1E
0x7a07  ldarg.0
0x7a08  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_SelectionData()
0x7a0d  ldloc.0
0x7a0e  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsGroupedBySeverity [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventSummaryListViewTag::get_GroupedBySeverity()
0x7a13  callvirt instance string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsGroupedBySeverity::get_SeverityName()
0x7a18  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData::set_DisplayName(string)
0x7a1d  ret
0x7a1e  ldarg.0
0x7a1f  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_SelectionData()
0x7a24  ldloc.0
0x7a25  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.InformationForContructingQuery [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventSummaryListViewTag::get_QueryInfo()
0x7a2a  callvirt instance string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.InformationForContructingQuery::get_SelectionDisplayString()
0x7a2f  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData::set_DisplayName(string)
0x7a34  ret
0x7a35  ldarg.1
0x7a36  isinst   [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.RecentViewsData
0x7a3b  brfalse.s loc_7A5B
0x7a3d  ldarg.1
0x7a3e  isinst   [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.RecentViewsData
0x7a43  stloc.1
0x7a44  ldarg.0
0x7a45  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_SelectionData()
0x7a4a  ldloc.1
0x7a4b  callvirt instance class [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.RecentViewsData/MmcNodePath [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.RecentViewsData::get_NodePath()
0x7a50  callvirt instance string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.RecentViewsData/MmcNodePath::get_NodePathString()
0x7a55  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData::set_DisplayName(string)
0x7a5a  ret
0x7a5b  ldarg.1
0x7a5c  isinst   [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.LogSummaryListViewData
0x7a61  brfalse.s loc_7A7B
0x7a63  ldarg.1
0x7a64  isinst   [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.LogSummaryListViewData
0x7a69  stloc.2
0x7a6a  ldarg.0
0x7a6b  call     instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::get_SelectionData()
0x7a70  ldloc.2
0x7a71  callvirt instance string [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.LogSummaryListViewData::get_Name()
0x7a76  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SelectionData::set_DisplayName(string)
0x7a7b  ret
```
