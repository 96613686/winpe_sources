# Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::GetJavascript

- ea: `0x3220`
- end: `0x36a8`
- name: `Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::GetJavascript`
- size: `1160`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x2290`

## callees

- `0x3220`
- `0x36b0`
- `0x14b00`
- `0x251c0`
- `0x297a0`
- `0x297e0`
- `0x29830`
- `0x29950`
- `0x299c0`
- `0x29a10`
- `0x29a70`
- `0x29a90`
- `0x29af0`
- `0x2acd0`

## string_xrefs

- `0x32ec`: `').disabled)\n                {\n                var textInput = $get(getCreateTermSetInputTextId());\n                if (!textInput || textInput.value == '00000000-0000-0000-0000-000000000000') \n                {\n                    return false;\n                }\n                var openLink = confirm('`
- `0x330c`: `');\n                if (openLink)\n                {\n                    var forms = document.getElementsByTagName('form');\n                    var link = '`
- `0x33ee`: `';\n                link += createTermSetId;\n                return window.open(link,'','scrollbars=no,menubar=no,height=600,width=800,resizable=yes,toolbar=no,location=no,status=no');\n                }\n            return openLink;\n            }\n            return false;\n        }`
- `0x33fb`: `';\n                    link += createTermSetId;\n                    for (var i=0;i<forms.length;i++)\n                    {\n                        var index = forms[i].action.indexOf('Source=',0);\n                        if (index >= 0)\n                        {\n                            index += 7;\n                            var start = forms[i].action.substring(0, index);\n                            var end = forms[i].action.substring(index, forms[i].action.length);\n    `
- `0x344e`: `getCreateSspInputTextId`
- `0x347a`: `getAnchorPathInputTextId`
- `0x3490`: `getCreateTermSetInputTextId`
- `0x34a6`: `getCreateAnchorInputTextId`
- `0x34bc`: `getCreateAnchorPathInputTextId`
- `0x34e8`: `getWebServicePath`
- `0x3599`: `getCreateTermSetDescriptionId`
- `0x35af`: `getCreateTermSetWarning`
- `0x35c5`: `getCreateTermSetDescriptionLabelId`
- `0x3649`: `\n            var createTermSetId = 'not yet set';\n            function setCreateTermSetId(termSetId)\n            {\n                createTermSetId = termSetId;\n            }`

## pseudocode

```c

```

## disassembly

