# Microsoft.SharePoint.Taxonomy.TaxonomyWebTaggingControl::getOnloadJavascript

- ea: `0x159e0`
- end: `0x1609f`
- name: `Microsoft.SharePoint.Taxonomy.TaxonomyWebTaggingControl::getOnloadJavascript`
- size: `1727`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: `service_task, broker_com_uri`

## callers

- `0x15340`

## callees

- `0x149b0`
- `0x14ae0`
- `0x14b20`
- `0x14b50`
- `0x14c90`
- `0x14cd0`
- `0x14cf0`
- `0x14d10`
- `0x14d40`
- `0x14d70`
- `0x14d90`
- `0x14db0`
- `0x14dd0`
- `0x14df0`
- `0x14e10`
- `0x14e30`
- `0x14e50`
- `0x14e70`
- `0x14e90`
- `0x14ed0`
- `0x14ef0`
- `0x159e0`
- `0x4baa0`
- `0x4cb30`
- `0x4cc10`
- `0x555c0`

## string_xrefs

- `0x15e16`: `tagUI['IsIncludePathData'] = `
- `0x15e4e`: `tagUI['IsUseCommaAsDelimiter'] = `
- `0x15f04`: `tagUI['WebServiceUrl'] = '`

## pseudocode

```c

```

## disassembly

