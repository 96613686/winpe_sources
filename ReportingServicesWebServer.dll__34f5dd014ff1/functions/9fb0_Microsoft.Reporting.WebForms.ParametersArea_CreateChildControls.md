# Microsoft.Reporting.WebForms.ParametersArea::CreateChildControls

- ea: `0x9fb0`
- end: `0xa24e`
- name: `Microsoft.Reporting.WebForms.ParametersArea::CreateChildControls`
- size: `670`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: `broker_com_uri`

## callees

- `0x1400`
- `0x1440`
- `0x1530`
- `0x3330`
- `0x40b0`
- `0x7a30`
- `0x9bf0`
- `0x9f90`
- `0x9fb0`
- `0xa250`
- `0xaa20`
- `0xb5a0`
- `0xb610`
- `0xb680`
- `0xb940`
- `0xbbf0`
- `0xc240`
- `0xc2a0`
- `0xc300`
- `0xc3c0`
- `0xca70`
- `0xf480`
- `0x22a90`
- `0x3a900`

## pseudocode

```c

```

## disassembly

```asm
0x9fb0  ldarg.0
0x9fb1  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x9fb6  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Clear()
0x9fbb  ldarg.0
0x9fbc  ldnull
0x9fbd  stfld    class Microsoft.Reporting.WebForms.ParameterControlCollection Microsoft.Reporting.WebForms.ParametersArea::m_paramControls
0x9fc2  ldarg.0
0x9fc3  ldnull
0x9fc4  stfld    class Microsoft.Reporting.WebForms.DataSourceControlCollection Microsoft.Reporting.WebForms.ParametersArea::m_dsControls
0x9fc9  ldarg.0
0x9fca  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Reporting.WebForms.BaseParameterInputControl, class Microsoft.Reporting.WebForms.SafeLiteralControl> Microsoft.Reporting.WebForms.ParametersArea::m_paramPrompts
0x9fcf  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Reporting.WebForms.BaseParameterInputControl, class Microsoft.Reporting.WebForms.SafeLiteralControl>::Clear()
0x9fd4  ldarg.0
0x9fd5  newobj   instance void Microsoft.Reporting.WebForms.ViewReportButton::.ctor()
0x9fda  stfld    class [System.Web]System.Web.UI.WebControls.Button Microsoft.Reporting.WebForms.ParametersArea::m_viewReportButton
0x9fdf  ldarg.0
0x9fe0  ldfld    class [System.Web]System.Web.UI.WebControls.Button Microsoft.Reporting.WebForms.ParametersArea::m_viewReportButton
0x9fe5  call     class Microsoft.Reporting.WebForms.IReportViewerMessages5 Microsoft.Reporting.WebForms.LocalizationHelper::get_Current()
0x9fea  callvirt instance string Microsoft.Reporting.WebForms.IReportViewerMessages::get_ViewReportButtonText()
0x9fef  callvirt instance void [System.Web]System.Web.UI.WebControls.Button::set_Text(string)
0x9ff4  ldarg.0
0x9ff5  ldfld    class [System.Web]System.Web.UI.WebControls.Button Microsoft.Reporting.WebForms.ParametersArea::m_viewReportButton
0x9ffa  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.WebControls.WebControl::get_Attributes()
0x9fff  ldstr    aTabindex// "tabindex"
0xa004  ldstr    a1_0// "1"
0xa009  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xa00e  ldarg.0
0xa00f  ldfld    class [System.Web]System.Web.UI.WebControls.Button Microsoft.Reporting.WebForms.ParametersArea::m_viewReportButton
0xa014  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.WebControls.WebControl::get_Attributes()
0xa019  ldstr    aClass// "class"
0xa01e  ldstr    aSubmitbutton// "SubmitButton"
0xa023  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xa028  ldarg.0
0xa029  ldfld    class [System.Web]System.Web.UI.WebControls.Button Microsoft.Reporting.WebForms.ParametersArea::m_viewReportButton
0xa02e  ldarg.0
0xa02f  ldftn    instance void Microsoft.Reporting.WebForms.ParametersArea::OnViewReport(object sender, class [mscorlib]System.EventArgs e)
0xa035  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0xa03a  callvirt instance void [System.Web]System.Web.UI.WebControls.Button::add_Click(class [mscorlib]System.EventHandler)
0xa03f  ldarg.0
0xa040  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xa045  ldarg.0
0xa046  ldfld    class [System.Web]System.Web.UI.WebControls.Button Microsoft.Reporting.WebForms.ParametersArea::m_viewReportButton
0xa04b  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xa050  ldarg.0
0xa051  call     class Microsoft.Reporting.WebForms.IReportViewerMessages5 Microsoft.Reporting.WebForms.LocalizationHelper::get_Current()
0xa056  callvirt instance string Microsoft.Reporting.WebForms.IReportViewerMessages::get_ChangeCredentialsText()
0xa05b  call     class Microsoft.Reporting.WebForms.IReportViewerMessages5 Microsoft.Reporting.WebForms.LocalizationHelper::get_Current()
0xa060  callvirt instance string Microsoft.Reporting.WebForms.IReportViewerMessages::get_ChangeCredentialsToolTip()
0xa065  ldarg.0
0xa066  ldfld    class Microsoft.Reporting.WebForms.IReportViewerStyles Microsoft.Reporting.WebForms.ParametersArea::m_styles
0xa06b  newobj   instance void Microsoft.Reporting.WebForms.TextButton::.ctor(string text, string tooltip, class Microsoft.Reporting.WebForms.IReportViewerStyles viewerStyle)
0xa070  stfld    class Microsoft.Reporting.WebForms.TextButton Microsoft.Reporting.WebForms.ParametersArea::m_changeCredentials
0xa075  ldarg.0
0xa076  ldfld    class Microsoft.Reporting.WebForms.TextButton Microsoft.Reporting.WebForms.ParametersArea::m_changeCredentials
0xa07b  ldc.i4.0
0xa07c  stfld    bool Microsoft.Reporting.WebForms.TextButton::ShowDisabled
0xa081  ldarg.0
0xa082  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xa087  ldarg.0
0xa088  ldfld    class Microsoft.Reporting.WebForms.TextButton Microsoft.Reporting.WebForms.ParametersArea::m_changeCredentials
0xa08d  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xa092  call     bool Microsoft.Reporting.WebForms.Global::get_IsDesignTime()
0xa097  brfalse.s loc_A09E
0xa099  leave    loc_A24D
0xa09e  ldarg.0
0xa09f  ldfld    class Microsoft.Reporting.WebForms.ReportParameterInfoCollection Microsoft.Reporting.WebForms.ParametersArea::m_paramsInfo
0xa0a4  brfalse.s loc_A0AE
0xa0a6  ldarg.0
0xa0a7  ldfld    class Microsoft.Reporting.WebForms.ParametersPaneLayout Microsoft.Reporting.WebForms.ParametersArea::m_paramsPaneLayoutInfo
0xa0ac  brtrue.s loc_A0B4
0xa0ae  ldarg.0
0xa0af  call     instance void Microsoft.Reporting.WebForms.ParametersArea::RefreshControlsFromReportMetadata()
0xa0b4  ldarg.0
0xa0b5  ldfld    class Microsoft.Reporting.WebForms.ReportDataSourceInfoCollection Microsoft.Reporting.WebForms.ParametersArea::m_dsInfos
0xa0ba  brfalse.s loc_A13B
0xa0bc  ldarg.0
0xa0bd  ldfld    class Microsoft.Reporting.WebForms.ReportDataSourceInfoCollection Microsoft.Reporting.WebForms.ParametersArea::m_dsInfos
0xa0c2  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class Microsoft.Reporting.WebForms.ReportDataSourceInfo>::get_Count()
0xa0c7  ldc.i4.0
0xa0c8  ble.s    loc_A13B
0xa0ca  ldarg.0
0xa0cb  ldarg.0
0xa0cc  ldfld    class Microsoft.Reporting.WebForms.ReportDataSourceInfoCollection Microsoft.Reporting.WebForms.ParametersArea::m_dsInfos
0xa0d1  ldarg.0
0xa0d2  dup
0xa0d3  ldvirtftn instance void Microsoft.Reporting.WebForms.ParametersArea::RenderOneDataSource(class Microsoft.Reporting.WebForms.DataSourceControl control, class [System.Web]System.Web.UI.HtmlTextWriter writer)
0xa0d9  newobj   instance void CredentialRenderer::.ctor(object object, native int method)
0xa0de  ldarg.0
0xa0df  ldfld    class Microsoft.Reporting.WebForms.IReportViewerStyles Microsoft.Reporting.WebForms.ParametersArea::m_styles
0xa0e4  call     class Microsoft.Reporting.WebForms.DataSourceControlCollection Microsoft.Reporting.WebForms.DataSourceControlCollection::Create(class Microsoft.Reporting.WebForms.ReportDataSourceInfoCollection dsInfos, class CredentialRenderer renderer, class Microsoft.Reporting.WebForms.IReportViewerStyles styles)
0xa0e9  stfld    class Microsoft.Reporting.WebForms.DataSourceControlCollection Microsoft.Reporting.WebForms.ParametersArea::m_dsControls
0xa0ee  ldarg.0
0xa0ef  ldfld    class Microsoft.Reporting.WebForms.DataSourceControlCollection Microsoft.Reporting.WebForms.ParametersArea::m_dsControls
0xa0f4  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Reporting.WebForms.DataSourceControl>::GetEnumerator()
0xa0f9  stloc.0
0xa0fa  br.s     loc_A122
0xa0fc  ldloca.s 0
0xa0fe  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Reporting.WebForms.DataSourceControl>::get_Current()
0xa103  stloc.1
0xa104  ldloc.1
0xa105  ldarg.0
0xa106  ldftn    instance void Microsoft.Reporting.WebForms.ParametersArea::OnCredentialsChanged(object sender, class [mscorlib]System.EventArgs e)
0xa10c  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0xa111  callvirt instance void Microsoft.Reporting.WebForms.DataSourceControl::add_ValueChanged(class [mscorlib]System.EventHandler value)
0xa116  ldarg.0
0xa117  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xa11c  ldloc.1
0xa11d  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xa122  ldloca.s 0
0xa124  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Reporting.WebForms.DataSourceControl>::MoveNext()
0xa129  brtrue.s loc_A0FC
0xa12b  leave.s  loc_A13B
0xa12d  ldloca.s 0
0xa12f  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Reporting.WebForms.DataSourceControl>
0xa135  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa13a  endfinally
0xa13b  ldarg.0
0xa13c  ldfld    class Microsoft.Reporting.WebForms.ReportParameterInfoCollection Microsoft.Reporting.WebForms.ParametersArea::m_paramsInfo
0xa141  brfalse  loc_A23B
0xa146  ldarg.0
0xa147  ldfld    class Microsoft.Reporting.WebForms.ReportParameterInfoCollection Microsoft.Reporting.WebForms.ParametersArea::m_paramsInfo
0xa14c  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class Microsoft.Reporting.WebForms.ReportParameterInfo>::get_Count()
0xa151  ldc.i4.0
0xa152  ble      loc_A23B
0xa157  ldarg.0
0xa158  ldfld    class Microsoft.Reporting.WebForms.IParameterSupplier Microsoft.Reporting.WebForms.ParametersArea::m_parameterSupplier
0xa15d  callvirt instance bool Microsoft.Reporting.WebForms.IParameterSupplier::get_IsQueryExecutionAllowed()
0xa162  stloc.2
0xa163  ldarg.0
0xa164  ldarg.0
0xa165  ldfld    class Microsoft.Reporting.WebForms.ReportParameterInfoCollection Microsoft.Reporting.WebForms.ParametersArea::m_paramsInfo
0xa16a  ldloc.2
0xa16b  ldarg.0
0xa16c  ldfld    class Microsoft.Reporting.WebForms.IReportViewerStyles Microsoft.Reporting.WebForms.ParametersArea::m_styles
0xa171  ldarg.0
0xa172  ldfld    bool Microsoft.Reporting.WebForms.ParametersArea::m_showHiddenParameters
0xa177  ldarg.0
0xa178  ldfld    bool Microsoft.Reporting.WebForms.ParametersArea::m_positioningMode
0xa17d  call     class Microsoft.Reporting.WebForms.ParameterControlCollection Microsoft.Reporting.WebForms.ParameterControlCollection::Create(class Microsoft.Reporting.WebForms.ReportParameterInfoCollection reportParams, bool allowQueryExecution, class Microsoft.Reporting.WebForms.IReportViewerStyles styles, bool showHiddenParameters, bool positioningMode)
0xa182  stfld    class Microsoft.Reporting.WebForms.ParameterControlCollection Microsoft.Reporting.WebForms.ParametersArea::m_paramControls
0xa187  ldstr    aDataParametern// "data-parameterName"
0xa18c  stloc.3
0xa18d  ldarg.0
0xa18e  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Reporting.WebForms.BaseParameterInputControl> Microsoft.Reporting.WebForms.ParametersArea::get_ParameterControls()
0xa193  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Reporting.WebForms.BaseParameterInputControl>::GetEnumerator()
0xa198  stloc.s  4
0xa19a  br       loc_A221
0xa19f  ldloc.s  4
0xa1a1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Reporting.WebForms.BaseParameterInputControl>::get_Current()
0xa1a6  stloc.s  5
0xa1a8  ldloc.s  5
0xa1aa  callvirt instance string Microsoft.Reporting.WebForms.BaseParameterInputControl::get_Prompt()
0xa1af  ldloc.s  5
0xa1b1  callvirt instance bool Microsoft.Reporting.WebForms.BaseParameterInputControl::get_Disabled()
0xa1b6  newobj   instance void Microsoft.Reporting.WebForms.SafeLiteralControl::.ctor(string text, bool disabled)
0xa1bb  stloc.s  6
0xa1bd  ldarg.0
0xa1be  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xa1c3  ldloc.s  6
0xa1c5  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xa1ca  ldarg.0
0xa1cb  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Reporting.WebForms.BaseParameterInputControl, class Microsoft.Reporting.WebForms.SafeLiteralControl> Microsoft.Reporting.WebForms.ParametersArea::m_paramPrompts
0xa1d0  ldloc.s  5
0xa1d2  ldloc.s  6
0xa1d4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Reporting.WebForms.BaseParameterInputControl, class Microsoft.Reporting.WebForms.SafeLiteralControl>::Add(var<u1>, !!T0)
0xa1d9  ldloc.s  5
0xa1db  ldarg.0
0xa1dc  ldftn    instance void Microsoft.Reporting.WebForms.ParametersArea::OnParametersChanged(object sender, class [mscorlib]System.EventArgs e)
0xa1e2  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0xa1e7  callvirt instance void Microsoft.Reporting.WebForms.BaseParameterInputControl::add_ValueChanged(class [mscorlib]System.EventHandler value)
0xa1ec  ldloc.s  5
0xa1ee  ldarg.0
0xa1ef  dup
0xa1f0  ldvirtftn instance void Microsoft.Reporting.WebForms.ParametersArea::OnAutoPostBackOccurred(object sender, class [mscorlib]System.EventArgs e)
0xa1f6  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0xa1fb  callvirt instance void Microsoft.Reporting.WebForms.BaseParameterInputControl::add_AutoPostBackOccurred(class [mscorlib]System.EventHandler value)
0xa200  ldloc.s  5
0xa202  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.WebControls.WebControl::get_Attributes()
0xa207  ldloc.3
0xa208  ldloc.s  5
0xa20a  callvirt instance class Microsoft.Reporting.WebForms.ReportParameterInfo Microsoft.Reporting.WebForms.BaseParameterInputControl::get_ReportParameter()
0xa20f  callvirt instance string Microsoft.Reporting.WebForms.ReportParameterInfo::get_Name()
0xa214  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xa219  ldarg.0
0xa21a  ldloc.s  5
0xa21c  callvirt instance void Microsoft.Reporting.WebForms.ParametersArea::CreateRenderedParameterControl(class Microsoft.Reporting.WebForms.BaseParameterInputControl parameterControl)
0xa221  ldloc.s  4
0xa223  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xa228  brtrue   loc_A19F
0xa22d  leave.s  loc_A23B
0xa22f  ldloc.s  4
0xa231  brfalse.s loc_A23A
0xa233  ldloc.s  4
0xa235  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa23a  endfinally
0xa23b  leave.s  loc_A24D
0xa23d  stloc.s  7
0xa23f  ldarg.0
0xa240  ldloc.s  7
0xa242  call     instance bool Microsoft.Reporting.WebForms.ParametersArea::OnError(class [mscorlib]System.Exception e)
0xa247  brtrue.s loc_A24B
0xa249  rethrow
0xa24b  leave.s  loc_A24D
0xa24d  ret
```
