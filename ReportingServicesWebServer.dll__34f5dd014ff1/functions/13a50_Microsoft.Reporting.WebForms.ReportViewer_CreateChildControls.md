# Microsoft.Reporting.WebForms.ReportViewer::CreateChildControls

- ea: `0x13a50`
- end: `0x13f0c`
- name: `Microsoft.Reporting.WebForms.ReportViewer::CreateChildControls`
- size: `1212`
- prototype: ``
- caller_count: `0`
- callee_count: `44`
- tags: `broker_com_uri`

## callees

- `0x1290`
- `0x12a0`
- `0x1600`
- `0x1610`
- `0x1620`
- `0x1630`
- `0x2cc0`
- `0x3a40`
- `0x3ea0`
- `0x3f40`
- `0x3fc0`
- `0x40b0`
- `0x57a0`
- `0x5800`
- `0x5ac0`
- `0x60a0`
- `0x67f0`
- `0x6c80`
- `0x6cd0`
- `0x6d30`
- `0x9780`
- `0x9a70`
- `0x9a90`
- `0x9d00`
- `0x9d30`
- `0x9d90`
- `0x9eb0`
- `0x9f10`
- `0xc0d0`
- `0xc0e0`
- `0xfe40`
- `0xfe70`
- `0xfeb0`
- `0xff10`
- `0x123b0`
- `0x13a50`
- `0x14230`
- `0x15790`
- `0x17c60`
- `0x17c90`
- `0x1b0c0`
- `0x1b250`
- `0x1b330`
- `0x3a630`

## pseudocode

```c

```

## disassembly

