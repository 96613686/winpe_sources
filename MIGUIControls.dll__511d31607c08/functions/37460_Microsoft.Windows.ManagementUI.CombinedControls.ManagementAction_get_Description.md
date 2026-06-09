# Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Description

- ea: `0x37460`
- end: `0x376f2`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::get_Description`
- size: `658`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x12ed0`
- `0x37460`

## string_xrefs

- `0x37550`: `ActionOpenLogDesc`
- `0x37590`: `ActionAddTaskDesc`
- `0x375c0`: `ActionAddTaskToEventDesc`
- `0x375f0`: `ActionCopyToClipboardDesc`
- `0x37600`: `ActionCopyTableDesc`
- `0x37610`: `ActionCopyDetailsAsTextDesc`
- `0x37630`: `ActionOpenItemDesc`
- `0x37640`: `ActionAddRemoveColumnsDesc`
- `0x37660`: `ActionRemoveGroupingDesc`
- `0x37670`: `ActionRemoveSortingDesc`
- `0x376d8`: `ActionCopyViewDesc`

## pseudocode

```c

```

## disassembly

```asm
0x37460  ldsfld   string [mscorlib]System.String::Empty
0x37465  stloc.0
0x37466  ldarg.0
0x37467  ldfld    valuetype Microsoft.Windows.ManagementUI.CombinedControls.ActionIdentifiers Microsoft.Windows.ManagementUI.CombinedControls.ManagementAction::actionId
0x3746c  stloc.1
0x3746d  ldloc.1
0x3746e  switch   loc_37510, loc_37520, loc_37530, loc_37540, loc_37550, loc_37560, loc_376F0, loc_37570, loc_37580, loc_37590, loc_375A0, loc_375B0, loc_376F0, loc_376F0, loc_375C0, loc_375D0, loc_376F0, loc_375E0, loc_376F0, loc_375F0, loc_37600, loc_37610, loc_37620, loc_37630, loc_37640, loc_376F0, loc_37650, loc_37660, loc_3767D, loc_3768A, loc_37697, loc_376A4, loc_376B1, loc_37670, loc_376BE, loc_376CB, loc_376D8, loc_376E5
0x3750b  br       loc_376F0
0x37510  ldstr    aActionnewviewd// "ActionNewViewDesc"
0x37515  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x3751a  stloc.0
0x3751b  br       loc_376F0
0x37520  ldstr    aActionfilterde// "ActionFilterDesc"
0x37525  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x3752a  stloc.0
0x3752b  br       loc_376F0
0x37530  ldstr    aActionsaveasvi_0// "ActionSaveAsViewDesc"
0x37535  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x3753a  stloc.0
0x3753b  br       loc_376F0
0x37540  ldstr    aActionpreviewp_0// "ActionPreviewPaneDesc"
0x37545  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x3754a  stloc.0
0x3754b  br       loc_376F0
0x37550  ldstr    aActionopenlogd// "ActionOpenLogDesc"
0x37555  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x3755a  stloc.0
0x3755b  br       loc_376F0
0x37560  ldstr    aActionexportlo_0// "ActionExportLogDesc"
0x37565  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x3756a  stloc.0
0x3756b  br       loc_376F0
0x37570  ldstr    aEnablelogdiscr// "EnableLogDiscription"
0x37575  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x3757a  stloc.0
0x3757b  br       loc_376F0
0x37580  ldstr    aActioneventpro_0// "ActionEventPropertiesDesc"
0x37585  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x3758a  stloc.0
0x3758b  br       loc_376F0
0x37590  ldstr    aActionaddtaskd// "ActionAddTaskDesc"
0x37595  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x3759a  stloc.0
0x3759b  br       loc_376F0
0x375a0  ldstr    aActionrefreshd// "ActionRefreshDesc"
0x375a5  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x375aa  stloc.0
0x375ab  br       loc_376F0
0x375b0  ldstr    aActionclearlog_0// "ActionClearLogDesc"
0x375b5  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x375ba  stloc.0
0x375bb  br       loc_376F0
0x375c0  ldstr    aActionaddtaskt_0// "ActionAddTaskToEventDesc"
0x375c5  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x375ca  stloc.0
0x375cb  br       loc_376F0
0x375d0  ldstr    aActionsortdesc// "ActionSortDesc"
0x375d5  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x375da  stloc.0
0x375db  br       loc_376F0
0x375e0  ldstr    aActionaddadmin_0// "ActionAddAdminViewDesc"
0x375e5  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x375ea  stloc.0
0x375eb  br       loc_376F0
0x375f0  ldstr    aActioncopytocl_0// "ActionCopyToClipboardDesc"
0x375f5  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x375fa  stloc.0
0x375fb  br       loc_376F0
0x37600  ldstr    aActioncopytabl_0// "ActionCopyTableDesc"
0x37605  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x3760a  stloc.0
0x3760b  br       loc_376F0
0x37610  ldstr    aActioncopydeta_0// "ActionCopyDetailsAsTextDesc"
0x37615  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x3761a  stloc.0
0x3761b  br       loc_376F0
0x37620  ldstr    aActionconnectr_0// "ActionConnectRemoteDesc"
0x37625  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x3762a  stloc.0
0x3762b  br       loc_376F0
0x37630  ldstr    aActionopenitem_0// "ActionOpenItemDesc"
0x37635  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x3763a  stloc.0
0x3763b  br       loc_376F0
0x37640  ldstr    aActionaddremov_0// "ActionAddRemoveColumnsDesc"
0x37645  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x3764a  stloc.0
0x3764b  br       loc_376F0
0x37650  ldstr    aActiongroupbyd// "ActionGroupByDesc"
0x37655  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x3765a  stloc.0
0x3765b  br       loc_376F0
0x37660  ldstr    aActionremovegr_0// "ActionRemoveGroupingDesc"
0x37665  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x3766a  stloc.0
0x3766b  br       loc_376F0
0x37670  ldstr    aActionremoveso_0// "ActionRemoveSortingDesc"
0x37675  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x3767a  stloc.0
0x3767b  br.s     loc_376F0
0x3767d  ldstr    aActionexpandal_0// "ActionExpandAllGroupsDesc"
0x37682  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x37687  stloc.0
0x37688  br.s     loc_376F0
0x3768a  ldstr    aActioncollapse_0// "ActionCollapseAllGroupsDesc"
0x3768f  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x37694  stloc.0
0x37695  br.s     loc_376F0
0x37697  ldstr    aActionshowdire_0// "ActionShowDirectChannelsDesc"
0x3769c  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x376a1  stloc.0
0x376a2  br.s     loc_376F0
0x376a4  ldstr    aActionclearfil_0// "ActionClearFilterDesc"
0x376a9  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x376ae  stloc.0
0x376af  br.s     loc_376F0
0x376b1  ldstr    aActionfinddesc// "ActionFindDesc"
0x376b6  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x376bb  stloc.0
0x376bc  br.s     loc_376F0
0x376be  ldstr    aActionexportvi_0// "ActionExportViewDesc"
0x376c3  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x376c8  stloc.0
0x376c9  br.s     loc_376F0
0x376cb  ldstr    aActionimportvi_0// "ActionImportViewDesc"
0x376d0  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x376d5  stloc.0
0x376d6  br.s     loc_376F0
0x376d8  ldstr    aActioncopyview_0// "ActionCopyViewDesc"
0x376dd  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x376e2  stloc.0
0x376e3  br.s     loc_376F0
0x376e5  ldstr    aActionpastevie_0// "ActionPasteViewDesc"
0x376ea  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x376ef  stloc.0
0x376f0  ldloc.0
0x376f1  ret
```
