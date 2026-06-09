# Microsoft.Reporting.WebForms.ReportViewerClientScript::SetViewerInfo

- ea: `0x6260`
- end: `0x65ef`
- name: `Microsoft.Reporting.WebForms.ReportViewerClientScript::SetViewerInfo`
- size: `911`
- prototype: ``
- caller_count: `1`
- callee_count: `30`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14e00`

## callees

- `0x1650`
- `0x16a0`
- `0x16b0`
- `0x16c0`
- `0x16d0`
- `0x16e0`
- `0x16f0`
- `0x1700`
- `0x1710`
- `0x1720`
- `0x1730`
- `0x1740`
- `0x40b0`
- `0x5090`
- `0x5170`
- `0x6260`
- `0x65f0`
- `0x8640`
- `0x8cd0`
- `0x8f10`
- `0x11820`
- `0x12540`
- `0x128c0`
- `0x12b30`
- `0x12c10`
- `0x15ab0`
- `0x15bd0`
- `0x15bf0`
- `0x22a20`
- `0x24350`

## string_xrefs

- `0x62c7`: `TopLevelUpdatePanelId`
- `0x62d4`: `DocMapUpdatePanelId`
- `0x6362`: `DirectionCacheId`
- `0x640b`: `PDF&rc:PrintOnOpen=true`
- `0x6436`: `PDF&rc:PrintOnOpen=true`
- `0x64ce`: `DownloadLinkText`

## pseudocode

```c

