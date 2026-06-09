# Microsoft.Reporting.WebForms.FindGroup::CreateChildControls

- ea: `0x193c0`
- end: `0x19655`
- name: `Microsoft.Reporting.WebForms.FindGroup::CreateChildControls`
- size: `661`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x1380`
- `0x1390`
- `0x13a0`
- `0x40b0`
- `0x15790`
- `0x17a30`
- `0x17b50`
- `0x185d0`
- `0x185f0`
- `0x193c0`
- `0x19ae0`
- `0x1a570`
- `0x1a580`
- `0x22ab0`

## string_xrefs

- `0x1953e`: `DisabledLink`

## pseudocode

```c

```

## disassembly

```asm
0x193c0  ldarg.0
0x193c1  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x193c6  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Clear()
0x193cb  ldarg.0
0x193cc  newobj   instance void [System.Web]System.Web.UI.WebControls.TextBox::.ctor()
0x193d1  stfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.Reporting.WebForms.FindGroup::m_findText
0x193d6  ldarg.0
0x193d7  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.Reporting.WebForms.FindGroup::m_findText
0x193dc  ldc.i4   0xFF
0x193e1  callvirt instance void [System.Web]System.Web.UI.WebControls.TextBox::set_MaxLength(int32)
0x193e6  ldarg.0
0x193e7  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.Reporting.WebForms.FindGroup::m_findText
0x193ec  ldc.i4.s 0xA
0x193ee  callvirt instance void [System.Web]System.Web.UI.WebControls.TextBox::set_Columns(int32)
0x193f3  ldarg.0
0x193f4  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.Reporting.WebForms.FindGroup::m_findText
0x193f9  call     class Microsoft.Reporting.WebForms.IReportViewerMessages5 Microsoft.Reporting.WebForms.LocalizationHelper::get_Current()
0x193fe  callvirt instance string Microsoft.Reporting.WebForms.IReportViewerMessages::get_SearchTextBoxToolTip()
0x19403  callvirt instance void [System.Web]System.Web.UI.WebControls.WebControl::set_ToolTip(string)
0x19408  ldarg.0
0x19409  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.Reporting.WebForms.FindGroup::m_findText
0x1940e  ldarg.0
0x1940f  ldfld    class Microsoft.Reporting.WebForms.ReportViewer Microsoft.Reporting.WebForms.ToolbarGroup::m_viewer
0x19414  callvirt instance class Microsoft.Reporting.WebForms.IReportViewerStyles Microsoft.Reporting.WebForms.ReportViewer::get_ViewerStyle()
0x19419  callvirt instance string Microsoft.Reporting.WebForms.IReportViewerStyles::get_ToolbarTextBox()
0x1941e  callvirt instance void [System.Web]System.Web.UI.WebControls.WebControl::set_CssClass(string)
0x19423  ldarg.0
0x19424  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.Reporting.WebForms.FindGroup::m_findText
0x19429  ldc.i4.0
0x1942a  callvirt instance void [System.Web]System.Web.UI.WebControls.WebControl::set_Enabled(bool)
0x1942f  ldarg.0
0x19430  ldarg.0
0x19431  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.Reporting.WebForms.FindGroup::m_findText
0x19436  call     instance void Microsoft.Reporting.WebForms.ToolbarGroup::SetDefaultTabIndex(class [System.Web]System.Web.UI.WebControls.WebControl control)
0x1943b  ldarg.0
0x1943c  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x19441  ldarg.0
0x19442  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.Reporting.WebForms.FindGroup::m_findText
0x19447  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x1944c  ldarg.0
0x1944d  call     instance bool [System.Web]System.Web.UI.Control::get_DesignMode()
0x19452  brfalse.s loc_19487
0x19454  ldarg.0
0x19455  ldstr    aMicrosoftRepor_59// "Microsoft.Reporting.WebForms.Icons.Find"
0x1945a  newobj   instance void Microsoft.Reporting.WebForms.ToolbarImageInfo::.ctor(string ltrImage)
0x1945f  ldstr    aMicrosoftRepor_59// "Microsoft.Reporting.WebForms.Icons.Find"
0x19464  newobj   instance void Microsoft.Reporting.WebForms.ToolbarImageInfo::.ctor(string ltrImage)
0x19469  ldc.i4.1
0x1946a  call     class Microsoft.Reporting.WebForms.IReportViewerMessages5 Microsoft.Reporting.WebForms.LocalizationHelper::get_Current()
0x1946f  callvirt instance string Microsoft.Reporting.WebForms.IReportViewerMessages::get_FindButtonToolTip()
0x19474  ldarg.0
0x19475  ldfld    class Microsoft.Reporting.WebForms.ReportViewer Microsoft.Reporting.WebForms.ToolbarGroup::m_viewer
0x1947a  ldnull
0x1947b  newobj   instance void Microsoft.Reporting.WebForms.ScriptSwitchImage::.ctor(class Microsoft.Reporting.WebForms.ToolbarImageInfo image1, class Microsoft.Reporting.WebForms.ToolbarImageInfo image2, bool image2Disabled, string tooltip, class Microsoft.Reporting.WebForms.ReportViewer viewer, [opt] string onClickScript)
0x19480  stfld    class Microsoft.Reporting.WebForms.ScriptSwitchImage Microsoft.Reporting.WebForms.FindGroup::m_findButton
0x19485  br.s     loc_194BD
0x19487  ldarg.0
0x19488  ldstr    aGlyphuiGlyphui_7// "glyphui glyphui-find"
0x1948d  ldstr    aMicrosoftRepor_59// "Microsoft.Reporting.WebForms.Icons.Find"
0x19492  newobj   instance void Microsoft.Reporting.WebForms.ToolbarImageInfo::.ctor(string ltrImage)
0x19497  ldstr    aMicrosoftRepor_59// "Microsoft.Reporting.WebForms.Icons.Find"
0x1949c  newobj   instance void Microsoft.Reporting.WebForms.ToolbarImageInfo::.ctor(string ltrImage)
0x194a1  ldc.i4.1
0x194a2  call     class Microsoft.Reporting.WebForms.IReportViewerMessages5 Microsoft.Reporting.WebForms.LocalizationHelper::get_Current()
0x194a7  callvirt instance string Microsoft.Reporting.WebForms.IReportViewerMessages::get_FindButtonToolTip()
0x194ac  ldarg.0
0x194ad  ldfld    class Microsoft.Reporting.WebForms.ReportViewer Microsoft.Reporting.WebForms.ToolbarGroup::m_viewer
0x194b2  ldnull
0x194b3  newobj   instance void Microsoft.Reporting.WebForms.ScriptSwitchImage::.ctor(string glyphCssStyling, class Microsoft.Reporting.WebForms.ToolbarImageInfo image1, class Microsoft.Reporting.WebForms.ToolbarImageInfo image2, bool image2Disabled, string tooltip, class Microsoft.Reporting.WebForms.ReportViewer viewer, [opt] string onClickScript)
0x194b8  stfld    class Microsoft.Reporting.WebForms.ScriptSwitchImage Microsoft.Reporting.WebForms.FindGroup::m_findButton
0x194bd  ldarg.0
0x194be  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x194c3  ldarg.0
0x194c4  ldfld    class Microsoft.Reporting.WebForms.ScriptSwitchImage Microsoft.Reporting.WebForms.FindGroup::m_findButton
0x194c9  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x194ce  ldarg.0
0x194cf  newobj   instance void [System.Web]System.Web.UI.WebControls.Label::.ctor()
0x194d4  stfld    class [System.Web]System.Web.UI.WebControls.Label Microsoft.Reporting.WebForms.FindGroup::m_findResultsLabel
0x194d9  ldarg.0
0x194da  ldfld    class [System.Web]System.Web.UI.WebControls.Label Microsoft.Reporting.WebForms.FindGroup::m_findResultsLabel
0x194df  ldarg.0
0x194e0  ldfld    class Microsoft.Reporting.WebForms.ReportViewer Microsoft.Reporting.WebForms.ToolbarGroup::m_viewer
0x194e5  callvirt instance class Microsoft.Reporting.WebForms.IReportViewerStyles Microsoft.Reporting.WebForms.ReportViewer::get_ViewerStyle()
0x194ea  callvirt instance string Microsoft.Reporting.WebForms.IReportViewerStyles::get_AccessibleOffScreen()
0x194ef  callvirt instance void [System.Web]System.Web.UI.WebControls.WebControl::set_CssClass(string)
0x194f4  ldarg.0
0x194f5  ldarg.0
0x194f6  ldfld    class [System.Web]System.Web.UI.WebControls.Label Microsoft.Reporting.WebForms.FindGroup::m_findResultsLabel
0x194fb  ldnull
0x194fc  ldstr    aAlert// "alert"
0x19501  call     instance void Microsoft.Reporting.WebForms.ToolbarGroup::SetAriaTags(class [System.Web]System.Web.UI.WebControls.WebControl control, string label, [opt] string role)
0x19506  ldarg.0
0x19507  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x1950c  ldarg.0
0x1950d  ldfld    class [System.Web]System.Web.UI.WebControls.Label Microsoft.Reporting.WebForms.FindGroup::m_findResultsLabel
0x19512  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x19517  ldarg.0
0x19518  newobj   instance void Microsoft.Reporting.WebForms.SafeLiteralControl::.ctor()
0x1951d  stfld    class Microsoft.Reporting.WebForms.SafeLiteralControl Microsoft.Reporting.WebForms.FindGroup::m_sep
0x19522  ldarg.0
0x19523  ldfld    class Microsoft.Reporting.WebForms.SafeLiteralControl Microsoft.Reporting.WebForms.FindGroup::m_sep
0x19528  ldstr    asc_4A43E// "|"
0x1952d  stfld    string Microsoft.Reporting.WebForms.SafeLiteralControl::Text
0x19532  ldarg.0
0x19533  ldfld    class Microsoft.Reporting.WebForms.SafeLiteralControl Microsoft.Reporting.WebForms.FindGroup::m_sep
0x19538  dup
0x19539  callvirt instance string [System.Web]System.Web.UI.WebControls.WebControl::get_CssClass()
0x1953e  ldstr    aDisabledlink// "DisabledLink"
0x19543  call     string [mscorlib]System.String::Concat(string, string)
0x19548  callvirt instance void [System.Web]System.Web.UI.WebControls.WebControl::set_CssClass(string)
0x1954d  ldarg.0
0x1954e  ldfld    class Microsoft.Reporting.WebForms.SafeLiteralControl Microsoft.Reporting.WebForms.FindGroup::m_sep
0x19553  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.WebControls.WebControl::get_Attributes()
0x19558  ldstr    aAriaHidden// "aria-hidden"
0x1955d  ldstr    aTrue// "true"
0x19562  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x19567  ldarg.0
0x19568  ldfld    class Microsoft.Reporting.WebForms.SafeLiteralControl Microsoft.Reporting.WebForms.FindGroup::m_sep
0x1956d  ldarg.0
0x1956e  ldfld    bool Microsoft.Reporting.WebForms.FindGroup::m_showTextSeparator
0x19573  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x19578  ldarg.0
0x19579  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x1957e  ldarg.0
0x1957f  ldfld    class Microsoft.Reporting.WebForms.SafeLiteralControl Microsoft.Reporting.WebForms.FindGroup::m_sep
0x19584  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x19589  ldarg.0
0x1958a  call     instance bool [System.Web]System.Web.UI.Control::get_DesignMode()
0x1958f  brfalse.s loc_195C4
0x19591  ldarg.0
0x19592  ldstr    aMicrosoftRepor_59// "Microsoft.Reporting.WebForms.Icons.Find"
0x19597  newobj   instance void Microsoft.Reporting.WebForms.ToolbarImageInfo::.ctor(string ltrImage)
0x1959c  ldstr    aMicrosoftRepor_59// "Microsoft.Reporting.WebForms.Icons.Find"
0x195a1  newobj   instance void Microsoft.Reporting.WebForms.ToolbarImageInfo::.ctor(string ltrImage)
0x195a6  ldc.i4.1
0x195a7  call     class Microsoft.Reporting.WebForms.IReportViewerMessages5 Microsoft.Reporting.WebForms.LocalizationHelper::get_Current()
0x195ac  callvirt instance string Microsoft.Reporting.WebForms.IReportViewerMessages::get_FindNextButtonToolTip()
0x195b1  ldarg.0
0x195b2  ldfld    class Microsoft.Reporting.WebForms.ReportViewer Microsoft.Reporting.WebForms.ToolbarGroup::m_viewer
0x195b7  ldnull
0x195b8  newobj   instance void Microsoft.Reporting.WebForms.ScriptSwitchImage::.ctor(class Microsoft.Reporting.WebForms.ToolbarImageInfo image1, class Microsoft.Reporting.WebForms.ToolbarImageInfo image2, bool image2Disabled, string tooltip, class Microsoft.Reporting.WebForms.ReportViewer viewer, [opt] string onClickScript)
0x195bd  stfld    class Microsoft.Reporting.WebForms.ScriptSwitchImage Microsoft.Reporting.WebForms.FindGroup::m_nextButton
0x195c2  br.s     loc_195FA
0x195c4  ldarg.0
0x195c5  ldstr    aGlyphuiGlyphui_8// "glyphui glyphui-findnext"
0x195ca  ldstr    aMicrosoftRepor_60// "Microsoft.Reporting.WebForms.Icons.Find"...
0x195cf  newobj   instance void Microsoft.Reporting.WebForms.ToolbarImageInfo::.ctor(string ltrImage)
0x195d4  ldstr    aMicrosoftRepor_60// "Microsoft.Reporting.WebForms.Icons.Find"...
0x195d9  newobj   instance void Microsoft.Reporting.WebForms.ToolbarImageInfo::.ctor(string ltrImage)
0x195de  ldc.i4.1
0x195df  call     class Microsoft.Reporting.WebForms.IReportViewerMessages5 Microsoft.Reporting.WebForms.LocalizationHelper::get_Current()
0x195e4  callvirt instance string Microsoft.Reporting.WebForms.IReportViewerMessages::get_FindNextButtonToolTip()
0x195e9  ldarg.0
0x195ea  ldfld    class Microsoft.Reporting.WebForms.ReportViewer Microsoft.Reporting.WebForms.ToolbarGroup::m_viewer
0x195ef  ldnull
0x195f0  newobj   instance void Microsoft.Reporting.WebForms.ScriptSwitchImage::.ctor(string glyphCssStyling, class Microsoft.Reporting.WebForms.ToolbarImageInfo image1, class Microsoft.Reporting.WebForms.ToolbarImageInfo image2, bool image2Disabled, string tooltip, class Microsoft.Reporting.WebForms.ReportViewer viewer, [opt] string onClickScript)
0x195f5  stfld    class Microsoft.Reporting.WebForms.ScriptSwitchImage Microsoft.Reporting.WebForms.FindGroup::m_nextButton
0x195fa  ldarg.0
0x195fb  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x19600  ldarg.0
0x19601  ldfld    class Microsoft.Reporting.WebForms.ScriptSwitchImage Microsoft.Reporting.WebForms.FindGroup::m_nextButton
0x19606  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x1960b  ldarg.0
0x1960c  newobj   instance void [System.Web]System.Web.UI.WebControls.Label::.ctor()
0x19611  stfld    class [System.Web]System.Web.UI.WebControls.Label Microsoft.Reporting.WebForms.FindGroup::m_nextResultsLabel
0x19616  ldarg.0
0x19617  ldfld    class [System.Web]System.Web.UI.WebControls.Label Microsoft.Reporting.WebForms.FindGroup::m_nextResultsLabel
0x1961c  ldarg.0
0x1961d  ldfld    class Microsoft.Reporting.WebForms.ReportViewer Microsoft.Reporting.WebForms.ToolbarGroup::m_viewer
0x19622  callvirt instance class Microsoft.Reporting.WebForms.IReportViewerStyles Microsoft.Reporting.WebForms.ReportViewer::get_ViewerStyle()
0x19627  callvirt instance string Microsoft.Reporting.WebForms.IReportViewerStyles::get_AccessibleOffScreen()
0x1962c  callvirt instance void [System.Web]System.Web.UI.WebControls.WebControl::set_CssClass(string)
0x19631  ldarg.0
0x19632  ldarg.0
0x19633  ldfld    class [System.Web]System.Web.UI.WebControls.Label Microsoft.Reporting.WebForms.FindGroup::m_nextResultsLabel
0x19638  ldnull
0x19639  ldstr    aAlert// "alert"
0x1963e  call     instance void Microsoft.Reporting.WebForms.ToolbarGroup::SetAriaTags(class [System.Web]System.Web.UI.WebControls.WebControl control, string label, [opt] string role)
0x19643  ldarg.0
0x19644  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x19649  ldarg.0
0x1964a  ldfld    class [System.Web]System.Web.UI.WebControls.Label Microsoft.Reporting.WebForms.FindGroup::m_nextResultsLabel
0x1964f  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x19654  ret
```