```asm
0x159e0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x159e5  stloc.0
0x159e6  ldloc.0
0x159e7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x159ec  pop
0x159ed  ldloc.0
0x159ee  ldstr    asc_858B2// "{"
0x159f3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x159f8  pop
0x159f9  ldloc.0
0x159fa  ldstr    aVarTaguiDocume// "var tagUI = document.getElementById('"
0x159ff  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x15a04  pop
0x15a05  ldloc.0
0x15a06  ldarg.0
0x15a07  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.SharePoint.Taxonomy.TaxonomyWebTaggingControl::container
0x15a0c  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x15a11  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPEncode::ScriptEncode(string)
0x15a16  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x15a1b  pop
0x15a1c  ldloc.0
0x15a1d  ldstr    asc_85902// "');"
0x15a22  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x15a27  pop
0x15a28  ldloc.0
0x15a29  ldstr    aIfTagui// "if (tagUI)"
0x15a2e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x15a33  pop
0x15a34  ldloc.0
0x15a35  ldstr    asc_858B2// "{"
0x15a3a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x15a3f  pop
0x15a40  ldloc.0
0x15a41  ldstr    aTaguiInputfiel// "tagUI['InputFieldId'] = '"
0x15a46  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x15a4b  pop
0x15a4c  ldloc.0
0x15a4d  ldarg.0
0x15a4e  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputHidden Microsoft.SharePoint.Taxonomy.TaxonomyWebTaggingControl::inputField
0x15a53  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x15a58  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPEncode::ScriptEncode(string)
0x15a5d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x15a62  pop
0x15a63  ldloc.0
0x15a64  ldstr    asc_85954// "';"
0x15a69  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x15a6e  pop
0x15a6f  ldloc.0
0x15a70  ldstr    aTaguiSspid// "tagUI['SspId'] = '"
0x15a75  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x15a7a  pop
0x15a7b  ldloc.0
0x15a7c  ldarg.0
0x15a7d  call     instance string Microsoft.SharePoint.Taxonomy.TaxonomyWebTaggingControl::get_SSPList()
0x15a82  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x15a87  pop
0x15a88  ldloc.0
0x15a89  ldstr    asc_85954// "';"
0x15a8e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x15a93  pop
0x15a94  ldloc.0
0x15a95  ldstr    aTaguiGroupid// "tagUI['GroupId'] = '"
0x15a9a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x15a9f  pop
0x15aa0  ldloc.0
0x15aa1  ldarg.0
0x15aa2  call     instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyWebTaggingControl::get_GroupId()
0x15aa7  box      [mscorlib]System.Guid
0x15aac  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x15ab1  pop
0x15ab2  ldloc.0
0x15ab3  ldstr    asc_85954// "';"
0x15ab8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x15abd  pop
0x15abe  ldloc.0
0x15abf  ldstr    aTaguiTermsetid// "tagUI['TermSetId'] = '"
0x15ac4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x15ac9  pop
0x15aca  ldloc.0
0x15acb  ldarg.0
0x15acc  call     instance string Microsoft.SharePoint.Taxonomy.TaxonomyWebTaggingControl::get_TermSetList()
0x15ad1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x15ad6  pop
0x15ad7  ldloc.0
0x15ad8  ldstr    asc_85954// "';"
0x15add  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x15ae2  pop
0x15ae3  ldloc.0
0x15ae4  ldstr    aTaguiAnchorid// "tagUI['AnchorId'] = '"
0x15ae9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x15aee  pop
0x15aef  ldloc.0
0x15af0  ldarg.0
0x15af1  call     instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyWebTaggingControl::get_AnchorId()
0x15af6  box      [mscorlib]System.Guid
0x15afb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x15b00  pop
0x15b01  ldloc.0
0x15b02  ldstr    asc_85954// "';"
0x15b07  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x15b0c  pop
0x15b0d  ldloc.0
0x15b0e  ldstr    aTaguiIsmulti// "tagUI['IsMulti'] = "
0x15b13  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x15b18  pop
0x15b19  ldloc.0
0x15b1a  ldarg.0
0x15b1b  call     instance bool Microsoft.SharePoint.Taxonomy.TaxonomyWebTaggingControl::get_IsMulti()
0x15b20  stloc.s  4
0x15b22  ldloca.s 4
0x15b24  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15b29  call     instance string [mscorlib]System.Boolean::ToString(class [mscorlib]System.IFormatProvider)
0x15b2e  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x15b33  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x15b38  pop
0x15b39  ldloc.0
0x15b3a  ldstr    asc_7CB8A// ";"
0x15b3f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x15b44  pop
0x15b45  ldloc.0
0x15b46  ldstr    aTaguiAllowfill// "tagUI['AllowFillIn'] = "
0x15b4b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x15b50  pop
0x15b51  ldloc.0
0x15b52  ldarg.0
0x15b53  call     instance bool Microsoft.SharePoint.Taxonomy.TaxonomyWebTaggingControl::get_AllowFillIn()
0x15b58  stloc.s  5
0x15b5a  ldloca.s 5
0x15b5c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15b61  call     instance string [mscorlib]System.Boolean::ToString(class [mscorlib]System.IFormatProvider)
0x15b66  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x15b6b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x15b70  pop
0x15b71  ldloc.0
0x15b72  ldstr    asc_7CB8A// ";"
0x15b77  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x15b7c  pop
0x15b7d  ldloc.0
0x15b7e  ldstr    aTaguiWidthcss// "tagUI['WidthCSS'] = '"
0x15b83  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x15b88  pop
0x15b89  ldloc.0
0x15b8a  ldarg.0
0x15b8b  ldfld    string Microsoft.SharePoint.Taxonomy.TaxonomyWebTaggingControl::widthCss
0x15b90  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x15b95  pop
0x15b96  ldloc.0
0x15b97  ldstr    asc_85954// "';"
0x15b9c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x15ba1  pop
0x15ba2  ldloc.0
0x15ba3  ldstr    aTaguiJavascrip// "tagUI['JavascriptOnValidation'] = \""
0x15ba8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x15bad  pop
0x15bae  ldloc.0
0x15baf  ldarg.0
0x15bb0  ldfld    string Microsoft.SharePoint.Taxonomy.TaxonomyWebTaggingControl::javascriptOnValidation
0x15bb5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x15bba  pop
0x15bbb  ldloc.0
0x15bbc  ldstr    asc_85AD0// "\";"
0x15bc1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x15bc6  pop
0x15bc7  ldarg.0
0x15bc8  ldfld    string Microsoft.SharePoint.Taxonomy.TaxonomyWebTaggingControl::asteriskErrorMessage
0x15bcd  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x15bd2  brtrue.s loc_15BF9
0x15bd4  ldloc.0
0x15bd5  ldstr    aTaguiAsteriske// "tagUI['asteriskError'] = '"
0x15bda  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x15bdf  pop
0x15be0  ldloc.0
0x15be1  ldarg.0
0x15be2  ldfld    string Microsoft.SharePoint.Taxonomy.TaxonomyWebTaggingControl::asteriskErrorMessage
0x15be7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x15bec  pop
0x15bed  ldloc.0
0x15bee  ldstr    asc_85954// "';"
0x15bf3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x15bf8  pop
0x15bf9  ldloc.0
0x15bfa  ldstr    aTaguiLcid// "tagUI['Lcid'] = "
0x15bff  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x15c04  pop
0x15c05  ldarg.0
0x15c06  ldfld    int32 Microsoft.SharePoint.Taxonomy.TaxonomyWebTaggingControl::language
0x15c0b  brfalse.s loc_15C1C
0x15c0d  ldloc.0
0x15c0e  ldarg.0
0x15c0f  ldfld    int32 Microsoft.SharePoint.Taxonomy.TaxonomyWebTaggingControl::language
0x15c14  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(int32)
0x15c19  pop
0x15c1a  br.s     loc_15C81
0x15c1c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x15c21  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Site()
0x15c26  newobj   instance void Microsoft.SharePoint.Taxonomy.TaxonomySession::.ctor(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite site)
0x15c2b  stloc.1
0x15c2c  ldloc.1
0x15c2d  callvirt instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomySession::get_DefaultKeywordsTermStore()
0x15c32  stloc.2
0x15c33  ldloc.2
0x15c34  brfalse.s loc_15C45
0x15c36  ldloc.0
0x15c37  ldloc.2
0x15c38  callvirt instance int32 Microsoft.SharePoint.Taxonomy.TermStore::get_WorkingLanguage()
0x15c3d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(int32)
0x15c42  pop
0x15c43  br.s     loc_15C81
0x15c45  ldloc.1
0x15c46  callvirt instance class Microsoft.SharePoint.Taxonomy.TermStoreCollection Microsoft.SharePoint.Taxonomy.TaxonomySession::get_TermStores()
0x15c4b  brfalse.s loc_15C75
0x15c4d  ldloc.1
0x15c4e  callvirt instance class Microsoft.SharePoint.Taxonomy.TermStoreCollection Microsoft.SharePoint.Taxonomy.TaxonomySession::get_TermStores()
0x15c53  callvirt instance int32 class Microsoft.SharePoint.Taxonomy.Generic.GenericCollection`1<class Microsoft.SharePoint.Taxonomy.TermStore>::get_Count()
0x15c58  ldc.i4.0
0x15c59  ble.s    loc_15C75
0x15c5b  ldloc.0
0x15c5c  ldloc.1
0x15c5d  callvirt instance class Microsoft.SharePoint.Taxonomy.TermStoreCollection Microsoft.SharePoint.Taxonomy.TaxonomySession::get_TermStores()
0x15c62  ldc.i4.0
0x15c63  callvirt instance var<u1> class Microsoft.SharePoint.Taxonomy.Generic.GenericCollection`1<class Microsoft.SharePoint.Taxonomy.TermStore>::get_Item(!!T0)
0x15c68  callvirt instance int32 Microsoft.SharePoint.Taxonomy.TermStore::get_WorkingLanguage()
0x15c6d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(int32)
0x15c72  pop
0x15c73  br.s     loc_15C81
0x15c75  ldloc.0
0x15c76  ldc.i4   0x409
0x15c7b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(int32)
0x15c80  pop
0x15c81  ldloc.0
0x15c82  ldstr    asc_7CB8A// ";"
0x15c87  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x15c8c  pop
0x15c8d  ldloc.0
0x15c8e  ldstr    aTaguiIsspanter// "tagUI['IsSpanTermSets'] = "
0x15c93  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x15c98  pop
0x15c99  ldloc.0
0x15c9a  ldarg.0
0x15c9b  call     instance bool Microsoft.SharePoint.Taxonomy.TaxonomyWebTaggingControl::get_IsSpanTermSets()
0x15ca0  stloc.s  6
0x15ca2  ldloca.s 6
0x15ca4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15ca9  call     instance string [mscorlib]System.Boolean::ToString(class [mscorlib]System.IFormatProvider)
0x15cae  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x15cb3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x15cb8  pop
0x15cb9  ldloc.0
0x15cba  ldstr    asc_7CB8A// ";"
0x15cbf  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x15cc4  pop
0x15cc5  ldloc.0
0x15cc6  ldstr    aTaguiIsspanter_0// "tagUI['IsSpanTermStores'] = "
0x15ccb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x15cd0  pop
0x15cd1  ldloc.0
0x15cd2  ldarg.0
0x15cd3  call     instance bool Microsoft.SharePoint.Taxonomy.TaxonomyWebTaggingControl::get_IsSpanTermStores()
0x15cd8  stloc.s  7
0x15cda  ldloca.s 7
0x15cdc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15ce1  call     instance string [mscorlib]System.Boolean::ToString(class [mscorlib]System.IFormatProvider)
0x15ce6  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x15ceb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x15cf0  pop
0x15cf1  ldloc.0
0x15cf2  ldstr    asc_7CB8A// ";"
0x15cf7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x15cfc  pop
0x15cfd  ldloc.0
0x15cfe  ldstr    aTaguiIsignoref// "tagUI['IsIgnoreFormatting'] = "
0x15d03  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x15d08  pop
0x15d09  ldloc.0
0x15d0a  ldarg.0
0x15d0b  call     instance bool Microsoft.SharePoint.Taxonomy.TaxonomyWebTaggingControl::get_IsIgnoreFormatting()
0x15d10  stloc.s  8
0x15d12  ldloca.s 8
0x15d14  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15d19  call     instance string [mscorlib]System.Boolean::ToString(class [mscorlib]System.IFormatProvider)
0x15d1e  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x15d23  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x15d28  pop
0x15d29  ldloc.0
0x15d2a  ldstr    asc_7CB8A// ";"
0x15d2f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x15d34  pop
0x15d35  ldloc.0
0x15d36  ldstr    aTaguiIsinclude// "tagUI['IsIncludeDeprecated'] = "
0x15d3b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x15d40  pop
0x15d41  ldloc.0
0x15d42  ldarg.0
0x15d43  call     instance bool Microsoft.SharePoint.Taxonomy.TaxonomyWebTaggingControl::get_IsIncludeDeprecated()
0x15d48  stloc.s  9
0x15d4a  ldloca.s 9
0x15d4c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15d51  call     instance string [mscorlib]System.Boolean::ToString(class [mscorlib]System.IFormatProvider)
0x15d56  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x15d5b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
  ... truncated ...
```