```asm
0x3220  newobj   instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::.ctor()
0x3225  stloc.0
0x3226  ldloc.0
0x3227  ldstr    aVarResetenable// "\r\n            var resetEnabled = fals"...
0x322c  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::Append(string script)
0x3231  ldloc.0
0x3232  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::AppendLine()
0x3237  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x323c  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Site()
0x3241  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPFeatureCollection [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_Features()
0x3246  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.FeatureIds::Taxonomy
0x324b  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPFeature [Microsoft.SharePoint]Microsoft.SharePoint.SPFeatureCollection::get_Item(valuetype [mscorlib]System.Guid)
0x3250  stloc.1
0x3251  ldloc.0
0x3252  ldstr    aGetfeatureenab// "getFeatureEnabled"
0x3257  ldloc.1
0x3258  ldnull
0x3259  ceq
0x325b  ldc.i4.0
0x325c  ceq
0x325e  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::AppendGetLiteralFunction(string functionName, bool literal)
0x3263  ldloc.0
0x3264  ldstr    aResettextbox// "resetTextBox"
0x3269  ldc.i4.3
0x326a  newarr   [mscorlib]System.Object
0x326f  stloc.s  5
0x3271  ldloc.s  5
0x3273  ldc.i4.0
0x3274  ldstr    aIfResetenabled// "\r\n            if (resetEnabled)\r\n  "...
0x3279  stelem.ref
0x327a  ldloc.s  5
0x327c  ldc.i4.1
0x327d  ldarg.0
0x327e  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::termSetSearchBox
0x3283  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x3288  stelem.ref
0x3289  ldloc.s  5
0x328b  ldc.i4.2
0x328c  ldstr    aTextboxValueMi// "');\r\n                textbox.value = "...
0x3291  stelem.ref
0x3292  ldloc.s  5
0x3294  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::AppendFunctionFragments(string functionName, object[] functionBodyFragments)
0x3299  ldloc.0
0x329a  ldstr    aGetfindtext// "getFindText"
0x329f  ldc.i4.3
0x32a0  newarr   [mscorlib]System.Object
0x32a5  stloc.s  6
0x32a7  ldloc.s  6
0x32a9  ldc.i4.0
0x32aa  ldstr    aVarTextboxDocu// "\r\n            var textbox = document."...
0x32af  stelem.ref
0x32b0  ldloc.s  6
0x32b2  ldc.i4.1
0x32b3  ldarg.0
0x32b4  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::termSetSearchBox
0x32b9  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x32be  stelem.ref
0x32bf  ldloc.s  6
0x32c1  ldc.i4.2
0x32c2  ldstr    aReturnTextboxV// "');\r\n            return textbox.value"...
0x32c7  stelem.ref
0x32c8  ldloc.s  6
0x32ca  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::AppendFunctionFragments(string functionName, object[] functionBodyFragments)
0x32cf  ldloc.0
0x32d0  ldstr    aFunctionTunnel// "function tunnelToTSMT()\r\n            "...
0x32d5  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::Append(string script)
0x32da  ldloc.0
0x32db  ldarg.0
0x32dc  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::createTermSetDescription
0x32e1  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x32e6  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::Append(string script)
0x32eb  ldloc.0
0x32ec  ldstr    aDisabledVarTex// "').disabled)\r\n                {\r\n  "...
0x32f1  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::Append(string script)
0x32f6  ldloc.0
0x32f7  ldstr    aTunneltotermst// "TunnelToTermStore"
0x32fc  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x3301  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPHttpUtility::EcmaScriptStringLiteralEncode(string)
0x3306  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::Append(string script)
0x330b  ldloc.0
0x330c  ldstr    aIfOpenlink// "');\r\n                if (openLink)\r"...
0x3311  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::Append(string script)
0x3316  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x331b  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Web()
0x3320  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_Url()
0x3325  newobj   instance void [System]System.Uri::.ctor(string)
0x332a  stloc.2
0x332b  ldloc.2
0x332c  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x3331  stloc.3
0x3332  ldloc.0
0x3333  ldloc.3
0x3334  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPHttpUtility::EcmaScriptStringLiteralEncode(string)
0x3339  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::Append(string script)
0x333e  ldloc.3
0x333f  ldstr    asc_781A8// "/"
0x3344  ldc.i4.5
0x3345  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x334a  brtrue.s loc_3357
0x334c  ldloc.0
0x334d  ldstr    asc_781A8// "/"
0x3352  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::Append(string script)
0x3357  ldloc.0
0x3358  call     string Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::get_RelativeLayoutsVersionUrl()
0x335d  ldstr    aTermstoremanag// "termstoremanager.aspx?SiteUrlAndTermSet"...
0x3362  call     string [mscorlib]System.String::Concat(string, string)
0x3367  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::Append(string script)
0x336c  ldloc.0
0x336d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x3372  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Web()
0x3377  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_ID()
0x337c  stloc.s  7
0x337e  ldloca.s 7
0x3380  constrained. [mscorlib]System.Guid
0x3386  callvirt instance string [mscorlib]System.Object::ToString()
0x338b  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::Append(string script)
0x3390  ldloc.0
0x3391  ldstr    asc_7A742// "|"
0x3396  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::Append(string script)
0x339b  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x33a0  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPList [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_List()
0x33a5  brfalse.s loc_33CB
0x33a7  ldloc.0
0x33a8  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x33ad  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPList [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_List()
0x33b2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPList::get_ID()
0x33b7  stloc.s  8
0x33b9  ldloca.s 8
0x33bb  constrained. [mscorlib]System.Guid
0x33c1  callvirt instance string [mscorlib]System.Object::ToString()
0x33c6  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::Append(string script)
0x33cb  ldloc.0
0x33cc  ldstr    asc_7A742// "|"
0x33d1  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::Append(string script)
0x33d6  ldarg.0
0x33d7  callvirt instance class [System.Web]System.Web.HttpContext [System.Web]System.Web.UI.Control::get_Context()
0x33dc  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x33e1  ldstr    aIsdlg// "IsDlg"
0x33e6  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPRequestParameterUtility::HasParameter(class [System.Web]System.Web.HttpRequest, string)
0x33eb  brfalse.s loc_33FA
0x33ed  ldloc.0
0x33ee  ldstr    aLinkCreateterm// "';\r\n                link += createTer"...
0x33f3  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::Append(string script)
0x33f8  br.s     loc_3405
0x33fa  ldloc.0
0x33fb  ldstr    aLinkCreateterm_0// "';\r\n                    link += creat"...
0x3400  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::Append(string script)
0x3405  ldloc.0
0x3406  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::AppendLine()
0x340b  ldloc.0
0x340c  ldstr    aGetgroupinputt// "getGroupInputTextId"
0x3411  ldarg.0
0x3412  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::reuseGroupId
0x3417  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x341c  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::AppendGetLiteralFunction(string functionName, string literal)
0x3421  ldloc.0
0x3422  ldstr    aGettermsetinpu// "getTermSetInputTextId"
0x3427  ldarg.0
0x3428  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::reuseTermSetId
0x342d  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x3432  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::AppendGetLiteralFunction(string functionName, string literal)
0x3437  ldloc.0
0x3438  ldstr    aGetsspinputtex// "getSspInputTextId"
0x343d  ldarg.0
0x343e  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::reuseSspId
0x3443  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x3448  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::AppendGetLiteralFunction(string functionName, string literal)
0x344d  ldloc.0
0x344e  ldstr    aGetcreatesspin// "getCreateSspInputTextId"
0x3453  ldarg.0
0x3454  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::createSspId
0x3459  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x345e  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::AppendGetLiteralFunction(string functionName, string literal)
0x3463  ldloc.0
0x3464  ldstr    aGetanchorinput// "getAnchorInputTextId"
0x3469  ldarg.0
0x346a  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::reuseAnchorId
0x346f  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x3474  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::AppendGetLiteralFunction(string functionName, string literal)
0x3479  ldloc.0
0x347a  ldstr    aGetanchorpathi// "getAnchorPathInputTextId"
0x347f  ldarg.0
0x3480  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::reuseAnchorIdPath
0x3485  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x348a  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::AppendGetLiteralFunction(string functionName, string literal)
0x348f  ldloc.0
0x3490  ldstr    aGetcreateterms// "getCreateTermSetInputTextId"
0x3495  ldarg.0
0x3496  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::createTermSetId
0x349b  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x34a0  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::AppendGetLiteralFunction(string functionName, string literal)
0x34a5  ldloc.0
0x34a6  ldstr    aGetcreateancho// "getCreateAnchorInputTextId"
0x34ab  ldarg.0
0x34ac  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::createAnchorId
0x34b1  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x34b6  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::AppendGetLiteralFunction(string functionName, string literal)
0x34bb  ldloc.0
0x34bc  ldstr    aGetcreateancho_0// "getCreateAnchorPathInputTextId"
0x34c1  ldarg.0
0x34c2  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::createAnchorIdPath
0x34c7  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x34cc  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::AppendGetLiteralFunction(string functionName, string literal)
0x34d1  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x34d6  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Site()
0x34db  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_Url()
0x34e0  newobj   instance void [System]System.Uri::.ctor(string)
0x34e5  stloc.s  4
0x34e7  ldloc.0
0x34e8  ldstr    aGetwebservicep// "getWebServicePath"
0x34ed  ldloc.s  4
0x34ef  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x34f4  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::AppendGetEncodedLiteralFunction(string functionName, string literal)
0x34f9  ldloc.0
0x34fa  ldstr    aGetwebid// "getWebId"
0x34ff  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x3504  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Web()
0x3509  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_ID()
0x350e  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::AppendGetLiteralFunction(string functionName, valuetype [mscorlib]System.Guid literal)
0x3513  ldloc.0
0x3514  ldstr    aGetlistid// "getListId"
0x3519  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x351e  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPList [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_List()
0x3523  brtrue.s loc_352C
0x3525  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x352a  br.s     loc_353B
0x352c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x3531  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPList [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_List()
0x3536  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPList::get_ID()
0x353b  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::AppendGetLiteralFunction(string functionName, valuetype [mscorlib]System.Guid literal)
0x3540  ldloc.0
0x3541  ldstr    aGettermecbmenu// "getTermEcbMenu"
0x3546  ldarg.0
0x3547  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.WebControls.MenuTemplate Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::termECBMenu
0x354c  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x3551  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::AppendGetLiteralFunction(string functionName, string literal)
0x3556  ldloc.0
0x3557  ldstr    aGettsecbmenu// "getTSEcbMenu"
0x355c  ldarg.0
0x355d  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.WebControls.MenuTemplate Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::termSetECBMenu
0x3562  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x3567  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::AppendGetLiteralFunction(string functionName, string literal)
0x356c  ldloc.0
0x356d  ldstr    aGettermsetsear// "getTermSetSearchBoxId"
0x3572  ldarg.0
0x3573  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::termSetSearchBox
0x3578  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x357d  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::AppendGetLiteralFunction(string functionName, string literal)
0x3582  ldloc.0
0x3583  ldstr    aGettermsetsear_0// "getTermSetSearchBoxLabelId"
0x3588  ldarg.0
0x3589  ldfld    class [System.Web]System.Web.UI.WebControls.Label Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::termSetSearchBoxLabel
0x358e  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x3593  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::AppendGetLiteralFunction(string functionName, string literal)
0x3598  ldloc.0
0x3599  ldstr    aGetcreateterms_0// "getCreateTermSetDescriptionId"
0x359e  ldarg.0
0x359f  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::createTermSetDescription
0x35a4  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x35a9  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::AppendGetLiteralFunction(string functionName, string literal)
0x35ae  ldloc.0
0x35af  ldstr    aGetcreateterms_1// "getCreateTermSetWarning"
0x35b4  ldarg.0
0x35b5  ldfld    class [System.Web]System.Web.UI.WebControls.Label Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::createTermSetWarning
0x35ba  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x35bf  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::AppendGetLiteralFunction(string functionName, string literal)
0x35c4  ldloc.0
0x35c5  ldstr    aGetcreateterms_2// "getCreateTermSetDescriptionLabelId"
0x35ca  ldarg.0
0x35cb  ldfld    class [System.Web]System.Web.UI.WebControls.Label Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::createTermSetDescriptionLabel
0x35d0  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x35d5  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::AppendGetLiteralFunction(string functionName, string literal)
0x35da  ldloc.0
0x35db  ldstr    aGetdefaultvalu// "getDefaultValueId"
0x35e0  ldarg.0
0x35e1  ldfld    class Microsoft.SharePoint.Taxonomy.TaxonomyWebTaggingControl Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::defaultValueControl
0x35e6  callvirt instance string Microsoft.SharePoint.Taxonomy.TaxonomyWebTaggingControl::get_ContainerId()
0x35eb  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::AppendGetLiteralFunction(string functionName, string literal)
0x35f0  ldloc.0
0x35f1  ldstr    aGetfillinfalse// "getFillInFalseId"
0x35f6  ldarg.0
0x35f7  ldfld    class [System.Web]System.Web.UI.WebControls.RadioButton Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::fillInFalse
0x35fc  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x3601  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::AppendGetLiteralFunction(string functionName, string literal)
0x3606  ldloc.0
0x3607  ldstr    aGetfillintruei// "getFillInTrueId"
0x360c  ldarg.0
0x360d  ldfld    class [System.Web]System.Web.UI.WebControls.RadioButton Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::fillInTrue
0x3612  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x3617  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::AppendGetLiteralFunction(string functionName, string literal)
0x361c  ldloc.0
0x361d  ldstr    aGetallowmultii// "getAllowMultiId"
0x3622  ldarg.0
0x3623  ldfld    class [System.Web]System.Web.UI.WebControls.CheckBox Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::multipleAllowed
0x3628  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x362d  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.JavascriptBuilder::AppendGetLiteralFunction(string functionName, string literal)
0x3632  ldloc.0
0x3633  ldstr    aGetisreuseterm// "getIsReuseTermSet"
0x3638  ldarg.0
0x3639  ldfld    class [System.Web]System.Web.UI.WebControls.RadioButton Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::reuseTermSet
  ... truncated ...
```
