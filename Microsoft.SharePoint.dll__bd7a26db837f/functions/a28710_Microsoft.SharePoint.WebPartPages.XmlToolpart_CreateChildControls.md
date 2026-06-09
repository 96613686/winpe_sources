# Microsoft.SharePoint.WebPartPages.XmlToolpart::CreateChildControls

- ea: `0xa28710`
- end: `0xa28b44`
- name: `Microsoft.SharePoint.WebPartPages.XmlToolpart::CreateChildControls`
- size: `1076`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1a1ea0`
- `0x87dee0`
- `0x994780`
- `0x994ab0`
- `0x9dc040`
- `0x9dc070`
- `0xa0c260`
- `0xa147f0`
- `0xa14820`
- `0xa14870`
- `0xa14880`
- `0xa286a0`
- `0xa28710`
- `0xa29230`
- `0xa292b0`
- `0xa29360`
- `0xa293c0`

## string_xrefs

- `0xa28926`: `TestLink`
- `0xa2897a`: `TestLink`
- `0xa287db`: `xmllink`
- `0xa287f0`: `XmlLinkLiteral`
- `0xa28949`: `XmlLinkLiteral`
- `0xa28a43`: `XmlLinkLiteral`
- `0xa288c5`: `xsllink`
- `0xa288da`: `XslLinkLiteral`
- `0xa2899d`: `XslLinkLiteral`
- `0xa28acf`: `XslLinkLiteral`
- `0xa28964`: `TestLink_xml`
- `0xa289b8`: `TestLink_xsl`
- `0xa28a2e`: `_downLevelXmlField`
- `0xa28af3`: `AddXml`
- `0xa28b08`: `AddXml`

## pseudocode

```c