```

## disassembly

```asm
0x6260  ldarg.0
0x6261  callvirt instance void [System.Web]System.Web.UI.Control::EnsureChildControls()
0x6266  ldarg.0
0x6267  ldc.i4.2
0x6268  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [System.Web.Extensions]System.Web.UI.ScriptDescriptor>::.ctor(int32)
0x626d  stfld    class [mscorlib]System.Collections.Generic.List`1<class [System.Web.Extensions]System.Web.UI.ScriptDescriptor> Microsoft.Reporting.WebForms.ReportViewerClientScript::m_scriptDescriptors
0x6272  ldstr    aMicrosoftRepor_3// "Microsoft.Reporting.WebFormsClient._Int"...
0x6277  ldarg.0
0x6278  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x627d  newobj   instance void [System.Web.Extensions]System.Web.UI.ScriptControlDescriptor::.ctor(string, string)
0x6282  stloc.0
0x6283  ldarg.0
0x6284  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [System.Web.Extensions]System.Web.UI.ScriptDescriptor> Microsoft.Reporting.WebForms.ReportViewerClientScript::m_scriptDescriptors
0x6289  ldloc.0
0x628a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [System.Web.Extensions]System.Web.UI.ScriptDescriptor>::Add(var<u1>)
0x628f  ldloc.0
0x6290  ldstr    aReportviewerid// "ReportViewerId"
0x6295  ldarg.1
0x6296  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x629b  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0x62a0  ldloc.0
0x62a1  ldstr    aReportareaid// "ReportAreaId"
0x62a6  ldarg.2
0x62a7  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0x62ac  ldloc.0
0x62ad  ldstr    aDocmapareaid// "DocMapAreaId"
0x62b2  ldarg.s  4
0x62b4  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0x62b9  ldloc.0
0x62ba  ldstr    aFixedtableid// "FixedTableId"
0x62bf  ldarg.s  5
0x62c1  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0x62c6  ldloc.0
0x62c7  ldstr    aToplevelupdate// "TopLevelUpdatePanelId"
0x62cc  ldarg.s  6
0x62ce  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0x62d3  ldloc.0
0x62d4  ldstr    aDocmapupdatepa// "DocMapUpdatePanelId"
0x62d9  ldarg.s  7
0x62db  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0x62e0  ldloc.0
0x62e1  ldstr    aActiontypeid// "ActionTypeId"
0x62e6  ldarg.0
0x62e7  ldfld    class [System.Web]System.Web.UI.WebControls.HiddenField Microsoft.Reporting.WebForms.ReportViewerClientScript::m_actionType
0x62ec  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x62f1  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0x62f6  ldloc.0
0x62f7  ldstr    aActionparamid// "ActionParamId"
0x62fc  ldarg.0
0x62fd  ldfld    class [System.Web]System.Web.UI.WebControls.HiddenField Microsoft.Reporting.WebForms.ReportViewerClientScript::m_actionParam
0x6302  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x6307  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0x630c  ldloc.0
0x630d  ldstr    aHassizingrow// "HasSizingRow"
0x6312  ldarg.1
0x6313  callvirt instance bool Microsoft.Reporting.WebForms.ReportViewer::get_SizeToReportContent()
0x6318  ldc.i4.0
0x6319  ceq
0x631b  box      [mscorlib]System.Boolean
0x6320  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0x6325  ldloc.0
0x6326  ldstr    aBaseheight// "BaseHeight"
0x632b  ldarg.1
0x632c  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.Unit [System.Web]System.Web.UI.WebControls.WebControl::get_Height()
0x6331  stloc.3
0x6332  ldloca.s 3
0x6334  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6339  call     instance string [System.Web]System.Web.UI.WebControls.Unit::ToString(class [mscorlib]System.Globalization.CultureInfo)
0x633e  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0x6343  ldloc.0
0x6344  ldstr    aBasewidth// "BaseWidth"
0x6349  ldarg.1
0x634a  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.Unit [System.Web]System.Web.UI.WebControls.WebControl::get_Width()
0x634f  stloc.3
0x6350  ldloca.s 3
0x6352  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6357  call     instance string [System.Web]System.Web.UI.WebControls.Unit::ToString(class [mscorlib]System.Globalization.CultureInfo)
0x635c  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0x6361  ldloc.0
0x6362  ldstr    aDirectioncache// "DirectionCacheId"
0x6367  ldarg.s  0xB
0x6369  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0x636e  ldloc.0
0x636f  ldstr    aBrowsermodeid// "BrowserModeId"
0x6374  ldarg.s  0xC
0x6376  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0x637b  ldloc.0
0x637c  ldstr    aPromptarearowi// "PromptAreaRowId"
0x6381  ldarg.3
0x6382  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0x6387  ldloc.0
0x6388  ldstr    aPromptsplitter// "PromptSplitterId"
0x638d  ldarg.s  8
0x638f  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0x6394  ldloc.0
0x6395  ldstr    aDocmapsplitter// "DocMapSplitterId"
0x639a  ldarg.s  9
0x639c  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0x63a1  ldloc.0
0x63a2  ldstr    aDocmapheaderov// "DocMapHeaderOverflowDivId"
0x63a7  ldarg.s  0xA
0x63a9  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0x63ae  ldarg.0
0x63af  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x63b4  callvirt instance class [System.Web]System.Web.UI.ClientScriptManager [System.Web]System.Web.UI.Page::get_ClientScript()
0x63b9  ldarg.0
0x63ba  ldnull
0x63bb  callvirt instance string [System.Web]System.Web.UI.ClientScriptManager::GetPostBackEventReference(class [System.Web]System.Web.UI.Control, string)
0x63c0  ldstr    asc_40D1E// ";"
0x63c5  call     string [mscorlib]System.String::Concat(string, string)
0x63ca  stloc.1
0x63cb  ldloc.0
0x63cc  ldstr    aPostbacktoclie// "PostBackToClientScript"
0x63d1  ldloc.1
0x63d2  call     string Microsoft.Reporting.WebForms.JavaScriptHelper::FormatAsFunction(string functionBody)
0x63d7  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddScriptProperty(string, string)
0x63dc  ldarg.1
0x63dd  callvirt instance class Microsoft.Reporting.WebForms.ReportControlSession Microsoft.Reporting.WebForms.ReportViewer::get_ReportControlSession()
0x63e2  stloc.2
0x63e3  ldloc.2
0x63e4  brfalse  loc_65B6
0x63e9  ldloc.2
0x63ea  callvirt instance class Microsoft.Reporting.WebForms.Report Microsoft.Reporting.WebForms.ReportControlSession::get_Report()
0x63ef  callvirt instance bool Microsoft.Reporting.WebForms.Report::get_IsReadyForRendering()
0x63f4  brfalse  loc_65B6
0x63f9  ldloc.2
0x63fa  callvirt instance class Microsoft.Reporting.WebForms.Report Microsoft.Reporting.WebForms.ReportControlSession::get_Report()
0x63ff  ldarg.1
0x6400  callvirt instance string Microsoft.Reporting.WebForms.ReportViewer::get_InstanceIdentifier()
0x6405  ldc.i4.0
0x6406  call     string Microsoft.Reporting.WebForms.ExportOperation::CreateUrl(class Microsoft.Reporting.WebForms.Report report, string instanceID, valuetype Microsoft.Reporting.WebForms.ContentDisposition contentDisposition)
0x640b  ldstr    aPdfRcPrintonop// "PDF&rc:PrintOnOpen=true"
0x6410  call     string [mscorlib]System.String::Concat(string, string)
0x6415  stloc.s  4
0x6417  ldloc.0
0x6418  ldstr    aPdfpreviewurl// "PdfPreviewUrl"
0x641d  ldloc.s  4
0x641f  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0x6424  ldloc.2
0x6425  callvirt instance class Microsoft.Reporting.WebForms.Report Microsoft.Reporting.WebForms.ReportControlSession::get_Report()
0x642a  ldarg.1
0x642b  callvirt instance string Microsoft.Reporting.WebForms.ReportViewer::get_InstanceIdentifier()
0x6430  ldc.i4.1
0x6431  call     string Microsoft.Reporting.WebForms.ExportOperation::CreateUrl(class Microsoft.Reporting.WebForms.Report report, string instanceID, valuetype Microsoft.Reporting.WebForms.ContentDisposition contentDisposition)
0x6436  ldstr    aPdfRcPrintonop// "PDF&rc:PrintOnOpen=true"
0x643b  call     string [mscorlib]System.String::Concat(string, string)
0x6440  stloc.s  5
0x6442  ldloc.0
0x6443  ldstr    aPdfdownloadurl// "PdfDownloadUrl"
0x6448  ldloc.s  5
0x644a  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0x644f  ldloc.0
0x6450  ldstr    aCaptiontext// "CaptionText"
0x6455  call     class Microsoft.Reporting.WebForms.IReportViewerMessages5 Microsoft.Reporting.WebForms.LocalizationHelper::get_Current()
0x645a  callvirt instance string Microsoft.Reporting.WebForms.IReportViewerMessages5::get_CaptionText()
0x645f  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0x6464  ldloc.0
0x6465  ldstr    aLoadingtext// "LoadingText"
0x646a  call     class Microsoft.Reporting.WebForms.IReportViewerMessages5 Microsoft.Reporting.WebForms.LocalizationHelper::get_Current()
0x646f  callvirt instance string Microsoft.Reporting.WebForms.IReportViewerMessages5::get_LoadingText()
0x6474  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0x6479  ldloc.0
0x647a  ldstr    aFootertext// "FooterText"
0x647f  call     class Microsoft.Reporting.WebForms.IReportViewerMessages5 Microsoft.Reporting.WebForms.LocalizationHelper::get_Current()
0x6484  callvirt instance string Microsoft.Reporting.WebForms.IReportViewerMessages5::get_FooterText()
0x6489  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0x648e  ldloc.0
0x648f  ldstr    aPrinttext// "PrintText"
0x6494  call     class Microsoft.Reporting.WebForms.IReportViewerMessages5 Microsoft.Reporting.WebForms.LocalizationHelper::get_Current()
0x6499  callvirt instance string Microsoft.Reporting.WebForms.IReportViewerMessages5::get_PrintText()
0x649e  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0x64a3  ldloc.0
0x64a4  ldstr    aDonetext// "DoneText"
0x64a9  call     class Microsoft.Reporting.WebForms.IReportViewerMessages5 Microsoft.Reporting.WebForms.LocalizationHelper::get_Current()
0x64ae  callvirt instance string Microsoft.Reporting.WebForms.IReportViewerMessages5::get_DoneText()
0x64b3  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0x64b8  ldloc.0
0x64b9  ldstr    aDownloadtext// "DownloadText"
0x64be  call     class Microsoft.Reporting.WebForms.IReportViewerMessages5 Microsoft.Reporting.WebForms.LocalizationHelper::get_Current()
0x64c3  callvirt instance string Microsoft.Reporting.WebForms.IReportViewerMessages5::get_DownloadText()
0x64c8  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0x64cd  ldloc.0
0x64ce  ldstr    aDownloadlinkte// "DownloadLinkText"
0x64d3  call     class Microsoft.Reporting.WebForms.IReportViewerMessages5 Microsoft.Reporting.WebForms.LocalizationHelper::get_Current()
0x64d8  callvirt instance string Microsoft.Reporting.WebForms.IReportViewerMessages5::get_DownloadLinkText()
0x64dd  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0x64e2  ldloc.0
0x64e3  ldstr    aSettingtext// "SettingText"
0x64e8  call     class Microsoft.Reporting.WebForms.IReportViewerMessages5 Microsoft.Reporting.WebForms.LocalizationHelper::get_Current()
0x64ed  callvirt instance string Microsoft.Reporting.WebForms.IReportViewerMessages5::get_SettingText()
0x64f2  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0x64f7  ldloc.0
0x64f8  ldstr    aPagesizelabelt// "PageSizeLabelText"
0x64fd  call     class Microsoft.Reporting.WebForms.IReportViewerMessages5 Microsoft.Reporting.WebForms.LocalizationHelper::get_Current()
0x6502  callvirt instance string Microsoft.Reporting.WebForms.IReportViewerMessages5::get_PageSizeLabelText()
0x6507  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0x650c  ldloc.0
0x650d  ldstr    aPageorientatio// "PageOrientationLabelText"
0x6512  call     class Microsoft.Reporting.WebForms.IReportViewerMessages5 Microsoft.Reporting.WebForms.LocalizationHelper::get_Current()
0x6517  callvirt instance string Microsoft.Reporting.WebForms.IReportViewerMessages5::get_PageOrientationLabelText()
0x651c  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0x6521  ldloc.0
0x6522  ldstr    aLandscapetext// "LandscapeText"
0x6527  call     class Microsoft.Reporting.WebForms.IReportViewerMessages5 Microsoft.Reporting.WebForms.LocalizationHelper::get_Current()
0x652c  callvirt instance string Microsoft.Reporting.WebForms.IReportViewerMessages5::get_LandscapeText()
0x6531  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0x6536  ldloc.0
0x6537  ldstr    aPortraittext// "PortraitText"
0x653c  call     class Microsoft.Reporting.WebForms.IReportViewerMessages5 Microsoft.Reporting.WebForms.LocalizationHelper::get_Current()
0x6541  callvirt instance string Microsoft.Reporting.WebForms.IReportViewerMessages5::get_PortraitText()
0x6546  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0x654b  ldloc.0
0x654c  ldstr    aLoadingiconurl// "LoadingIconUrl"
0x6551  ldstr    aMicrosoftRepor_4// "Microsoft.Reporting.WebForms.Icons.Prin"...
0x6556  call     string Microsoft.Reporting.WebForms.EmbeddedResourceOperation::CreateUrl(string resourceName)
0x655b  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0x6560  ldarg.0
0x6561  ldloc.0
0x6562  ldarg.1
0x6563  callvirt instance class Microsoft.Reporting.WebForms.Report Microsoft.Reporting.WebForms.ReportViewer::get_Report()
0x6568  callvirt instance class Microsoft.Reporting.WebForms.ReportPageSettings Microsoft.Reporting.WebForms.Report::GetDefaultPageSettings()
0x656d  call     instance void Microsoft.Reporting.WebForms.ReportViewerClientScript::AttachPageSizeList(class [System.Web.Extensions]System.Web.UI.ScriptControlDescriptor desc, class Microsoft.Reporting.WebForms.ReportPageSettings pageSettings)
0x6572  ldloc.2
0x6573  callvirt instance class Microsoft.Reporting.WebForms.Report Microsoft.Reporting.WebForms.ReportControlSession::get_Report()
0x6578  ldarg.1
0x6579  callvirt instance string Microsoft.Reporting.WebForms.ReportViewer::get_InstanceIdentifier()
0x657e  ldarg.1
0x657f  callvirt instance valuetype Microsoft.Reporting.WebForms.ContentDisposition Microsoft.Reporting.WebForms.ReportViewer::get_ExportContentDisposition()
0x6584  call     string Microsoft.Reporting.WebForms.ExportOperation::CreateUrl(class Microsoft.Reporting.WebForms.Report report, string instanceID, valuetype Microsoft.Reporting.WebForms.ContentDisposition contentDisposition)
0x6589  stloc.s  6
0x658b  ldloc.0
0x658c  ldstr    aExporturlbase// "ExportUrlBase"
0x6591  ldloc.s  6
0x6593  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0x6598  ldloc.2
0x6599  isinst   Microsoft.Reporting.WebForms.ServerModeSession
0x659e  brfalse.s loc_65B6
0x65a0  ldloc.0
0x65a1  ldstr    aServerversion// "ServerVersion"
0x65a6  ldarg.1
0x65a7  callvirt instance class Microsoft.Reporting.WebForms.ServerReport Microsoft.Reporting.WebForms.ReportViewer::get_ServerReport()
0x65ac  callvirt instance string Microsoft.Reporting.WebForms.ServerReport::GetServerVersion()
0x65b1  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0x65b6  ldarg.1
0x65b7  callvirt instance bool Microsoft.Reporting.WebForms.ReportViewer::get_KeepSessionAlive()
0x65bc  brfalse.s loc_65EE
0x65be  ldarg.1
0x65bf  call     class [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor Microsoft.Reporting.WebForms.SessionKeepAliveOperation::CreateRequest(class Microsoft.Reporting.WebForms.ReportViewer viewer)
0x65c4  stloc.s  7
0x65c6  ldloc.s  7
0x65c8  brfalse.s loc_65EE
0x65ca  ldarg.0
0x65cb  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [System.Web.Extensions]System.Web.UI.ScriptDescriptor> Microsoft.Reporting.WebForms.ReportViewerClientScript::m_scriptDescriptors
0x65d0  ldloc.s  7
0x65d2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [System.Web.Extensions]System.Web.UI.ScriptDescriptor>::Add(var<u1>)
0x65d7  ldloc.s  7
0x65d9  ldarg.1
0x65da  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x65df  ldstr    aSessionkeepali// "_SessionKeepAlive"
0x65e4  call     string [mscorlib]System.String::Concat(string, string)
0x65e9  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::set_ID(string)
0x65ee  ret
```
