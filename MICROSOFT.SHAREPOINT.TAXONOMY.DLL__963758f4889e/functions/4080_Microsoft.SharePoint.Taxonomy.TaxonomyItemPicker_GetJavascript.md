# Microsoft.SharePoint.Taxonomy.TaxonomyItemPicker::GetJavascript

- ea: `0x4080`
- end: `0x4227`
- name: `Microsoft.SharePoint.Taxonomy.TaxonomyItemPicker::GetJavascript`
- size: `423`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x37f0`

## callees

- `0x297a0`
- `0x297e0`
- `0x29830`
- `0x29950`
- `0x299c0`
- `0x29a10`
- `0x29a70`
- `0x29a90`
- `0x29af0`

## string_xrefs

- `0x418d`: `/_vti_bin/TaxonomyInternalService.json`
- `0x419e`: `getWebServicePath`
- `0x40cd`: `');\n                textbox.value = '';\n                Microsoft.SharePoint.Taxonomy.TaxonomyItemPickerScript.showReuseTaxTree();\n                resetEnabled = false;\n            }`
- `0x4153`: `getTermPathInputTextId`
- `0x4210`: `\n            function loadTaxonomyItemPickerScript()\n            {\n                EnsureScript('TaxonomyItemPickerScript.js', typeof(Microsoft.SharePoint.Taxonomy.TaxonomyItemPickerScript), null);\n            }\n            ExecuteOrDelayUntilScriptLoaded(loadTaxonomyItemPickerScript, 'ScriptForWebTaggingUI.js');\n            `

## pseudocode

```c

```

## disassembly

