# Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_DisplayName

- ea: `0x371b0`
- end: `0x37452`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_DisplayName`
- size: `674`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x31040`

## callees

- `0x12ed0`
- `0x371b0`

## string_xrefs

- `0x37350`: `ActionCopyToClipboard`
- `0x37360`: `ActionCopyTable`
- `0x37370`: `ActionCopyDetailsAsText`
- `0x372a0`: `ActionOpenLog`
- `0x372f0`: `ActionAddTask`
- `0x37320`: `ActionAddTaskToEvent`
- `0x37390`: `ActionOpenItem`
- `0x373a0`: `ActionAddRemoveColumns`
- `0x373c0`: `ActionRemoveGrouping`
- `0x373d0`: `ActionRemoveSorting`
- `0x37438`: `ActionCopyView`

## pseudocode

```c

```

## disassembly

```asm
0x371b0  ldsfld   string [mscorlib]System.String::Empty
0x371b5  stloc.0
0x371b6  ldarg.0
0x371b7  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::actionId
0x371bc  stloc.1
0x371bd  ldloc.1
0x371be  switch   loc_37260, loc_37270, loc_37280, loc_37290, loc_372A0, loc_372B0, loc_372C0, loc_372D0, loc_372E0, loc_372F0, loc_37300, loc_37310, loc_37450, loc_37450, loc_37320, loc_37330, loc_37450, loc_37340, loc_37450, loc_37350, loc_37360, loc_37370, loc_37380, loc_37390, loc_373A0, loc_37450, loc_373B0, loc_373C0, loc_373DD, loc_373EA, loc_373F7, loc_37404, loc_37411, loc_373D0, loc_3741E, loc_3742B, loc_37438, loc_37445
0x3725b  br       loc_37450
0x37260  ldstr    aActionnewview// "ActionNewView"
0x37265  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x3726a  stloc.0
0x3726b  br       loc_37450
0x37270  ldstr    aActionfilter// "ActionFilter"
0x37275  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x3727a  stloc.0
0x3727b  br       loc_37450
0x37280  ldstr    aActionsaveasvi// "ActionSaveAsView"
0x37285  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x3728a  stloc.0
0x3728b  br       loc_37450
0x37290  ldstr    aActionpreviewp// "ActionPreviewPane"
0x37295  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x3729a  stloc.0
0x3729b  br       loc_37450
0x372a0  ldstr    aActionopenlog// "ActionOpenLog"
0x372a5  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x372aa  stloc.0
0x372ab  br       loc_37450
0x372b0  ldstr    aActionexportlo// "ActionExportLog"
0x372b5  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x372ba  stloc.0
0x372bb  br       loc_37450
0x372c0  ldstr    aActionproperti// "ActionProperties"
0x372c5  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x372ca  stloc.0
0x372cb  br       loc_37450
0x372d0  ldstr    aEnablelog// "EnableLog"
0x372d5  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x372da  stloc.0
0x372db  br       loc_37450
0x372e0  ldstr    aActioneventpro// "ActionEventProperties"
0x372e5  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x372ea  stloc.0
0x372eb  br       loc_37450
0x372f0  ldstr    aActionaddtask// "ActionAddTask"
0x372f5  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x372fa  stloc.0
0x372fb  br       loc_37450
0x37300  ldstr    aActionrefresh// "ActionRefresh"
0x37305  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x3730a  stloc.0
0x3730b  br       loc_37450
0x37310  ldstr    aActionclearlog// "ActionClearLog"
0x37315  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x3731a  stloc.0
0x3731b  br       loc_37450
0x37320  ldstr    aActionaddtaskt// "ActionAddTaskToEvent"
0x37325  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x3732a  stloc.0
0x3732b  br       loc_37450
0x37330  ldstr    aActionsorteven// "ActionSortEvent"
0x37335  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x3733a  stloc.0
0x3733b  br       loc_37450
0x37340  ldstr    aActionaddadmin// "ActionAddAdminView"
0x37345  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x3734a  stloc.0
0x3734b  br       loc_37450
0x37350  ldstr    aActioncopytocl// "ActionCopyToClipboard"
0x37355  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x3735a  stloc.0
0x3735b  br       loc_37450
0x37360  ldstr    aActioncopytabl// "ActionCopyTable"
0x37365  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x3736a  stloc.0
0x3736b  br       loc_37450
0x37370  ldstr    aActioncopydeta// "ActionCopyDetailsAsText"
0x37375  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x3737a  stloc.0
0x3737b  br       loc_37450
0x37380  ldstr    aActionconnectr// "ActionConnectRemote"
0x37385  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x3738a  stloc.0
0x3738b  br       loc_37450
0x37390  ldstr    aActionopenitem// "ActionOpenItem"
0x37395  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x3739a  stloc.0
0x3739b  br       loc_37450
0x373a0  ldstr    aActionaddremov// "ActionAddRemoveColumns"
0x373a5  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x373aa  stloc.0
0x373ab  br       loc_37450
0x373b0  ldstr    aActiongroupby// "ActionGroupBy"
0x373b5  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x373ba  stloc.0
0x373bb  br       loc_37450
0x373c0  ldstr    aActionremovegr// "ActionRemoveGrouping"
0x373c5  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x373ca  stloc.0
0x373cb  br       loc_37450
0x373d0  ldstr    aActionremoveso// "ActionRemoveSorting"
0x373d5  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x373da  stloc.0
0x373db  br.s     loc_37450
0x373dd  ldstr    aActionexpandal// "ActionExpandAllGroups"
0x373e2  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x373e7  stloc.0
0x373e8  br.s     loc_37450
0x373ea  ldstr    aActioncollapse// "ActionCollapseAllGroups"
0x373ef  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x373f4  stloc.0
0x373f5  br.s     loc_37450
0x373f7  ldstr    aActionshowdire// "ActionShowDirectChannels"
0x373fc  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x37401  stloc.0
0x37402  br.s     loc_37450
0x37404  ldstr    aActionclearfil// "ActionClearFilter"
0x37409  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x3740e  stloc.0
0x3740f  br.s     loc_37450
0x37411  ldstr    aActionfind// "ActionFind"
0x37416  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x3741b  stloc.0
0x3741c  br.s     loc_37450
0x3741e  ldstr    aActionexportvi// "ActionExportView"
0x37423  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x37428  stloc.0
0x37429  br.s     loc_37450
0x3742b  ldstr    aActionimportvi// "ActionImportView"
0x37430  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x37435  stloc.0
0x37436  br.s     loc_37450
0x37438  ldstr    aActioncopyview// "ActionCopyView"
0x3743d  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x37442  stloc.0
0x37443  br.s     loc_37450
0x37445  ldstr    aActionpastevie// "ActionPasteView"
0x3744a  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x3744f  stloc.0
0x37450  ldloc.0
0x37451  ret
```