```asm
0x13a50  ldarg.0
0x13a51  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x13a56  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Clear()
0x13a5b  ldarg.0
0x13a5c  ldfld    class Microsoft.Reporting.WebForms.PanelUpdater Microsoft.Reporting.WebForms.ReportViewer::m_panelUpdater
0x13a61  callvirt instance void Microsoft.Reporting.WebForms.PanelUpdater::UnregisterAllPanels()
0x13a66  ldarg.0
0x13a67  callvirt instance void Microsoft.Reporting.WebForms.ReportViewer::CreateGlyphStylings()
0x13a6c  ldarg.0
0x13a6d  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x13a72  ldarg.0
0x13a73  ldfld    class [System.Web]System.Web.UI.LiteralControl Microsoft.Reporting.WebForms.ReportViewer::m_styling
0x13a78  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x13a7d  ldarg.0
0x13a7e  call     instance bool [System.Web]System.Web.UI.Control::get_DesignMode()
0x13a83  brtrue.s loc_13AA0
0x13a85  ldarg.0
0x13a86  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x13a8b  brfalse.s loc_13A9A
0x13a8d  ldarg.0
0x13a8e  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x13a93  call     class [System.Web.Extensions]System.Web.UI.ScriptManager [System.Web.Extensions]System.Web.UI.ScriptManager::GetCurrent(class [System.Web]System.Web.UI.Page)
0x13a98  brtrue.s loc_13AA0
0x13a9a  newobj   instance void Microsoft.Reporting.WebForms.ScriptManagerNotFoundException::.ctor()
0x13a9f  throw
0x13aa0  ldarg.0
0x13aa1  newobj   instance void Microsoft.Reporting.WebForms.NoScriptControl::.ctor()
0x13aa6  stfld    class Microsoft.Reporting.WebForms.NoScriptControl Microsoft.Reporting.WebForms.ReportViewer::m_noScriptControl
0x13aab  ldarg.0
0x13aac  ldfld    class Microsoft.Reporting.WebForms.NoScriptControl Microsoft.Reporting.WebForms.ReportViewer::m_noScriptControl
0x13ab1  ldarg.0
0x13ab2  call     instance bool [System.Web]System.Web.UI.Control::get_DesignMode()
0x13ab7  ldc.i4.0
0x13ab8  ceq
0x13aba  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x13abf  ldarg.0
0x13ac0  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x13ac5  ldarg.0
0x13ac6  ldfld    class Microsoft.Reporting.WebForms.NoScriptControl Microsoft.Reporting.WebForms.ReportViewer::m_noScriptControl
0x13acb  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x13ad0  ldarg.0
0x13ad1  newobj   instance void [System.Web.Extensions]System.Web.UI.UpdatePanel::.ctor()
0x13ad6  stfld    class [System.Web.Extensions]System.Web.UI.UpdatePanel Microsoft.Reporting.WebForms.ReportViewer::m_topLevelUpdatePanel
0x13adb  ldarg.0
0x13adc  ldfld    class [System.Web.Extensions]System.Web.UI.UpdatePanel Microsoft.Reporting.WebForms.ReportViewer::m_topLevelUpdatePanel
0x13ae1  ldc.i4.1
0x13ae2  callvirt instance void [System.Web.Extensions]System.Web.UI.UpdatePanel::set_UpdateMode(valuetype [System.Web.Extensions]System.Web.UI.UpdatePanelUpdateMode)
0x13ae7  ldarg.0
0x13ae8  ldfld    class [System.Web.Extensions]System.Web.UI.UpdatePanel Microsoft.Reporting.WebForms.ReportViewer::m_topLevelUpdatePanel
0x13aed  ldc.i4.0
0x13aee  callvirt instance void [System.Web.Extensions]System.Web.UI.UpdatePanel::set_RenderMode(valuetype [System.Web.Extensions]System.Web.UI.UpdatePanelRenderMode)
0x13af3  ldarg.0
0x13af4  ldfld    class [System.Web.Extensions]System.Web.UI.UpdatePanel Microsoft.Reporting.WebForms.ReportViewer::m_topLevelUpdatePanel
0x13af9  ldc.i4.0
0x13afa  callvirt instance void [System.Web.Extensions]System.Web.UI.UpdatePanel::set_ChildrenAsTriggers(bool)
0x13aff  ldarg.0
0x13b00  ldfld    class [System.Web.Extensions]System.Web.UI.UpdatePanel Microsoft.Reporting.WebForms.ReportViewer::m_topLevelUpdatePanel
0x13b05  ldstr    aReportviewer// "ReportViewer"
0x13b0a  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x13b0f  ldarg.0
0x13b10  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x13b15  ldarg.0
0x13b16  ldfld    class [System.Web.Extensions]System.Web.UI.UpdatePanel Microsoft.Reporting.WebForms.ReportViewer::m_topLevelUpdatePanel
0x13b1b  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x13b20  ldarg.0
0x13b21  ldfld    class Microsoft.Reporting.WebForms.PanelUpdater Microsoft.Reporting.WebForms.ReportViewer::m_panelUpdater
0x13b26  ldarg.0
0x13b27  ldfld    class [System.Web.Extensions]System.Web.UI.UpdatePanel Microsoft.Reporting.WebForms.ReportViewer::m_topLevelUpdatePanel
0x13b2c  ldc.i4.s 0xE
0x13b2e  callvirt instance void Microsoft.Reporting.WebForms.PanelUpdater::RegisterPanel(class [System.Web.Extensions]System.Web.UI.UpdatePanel panel, valuetype Microsoft.Reporting.WebForms.UpdateGroup groupForMembership)
0x13b33  ldarg.0
0x13b34  ldftn    instance bool Microsoft.Reporting.WebForms.ReportViewer::RenderTopLevelUpdatePanelContents(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x13b3a  newobj   instance void RenderDelegate::.ctor(object object, native int method)
0x13b3f  newobj   instance void Microsoft.Reporting.WebForms.DelegatedRenderingControl::.ctor(class RenderDelegate renderChildrenDelegate)
0x13b44  stloc.0
0x13b45  ldarg.0
0x13b46  ldfld    class [System.Web.Extensions]System.Web.UI.UpdatePanel Microsoft.Reporting.WebForms.ReportViewer::m_topLevelUpdatePanel
0x13b4b  callvirt instance class [System.Web]System.Web.UI.Control [System.Web.Extensions]System.Web.UI.UpdatePanel::get_ContentTemplateContainer()
0x13b50  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x13b55  ldloc.0
0x13b56  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x13b5b  ldarg.0
0x13b5c  newobj   instance void Microsoft.Reporting.WebForms.ReportViewerClientScript::.ctor()
0x13b61  stfld    class Microsoft.Reporting.WebForms.ReportViewerClientScript Microsoft.Reporting.WebForms.ReportViewer::m_clientScript
0x13b66  ldarg.0
0x13b67  ldfld    class Microsoft.Reporting.WebForms.ReportViewerClientScript Microsoft.Reporting.WebForms.ReportViewer::m_clientScript
0x13b6c  ldarg.0
0x13b6d  ldftn    instance void Microsoft.Reporting.WebForms.ReportViewer::OnReportAction(object sender, class Microsoft.Reporting.WebForms.ReportActionEventArgs e)
0x13b73  newobj   instance void class [mscorlib]System.EventHandler`1<class Microsoft.Reporting.WebForms.ReportActionEventArgs>::.ctor(object, native int)
0x13b78  callvirt instance void Microsoft.Reporting.WebForms.ReportViewerClientScript::add_ReportAction(class [mscorlib]System.EventHandler`1<class Microsoft.Reporting.WebForms.ReportActionEventArgs> value)
0x13b7d  ldloc.0
0x13b7e  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x13b83  ldarg.0
0x13b84  ldfld    class Microsoft.Reporting.WebForms.ReportViewerClientScript Microsoft.Reporting.WebForms.ReportViewer::m_clientScript
0x13b89  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x13b8e  ldarg.0
0x13b8f  ldarg.0
0x13b90  newobj   instance void Microsoft.Reporting.WebForms.ParametersArea::.ctor(class Microsoft.Reporting.WebForms.ReportViewer viewer)
0x13b95  stfld    class Microsoft.Reporting.WebForms.ParametersArea Microsoft.Reporting.WebForms.ReportViewer::m_parametersArea
0x13b9a  ldarg.0
0x13b9b  ldfld    class Microsoft.Reporting.WebForms.ParametersArea Microsoft.Reporting.WebForms.ReportViewer::m_parametersArea
0x13ba0  ldarg.0
0x13ba1  ldftn    instance void Microsoft.Reporting.WebForms.ReportViewer::OnViewReport(object sender, class [mscorlib]System.EventArgs e)
0x13ba7  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x13bac  callvirt instance void Microsoft.Reporting.WebForms.ParametersArea::add_ViewReportClick(class [mscorlib]System.EventHandler value)
0x13bb1  ldarg.0
0x13bb2  ldfld    class Microsoft.Reporting.WebForms.ParametersArea Microsoft.Reporting.WebForms.ReportViewer::m_parametersArea
0x13bb7  ldarg.0
0x13bb8  ldftn    instance void Microsoft.Reporting.WebForms.ReportViewer::OnParameterValuesChanged(object sender, class [mscorlib]System.EventArgs e)
0x13bbe  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x13bc3  callvirt instance void Microsoft.Reporting.WebForms.ParametersArea::add_ParameterValuesChanged(class [mscorlib]System.EventHandler value)
0x13bc8  ldarg.0
0x13bc9  ldfld    class Microsoft.Reporting.WebForms.ParametersArea Microsoft.Reporting.WebForms.ReportViewer::m_parametersArea
0x13bce  ldarg.0
0x13bcf  ldftn    instance void Microsoft.Reporting.WebForms.ReportViewer::OnSubmittingDataSourceCredentials(object sender, class Microsoft.Reporting.WebForms.ReportCredentialsEventArgs credentialArgs)
0x13bd5  newobj   instance void Microsoft.Reporting.WebForms.ReportCredentialsEventHandler::.ctor(object object, native int method)
0x13bda  callvirt instance void Microsoft.Reporting.WebForms.ParametersArea::add_SubmittingDataSourceCredentials(class Microsoft.Reporting.WebForms.ReportCredentialsEventHandler value)
0x13bdf  ldarg.0
0x13be0  ldfld    class Microsoft.Reporting.WebForms.ParametersArea Microsoft.Reporting.WebForms.ReportViewer::m_parametersArea
0x13be5  ldarg.0
0x13be6  ldftn    instance void Microsoft.Reporting.WebForms.ReportViewer::OnSubmittingParameterValues(object sender, class Microsoft.Reporting.WebForms.ReportParametersEventArgs parameterArgs)
0x13bec  newobj   instance void Microsoft.Reporting.WebForms.ReportParametersEventHandler::.ctor(object object, native int method)
0x13bf1  callvirt instance void Microsoft.Reporting.WebForms.ParametersArea::add_SubmittingParameterValues(class Microsoft.Reporting.WebForms.ReportParametersEventHandler value)
0x13bf6  ldloc.0
0x13bf7  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x13bfc  ldarg.0
0x13bfd  ldfld    class Microsoft.Reporting.WebForms.ParametersArea Microsoft.Reporting.WebForms.ReportViewer::m_parametersArea
0x13c02  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x13c07  ldarg.0
0x13c08  ldarg.0
0x13c09  callvirt instance class Microsoft.Reporting.WebForms.IReportViewerStyles Microsoft.Reporting.WebForms.ReportViewer::get_ViewerStyle()
0x13c0e  ldc.i4.0
0x13c0f  call     class Microsoft.Reporting.WebForms.IReportViewerMessages5 Microsoft.Reporting.WebForms.LocalizationHelper::get_Current()
0x13c14  callvirt instance string Microsoft.Reporting.WebForms.IReportViewerMessages4::get_ShowParameterAreaButtonToolTip()
0x13c19  call     class Microsoft.Reporting.WebForms.IReportViewerMessages5 Microsoft.Reporting.WebForms.LocalizationHelper::get_Current()
0x13c1e  callvirt instance string Microsoft.Reporting.WebForms.IReportViewerMessages4::get_HideParameterAreaButtonToolTip()
0x13c23  call     class Microsoft.Reporting.WebForms.IReportViewerMessages5 Microsoft.Reporting.WebForms.LocalizationHelper::get_Current()
0x13c28  callvirt instance string Microsoft.Reporting.WebForms.IReportViewerMessages::get_ParameterAreaButtonToolTip()
0x13c2d  newobj   instance void Microsoft.Reporting.WebForms.ReportSplitter::.ctor(class Microsoft.Reporting.WebForms.IReportViewerStyles viewerStyle, bool isVertical, string expandTooltip, string collapseTooltip, string defaultToolTip)
0x13c32  stfld    class Microsoft.Reporting.WebForms.ReportSplitter Microsoft.Reporting.WebForms.ReportViewer::m_parametersAreaSplitter
0x13c37  ldarg.0
0x13c38  ldfld    class Microsoft.Reporting.WebForms.ReportSplitter Microsoft.Reporting.WebForms.ReportViewer::m_parametersAreaSplitter
0x13c3d  ldc.i4.0
0x13c3e  callvirt instance void Microsoft.Reporting.WebForms.ReportSplitter::set_IsResizable(bool value)
0x13c43  ldarg.0
0x13c44  ldfld    class Microsoft.Reporting.WebForms.ReportSplitter Microsoft.Reporting.WebForms.ReportViewer::m_parametersAreaSplitter
0x13c49  ldstr    aToggleparam// "ToggleParam"
0x13c4e  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x13c53  ldloc.0
0x13c54  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x13c59  ldarg.0
0x13c5a  ldfld    class Microsoft.Reporting.WebForms.ReportSplitter Microsoft.Reporting.WebForms.ReportViewer::m_parametersAreaSplitter
0x13c5f  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x13c64  ldarg.0
0x13c65  ldarg.0
0x13c66  newobj   instance void Microsoft.Reporting.WebForms.ToolbarControl::.ctor(class Microsoft.Reporting.WebForms.ReportViewer viewer)
0x13c6b  stfld    class Microsoft.Reporting.WebForms.ToolbarControl Microsoft.Reporting.WebForms.ReportViewer::m_toolbarArea
0x13c70  ldarg.0
0x13c71  ldfld    class Microsoft.Reporting.WebForms.ToolbarControl Microsoft.Reporting.WebForms.ReportViewer::m_toolbarArea
0x13c76  ldarg.0
0x13c77  ldftn    instance void Microsoft.Reporting.WebForms.ReportViewer::OnReportAction(object sender, class Microsoft.Reporting.WebForms.ReportActionEventArgs e)
0x13c7d  newobj   instance void class [mscorlib]System.EventHandler`1<class Microsoft.Reporting.WebForms.ReportActionEventArgs>::.ctor(object, native int)
0x13c82  callvirt instance void Microsoft.Reporting.WebForms.ToolbarControl::add_ReportAction(class [mscorlib]System.EventHandler`1<class Microsoft.Reporting.WebForms.ReportActionEventArgs> value)
0x13c87  ldloc.0
0x13c88  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x13c8d  ldarg.0
0x13c8e  ldfld    class Microsoft.Reporting.WebForms.ToolbarControl Microsoft.Reporting.WebForms.ReportViewer::m_toolbarArea
0x13c93  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x13c98  ldarg.0
0x13c99  newobj   instance void [System.Web.Extensions]System.Web.UI.UpdatePanel::.ctor()
0x13c9e  stfld    class [System.Web.Extensions]System.Web.UI.UpdatePanel Microsoft.Reporting.WebForms.ReportViewer::m_docMapUpdatePanel
0x13ca3  ldarg.0
0x13ca4  ldfld    class [System.Web.Extensions]System.Web.UI.UpdatePanel Microsoft.Reporting.WebForms.ReportViewer::m_docMapUpdatePanel
0x13ca9  ldc.i4.1
0x13caa  callvirt instance void [System.Web.Extensions]System.Web.UI.UpdatePanel::set_UpdateMode(valuetype [System.Web.Extensions]System.Web.UI.UpdatePanelUpdateMode)
0x13caf  ldarg.0
0x13cb0  ldfld    class [System.Web.Extensions]System.Web.UI.UpdatePanel Microsoft.Reporting.WebForms.ReportViewer::m_docMapUpdatePanel
0x13cb5  ldc.i4.0
0x13cb6  callvirt instance void [System.Web.Extensions]System.Web.UI.UpdatePanel::set_RenderMode(valuetype [System.Web.Extensions]System.Web.UI.UpdatePanelRenderMode)
0x13cbb  ldarg.0
0x13cbc  ldfld    class [System.Web.Extensions]System.Web.UI.UpdatePanel Microsoft.Reporting.WebForms.ReportViewer::m_docMapUpdatePanel
0x13cc1  ldc.i4.0
0x13cc2  callvirt instance void [System.Web.Extensions]System.Web.UI.UpdatePanel::set_ChildrenAsTriggers(bool)
0x13cc7  ldarg.0
0x13cc8  ldfld    class [System.Web.Extensions]System.Web.UI.UpdatePanel Microsoft.Reporting.WebForms.ReportViewer::m_docMapUpdatePanel
0x13ccd  ldstr    aDocmap// "DocMap"
0x13cd2  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x13cd7  ldloc.0
0x13cd8  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x13cdd  ldarg.0
0x13cde  ldfld    class [System.Web.Extensions]System.Web.UI.UpdatePanel Microsoft.Reporting.WebForms.ReportViewer::m_docMapUpdatePanel
0x13ce3  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x13ce8  ldarg.0
0x13ce9  ldfld    class Microsoft.Reporting.WebForms.PanelUpdater Microsoft.Reporting.WebForms.ReportViewer::m_panelUpdater
0x13cee  ldarg.0
0x13cef  ldfld    class [System.Web.Extensions]System.Web.UI.UpdatePanel Microsoft.Reporting.WebForms.ReportViewer::m_docMapUpdatePanel
0x13cf4  ldc.i4.6
0x13cf5  callvirt instance void Microsoft.Reporting.WebForms.PanelUpdater::RegisterPanel(class [System.Web.Extensions]System.Web.UI.UpdatePanel panel, valuetype Microsoft.Reporting.WebForms.UpdateGroup groupForMembership)
0x13cfa  ldarg.0
0x13cfb  ldarg.0
0x13cfc  callvirt instance class Microsoft.Reporting.WebForms.IReportViewerStyles Microsoft.Reporting.WebForms.ReportViewer::get_ViewerStyle()
0x13d01  ldc.i4.1
0x13d02  call     class Microsoft.Reporting.WebForms.IReportViewerMessages5 Microsoft.Reporting.WebForms.LocalizationHelper::get_Current()
0x13d07  callvirt instance string Microsoft.Reporting.WebForms.IReportViewerMessages4::get_ShowDocumentMapButtonTooltip()
0x13d0c  call     class Microsoft.Reporting.WebForms.IReportViewerMessages5 Microsoft.Reporting.WebForms.LocalizationHelper::get_Current()
0x13d11  callvirt instance string Microsoft.Reporting.WebForms.IReportViewerMessages4::get_HideDocumentMapButtonTooltip()
0x13d16  call     class Microsoft.Reporting.WebForms.IReportViewerMessages5 Microsoft.Reporting.WebForms.LocalizationHelper::get_Current()
0x13d1b  callvirt instance string Microsoft.Reporting.WebForms.IReportViewerMessages::get_DocumentMapButtonToolTip()
0x13d20  newobj   instance void Microsoft.Reporting.WebForms.ReportSplitter::.ctor(class Microsoft.Reporting.WebForms.IReportViewerStyles viewerStyle, bool isVertical, string expandTooltip, string collapseTooltip, string defaultToolTip)
0x13d25  stfld    class Microsoft.Reporting.WebForms.ReportSplitter Microsoft.Reporting.WebForms.ReportViewer::m_docMapAreaSplitter
0x13d2a  ldloc.0
0x13d2b  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x13d30  ldarg.0
0x13d31  ldfld    class Microsoft.Reporting.WebForms.ReportSplitter Microsoft.Reporting.WebForms.ReportViewer::m_docMapAreaSplitter
0x13d36  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x13d3b  ldarg.0
0x13d3c  ldarg.0
0x13d3d  newobj   instance void Microsoft.Reporting.WebForms.DocMapArea::.ctor(class Microsoft.Reporting.WebForms.ReportViewer viewer)
0x13d42  stfld    class Microsoft.Reporting.WebForms.DocMapArea Microsoft.Reporting.WebForms.ReportViewer::m_docMapArea
0x13d47  ldarg.0
0x13d48  ldfld    class Microsoft.Reporting.WebForms.DocMapArea Microsoft.Reporting.WebForms.ReportViewer::m_docMapArea
0x13d4d  ldarg.0
0x13d4e  ldftn    instance void Microsoft.Reporting.WebForms.ReportViewer::OnDocumentMapNavigation(object sender, class Microsoft.Reporting.WebForms.DocumentMapNavigationEventArgs e)
0x13d54  newobj   instance void Microsoft.Reporting.WebForms.DocumentMapNavigationEventHandler::.ctor(object object, native int method)
0x13d59  callvirt instance void Microsoft.Reporting.WebForms.DocMapArea::add_NodeClick(class Microsoft.Reporting.WebForms.DocumentMapNavigationEventHandler value)
0x13d5e  ldarg.0
0x13d5f  ldfld    class [System.Web.Extensions]System.Web.UI.UpdatePanel Microsoft.Reporting.WebForms.ReportViewer::m_docMapUpdatePanel
0x13d64  callvirt instance class [System.Web]System.Web.UI.Control [System.Web.Extensions]System.Web.UI.UpdatePanel::get_ContentTemplateContainer()
0x13d69  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x13d6e  ldarg.0
0x13d6f  ldfld    class Microsoft.Reporting.WebForms.DocMapArea Microsoft.Reporting.WebForms.ReportViewer::m_docMapArea
0x13d74  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x13d79  ldarg.0
0x13d7a  ldarg.0
0x13d7b  callvirt instance class Microsoft.Reporting.WebForms.IReportViewerStyles Microsoft.Reporting.WebForms.ReportViewer::get_ViewerStyle()
0x13d80  ldarg.0
0x13d81  call     instance bool Microsoft.Reporting.WebForms.ReportViewer::get_EnableHybrid()
0x13d86  newobj   instance void Microsoft.Reporting.WebForms.ReportArea::.ctor(class Microsoft.Reporting.WebForms.IReportViewerStyles styles, bool enableHybrid)
0x13d8b  stfld    class Microsoft.Reporting.WebForms.ReportArea Microsoft.Reporting.WebForms.ReportViewer::m_reportArea
0x13d90  ldarg.0
0x13d91  ldfld    class Microsoft.Reporting.WebForms.ReportArea Microsoft.Reporting.WebForms.ReportViewer::m_reportArea
0x13d96  ldarg.0
0x13d97  ldftn    instance void Microsoft.Reporting.WebForms.ReportViewer::OnReportAction(object sender, class Microsoft.Reporting.WebForms.ReportActionEventArgs e)
0x13d9d  newobj   instance void class [mscorlib]System.EventHandler`1<class Microsoft.Reporting.WebForms.ReportActionEventArgs>::.ctor(object, native int)
0x13da2  callvirt instance void Microsoft.Reporting.WebForms.ReportArea::add_ReportAction(class [mscorlib]System.EventHandler`1<class Microsoft.Reporting.WebForms.ReportActionEventArgs> value)
0x13da7  ldarg.0
0x13da8  ldfld    class Microsoft.Reporting.WebForms.ReportArea Microsoft.Reporting.WebForms.ReportViewer::m_reportArea
0x13dad  ldarg.0
0x13dae  ldftn    instance void Microsoft.Reporting.WebForms.ReportViewer::OnClientSideZoomChanged(object sender, class Microsoft.Reporting.WebForms.ZoomChangeEventArgs e)
0x13db4  newobj   instance void Microsoft.Reporting.WebForms.ZoomChangedEventHandler::.ctor(object object, native int method)
0x13db9  callvirt instance void Microsoft.Reporting.WebForms.ReportArea::add_ZoomChanged(class Microsoft.Reporting.WebForms.ZoomChangedEventHandler value)
0x13dbe  ldarg.0
0x13dbf  ldfld    class Microsoft.Reporting.WebForms.ReportArea Microsoft.Reporting.WebForms.ReportViewer::m_reportArea
0x13dc4  ldarg.0
0x13dc5  ldftn    instance void Microsoft.Reporting.WebForms.ReportViewer::OnAsyncLoadReport(object sender, class [mscorlib]System.EventArgs e)
0x13dcb  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x13dd0  callvirt instance void Microsoft.Reporting.WebForms.ReportArea::add_AsyncLoadRequested(class [mscorlib]System.EventHandler value)
0x13dd5  ldarg.0
0x13dd6  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x13ddb  call     class [System.Web.Extensions]System.Web.UI.ScriptManager [System.Web.Extensions]System.Web.UI.ScriptManager::GetCurrent(class [System.Web]System.Web.UI.Page)
0x13de0  brfalse.s loc_13DF3
0x13de2  ldloc.0
0x13de3  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x13de8  ldarg.0
0x13de9  ldfld    class Microsoft.Reporting.WebForms.ReportArea Microsoft.Reporting.WebForms.ReportViewer::m_reportArea
0x13dee  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x13df3  ldarg.0
0x13df4  newobj   instance void Microsoft.Reporting.WebForms.HttpHandlerMissingErrorMessage::.ctor()
0x13df9  stfld    class Microsoft.Reporting.WebForms.HttpHandlerMissingErrorMessage Microsoft.Reporting.WebForms.ReportViewer::m_httpHandlerMissingError
0x13dfe  ldarg.0
0x13dff  ldfld    class Microsoft.Reporting.WebForms.HttpHandlerMissingErrorMessage Microsoft.Reporting.WebForms.ReportViewer::m_httpHandlerMissingError
0x13e04  ldstr    aHttphandlermis// "HttpHandlerMissingErrorMessage"
0x13e09  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x13e0e  ldloc.0
0x13e0f  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x13e14  ldarg.0
0x13e15  ldfld    class Microsoft.Reporting.WebForms.HttpHandlerMissingErrorMessage Microsoft.Reporting.WebForms.ReportViewer::m_httpHandlerMissingError
0x13e1a  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x13e1f  ldarg.0
0x13e20  newobj   instance void Microsoft.Reporting.WebForms.NotSupportedBrowserErrorMessage::.ctor()
0x13e25  stfld    class Microsoft.Reporting.WebForms.NotSupportedBrowserErrorMessage Microsoft.Reporting.WebForms.ReportViewer::m_browserNotSupportedErrorMessage
0x13e2a  ldarg.0
0x13e2b  ldfld    class Microsoft.Reporting.WebForms.NotSupportedBrowserErrorMessage Microsoft.Reporting.WebForms.ReportViewer::m_browserNotSupportedErrorMessage
0x13e30  ldstr    aBrowsernotsupp// "BrowserNotSupportedErrorMessage"
0x13e35  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x13e3a  ldloc.0
0x13e3b  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x13e40  ldarg.0
0x13e41  ldfld    class Microsoft.Reporting.WebForms.NotSupportedBrowserErrorMessage Microsoft.Reporting.WebForms.ReportViewer::m_browserNotSupportedErrorMessage
0x13e46  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x13e4b  ldarg.0
0x13e4c  ldfld    class Microsoft.Reporting.WebForms.ReportSplitter Microsoft.Reporting.WebForms.ReportViewer::m_docMapAreaSplitter
0x13e51  ldarg.0
0x13e52  ldftn    instance void Microsoft.Reporting.WebForms.ReportViewer::ClientSideDocMapAreaVisibilityChanged(object sender, class [mscorlib]System.EventArgs e)
0x13e58  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x13e5d  callvirt instance void Microsoft.Reporting.WebForms.ReportSplitter::add_CollapsedChanged(class [mscorlib]System.EventHandler value)
0x13e62  ldarg.0
0x13e63  ldfld    class Microsoft.Reporting.WebForms.ReportSplitter Microsoft.Reporting.WebForms.ReportViewer::m_parametersAreaSplitter
0x13e68  ldarg.0
0x13e69  ldftn    instance void Microsoft.Reporting.WebForms.ReportViewer::ClientSidePromptAreaVisibilityChanged(object sender, class [mscorlib]System.EventArgs e)
  ... truncated ...
```