```asm
0x4080  newobj   instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::.ctor()
0x4085  stloc.0
0x4086  ldloc.0
0x4087  ldstr    aVarResetenable// "\r\n            var resetEnabled = fals"...
0x408c  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::Append(string script)
0x4091  ldloc.0
0x4092  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::AppendLine()
0x4097  ldloc.0
0x4098  ldstr    aGetfeatureenab// "getFeatureEnabled"
0x409d  ldarg.0
0x409e  ldfld    bool Microsoft.SharePoint.Taxonomy.TaxonomyItemPicker::taxonomyFeatureEnabled
0x40a3  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::AppendGetLiteralFunction(string functionName, bool literal)
0x40a8  ldloc.0
0x40a9  ldstr    aResettextbox// "resetTextBox"
0x40ae  ldc.i4.3
0x40af  newarr   [mscorlib]System.Object
0x40b4  stloc.2
0x40b5  ldloc.2
0x40b6  ldc.i4.0
0x40b7  ldstr    aIfResetenabled// "\r\n            if (resetEnabled)\r\n  "...
0x40bc  stelem.ref
0x40bd  ldloc.2
0x40be  ldc.i4.1
0x40bf  ldarg.0
0x40c0  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.Taxonomy.TaxonomyItemPicker::termSetSearchBox
0x40c5  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x40ca  stelem.ref
0x40cb  ldloc.2
0x40cc  ldc.i4.2
0x40cd  ldstr    aTextboxValueMi_0// "');\r\n                textbox.value = "...
0x40d2  stelem.ref
0x40d3  ldloc.2
0x40d4  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::AppendFunctionFragments(string functionName, object[] functionBodyFragments)
0x40d9  ldloc.0
0x40da  ldstr    aGetfindtext// "getFindText"
0x40df  ldc.i4.3
0x40e0  newarr   [mscorlib]System.Object
0x40e5  stloc.3
0x40e6  ldloc.3
0x40e7  ldc.i4.0
0x40e8  ldstr    aVarTextboxDocu// "\r\n            var textbox = document."...
0x40ed  stelem.ref
0x40ee  ldloc.3
0x40ef  ldc.i4.1
0x40f0  ldarg.0
0x40f1  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.Taxonomy.TaxonomyItemPicker::termSetSearchBox
0x40f6  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x40fb  stelem.ref
0x40fc  ldloc.3
0x40fd  ldc.i4.2
0x40fe  ldstr    aReturnTextboxV// "');\r\n            return textbox.value"...
0x4103  stelem.ref
0x4104  ldloc.3
0x4105  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::AppendFunctionFragments(string functionName, object[] functionBodyFragments)
0x410a  ldloc.0
0x410b  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::AppendLine()
0x4110  ldloc.0
0x4111  ldstr    aGettermstorein// "getTermStoreInputTextId"
0x4116  ldarg.0
0x4117  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputHidden Microsoft.SharePoint.Taxonomy.TaxonomyItemPicker::taxonomyItemPickerTermStoreId
0x411c  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x4121  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::AppendGetLiteralFunction(string functionName, string literal)
0x4126  ldloc.0
0x4127  ldstr    aGettermsetinpu// "getTermSetInputTextId"
0x412c  ldarg.0
0x412d  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputHidden Microsoft.SharePoint.Taxonomy.TaxonomyItemPicker::taxonomyItemPickerTermSetId
0x4132  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x4137  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::AppendGetLiteralFunction(string functionName, string literal)
0x413c  ldloc.0
0x413d  ldstr    aGetgroupinputt// "getGroupInputTextId"
0x4142  ldarg.0
0x4143  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputHidden Microsoft.SharePoint.Taxonomy.TaxonomyItemPicker::taxonomyItemPickerGroupId
0x4148  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x414d  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::AppendGetLiteralFunction(string functionName, string literal)
0x4152  ldloc.0
0x4153  ldstr    aGettermpathinp// "getTermPathInputTextId"
0x4158  ldarg.0
0x4159  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputHidden Microsoft.SharePoint.Taxonomy.TaxonomyItemPicker::taxonomyItemPickerTermPath
0x415e  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x4163  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::AppendGetLiteralFunction(string functionName, string literal)
0x4168  ldloc.0
0x4169  ldstr    aGetoptionsinpu// "getOptionsInputTextId"
0x416e  ldarg.0
0x416f  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputHidden Microsoft.SharePoint.Taxonomy.TaxonomyItemPicker::taxonomyItemPickerOptions
0x4174  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x4179  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::AppendGetLiteralFunction(string functionName, string literal)
0x417e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x4183  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Web()
0x4188  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_Url()
0x418d  ldstr    aVtiBinTaxonomy// "/_vti_bin/TaxonomyInternalService.json"
0x4192  call     string [mscorlib]System.String::Concat(string, string)
0x4197  newobj   instance void [System]System.Uri::.ctor(string)
0x419c  stloc.1
0x419d  ldloc.0
0x419e  ldstr    aGetwebservicep// "getWebServicePath"
0x41a3  ldloc.1
0x41a4  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x41a9  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::AppendGetEncodedLiteralFunction(string functionName, string literal)
0x41ae  ldloc.0
0x41af  ldstr    aGetwebid// "getWebId"
0x41b4  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x41b9  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Web()
0x41be  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_ID()
0x41c3  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::AppendGetLiteralFunction(string functionName, valuetype [mscorlib]System.Guid literal)
0x41c8  ldloc.0
0x41c9  ldstr    aGettermsetsear// "getTermSetSearchBoxId"
0x41ce  ldarg.0
0x41cf  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.Taxonomy.TaxonomyItemPicker::termSetSearchBox
0x41d4  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x41d9  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::AppendGetLiteralFunction(string functionName, string literal)
0x41de  ldloc.0
0x41df  ldstr    aGettermsetsear_0// "getTermSetSearchBoxLabelId"
0x41e4  ldarg.0
0x41e5  ldfld    class [System.Web]System.Web.UI.WebControls.Label Microsoft.SharePoint.Taxonomy.TaxonomyItemPicker::termSetSearchBoxLabel
0x41ea  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x41ef  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::AppendGetLiteralFunction(string functionName, string literal)
0x41f4  ldloc.0
0x41f5  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::AppendLine()
0x41fa  ldloc.0
0x41fb  ldstr    aGetlcid// "getLCID"
0x4200  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x4205  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x420a  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::AppendGetLiteralFunction(string functionName, int32 literal)
0x420f  ldloc.0
0x4210  ldstr    aFunctionLoadta// "\r\n            function loadTaxonomyIt"...
0x4215  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::Append(string script)
0x421a  ldloc.0
0x421b  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::AppendLine()
0x4220  ldloc.0
0x4221  callvirt instance string [mscorlib]System.Object::ToString()
0x4226  ret
```
