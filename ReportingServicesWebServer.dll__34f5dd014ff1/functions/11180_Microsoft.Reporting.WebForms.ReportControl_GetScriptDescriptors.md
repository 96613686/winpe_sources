# Microsoft.Reporting.WebForms.ReportControl::GetScriptDescriptors

- ea: `0x11180`
- end: `0x1146b`
- name: `Microsoft.Reporting.WebForms.ReportControl::GetScriptDescriptors`
- size: `747`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0xfdf0`
- `0xfe00`
- `0xfe10`
- `0x10820`
- `0x11100`
- `0x11140`
- `0x11160`
- `0x11180`
- `0x181d0`
- `0x22a20`

## string_xrefs

- `0x11296`: `CurrentViewNavigationFocusId`
- `0x11423`: `ToolBarUpdate`

## pseudocode

```c

```

## disassembly

```asm
0x11180  ldstr    aMicrosoftRepor_45// "Microsoft.Reporting.WebFormsClient._Rep"...
0x11185  ldarg.0
0x11186  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x1118b  newobj   instance void [System.Web.Extensions]System.Web.UI.ScriptControlDescriptor::.ctor(string, string)
0x11190  stloc.0
0x11191  ldarg.0
0x11192  ldfld    class [mscorlib]System.IO.Stream Microsoft.Reporting.WebForms.ReportControl::m_reportStream
0x11197  brfalse  loc_1142F
0x1119c  ldarg.0
0x1119d  call     instance string Microsoft.Reporting.WebForms.ReportControl::get_UniqueRenderingId()
0x111a2  stloc.1
0x111a3  ldloc.0
0x111a4  ldstr    aSearchhitprefi// "SearchHitPrefix"
0x111a9  ldloc.1
0x111aa  ldsfld   string [Microsoft.ReportingServices.HtmlRendering]Microsoft.ReportingServices.Rendering.HtmlRenderer.HTML4Renderer::m_searchHitIdPrefix
0x111af  call     string [mscorlib]System.String::Concat(string, string)
0x111b4  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0x111b9  ldloc.0
0x111ba  ldstr    aReportcellid// "ReportCellId"
0x111bf  ldloc.1
0x111c0  ldstr    aOreportcell// "oReportCell"
0x111c5  call     string [mscorlib]System.String::Concat(string, string)
0x111ca  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0x111cf  ldloc.0
0x111d0  ldstr    aReportdivid// "ReportDivId"
0x111d5  ldloc.1
0x111d6  ldstr    aOreportdiv// "oReportDiv"
0x111db  call     string [mscorlib]System.String::Concat(string, string)
0x111e0  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0x111e5  ldloc.0
0x111e6  ldstr    aScrollablecont// "ScrollableContainerId"
0x111eb  ldarg.0
0x111ec  call     instance string Microsoft.Reporting.WebForms.ReportControl::get_ScrollContainerId()
0x111f1  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0x111f6  ldarg.0
0x111f7  ldfld    string Microsoft.Reporting.WebForms.ReportControl::m_alertMessage
0x111fc  brfalse.s loc_1120F
0x111fe  ldloc.0
0x111ff  ldstr    aLoadmessage// "LoadMessage"
0x11204  ldarg.0
0x11205  ldfld    string Microsoft.Reporting.WebForms.ReportControl::m_alertMessage
0x1120a  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0x1120f  ldarg.0
0x11210  ldfld    class Microsoft.Reporting.WebForms.ScrollTarget Microsoft.Reporting.WebForms.ReportControl::m_scrollTarget
0x11215  brfalse  loc_11311
0x1121a  ldarg.0
0x1121b  ldfld    class Microsoft.Reporting.WebForms.ScrollTarget Microsoft.Reporting.WebForms.ReportControl::m_scrollTarget
0x11220  callvirt instance string Microsoft.Reporting.WebForms.ScrollTarget::get_NavigationId()
0x11225  stloc.s  5
0x11227  ldloc.s  5
0x11229  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1122e  brtrue.s loc_11243
0x11230  ldloc.0
0x11231  ldstr    aNavigationid// "NavigationId"
0x11236  ldloc.1
0x11237  ldloc.s  5
0x11239  call     string [mscorlib]System.String::Concat(string, string)
0x1123e  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0x11243  ldarg.0
0x11244  ldfld    class Microsoft.Reporting.WebForms.ScrollTarget Microsoft.Reporting.WebForms.ReportControl::m_scrollTarget
0x11249  callvirt instance valuetype Microsoft.Reporting.WebForms.ActionScrollStyle Microsoft.Reporting.WebForms.ScrollTarget::get_ScrollStyle()
0x1124e  ldc.i4.1
0x1124f  bne.un.s loc_1127A
0x11251  ldarg.0
0x11252  ldfld    string Microsoft.Reporting.WebForms.ReportControl::m_viewerInstanceIdentifier
0x11257  ldarg.0
0x11258  call     instance int32 Microsoft.Reporting.WebForms.ReportControl::get_ViewIteration()
0x1125d  ldc.i4.1
0x1125e  sub
0x1125f  call     string Microsoft.Reporting.WebForms.ReportControl::MakeUniqueRenderingId(string instanceId, int32 viewiteration)
0x11264  stloc.s  7
0x11266  ldloc.0
0x11267  ldstr    aPreviousviewna// "PreviousViewNavigationAlignmentId"
0x1126c  ldloc.s  7
0x1126e  ldloc.s  5
0x11270  call     string [mscorlib]System.String::Concat(string, string)
0x11275  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0x1127a  ldarg.0
0x1127b  ldfld    class Microsoft.Reporting.WebForms.ScrollTarget Microsoft.Reporting.WebForms.ReportControl::m_scrollTarget
0x11280  callvirt instance valuetype Microsoft.Reporting.WebForms.ActionScrollStyle Microsoft.Reporting.WebForms.ScrollTarget::get_ScrollStyle()
0x11285  ldc.i4.1
0x11286  beq.s    loc_11295
0x11288  ldarg.0
0x11289  ldfld    class Microsoft.Reporting.WebForms.ScrollTarget Microsoft.Reporting.WebForms.ReportControl::m_scrollTarget
0x1128e  callvirt instance valuetype Microsoft.Reporting.WebForms.ActionScrollStyle Microsoft.Reporting.WebForms.ScrollTarget::get_ScrollStyle()
0x11293  brtrue.s loc_112B2
0x11295  ldloc.0
0x11296  ldstr    aCurrentviewnav// "CurrentViewNavigationFocusId"
0x1129b  ldarg.0
0x1129c  call     instance string Microsoft.Reporting.WebForms.ReportControl::get_UniqueRenderingId()
0x112a1  ldloc.s  5
0x112a3  ldstr    aNa// "_na"
0x112a8  call     string [mscorlib]System.String::Concat(string, string, string)
0x112ad  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0x112b2  ldloc.0
0x112b3  ldstr    aAvoidscrollcha// "AvoidScrollChange"
0x112b8  ldarg.0
0x112b9  ldfld    class Microsoft.Reporting.WebForms.ScrollTarget Microsoft.Reporting.WebForms.ReportControl::m_scrollTarget
0x112be  callvirt instance valuetype Microsoft.Reporting.WebForms.ActionScrollStyle Microsoft.Reporting.WebForms.ScrollTarget::get_ScrollStyle()
0x112c3  ldc.i4.3
0x112c4  ceq
0x112c6  box      [mscorlib]System.Boolean
0x112cb  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0x112d0  ldloc.0
0x112d1  ldstr    aAvoidscrollfro// "AvoidScrollFromOrigin"
0x112d6  ldarg.0
0x112d7  ldfld    class Microsoft.Reporting.WebForms.ScrollTarget Microsoft.Reporting.WebForms.ReportControl::m_scrollTarget
0x112dc  callvirt instance valuetype Microsoft.Reporting.WebForms.ActionScrollStyle Microsoft.Reporting.WebForms.ScrollTarget::get_ScrollStyle()
0x112e1  ldc.i4.4
0x112e2  ceq
0x112e4  box      [mscorlib]System.Boolean
0x112e9  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0x112ee  ldarg.0
0x112ef  ldfld    class Microsoft.Reporting.WebForms.ScrollTarget Microsoft.Reporting.WebForms.ReportControl::m_scrollTarget
0x112f4  callvirt instance string Microsoft.Reporting.WebForms.ScrollTarget::get_PixelPosition()
0x112f9  stloc.s  6
0x112fb  ldloc.s  6
0x112fd  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x11302  brtrue.s loc_11311
0x11304  ldloc.0
0x11305  ldstr    aSpecificscroll// "SpecificScrollPosition"
0x1130a  ldloc.s  6
0x1130c  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0x11311  ldloc.0
0x11312  ldstr    aReportstyles// "ReportStyles"
0x11317  ldarg.0
0x11318  ldfld    string Microsoft.Reporting.WebForms.ReportControl::m_styleBytesString
0x1131d  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0x11322  ldloc.0
0x11323  ldstr    aPrefixid// "PrefixId"
0x11328  ldloc.1
0x11329  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0x1132e  ldarg.0
0x1132f  ldfld    string Microsoft.Reporting.WebForms.ReportControl::m_scrollScript
0x11334  brfalse.s loc_11347
0x11336  ldloc.0
0x11337  ldstr    aScrollscript// "ScrollScript"
0x1133c  ldarg.0
0x1133d  ldfld    string Microsoft.Reporting.WebForms.ReportControl::m_scrollScript
0x11342  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddScriptProperty(string, string)
0x11347  ldarg.0
0x11348  ldfld    string Microsoft.Reporting.WebForms.ReportControl::m_pageStyles
0x1134d  brfalse.s loc_11360
0x1134f  ldloc.0
0x11350  ldstr    aReportpagestyl// "ReportPageStyles"
0x11355  ldarg.0
0x11356  ldfld    string Microsoft.Reporting.WebForms.ReportControl::m_pageStyles
0x1135b  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0x11360  ldloc.0
0x11361  ldstr    aInteractivitym// "InteractivityMode"
0x11366  ldarg.0
0x11367  ldflda   valuetype Microsoft.Reporting.WebForms.InteractivityPostBackMode Microsoft.Reporting.WebForms.ReportControl::m_interactivityMode
0x1136c  constrained. Microsoft.Reporting.WebForms.InteractivityPostBackMode
0x11372  callvirt instance string [mscorlib]System.Object::ToString()
0x11377  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0x1137c  ldloc.0
0x1137d  ldstr    aActiontypeid// "ActionTypeId"
0x11382  ldarg.0
0x11383  ldfld    class [System.Web]System.Web.UI.WebControls.HiddenField Microsoft.Reporting.WebForms.ReportControl::m_hiddenActionType
0x11388  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x1138d  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0x11392  ldloc.0
0x11393  ldstr    aActionparamid// "ActionParamId"
0x11398  ldarg.0
0x11399  ldfld    class [System.Web]System.Web.UI.WebControls.HiddenField Microsoft.Reporting.WebForms.ReportControl::m_hiddenActionParam
0x1139e  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x113a3  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0x113a8  ldarg.0
0x113a9  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x113ae  callvirt instance class [System.Web]System.Web.UI.ClientScriptManager [System.Web]System.Web.UI.Page::get_ClientScript()
0x113b3  ldarg.0
0x113b4  ldfld    class Microsoft.Reporting.WebForms.PostBackTarget Microsoft.Reporting.WebForms.ReportControl::m_syncPostBackTarget
0x113b9  ldnull
0x113ba  callvirt instance string [System.Web]System.Web.UI.ClientScriptManager::GetPostBackEventReference(class [System.Web]System.Web.UI.Control, string)
0x113bf  stloc.2
0x113c0  ldloc.0
0x113c1  ldstr    aTriggersyncint// "TriggerSyncInteractivity"
0x113c6  ldloc.2
0x113c7  ldstr    asc_40D1E// ";"
0x113cc  call     string [mscorlib]System.String::Concat(string, string)
0x113d1  call     string Microsoft.Reporting.WebForms.JavaScriptHelper::FormatAsFunction(string functionBody)
0x113d6  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddScriptProperty(string, string)
0x113db  ldarg.0
0x113dc  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x113e1  callvirt instance class [System.Web]System.Web.UI.ClientScriptManager [System.Web]System.Web.UI.Page::get_ClientScript()
0x113e6  ldarg.0
0x113e7  ldnull
0x113e8  callvirt instance string [System.Web]System.Web.UI.ClientScriptManager::GetPostBackEventReference(class [System.Web]System.Web.UI.Control, string)
0x113ed  stloc.3
0x113ee  ldloc.0
0x113ef  ldstr    aTriggerasyncin// "TriggerAsyncInteractivity"
0x113f4  ldloc.3
0x113f5  ldstr    asc_40D1E// ";"
0x113fa  call     string [mscorlib]System.String::Concat(string, string)
0x113ff  call     string Microsoft.Reporting.WebForms.JavaScriptHelper::FormatAsFunction(string functionBody)
0x11404  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddScriptProperty(string, string)
0x11409  ldarg.0
0x1140a  ldfld    class Microsoft.Reporting.WebForms.ReportControlSession Microsoft.Reporting.WebForms.ReportControl::m_session
0x1140f  ldarg.0
0x11410  ldfld    int32 Microsoft.Reporting.WebForms.ReportControl::m_pageNumber
0x11415  ldarg.0
0x11416  ldfld    class Microsoft.Reporting.WebForms.SearchState Microsoft.Reporting.WebForms.ReportControl::m_searchState
0x1141b  call     string Microsoft.Reporting.WebForms.ToolbarControl::GenerateUpdateProperties(class Microsoft.Reporting.WebForms.ReportControlSession session, int32 pageNumber, class Microsoft.Reporting.WebForms.SearchState searchState)
0x11420  stloc.s  4
0x11422  ldloc.0
0x11423  ldstr    aToolbarupdate// "ToolBarUpdate"
0x11428  ldloc.s  4
0x1142a  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddScriptProperty(string, string)
0x1142f  ldloc.0
0x11430  ldstr    aHiddenzoomleve// "HiddenZoomLevelId"
0x11435  ldarg.0
0x11436  ldfld    class [System.Web]System.Web.UI.WebControls.HiddenField Microsoft.Reporting.WebForms.ReportControl::m_hiddenZoomLevel
0x1143b  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x11440  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0x11445  ldloc.0
0x11446  ldstr    aStyleelementid// "StyleElementId"
0x1144b  ldarg.0
0x1144c  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x11451  ldstr    aStyles// "_styles"
0x11456  call     string [mscorlib]System.String::Concat(string, string)
0x1145b  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0x11460  ldc.i4.1
0x11461  newarr   [System.Web.Extensions]System.Web.UI.ScriptDescriptor
0x11466  dup
0x11467  ldc.i4.0
0x11468  ldloc.0
0x11469  stelem.ref
0x1146a  ret
```
