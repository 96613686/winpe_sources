# Microsoft.SharePoint.WebControls.ActionsMenu::SetMenuItemProperties

- ea: `0x8490b0`
- end: `0x84a59a`
- name: `Microsoft.SharePoint.WebControls.ActionsMenu::SetMenuItemProperties`
- size: `5354`
- prototype: ``
- caller_count: `2`
- callee_count: `86`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x84a5c0`
- `0x84a670`

## callees

- `0x189150`
- `0x18daf0`
- `0x197690`
- `0x1a1ea0`
- `0x1a2030`
- `0x26f0e0`
- `0x342910`
- `0x342ec0`
- `0x3431e0`
- `0x343230`
- `0x3438f0`
- `0x343930`
- `0x343980`
- `0x343e80`
- `0x344680`
- `0x344c40`
- `0x346530`
- `0x346c40`
- `0x3472e0`
- `0x347690`
- `0x347ec0`
- `0x3559a0`
- `0x3559e0`
- `0x3564a0`
- `0x356750`
- `0x4cdd90`
- `0x4cf6b0`
- `0x4cf7e0`
- `0x4d0990`
- `0x4d09b0`
- `0x4d0e90`
- `0x4dae10`
- `0x4daea0`
- `0x52a050`
- `0x52a120`
- `0x535ba0`
- `0x577060`
- `0x5ba850`
- `0x5ba880`
- `0x5bae00`
- `0x5bae20`
- `0x5bb0c0`
- `0x5bbe90`
- `0x5c10e0`
- `0x5c24f0`
- `0x5c3b50`
- `0x5c4420`
- `0x5c5690`
- `0x5c5c00`
- `0x5cce10`

## string_xrefs

- `0x84939f`: `TaskPaneButton`
- `0x8493b4`: `ShowHideTaskPane(); return false;`
- `0x84944a`: `OpenInExplorer`
- `0x84960d`: `var diagramButtonAppName = GetDiagramLaunchInstalled();\nvar diagramBtnText = '`
- `0x849707`: `ProjectTaskButton`
- `0x849824`: `project_task_js`
- `0x849963`: `project_task_js`
- `0x849829`: `var projectTaskButtonAppName = 'Microsoft Project';\nvar projectTaskBtnText = '`
- `0x849968`: `var projectTaskButtonAppName = 'Microsoft Project';\nvar projectTaskBtnText = '`
- `0x84982e`: `ToolBarMenuItemProjectTaskTextPrefix`
- `0x84996d`: `ToolBarMenuItemProjectTaskTextPrefix`
- `0x849843`: `' + projectTaskButtonAppName;\n`
- `0x849982`: `' + projectTaskButtonAppName;\n`
- `0x84985f`: `javaScript:CoreInvoke('OpenTasks', '`
- `0x8498d7`: `javascript:projectTaskBtnText`
- `0x8499b0`: `javascript:projectTaskBtnText`
- `0x8498e2`: `!projectTaskButtonAppName`
- `0x8499bb`: `!projectTaskButtonAppName`
- `0x849992`: `SP.Ribbon.HierarchyTaskList.OpenSchedule(SP.ClientContext.get_current().get_web(), new SP.Guid('`
- `0x849a6c`: `/images/menu');\nvar offlineBtnText = '';var offlineBtnImg = '';if(objStsSync){ offlineBtnText = objStsSync.BtnText;\nofflineBtnImg = objStsSync.BtnImagePath;\n}`
- `0x849acb`: `/images/menu');\nif(objStsSync){ offlineBtnText = objStsSync.BtnText;\nofflineBtnImg = objStsSync.BtnImagePath;\n}}, 'strings.js');`
- `0x849d5e`: `ExportToSpreadsheet`
- `0x849e60`: `_vti_bin/owssvr.dll?CS=65001&Using=`
- `0x849eaa`: `&CacheControl=1`
- `0x849f42`: `_vti_bin/owssvr.dll?CS=65001`
- `0x849fb6`: `var databaseBtnText = '';var databaseBtnDesc = '';var fDBInstalled = false;var ExpDatabase = GetDataBaseInstalled();\ntry{ \ndatabaseBtnText = ExpDatabase.MenuTitle;databaseBtnDesc = ExpDatabase.MenuDescription;fDBInstalled = true;\n} catch(e){}`
- `0x849fd7`: `!fDBInstalled`
- `0x84a151`: `DeletePictures`
- `0x84a171`: `CoreInvoke('DeleteImages');`
- `0x84a410`: `AddToMyLinksButton`
- `0x84a553`: `ToolBarMenuItemMyLinksDescription`