```

## disassembly

```asm
0xa28710  ldarg.0
0xa28711  ldarg.0
0xa28712  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0xa28717  ldstr    aXtpJs// "xtp.js"
0xa2871c  call     int32 Microsoft.SharePoint.Utilities.SPUtility::get_ContextCompatibilityLevel()
0xa28721  ldc.i4.s 0xF
0xa28723  clt
0xa28725  call     void Microsoft.SharePoint.WebControls.ScriptLink::Register(class [System.Web]System.Web.UI.Control ctrl, class [System.Web]System.Web.UI.Page page, string name, bool localizable)
0xa2872a  ldarg.0
0xa2872b  ldarg.0
0xa2872c  call     instance class Microsoft.SharePoint.WebPartPages.ToolPane Microsoft.SharePoint.WebPartPages.ToolPart::get_ParentToolPane()
0xa28731  callvirt instance class [System.Web]System.Web.UI.WebControls.WebParts.WebPart Microsoft.SharePoint.WebPartPages.ToolPane::get_SelectedAspWebPart()
0xa28736  castclass Microsoft.SharePoint.WebPartPages.XmlWebPart
0xa2873b  stfld    class Microsoft.SharePoint.WebPartPages.XmlWebPart Microsoft.SharePoint.WebPartPages.XmlToolpart::_xmlPart
0xa28740  ldarg.0
0xa28741  newobj   instance void [System.Web]System.Web.UI.WebControls.TextBox::.ctor()
0xa28746  stfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.WebPartPages.XmlToolpart::_xmlLink
0xa2874b  ldarg.0
0xa2874c  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.WebPartPages.XmlToolpart::_xmlLink
0xa28751  ldarg.0
0xa28752  ldfld    class Microsoft.SharePoint.WebPartPages.XmlWebPart Microsoft.SharePoint.WebPartPages.XmlToolpart::_xmlPart
0xa28757  callvirt instance string Microsoft.SharePoint.WebPartPages.XmlWebPart::get_XmlLink()
0xa2875c  callvirt instance void [System.Web]System.Web.UI.WebControls.TextBox::set_Text(string)
0xa28761  ldarg.0
0xa28762  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0xa28767  call     bool Microsoft.SharePoint.WebPartPages.Utility::IsToolPaneMaximized(class [System.Web]System.Web.UI.Page page)
0xa2876c  brtrue.s loc_A28775
0xa2876e  ldc.i4   0xAF
0xa28773  br.s     loc_A28780
0xa28775  ldc.i4   0xAF
0xa2877a  call     int32 Microsoft.SharePoint.WebPartPages.Utility::get_ChangeInToolPaneWidthWhenMaximized()
0xa2877f  add
0xa28780  stloc.0
0xa28781  ldarg.0
0xa28782  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.WebPartPages.XmlToolpart::_xmlLink
0xa28787  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.WebControls.WebControl::get_Style()
0xa2878c  ldstr    aWidth_0// "width"
0xa28791  ldloc.0
0xa28792  box      [mscorlib]System.Int32
0xa28797  ldstr    aPx_1// "px"
0xa2879c  call     string [mscorlib]System.String::Concat(object, object)
0xa287a1  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::set_Item(string, string)
0xa287a6  ldarg.0
0xa287a7  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.WebPartPages.XmlToolpart::_xmlLink
0xa287ac  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.WebControls.WebControl::get_Style()
0xa287b1  ldstr    aDirection_1// "direction"
0xa287b6  ldstr    aLtr// "ltr"
0xa287bb  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::set_Item(string, string)
0xa287c0  ldarg.0
0xa287c1  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.WebPartPages.XmlToolpart::_xmlLink
0xa287c6  ldstr    aUserinput// "UserInput"
0xa287cb  callvirt instance void [System.Web]System.Web.UI.WebControls.WebControl::set_CssClass(string)
0xa287d0  ldarg.0
0xa287d1  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.WebPartPages.XmlToolpart::_xmlLink
0xa287d6  ldsfld   string Microsoft.SharePoint.WebPartPages.XmlToolpart::ToolpartQualifier
0xa287db  ldstr    aXmllink// "xmllink"
0xa287e0  call     string [mscorlib]System.String::Concat(string, string)
0xa287e5  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0xa287ea  ldarg.0
0xa287eb  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.WebPartPages.XmlToolpart::_xmlLink
0xa287f0  ldstr    aXmllinkliteral// "XmlLinkLiteral"
0xa287f5  call     string Microsoft.SharePoint.WebPartPages.WebPartPageResource::GetString(string name)
0xa287fa  callvirt instance void [System.Web]System.Web.UI.WebControls.WebControl::set_ToolTip(string)
0xa287ff  ldarg.0
0xa28800  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.WebPartPages.XmlToolpart::_xmlLink
0xa28805  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.WebControls.WebControl::get_Attributes()
0xa2880a  call     string Microsoft.SharePoint.WebPartPages.Utility::get_ToolpaneWidenAttribute()
0xa2880f  ldstr    aTrue// "true"
0xa28814  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xa28819  ldarg.0
0xa2881a  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xa2881f  ldarg.0
0xa28820  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.WebPartPages.XmlToolpart::_xmlLink
0xa28825  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xa2882a  ldarg.0
0xa2882b  newobj   instance void [System.Web]System.Web.UI.WebControls.TextBox::.ctor()
0xa28830  stfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.WebPartPages.XmlToolpart::_xslLink
0xa28835  ldarg.0
0xa28836  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.WebPartPages.XmlToolpart::_xslLink
0xa2883b  ldarg.0
0xa2883c  ldfld    class Microsoft.SharePoint.WebPartPages.XmlWebPart Microsoft.SharePoint.WebPartPages.XmlToolpart::_xmlPart
0xa28841  callvirt instance string Microsoft.SharePoint.WebPartPages.XmlWebPart::get_XslLink()
0xa28846  callvirt instance void [System.Web]System.Web.UI.WebControls.TextBox::set_Text(string)
0xa2884b  ldarg.0
0xa2884c  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0xa28851  call     bool Microsoft.SharePoint.WebPartPages.Utility::IsToolPaneMaximized(class [System.Web]System.Web.UI.Page page)
0xa28856  brtrue.s loc_A2885F
0xa28858  ldc.i4   0xAF
0xa2885d  br.s     loc_A2886A
0xa2885f  ldc.i4   0xAF
0xa28864  call     int32 Microsoft.SharePoint.WebPartPages.Utility::get_ChangeInToolPaneWidthWhenMaximized()
0xa28869  add
0xa2886a  stloc.1
0xa2886b  ldarg.0
0xa2886c  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.WebPartPages.XmlToolpart::_xslLink
0xa28871  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.WebControls.WebControl::get_Style()
0xa28876  ldstr    aWidth_0// "width"
0xa2887b  ldloc.1
0xa2887c  box      [mscorlib]System.Int32
0xa28881  ldstr    aPx_1// "px"
0xa28886  call     string [mscorlib]System.String::Concat(object, object)
0xa2888b  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::set_Item(string, string)
0xa28890  ldarg.0
0xa28891  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.WebPartPages.XmlToolpart::_xslLink
0xa28896  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.WebControls.WebControl::get_Style()
0xa2889b  ldstr    aDirection_1// "direction"
0xa288a0  ldstr    aLtr// "ltr"
0xa288a5  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::set_Item(string, string)
0xa288aa  ldarg.0
0xa288ab  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.WebPartPages.XmlToolpart::_xslLink
0xa288b0  ldstr    aUserinput// "UserInput"
0xa288b5  callvirt instance void [System.Web]System.Web.UI.WebControls.WebControl::set_CssClass(string)
0xa288ba  ldarg.0
0xa288bb  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.WebPartPages.XmlToolpart::_xslLink
0xa288c0  ldsfld   string Microsoft.SharePoint.WebPartPages.XmlToolpart::ToolpartQualifier
0xa288c5  ldstr    aXsllink_0// "xsllink"
0xa288ca  call     string [mscorlib]System.String::Concat(string, string)
0xa288cf  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0xa288d4  ldarg.0
0xa288d5  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.WebPartPages.XmlToolpart::_xslLink
0xa288da  ldstr    aXsllinkliteral// "XslLinkLiteral"
0xa288df  call     string Microsoft.SharePoint.WebPartPages.WebPartPageResource::GetString(string name)
0xa288e4  callvirt instance void [System.Web]System.Web.UI.WebControls.WebControl::set_ToolTip(string)
0xa288e9  ldarg.0
0xa288ea  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.WebPartPages.XmlToolpart::_xslLink
0xa288ef  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.WebControls.WebControl::get_Attributes()
0xa288f4  call     string Microsoft.SharePoint.WebPartPages.Utility::get_ToolpaneWidenAttribute()
0xa288f9  ldstr    aTrue// "true"
0xa288fe  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xa28903  ldarg.0
0xa28904  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xa28909  ldarg.0
0xa2890a  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.WebPartPages.XmlToolpart::_xslLink
0xa2890f  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xa28914  ldarg.0
0xa28915  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0xa2891a  call     bool Microsoft.SharePoint.WebPartPages.Utility::CheckForCustomToolpane(class [System.Web]System.Web.UI.Page page)
0xa2891f  brtrue   loc_A289CC
0xa28924  ldarg.0
0xa28925  ldarg.0
0xa28926  ldstr    aTestlink// "TestLink"
0xa2892b  call     string Microsoft.SharePoint.WebPartPages.WebPartPageResource::GetString(string name)
0xa28930  ldarg.0
0xa28931  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.WebPartPages.XmlToolpart::_xmlLink
0xa28936  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0xa2893b  ldstr    aInvalidurlgene// "InvalidURLGeneral"
0xa28940  ldc.i4.1
0xa28941  newarr   [mscorlib]System.Object
0xa28946  stloc.2
0xa28947  ldloc.2
0xa28948  ldc.i4.0
0xa28949  ldstr    aXmllinkliteral// "XmlLinkLiteral"
0xa2894e  call     string Microsoft.SharePoint.WebPartPages.WebPartPageResource::GetString(string name)
0xa28953  stelem.ref
0xa28954  ldloc.2
0xa28955  call     string Microsoft.SharePoint.WebPartPages.WebPartPageResource::GetString(string name, object[] values)
0xa2895a  ldstr    a12// "12"
0xa2895f  ldsfld   string Microsoft.SharePoint.WebPartPages.XmlToolpart::ToolpartQualifier
0xa28964  ldstr    aTestlinkXml// "TestLink_xml"
0xa28969  call     string [mscorlib]System.String::Concat(string, string)
0xa2896e  call     instance string Microsoft.SharePoint.WebPartPages.FrameworkClassesToolPart::CreatePreviewButton(string buttonText, string clientID, string errorMessage, string validPatterns, string buttonID)
0xa28973  stfld    string Microsoft.SharePoint.WebPartPages.XmlToolpart::_testXmlLinkButton
0xa28978  ldarg.0
0xa28979  ldarg.0
0xa2897a  ldstr    aTestlink// "TestLink"
0xa2897f  call     string Microsoft.SharePoint.WebPartPages.WebPartPageResource::GetString(string name)
0xa28984  ldarg.0
0xa28985  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.WebPartPages.XmlToolpart::_xslLink
0xa2898a  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0xa2898f  ldstr    aInvalidurlgene// "InvalidURLGeneral"
0xa28994  ldc.i4.1
0xa28995  newarr   [mscorlib]System.Object
0xa2899a  stloc.3
0xa2899b  ldloc.3
0xa2899c  ldc.i4.0
0xa2899d  ldstr    aXsllinkliteral// "XslLinkLiteral"
0xa289a2  call     string Microsoft.SharePoint.WebPartPages.WebPartPageResource::GetString(string name)
0xa289a7  stelem.ref
0xa289a8  ldloc.3
0xa289a9  call     string Microsoft.SharePoint.WebPartPages.WebPartPageResource::GetString(string name, object[] values)
0xa289ae  ldstr    a12// "12"
0xa289b3  ldsfld   string Microsoft.SharePoint.WebPartPages.XmlToolpart::ToolpartQualifier
0xa289b8  ldstr    aTestlinkXsl// "TestLink_xsl"
0xa289bd  call     string [mscorlib]System.String::Concat(string, string)
0xa289c2  call     instance string Microsoft.SharePoint.WebPartPages.FrameworkClassesToolPart::CreatePreviewButton(string buttonText, string clientID, string errorMessage, string validPatterns, string buttonID)
0xa289c7  stfld    string Microsoft.SharePoint.WebPartPages.XmlToolpart::_testXslLinkButton
0xa289cc  ldarg.0
0xa289cd  ldfld    bool Microsoft.SharePoint.WebPartPages.FrameworkClassesToolPart::_downLevel
0xa289d2  brfalse  loc_A28AF1
0xa289d7  ldarg.0
0xa289d8  newobj   instance void [System.Web]System.Web.UI.WebControls.TextBox::.ctor()
0xa289dd  stfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.WebPartPages.XmlToolpart::_downLevelXmlField
0xa289e2  ldarg.0
0xa289e3  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.WebPartPages.XmlToolpart::_downLevelXmlField
0xa289e8  ldc.i4.1
0xa289e9  callvirt instance void [System.Web]System.Web.UI.WebControls.TextBox::set_TextMode(valuetype [System.Web]System.Web.UI.WebControls.TextBoxMode)
0xa289ee  ldarg.0
0xa289ef  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.WebPartPages.XmlToolpart::_downLevelXmlField
0xa289f4  ldarg.0
0xa289f5  ldfld    class Microsoft.SharePoint.WebPartPages.XmlWebPart Microsoft.SharePoint.WebPartPages.XmlToolpart::_xmlPart
0xa289fa  callvirt instance class [System.Xml]System.Xml.XmlElement Microsoft.SharePoint.WebPartPages.XmlWebPart::get_Xml()
0xa289ff  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0xa28a04  callvirt instance void [System.Web]System.Web.UI.WebControls.TextBox::set_Text(string)
0xa28a09  ldarg.0
0xa28a0a  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.WebPartPages.XmlToolpart::_downLevelXmlField
0xa28a0f  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.WebControls.WebControl::get_Style()
0xa28a14  ldstr    aWidth_0// "width"
0xa28a19  ldstr    a180px// "180px"
0xa28a1e  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::set_Item(string, string)
0xa28a23  ldarg.0
0xa28a24  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.WebPartPages.XmlToolpart::_downLevelXmlField
0xa28a29  ldsfld   string Microsoft.SharePoint.WebPartPages.XmlToolpart::ToolpartQualifier
0xa28a2e  ldstr    aDownlevelxmlfi// "_downLevelXmlField"
0xa28a33  call     string [mscorlib]System.String::Concat(string, string)
0xa28a38  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0xa28a3d  ldarg.0
0xa28a3e  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.WebPartPages.XmlToolpart::_downLevelXmlField
0xa28a43  ldstr    aXmllinkliteral// "XmlLinkLiteral"
0xa28a48  call     string Microsoft.SharePoint.WebPartPages.WebPartPageResource::GetString(string name)
0xa28a4d  callvirt instance void [System.Web]System.Web.UI.WebControls.WebControl::set_ToolTip(string)
0xa28a52  ldarg.0
0xa28a53  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xa28a58  ldarg.0
0xa28a59  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.WebPartPages.XmlToolpart::_downLevelXmlField
0xa28a5e  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xa28a63  ldarg.0
0xa28a64  newobj   instance void [System.Web]System.Web.UI.WebControls.TextBox::.ctor()
0xa28a69  stfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.WebPartPages.XmlToolpart::_downLevelXslField
0xa28a6e  ldarg.0
0xa28a6f  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.WebPartPages.XmlToolpart::_downLevelXslField
0xa28a74  ldc.i4.1
0xa28a75  callvirt instance void [System.Web]System.Web.UI.WebControls.TextBox::set_TextMode(valuetype [System.Web]System.Web.UI.WebControls.TextBoxMode)
0xa28a7a  ldarg.0
0xa28a7b  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.WebPartPages.XmlToolpart::_downLevelXslField
0xa28a80  ldarg.0
0xa28a81  ldfld    class Microsoft.SharePoint.WebPartPages.XmlWebPart Microsoft.SharePoint.WebPartPages.XmlToolpart::_xmlPart
0xa28a86  callvirt instance class [System.Xml]System.Xml.XmlElement Microsoft.SharePoint.WebPartPages.XmlWebPart::get_Xsl()
0xa28a8b  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0xa28a90  callvirt instance void [System.Web]System.Web.UI.WebControls.TextBox::set_Text(string)
0xa28a95  ldarg.0
0xa28a96  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.WebPartPages.XmlToolpart::_downLevelXslField
0xa28a9b  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.WebControls.WebControl::get_Style()
0xa28aa0  ldstr    aWidth_0// "width"
0xa28aa5  ldstr    a180px// "180px"
0xa28aaa  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::set_Item(string, string)
0xa28aaf  ldarg.0
0xa28ab0  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.WebPartPages.XmlToolpart::_downLevelXslField
0xa28ab5  ldsfld   string Microsoft.SharePoint.WebPartPages.XmlToolpart::ToolpartQualifier
0xa28aba  ldstr    aDownlevelxslfi_0// "_downLevelXslField"
0xa28abf  call     string [mscorlib]System.String::Concat(string, string)
0xa28ac4  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0xa28ac9  ldarg.0
0xa28aca  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.WebPartPages.XmlToolpart::_downLevelXslField
0xa28acf  ldstr    aXsllinkliteral// "XslLinkLiteral"
0xa28ad4  call     string Microsoft.SharePoint.WebPartPages.WebPartPageResource::GetString(string name)
0xa28ad9  callvirt instance void [System.Web]System.Web.UI.WebControls.WebControl::set_ToolTip(string)
0xa28ade  ldarg.0
0xa28adf  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xa28ae4  ldarg.0
0xa28ae5  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.WebPartPages.XmlToolpart::_downLevelXslField
0xa28aea  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xa28aef  br.s     loc_A28B3D
0xa28af1  ldarg.0
0xa28af2  ldarg.0
0xa28af3  ldstr    aAddxml// "AddXml"
0xa28af8  call     string Microsoft.SharePoint.WebPartPages.WebPartPageResource::GetString(string name)
0xa28afd  ldstr    aXml_8// "XML"
0xa28b02  ldarg.0
0xa28b03  ldfld    string Microsoft.SharePoint.WebPartPages.XmlToolpart::EditButtonEventHandler
0xa28b08  ldstr    aAddxml// "AddXml"
0xa28b0d  call     instance string Microsoft.SharePoint.WebPartPages.XmlToolpart::CreateEditButton(string buttonText, string targetProperty, string editButtonEventHandler, string buttonID)
0xa28b12  stfld    string Microsoft.SharePoint.WebPartPages.XmlToolpart::_editXmlButton
0xa28b17  ldarg.0
0xa28b18  ldarg.0
0xa28b19  ldstr    aAddxsl// "AddXsl"
0xa28b1e  call     string Microsoft.SharePoint.WebPartPages.WebPartPageResource::GetString(string name)
0xa28b23  ldstr    aXsl_2// "XSL"
0xa28b28  ldarg.0
0xa28b29  ldfld    string Microsoft.SharePoint.WebPartPages.XmlToolpart::EditButtonEventHandler
0xa28b2e  ldstr    aAddxsl// "AddXsl"
0xa28b33  call     instance string Microsoft.SharePoint.WebPartPages.XmlToolpart::CreateEditButton(string buttonText, string targetProperty, string editButtonEventHandler, string buttonID)
0xa28b38  stfld    string Microsoft.SharePoint.WebPartPages.XmlToolpart::_editXslButton
0xa28b3d  ldarg.0
0xa28b3e  call     instance void [System.Web]System.Web.UI.Control::CreateChildControls()
0xa28b43  ret
```
