# Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::OnLoad

- ea: `0x2290`
- end: `0x23f5`
- name: `Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::OnLoad`
- size: `357`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x2290`
- `0x3220`
- `0x14cc0`
- `0x14ce0`
- `0x14ec0`
- `0x14ee0`
- `0x2acd0`

## string_xrefs

- `0x232b`: `Microsoft.SharePoint.Taxonomy.FieldEditor.disableReuseSection(true, true);Microsoft.SharePoint.Taxonomy.FieldEditor.disableCreateSection(false, true);`
- `0x2345`: `Microsoft.SharePoint.Taxonomy.FieldEditor.disableReuseSection(false, true);Microsoft.SharePoint.Taxonomy.FieldEditor.disableCreateSection(true, true);`
- `0x2397`: `/_vti_bin/TaxonomyInternalService.json`

## pseudocode

```c

```

## disassembly

```asm
0x2290  ldarg.0
0x2291  ldarg.1
0x2292  call     instance void [System.Web]System.Web.UI.Control::OnLoad(class [mscorlib]System.EventArgs)
0x2297  ldarg.0
0x2298  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x229d  ldstr    aScriptresource// "ScriptResources.resx"
0x22a2  ldc.i4.0
0x22a3  ldc.i4.1
0x22a4  call     void [Microsoft.SharePoint]Microsoft.SharePoint.WebControls.ScriptLink::RegisterScriptAfterUI(class [System.Web]System.Web.UI.Page, string, bool, bool)
0x22a9  ldarg.0
0x22aa  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x22af  ldstr    aSpCoreJs// "SP.Core.js"
0x22b4  ldc.i4.0
0x22b5  call     void [Microsoft.SharePoint]Microsoft.SharePoint.WebControls.ScriptLink::RegisterScriptAfterUI(class [System.Web]System.Web.UI.Page, string, bool)
0x22ba  ldarg.0
0x22bb  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x22c0  ldstr    aSpJs// "SP.js"
0x22c5  ldc.i4.0
0x22c6  call     void [Microsoft.SharePoint]Microsoft.SharePoint.WebControls.ScriptLink::RegisterScriptAfterUI(class [System.Web]System.Web.UI.Page, string, bool)
0x22cb  ldarg.0
0x22cc  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x22d1  ldstr    aTreecontrolJs// "TreeControl.js"
0x22d6  ldc.i4.0
0x22d7  call     void [Microsoft.SharePoint]Microsoft.SharePoint.WebControls.ScriptLink::RegisterScriptAfterUI(class [System.Web]System.Web.UI.Page, string, bool)
0x22dc  ldarg.0
0x22dd  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x22e2  ldstr    aFieldeditorJs// "FieldEditor.js"
0x22e7  ldc.i4.0
0x22e8  call     void [Microsoft.SharePoint]Microsoft.SharePoint.WebControls.ScriptLink::RegisterOnDemand(class [System.Web]System.Web.UI.Page, string, bool)
0x22ed  ldarg.0
0x22ee  ldfld    class [Microsoft.Office.Server]Microsoft.Office.Server.WebControls.DelegateValidationControl Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::treeControlValidator
0x22f3  ldarg.0
0x22f4  ldftn    instance void Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::TermSetValidationCallback(class [Microsoft.Office.Server]Microsoft.Office.Server.WebControls.DelegateValidationControl validationControl)
0x22fa  newobj   instance void [Microsoft.Office.Server]Microsoft.Office.Server.WebControls.DelegateValidationControl/ValidationCallbackDefinition::.ctor(object, native int)
0x22ff  callvirt instance void [Microsoft.Office.Server]Microsoft.Office.Server.WebControls.DelegateValidationControl::set_ValidationCallback(class [Microsoft.Office.Server]Microsoft.Office.Server.WebControls.DelegateValidationControl/ValidationCallbackDefinition)
0x2304  ldarg.0
0x2305  ldfld    class [Microsoft.Office.Server]Microsoft.Office.Server.WebControls.DelegateValidationControl Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::defaultControlValidator
0x230a  ldarg.0
0x230b  ldftn    instance void Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::DefaultValueValidationCallback(class [Microsoft.Office.Server]Microsoft.Office.Server.WebControls.DelegateValidationControl validationControl)
0x2311  newobj   instance void [Microsoft.Office.Server]Microsoft.Office.Server.WebControls.DelegateValidationControl/ValidationCallbackDefinition::.ctor(object, native int)
0x2316  callvirt instance void [Microsoft.Office.Server]Microsoft.Office.Server.WebControls.DelegateValidationControl::set_ValidationCallback(class [Microsoft.Office.Server]Microsoft.Office.Server.WebControls.DelegateValidationControl/ValidationCallbackDefinition)
0x231b  ldarg.0
0x231c  ldfld    class [System.Web]System.Web.UI.WebControls.RadioButton Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::createTermSet
0x2321  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.WebControls.WebControl::get_Attributes()
0x2326  ldstr    aOnclick_0// "onClick"
0x232b  ldstr    aMicrosoftShare// "Microsoft.SharePoint.Taxonomy.FieldEdit"...
0x2330  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x2335  ldarg.0
0x2336  ldfld    class [System.Web]System.Web.UI.WebControls.RadioButton Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::reuseTermSet
0x233b  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.WebControls.WebControl::get_Attributes()
0x2340  ldstr    aOnclick_0// "onClick"
0x2345  ldstr    aMicrosoftShare_0// "Microsoft.SharePoint.Taxonomy.FieldEdit"...
0x234a  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x234f  ldarg.0
0x2350  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x2355  ldstr    aTaxeditorjavas// "taxEditorJavaScript"
0x235a  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.WebControls.SPPageContentManager::IsClientScriptBlockRegistered(class [System.Web]System.Web.UI.Page, string)
0x235f  brtrue.s loc_2382
0x2361  ldarg.0
0x2362  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x2367  ldarg.0
0x2368  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x236d  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2372  ldstr    aTaxeditorjavas// "taxEditorJavaScript"
0x2377  ldarg.0
0x2378  call     instance string Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::GetJavascript()
0x237d  call     void [Microsoft.SharePoint]Microsoft.SharePoint.WebControls.SPPageContentManager::RegisterClientScriptBlock(class [System.Web]System.Web.UI.Page, class [mscorlib]System.Type, string, string)
0x2382  ldarg.0
0x2383  ldfld    class Microsoft.SharePoint.Taxonomy.TaxonomyWebTaggingControl Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::defaultValueControl
0x2388  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x238d  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Web()
0x2392  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_Url()
0x2397  ldstr    aVtiBinTaxonomy// "/_vti_bin/TaxonomyInternalService.json"
0x239c  call     string [mscorlib]System.String::Concat(string, string)
0x23a1  newobj   instance void [System]System.Uri::.ctor(string)
0x23a6  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyWebTaggingControl::set_WebServiceUrl(class [System]System.Uri value)
0x23ab  ldarg.0
0x23ac  ldfld    class Microsoft.SharePoint.Taxonomy.TaxonomyWebTaggingControl Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::defaultValueControl
0x23b1  ldc.i4.0
0x23b2  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyWebTaggingControl::set_IsMulti(bool value)
0x23b7  ldarg.0
0x23b8  ldfld    class Microsoft.SharePoint.Taxonomy.TaxonomyWebTaggingControl Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::defaultValueControl
0x23bd  ldstr    aDefaultvaluena// "DefaultValueName"
0x23c2  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x23c7  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyWebTaggingControl::set_FieldName(string value)
0x23cc  ldarg.0
0x23cd  ldfld    class Microsoft.SharePoint.Taxonomy.TaxonomyWebTaggingControl Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::defaultValueControl
0x23d2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x23d7  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x23dc  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyWebTaggingControl::set_Language(int32 value)
0x23e1  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPAppRequestContext [Microsoft.SharePoint]Microsoft.SharePoint.SPAppRequestContext::get_Current()
0x23e6  brfalse.s loc_23F4
0x23e8  ldarg.0
0x23e9  ldfld    class [System.Web]System.Web.UI.WebControls.Literal Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::tunnelToTermStoreLinkText
0x23ee  ldc.i4.0
0x23ef  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x23f4  ret
```