## pseudocode

```c

```

## disassembly

```asm
0x8490b0  ldarg.0
0x8490b1  call     instance class Microsoft.SharePoint.WebControls.MenuTemplate Microsoft.SharePoint.WebControls.ToolBarMenuButton::get_MenuTemplateControl()
0x8490b6  ldc.i4.1
0x8490b7  callvirt instance void Microsoft.SharePoint.WebControls.MenuTemplate::set_LargeIconMode(bool value)
0x8490bc  ldarg.0
0x8490bd  call     instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.WebControls.ToolBarMenuButton::get_ViewId()
0x8490c2  stloc.s  0x33
0x8490c4  ldloca.s 0x33
0x8490c6  ldstr    aB// "B"
0x8490cb  call     instance string [mscorlib]System.Guid::ToString(string)
0x8490d0  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x8490d5  stloc.1
0x8490d6  ldarg.0
0x8490d7  call     instance class Microsoft.SharePoint.SPContext Microsoft.SharePoint.WebControls.TemplateBasedControl::get_RenderContext()
0x8490dc  callvirt instance class Microsoft.SharePoint.SPViewContext Microsoft.SharePoint.SPContext::get_ViewContext()
0x8490e1  callvirt instance valuetype Microsoft.SharePoint.WebPartPages.ViewType Microsoft.SharePoint.SPViewContext::get_ViewType()
0x8490e6  stloc.2
0x8490e7  ldarg.0
0x8490e8  call     instance class Microsoft.SharePoint.SPContext Microsoft.SharePoint.WebControls.TemplateBasedControl::get_RenderContext()
0x8490ed  callvirt instance class Microsoft.SharePoint.SPViewContext Microsoft.SharePoint.SPContext::get_ViewContext()
0x8490f2  callvirt instance string Microsoft.SharePoint.SPViewContext::get_Qualifier()
0x8490f7  stloc.3
0x8490f8  call     string Microsoft.SharePoint.WebControls.SPRibbon::get_OriginalServerRelativeRequestPath()
0x8490fd  ldc.i4.1
0x8490fe  call     string Microsoft.SharePoint.Utilities.SPHttpUtility::UrlPathEncodeEx(string urlToEncode, bool allowHashParameter)
0x849103  call     string Microsoft.SharePoint.Utilities.SPHttpUtility::EcmaScriptStringLiteralEncode(string scriptLiteralToEncode)
0x849108  stloc.s  4
0x84910a  ldarg.0
0x84910b  call     instance class Microsoft.SharePoint.SPContext Microsoft.SharePoint.WebControls.TemplateBasedControl::get_RenderContext()
0x849110  callvirt instance string Microsoft.SharePoint.SPContext::get_RootFolderUrl()
0x849115  call     string Microsoft.SharePoint.Utilities.SPHttpUtility::UrlKeyValueEncode(string keyOrValueToEncode)
0x84911a  stloc.s  5
0x84911c  ldarg.0
0x84911d  ldstr    aEditingridbutt// "EditInGridButton"
0x849122  call     instance class Microsoft.SharePoint.WebControls.MenuItemTemplate Microsoft.SharePoint.WebControls.ToolBarMenuButton::GetMenuItem(string menuItemId)
0x849127  stloc.0
0x849128  ldloc.0
0x849129  brfalse  loc_849335
0x84912e  call     int32 Microsoft.SharePoint.Utilities.SPUtility::get_ContextCompatibilityLevel()
0x849133  ldc.i4.s 0xE
0x849135  ble.s    loc_849143
0x849137  ldloc.0
0x849138  ldc.i4.0
0x849139  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x84913e  br       loc_849335
0x849143  ldarg.0
0x849144  callvirt instance class [System.Web]System.Web.UI.Control [System.Web]System.Web.UI.Control::get_Parent()
0x849149  stloc.s  6
0x84914b  br.s     loc_849156
0x84914d  ldloc.s  6
0x84914f  callvirt instance class [System.Web]System.Web.UI.Control [System.Web]System.Web.UI.Control::get_Parent()
0x849154  stloc.s  6
0x849156  ldloc.s  6
0x849158  brfalse.s loc_849175
0x84915a  ldloc.s  6
0x84915c  isinst   [System.Web]System.Web.UI.HtmlControls.HtmlForm
0x849161  brtrue.s loc_849175
0x849163  ldloc.s  6
0x849165  isinst   Microsoft.SharePoint.WebPartPages.ListViewWebPart
0x84916a  brtrue.s loc_849175
0x84916c  ldloc.s  6
0x84916e  isinst   Microsoft.SharePoint.WebPartPages.XsltListViewWebPart
0x849173  brfalse.s loc_84914D
0x849175  ldloc.s  6
0x849177  isinst   Microsoft.SharePoint.WebPartPages.WebPart
0x84917c  stloc.s  7
0x84917e  ldarg.0
0x84917f  call     instance class Microsoft.SharePoint.SPView Microsoft.SharePoint.WebControls.ToolBarMenuButton::get_View()
0x849184  brfalse.s loc_8491C5
0x849186  ldarg.0
0x849187  call     instance class Microsoft.SharePoint.SPView Microsoft.SharePoint.WebControls.ToolBarMenuButton::get_View()
0x84918c  callvirt instance string Microsoft.SharePoint.SPView::get_Title()
0x849191  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x849196  brtrue.s loc_8491C5
0x849198  ldloc.2
0x849199  ldc.i4.1
0x84919a  beq.s    loc_8491C5
0x84919c  ldloc.2
0x84919d  ldc.i4.4
0x84919e  beq.s    loc_8491C5
0x8491a0  ldloc.s  7
0x8491a2  brtrue.s loc_8491AB
0x8491a4  call     bool Microsoft.SharePoint.WebControls.SPRibbon::get_ToolbarRibbonAdapterDataRenderingOnly()
0x8491a9  brfalse.s loc_8491C5
0x8491ab  ldloc.s  7
0x8491ad  brfalse.s loc_8491B8
0x8491af  ldloc.s  7
0x8491b1  callvirt instance bool [System.Web]System.Web.UI.WebControls.WebParts.WebPart::get_IsStandalone()
0x8491b6  brtrue.s loc_8491C5
0x8491b8  ldarg.0
0x8491b9  callvirt instance class Microsoft.SharePoint.SPList Microsoft.SharePoint.WebControls.ToolBarMenuButton::get_List()
0x8491be  callvirt instance bool Microsoft.SharePoint.SPList::get_DisableGridEditing()
0x8491c3  brfalse.s loc_8491D1
0x8491c5  ldloc.0
0x8491c6  ldc.i4.0
0x8491c7  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x8491cc  br       loc_8492EA
0x8491d1  ldarg.0
0x8491d2  call     instance bool Microsoft.SharePoint.WebControls.ToolBarMenuButton::get_DoclibExplorerView()
0x8491d7  brfalse.s loc_8491E5
0x8491d9  ldloc.0
0x8491da  ldc.i4.0
0x8491db  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x8491e0  br       loc_8492EA
0x8491e5  ldarg.0
0x8491e6  call     instance class Microsoft.SharePoint.SPContext Microsoft.SharePoint.WebControls.TemplateBasedControl::get_RenderContext()
0x8491eb  callvirt instance bool Microsoft.SharePoint.SPContext::get_IsInsideDataView()
0x8491f0  brfalse.s loc_8491FE
0x8491f2  ldloc.0
0x8491f3  ldc.i4.0
0x8491f4  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x8491f9  br       loc_8492EA
0x8491fe  ldarg.0
0x8491ff  callvirt instance class Microsoft.SharePoint.SPList Microsoft.SharePoint.WebControls.ToolBarMenuButton::get_List()
0x849204  callvirt instance bool Microsoft.SharePoint.SPList::get_HasExternalDataSource()
0x849209  brfalse.s loc_849217
0x84920b  ldloc.0
0x84920c  ldc.i4.0
0x84920d  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x849212  br       loc_8492EA
0x849217  ldarg.0
0x849218  ldfld    bool Microsoft.SharePoint.WebControls.ActionsMenu::m_fAllMeetings
0x84921d  brfalse.s loc_84922B
0x84921f  ldloc.0
0x849220  ldc.i4.0
0x849221  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x849226  br       loc_8492EA
0x84922b  ldarg.0
0x84922c  callvirt instance class Microsoft.SharePoint.SPList Microsoft.SharePoint.WebControls.ToolBarMenuButton::get_List()
0x849231  callvirt instance valuetype Microsoft.SharePoint.SPBaseType Microsoft.SharePoint.SPList::get_BaseType()
0x849236  brtrue.s loc_849253
0x849238  ldarg.0
0x849239  callvirt instance class Microsoft.SharePoint.SPList Microsoft.SharePoint.WebControls.ToolBarMenuButton::get_List()
0x84923e  callvirt instance valuetype Microsoft.SharePoint.SPListTemplateType Microsoft.SharePoint.SPList::get_BaseTemplate()
0x849243  ldc.i4.s 0x6C
0x849245  bne.un.s loc_849253
0x849247  ldloc.0
0x849248  ldc.i4.0
0x849249  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x84924e  br       loc_8492EA
0x849253  ldarg.0
0x849254  callvirt instance class Microsoft.SharePoint.SPList Microsoft.SharePoint.WebControls.ToolBarMenuButton::get_List()
0x849259  ldc.i4.4
0x84925a  conv.i8
0x84925b  ldc.i4.1
0x84925c  callvirt instance bool Microsoft.SharePoint.SPList::DoesUserHavePermissionsForUI(valuetype Microsoft.SharePoint.SPBasePermissions permissionMask, bool checkFolder)
0x849261  brtrue.s loc_849298
0x849263  ldloc.0
0x849264  ldstr    aToolbarmenuite_10// "ToolBarMenuItemViewInDatasheet"
0x849269  ldc.i4.0
0x84926a  newarr   [mscorlib]System.Object
0x84926f  call     string Microsoft.SharePoint.SPResource::GetString(string name, object[] values)
0x849274  callvirt instance void Microsoft.SharePoint.WebControls.MenuItemTemplate::set_Text(string value)
0x849279  ldloc.0
0x84927a  ldstr    aToolbarmenuite_11// "ToolBarMenuItemViewInDatasheetDescripti"...
0x84927f  ldc.i4.0
0x849280  newarr   [mscorlib]System.Object
0x849285  call     string Microsoft.SharePoint.SPResource::GetString(string name, object[] values)
0x84928a  callvirt instance void Microsoft.SharePoint.WebControls.MenuItemTemplate::set_Description(string value)
0x84928f  ldloc.0
0x849290  ldc.i4.1
0x849291  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x849296  br.s     loc_8492EA
0x849298  ldarg.0
0x849299  callvirt instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.WebControls.TemplateBasedControl::get_Web()
0x84929e  ldc.i8   0x3000000000
0x8492a7  callvirt instance bool Microsoft.SharePoint.SPSecurableObject::DoesUserHavePermissions(valuetype Microsoft.SharePoint.SPBasePermissions permissionMask)
0x8492ac  brtrue.s loc_8492B7
0x8492ae  ldloc.0
0x8492af  ldc.i4.0
0x8492b0  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x8492b5  br.s     loc_8492EA
0x8492b7  ldloc.0
0x8492b8  ldstr    aToolbarmenuite_12// "ToolBarMenuItemEditInDatasheet"
0x8492bd  ldc.i4.0
0x8492be  newarr   [mscorlib]System.Object
0x8492c3  call     string Microsoft.SharePoint.SPResource::GetString(string name, object[] values)
0x8492c8  callvirt instance void Microsoft.SharePoint.WebControls.MenuItemTemplate::set_Text(string value)
0x8492cd  ldloc.0
0x8492ce  ldstr    aToolbarmenuite_13// "ToolBarMenuItemEditInDatasheetDescripti"...
0x8492d3  ldc.i4.0
0x8492d4  newarr   [mscorlib]System.Object
0x8492d9  call     string Microsoft.SharePoint.SPResource::GetString(string name, object[] values)
0x8492de  callvirt instance void Microsoft.SharePoint.WebControls.MenuItemTemplate::set_Description(string value)
0x8492e3  ldloc.0
0x8492e4  ldc.i4.1
0x8492e5  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x8492ea  ldloc.0
0x8492eb  ldstr    aBrowserisIeBro// "(!(browseris.ie) || (browseris.win64bit"...
0x8492f0  callvirt instance void Microsoft.SharePoint.WebControls.MenuItemTemplate::set_HiddenScript(string value)
0x8492f5  ldloc.0
0x8492f6  ldc.i4.5
0x8492f7  newarr   [mscorlib]System.String
0x8492fc  stloc.s  0x34
0x8492fe  ldloc.s  0x34
0x849300  ldc.i4.0
0x849301  ldstr    aJavascriptCore_9// "javascript:CoreInvoke('EditInGrid','"
0x849306  stelem.ref
0x849307  ldloc.s  0x34
0x849309  ldc.i4.1
0x84930a  ldloc.s  4
0x84930c  stelem.ref
0x84930d  ldloc.s  0x34
0x84930f  ldc.i4.2
0x849310  ldstr    asc_11A62F8// "', '"
0x849315  stelem.ref
0x849316  ldloc.s  0x34
0x849318  ldc.i4.3
0x849319  ldloc.1
0x84931a  call     string Microsoft.SharePoint.Utilities.SPHttpUtility::EcmaScriptStringLiteralEncode(string scriptLiteralToEncode)
0x84931f  stelem.ref
0x849320  ldloc.s  0x34
0x849322  ldc.i4.4
0x849323  ldstr    asc_10B36B4// "')"
0x849328  stelem.ref
0x849329  ldloc.s  0x34
0x84932b  call     string [mscorlib]System.String::Concat(string[])
0x849330  callvirt instance void Microsoft.SharePoint.WebControls.MenuItemTemplate::set_ClientOnClickScript(string value)
0x849335  ldloc.2
0x849336  ldc.i4.1
0x849337  bne.un.s loc_849342
0x849339  call     int32 Microsoft.SharePoint.Utilities.SPUtility::get_ContextCompatibilityLevel()
0x84933e  ldc.i4.s 0xE
0x849340  ble.s    loc_849352
0x849342  ldarg.0
0x849343  ldc.i4   0x12C
0x849348  call     instance void Microsoft.SharePoint.WebControls.ToolBarMenuButton::HideMenuItemGroup(int32 menuItemGroupId)
0x84934d  br       loc_849449
0x849352  ldarg.0
0x849353  ldc.i4   0x12C
0x849358  call     instance void Microsoft.SharePoint.WebControls.ToolBarMenuButton::ShowMenuItemGroup(int32 menuItemGroupId)
0x84935d  ldarg.0
0x84935e  ldstr    aShowinstdviewb// "ShowInStdViewButton"
0x849363  call     instance class Microsoft.SharePoint.WebControls.MenuItemTemplate Microsoft.SharePoint.WebControls.ToolBarMenuButton::GetMenuItem(string menuItemId)
0x849368  stloc.0
0x849369  ldloc.0
0x84936a  brfalse.s loc_84939E
0x84936c  ldarg.0
0x84936d  call     instance class Microsoft.SharePoint.SPView Microsoft.SharePoint.WebControls.ToolBarMenuButton::get_View()
0x849372  callvirt instance string Microsoft.SharePoint.SPView::get_Title()
0x849377  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x84937c  brfalse.s loc_849387
0x84937e  ldloc.0
0x84937f  ldc.i4.0
0x849380  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x849385  br.s     loc_84939E
0x849387  ldloc.0
0x849388  ldstr    aJavascriptCore_10// "javascript:CoreInvoke('ExitGrid','"
0x84938d  ldloc.s  4
0x84938f  ldstr    asc_10B36B4// "')"
0x849394  call     string [mscorlib]System.String::Concat(string, string, string)
0x849399  callvirt instance void Microsoft.SharePoint.WebControls.MenuItemTemplate::set_ClientOnClickScript(string value)
0x84939e  ldarg.0
0x84939f  ldstr    aTaskpanebutton// "TaskPaneButton"
0x8493a4  call     instance class Microsoft.SharePoint.WebControls.MenuItemTemplate Microsoft.SharePoint.WebControls.ToolBarMenuButton::GetMenuItem(string menuItemId)
0x8493a9  stloc.0
0x8493aa  ldloc.0
0x8493ab  brfalse.s loc_8493C3
0x8493ad  ldloc.0
0x8493ae  ldstr    aJavascript// "javascript:"
0x8493b3  ldloc.3
0x8493b4  ldstr    aShowhidetaskpa// "ShowHideTaskPane(); return false;"
0x8493b9  call     string [mscorlib]System.String::Concat(string, string, string)
0x8493be  callvirt instance void Microsoft.SharePoint.WebControls.MenuItemTemplate::set_ClientOnClickScript(string value)
0x8493c3  ldarg.0
0x8493c4  ldstr    aTotalsbutton// "TotalsButton"
0x8493c9  call     instance class Microsoft.SharePoint.WebControls.MenuItemTemplate Microsoft.SharePoint.WebControls.ToolBarMenuButton::GetMenuItem(string menuItemId)
0x8493ce  stloc.0
0x8493cf  ldloc.0
0x8493d0  brfalse.s loc_8493E8
0x8493d2  ldloc.0
0x8493d3  ldstr    aJavascript// "javascript:"
0x8493d8  ldloc.3
0x8493d9  ldstr    aShowhidetotals// "ShowHideTotalsRow(); return false"
0x8493de  call     string [mscorlib]System.String::Concat(string, string, string)
0x8493e3  callvirt instance void Microsoft.SharePoint.WebControls.MenuItemTemplate::set_ClientOnClickScript(string value)
0x8493e8  ldarg.0
0x8493e9  ldstr    aRefreshdatabut// "RefreshDataButton"
0x8493ee  call     instance class Microsoft.SharePoint.WebControls.MenuItemTemplate Microsoft.SharePoint.WebControls.ToolBarMenuButton::GetMenuItem(string menuItemId)
0x8493f3  stloc.0
0x8493f4  ldloc.0
0x8493f5  brfalse.s loc_84940D
0x8493f7  ldloc.0
0x8493f8  ldstr    aJavascript// "javascript:"
0x8493fd  ldloc.3
0x8493fe  ldstr    aRefreshReturnF// "Refresh(); return false;"
0x849403  call     string [mscorlib]System.String::Concat(string, string, string)
0x849408  callvirt instance void Microsoft.SharePoint.WebControls.MenuItemTemplate::set_ClientOnClickScript(string value)
0x84940d  ldarg.0
0x84940e  ldstr    aNewrowbutton// "NewRowButton"
0x849413  call     instance class Microsoft.SharePoint.WebControls.MenuItemTemplate Microsoft.SharePoint.WebControls.ToolBarMenuButton::GetMenuItem(string menuItemId)
0x849418  stloc.0
0x849419  ldloc.0
0x84941a  brfalse.s loc_849449
0x84941c  ldarg.0
0x84941d  callvirt instance class Microsoft.SharePoint.SPList Microsoft.SharePoint.WebControls.ToolBarMenuButton::get_List()
0x849422  callvirt instance valuetype Microsoft.SharePoint.SPBaseType Microsoft.SharePoint.SPList::get_BaseType()
0x849427  ldc.i4.1
0x849428  bne.un.s loc_849433
0x84942a  ldloc.0
  ... truncated ...
```
