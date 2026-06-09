# Microsoft.SharePoint.Taxonomy.TermProperty::RenderWebPart

- ea: `0x162e0`
- end: `0x163c7`
- name: `Microsoft.SharePoint.Taxonomy.TermProperty::RenderWebPart`
- size: `231`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x16150`
- `0x162e0`
- `0x16430`
- `0x164e0`
- `0x242a0`
- `0x2ad40`

## string_xrefs

- `0x162e1`: `writer`
- `0x16383`: `TermPropertyToolPart_ConfigureShortcut`

## pseudocode

```c

```

## disassembly

```asm
0x162e0  ldarg.1
0x162e1  ldstr    aWriter// "writer"
0x162e6  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x162eb  ldarg.0
0x162ec  ldfld    bool Microsoft.SharePoint.Taxonomy.TermProperty::errorCannotFindTerm
0x162f1  brtrue.s loc_1635E
0x162f3  ldarg.0
0x162f4  ldfld    class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.TermProperty::term
0x162f9  brfalse.s loc_1635E
0x162fb  ldarg.0
0x162fc  call     instance string Microsoft.SharePoint.Taxonomy.TermProperty::get_Property()
0x16301  ldloca.s 0
0x16303  call     valuetype SupportedProperty Microsoft.SharePoint.Taxonomy.TermProperty::ParseSupportedProperty(string property, [out] string& customPropertyKey)
0x16308  stloc.1
0x16309  ldarg.0
0x1630a  ldfld    class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.TermProperty::term
0x1630f  ldloc.1
0x16310  ldloc.0
0x16311  call     string Microsoft.SharePoint.Taxonomy.TermProperty::GetSupportedPropertyValue(class Microsoft.SharePoint.Taxonomy.Term term, valuetype SupportedProperty property, [opt] string customPropertyKey)
0x16316  stloc.2
0x16317  ldloc.2
0x16318  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x1631d  brtrue   loc_163C6
0x16322  ldloc.1
0x16323  ldc.i4.s 0x10
0x16325  bne.un.s loc_16351
0x16327  ldloc.0
0x16328  ldstr    aSysNavCategory// "_Sys_Nav_CategoryImageUrl"
0x1632d  ldc.i4.5
0x1632e  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x16333  brfalse.s loc_16351
0x16335  ldarg.1
0x16336  ldstr    aImgSrc// "<img src=\""
0x1633b  ldloc.2
0x1633c  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPHttpUtility::HtmlEncode(string)
0x16341  ldstr    asc_86DE4// "\" />"
0x16346  call     string [mscorlib]System.String::Concat(string, string, string)
0x1634b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x16350  ret
0x16351  ldarg.1
0x16352  ldloc.2
0x16353  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPHttpUtility::HtmlEncode(string)
0x16358  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1635d  ret
0x1635e  ldarg.0
0x1635f  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x16364  call     bool [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.PageUtility::IsPageCurrentlyInSomeEditMode(class [System.Web]System.Web.UI.Page)
0x16369  brfalse.s loc_163C6
0x1636b  ldarg.0
0x1636c  call     instance class [System.Web]System.Web.UI.WebControls.WebParts.WebPartZoneBase [System.Web]System.Web.UI.WebControls.WebParts.WebPart::get_Zone()
0x16371  brfalse.s loc_163C6
0x16373  ldarg.0
0x16374  call     instance bool [System.Web]System.Web.UI.WebControls.WebParts.WebPart::get_IsStatic()
0x16379  brtrue.s loc_163C6
0x1637b  ldarg.0
0x1637c  call     instance bool [System.Web]System.Web.UI.WebControls.WebParts.WebPart::get_IsStandalone()
0x16381  brtrue.s loc_163C6
0x16383  ldstr    aTermpropertyto// "TermPropertyToolPart_ConfigureShortcut"
0x16388  ldc.i4.2
0x16389  newarr   [mscorlib]System.Object
0x1638e  stloc.s  4
0x16390  ldloc.s  4
0x16392  ldc.i4.0
0x16393  ldstr    aAHrefOnclick// "<a href=\"#\" onclick=\""
0x16398  ldarg.0
0x16399  ldsfld   class [System.Web]System.Web.UI.WebControls.WebParts.WebPartDisplayMode [System.Web]System.Web.UI.WebControls.WebParts.WebPartManager::EditDisplayMode
0x1639e  call     string [Microsoft.SharePoint]Microsoft.SharePoint.WebPartPages.ToolPane::GetShowToolPaneEvent(class [Microsoft.SharePoint]Microsoft.SharePoint.WebPartPages.WebPart, class [System.Web]System.Web.UI.WebControls.WebParts.WebPartDisplayMode)
0x163a3  ldstr    asc_78490// "\">"
0x163a8  call     string [mscorlib]System.String::Concat(string, string, string)
0x163ad  stelem.ref
0x163ae  ldloc.s  4
0x163b0  ldc.i4.1
0x163b1  ldstr    aA// "</a>"
0x163b6  stelem.ref
0x163b7  ldloc.s  4
0x163b9  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x163be  stloc.3
0x163bf  ldarg.1
0x163c0  ldloc.3
0x163c1  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x163c6  ret
```
