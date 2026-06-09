# Microsoft.ReportingServices.WebServer.ReportViewerHost::OnLoad

- ea: `0x34050`
- end: `0x3439e`
- name: `Microsoft.ReportingServices.WebServer.ReportViewerHost::OnLoad`
- size: `846`
- prototype: ``
- caller_count: `0`
- callee_count: `31`
- tags: `service_task, broker_com_uri`

## callees

- `0x120b0`
- `0x12100`
- `0x12190`
- `0x122a0`
- `0x12300`
- `0x128c0`
- `0x12920`
- `0x12940`
- `0x12970`
- `0x129a0`
- `0x129e0`
- `0x12ad0`
- `0x12b10`
- `0x23820`
- `0x23860`
- `0x23be0`
- `0x23cf0`
- `0x23f90`
- `0x2da10`
- `0x2db10`
- `0x2dc30`
- `0x32b00`
- `0x33620`
- `0x34050`
- `0x343a0`
- `0x343d0`
- `0x344b0`
- `0x344e0`
- `0x34540`
- `0x345d0`
- `0x345e0`

## string_xrefs

- `0x3420f`: `ReplacementRoot`
- `0x34232`: `ReplacementRoot`
- `0x341e2`: `LinkTarget`
- `0x34262`: `AccessibleTablix`

## pseudocode

```c

```

## disassembly

```asm
0x34050  ldarg.0
0x34051  ldarg.1
0x34052  call     instance void [System.Web]System.Web.UI.Control::OnLoad(class [mscorlib]System.EventArgs)
0x34057  ldarg.0
0x34058  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x3405d  callvirt instance class [System.Web]System.Web.UI.HtmlControls.HtmlHead [System.Web]System.Web.UI.Page::get_Header()
0x34062  brfalse.s loc_34088
0x34064  ldarg.0
0x34065  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x3406a  callvirt instance class [System.Web]System.Web.UI.HtmlControls.HtmlHead [System.Web]System.Web.UI.Page::get_Header()
0x3406f  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x34074  ldstr    aLang// "lang"
0x34079  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x3407e  callvirt instance string [mscorlib]System.Globalization.CultureInfo::get_Name()
0x34083  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x34088  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.WebServer.Global::get_Service()
0x3408d  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPathTranslator)
0x34092  stloc.0
0x34093  call     string Microsoft.ReportingServices.WebServer.ReportViewerHost::GetReportPath()
0x34098  stloc.1
0x34099  ldloc.0
0x3409a  ldloc.1
0x3409b  ldc.i4.s 0xF
0x3409d  callvirt instance bool class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::SetPath(string, valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathOptions)
0x340a2  brtrue.s loc_340AB
0x340a4  ldloc.1
0x340a5  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidItemPathException::.ctor(string)
0x340aa  throw
0x340ab  ldloc.0
0x340ac  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_RSRequestParameters()
0x340b1  call     class [System]System.Collections.Specialized.NameValueCollection Microsoft.ReportingServices.WebServer.Global::get_RequestParameters()
0x340b6  newobj   instance void [System]System.Collections.Specialized.NameValueCollection::.ctor(class [System]System.Collections.Specialized.NameValueCollection)
0x340bb  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSParameterTranslator::.ctor()
0x340c0  ldloc.0
0x340c1  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_ItemPath()
0x340c6  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters::ParseQueryString(class [System]System.Collections.Specialized.NameValueCollection, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IParametersTranslator, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath)
0x340cb  ldarg.0
0x340cc  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x340d1  callvirt instance bool [System.Web]System.Web.UI.Page::get_IsPostBack()
0x340d6  brtrue   loc_34385
0x340db  ldarg.0
0x340dc  ldloc.0
0x340dd  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_RSRequestParameters()
0x340e2  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters::get_RenderingParameters()
0x340e7  ldstr    aStylesheet// "StyleSheet"
0x340ec  callvirt instance string [mscorlib]System.Object::ToString()
0x340f1  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x340f6  call     instance void Microsoft.ReportingServices.WebServer.ReportViewerWithV1Styles::set_V1StyleSheetName(string value)
0x340fb  ldloc.0
0x340fc  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_RSRequestParameters()
0x34101  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters::get_RenderingParameters()
0x34106  ldstr    aToolbar// "Toolbar"
0x3410b  callvirt instance string [mscorlib]System.Object::ToString()
0x34110  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x34115  ldc.i4.1
0x34116  call     bool Microsoft.ReportingServices.WebServer.ParamsParsing::ParseBool(string boolValue, bool defaultValue)
0x3411b  stloc.2
0x3411c  ldloc.0
0x3411d  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_RSRequestParameters()
0x34122  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters::get_CatalogParameters()
0x34127  ldstr    aParameterlangu// "ParameterLanguage"
0x3412c  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x34131  stloc.3
0x34132  ldloc.3
0x34133  brfalse.s loc_3413B
0x34135  ldloc.3
0x34136  call     void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Localization::SetReportParameterCulture(string)
0x3413b  ldloc.0
0x3413c  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_RSRequestParameters()
0x34141  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters::get_CatalogParameters()
0x34146  ldstr    aPagecountmode// "PageCountMode"
0x3414b  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x34150  ldstr    aActual// "Actual"
0x34155  ldc.i4.5
0x34156  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x3415b  brtrue.s loc_34164
0x3415d  ldarg.0
0x3415e  ldc.i4.0
0x3415f  call     instance void Microsoft.Reporting.WebForms.ReportViewer::set_PageCountMode(valuetype Microsoft.Reporting.WebForms.PageCountMode value)
0x34164  ldloc.0
0x34165  ldloca.s 4
0x34167  ldloca.s 5
0x34169  call     void Microsoft.ReportingServices.WebServer.ReportViewerHost::GetPromptAreaState(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext itemContext, [out] bool& promptAreaCollapsed, [out] bool& showPromptAreaButton)
0x3416e  ldloc.0
0x3416f  ldloca.s 6
0x34171  ldloca.s 7
0x34173  call     void Microsoft.ReportingServices.WebServer.ReportViewerHost::GetZoomState(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext itemContext, [out] valuetype Microsoft.Reporting.WebForms.ZoomMode& zoomMode, [out] int32& zoomPercent)
0x34178  ldarg.0
0x34179  ldloc.s  4
0x3417b  brtrue.s loc_34183
0x3417d  ldloc.2
0x3417e  ldc.i4.0
0x3417f  ceq
0x34181  br.s     loc_34184
0x34183  ldc.i4.1
0x34184  call     instance void Microsoft.Reporting.WebForms.ReportViewer::set_PromptAreaCollapsed(bool value)
0x34189  ldarg.0
0x3418a  ldloc.0
0x3418b  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_RSRequestParameters()
0x34190  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters::get_RenderingParameters()
0x34195  ldstr    aDocmap// "DocMap"
0x3419a  callvirt instance string [mscorlib]System.Object::ToString()
0x3419f  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x341a4  ldc.i4.1
0x341a5  call     bool Microsoft.ReportingServices.WebServer.ParamsParsing::ParseBool(string boolValue, bool defaultValue)
0x341aa  brfalse.s loc_341B2
0x341ac  ldloc.2
0x341ad  ldc.i4.0
0x341ae  ceq
0x341b0  br.s     loc_341B3
0x341b2  ldc.i4.1
0x341b3  call     instance void Microsoft.Reporting.WebForms.ReportViewer::set_DocumentMapCollapsed(bool value)
0x341b8  ldarg.0
0x341b9  ldloc.s  5
0x341bb  call     instance void Microsoft.Reporting.WebForms.ReportViewer::set_ShowPromptAreaButton(bool value)
0x341c0  ldarg.0
0x341c1  ldloc.2
0x341c2  call     instance void Microsoft.Reporting.WebForms.ReportViewer::set_ShowToolBar(bool value)
0x341c7  ldarg.0
0x341c8  ldloc.s  6
0x341ca  call     instance void Microsoft.Reporting.WebForms.ReportViewer::set_ZoomMode(valuetype Microsoft.Reporting.WebForms.ZoomMode value)
0x341cf  ldarg.0
0x341d0  ldloc.s  7
0x341d2  call     instance void Microsoft.Reporting.WebForms.ReportViewer::set_ZoomPercent(int32 value)
0x341d7  ldloc.0
0x341d8  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_RSRequestParameters()
0x341dd  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters::get_RenderingParameters()
0x341e2  ldstr    aLinktarget// "LinkTarget"
0x341e7  callvirt instance string [mscorlib]System.Object::ToString()
0x341ec  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x341f1  stloc.s  8
0x341f3  ldloc.s  8
0x341f5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x341fa  brtrue.s loc_34204
0x341fc  ldarg.0
0x341fd  ldloc.s  8
0x341ff  call     instance void Microsoft.Reporting.WebForms.ReportViewer::set_HyperlinkTarget(string value)
0x34204  ldloc.0
0x34205  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_RSRequestParameters()
0x3420a  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters::get_RenderingParameters()
0x3420f  ldstr    aReplacementroo// "ReplacementRoot"
0x34214  callvirt instance string [mscorlib]System.Object::ToString()
0x34219  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x3421e  stloc.s  9
0x34220  ldloc.s  9
0x34222  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x34227  brtrue.s loc_3424A
0x34229  ldloc.s  9
0x3422b  call     bool Microsoft.ReportingServices.WebServer.ReportViewerHost::VerifySafeForRoots(string value)
0x34230  brtrue.s loc_34242
0x34232  ldstr    aReplacementroo// "ReplacementRoot"
0x34237  callvirt instance string [mscorlib]System.Object::ToString()
0x3423c  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidParameterException::.ctor(string)
0x34241  throw
0x34242  ldarg.0
0x34243  ldloc.s  9
0x34245  call     instance void Microsoft.Reporting.WebForms.ReportViewer::set_ReplacementRoot(string value)
0x3424a  ldarg.0
0x3424b  ldstr    aImageconsolida_0// "ImageConsolidation"
0x34250  ldloc.0
0x34251  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_RSRequestParameters()
0x34256  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters::get_RenderingParameters()
0x3425b  ldc.i4.0
0x3425c  call     instance void Microsoft.ReportingServices.WebServer.ReportViewerHost::SetDeviceInfo(string deviceInfo, class [System]System.Collections.Specialized.NameValueCollection requestParameters, bool checkConfig)
0x34261  ldarg.0
0x34262  ldstr    aAccessibletabl// "AccessibleTablix"
0x34267  ldloc.0
0x34268  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_RSRequestParameters()
0x3426d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters::get_RenderingParameters()
0x34272  ldc.i4.1
0x34273  call     instance void Microsoft.ReportingServices.WebServer.ReportViewerHost::SetDeviceInfo(string deviceInfo, class [System]System.Collections.Specialized.NameValueCollection requestParameters, bool checkConfig)
0x34278  ldarg.0
0x34279  ldstr    aDatavisualizat// "DataVisualizationFitSizing"
0x3427e  ldloc.0
0x3427f  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_RSRequestParameters()
0x34284  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters::get_RenderingParameters()
0x34289  ldc.i4.1
0x3428a  call     instance void Microsoft.ReportingServices.WebServer.ReportViewerHost::SetDeviceInfo(string deviceInfo, class [System]System.Collections.Specialized.NameValueCollection requestParameters, bool checkConfig)
0x3428f  ldarg.0
0x34290  ldloc.2
0x34291  call     instance void Microsoft.Reporting.WebForms.ReportViewer::set_AsyncRendering(bool value)
0x34296  ldloc.0
0x34297  call     string Microsoft.ReportingServices.WebServer.HttpClientRequest::ExtractSessionFromRequest(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext itemContext)
0x3429c  stloc.s  0xA
0x3429e  ldloc.s  0xA
0x342a0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x342a5  brtrue.s loc_342B6
0x342a7  ldarg.0
0x342a8  call     instance class Microsoft.Reporting.WebForms.ServerReport Microsoft.Reporting.WebForms.ReportViewer::get_ServerReport()
0x342ad  ldloc.s  0xA
0x342af  callvirt instance void Microsoft.Reporting.WebForms.ServerReport::SetExecutionId(string executionId)
0x342b4  br.s     loc_342D8
0x342b6  ldarg.0
0x342b7  call     instance class Microsoft.Reporting.WebForms.ServerReport Microsoft.Reporting.WebForms.ReportViewer::get_ServerReport()
0x342bc  ldloc.1
0x342bd  callvirt instance void Microsoft.Reporting.WebForms.ServerReport::set_ReportPath(string value)
0x342c2  ldarg.0
0x342c3  call     instance class Microsoft.Reporting.WebForms.ServerReport Microsoft.Reporting.WebForms.ReportViewer::get_ServerReport()
0x342c8  ldloc.0
0x342c9  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_RSRequestParameters()
0x342ce  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters::get_SnapshotParamValue()
0x342d3  callvirt instance void Microsoft.Reporting.WebForms.ServerReport::set_HistoryId(string value)
0x342d8  ldarg.0
0x342d9  call     instance class Microsoft.Reporting.WebForms.ServerReport Microsoft.Reporting.WebForms.ReportViewer::get_ServerReport()
0x342de  ldloc.0
0x342df  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_RSRequestParameters()
0x342e4  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters::get_ReportParameters()
0x342e9  callvirt instance void Microsoft.Reporting.WebForms.ServerReport::SetParameters(class [System]System.Collections.Specialized.NameValueCollection parameters)
0x342ee  ldarg.0
0x342ef  call     instance class Microsoft.Reporting.WebForms.ServerReport Microsoft.Reporting.WebForms.ReportViewer::get_ServerReport()
0x342f4  ldloc.0
0x342f5  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_RSRequestParameters()
0x342fa  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.DatasourceCredentialsCollection [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters::get_DatasourcesCred()
0x342ff  callvirt instance void Microsoft.Reporting.WebForms.ServerReport::SetCredentials(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.DatasourceCredentialsCollection credentials)
0x34304  ldarg.0
0x34305  ldloc.0
0x34306  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_RSRequestParameters()
0x3430b  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters::get_RenderingParameters()
0x34310  ldstr    aShowbackbutton_0// "ShowBackButton"
0x34315  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x3431a  ldc.i4.0
0x3431b  call     bool Microsoft.ReportingServices.WebServer.ParamsParsing::ParseBool(string boolValue, bool defaultValue)
0x34320  call     instance void Microsoft.Reporting.WebForms.ReportViewer::set_ShowBackButton(bool value)
0x34325  ldloc.0
0x34326  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_RSRequestParameters()
0x3432b  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters::get_FormatParamValue()
0x34330  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x34335  brtrue.s loc_3434F
0x34337  ldloc.0
0x34338  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_RSRequestParameters()
0x3433d  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters::get_FormatParamValue()
0x34342  ldstr    aHtml40// "HTML4.0"
0x34347  ldc.i4.5
0x34348  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x3434d  br.s     loc_34350
0x3434f  ldc.i4.0
0x34350  pop
0x34351  ldloc.0
0x34352  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_RSRequestParameters()
0x34357  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters::get_RenderingParameters()
0x3435c  ldstr    aSection// "Section"
0x34361  callvirt instance string [mscorlib]System.Object::ToString()
0x34366  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x3436b  ldc.i4.1
0x3436c  call     int32 Microsoft.ReportingServices.WebServer.ParamsParsing::ParseInt(string intValue, int32 defaultValue)
0x34371  stloc.s  0xB
0x34373  ldc.i4.1
0x34374  ldloc.s  0xB
0x34376  call     int32 [mscorlib]System.Math::Max(int32, int32)
0x3437b  stloc.s  0xB
0x3437d  ldarg.0
0x3437e  ldloc.s  0xB
0x34380  call     instance void Microsoft.Reporting.WebForms.ReportViewer::set_CurrentPage(int32 value)
0x34385  leave.s  loc_3439D
0x34387  call     void Microsoft.ReportingServices.WebServer.Global::WriteServerError(class [mscorlib]System.Exception e)
0x3438c  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x34391  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x34396  callvirt instance void [System.Web]System.Web.HttpResponse::End()
0x3439b  leave.s  loc_3439D
0x3439d  ret
```
