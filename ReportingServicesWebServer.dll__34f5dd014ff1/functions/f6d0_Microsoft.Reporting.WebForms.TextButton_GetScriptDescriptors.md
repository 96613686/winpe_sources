# Microsoft.Reporting.WebForms.TextButton::GetScriptDescriptors

- ea: `0xf6d0`
- end: `0xf7cb`
- name: `Microsoft.Reporting.WebForms.TextButton::GetScriptDescriptors`
- size: `251`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0xf6d0`
- `0x17810`
- `0x17820`
- `0x17830`
- `0x179d0`
- `0x179e0`

## string_xrefs

- `0xf708`: `ActiveLinkStyle`
- `0xf71e`: `DisabledLinkStyle`
- `0xf736`: `ActiveLinkColor`
- `0xf751`: `DisabledLinkColor`
- `0xf76c`: `ActiveHoverLinkColor`

## pseudocode

```c

```

## disassembly

```asm
0xf6d0  ldstr    aMicrosoftRepor_41// "Microsoft.Reporting.WebFormsClient._Tex"...
0xf6d5  ldarg.0
0xf6d6  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0xf6db  newobj   instance void [System.Web.Extensions]System.Web.UI.ScriptControlDescriptor::.ctor(string, string)
0xf6e0  stloc.0
0xf6e1  ldloc.0
0xf6e2  ldstr    aIsactive// "IsActive"
0xf6e7  ldarg.0
0xf6e8  ldfld    bool Microsoft.Reporting.WebForms.TextButton::ShowDisabled
0xf6ed  ldc.i4.0
0xf6ee  ceq
0xf6f0  box      [mscorlib]System.Boolean
0xf6f5  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0xf6fa  ldarg.0
0xf6fb  ldfld    class Microsoft.Reporting.WebForms.IReportViewerStyles Microsoft.Reporting.WebForms.TextButton::m_viewerStyle
0xf700  callvirt instance string Microsoft.Reporting.WebForms.IReportViewerStyles::get_LinkActive()
0xf705  brfalse.s loc_F735
0xf707  ldloc.0
0xf708  ldstr    aActivelinkstyl// "ActiveLinkStyle"
0xf70d  ldarg.0
0xf70e  ldfld    class Microsoft.Reporting.WebForms.IReportViewerStyles Microsoft.Reporting.WebForms.TextButton::m_viewerStyle
0xf713  callvirt instance string Microsoft.Reporting.WebForms.IReportViewerStyles::get_LinkActive()
0xf718  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0xf71d  ldloc.0
0xf71e  ldstr    aDisabledlinkst// "DisabledLinkStyle"
0xf723  ldarg.0
0xf724  ldfld    class Microsoft.Reporting.WebForms.IReportViewerStyles Microsoft.Reporting.WebForms.TextButton::m_viewerStyle
0xf729  callvirt instance string Microsoft.Reporting.WebForms.IReportViewerStyles::get_LinkDisabled()
0xf72e  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0xf733  br.s     loc_F786
0xf735  ldloc.0
0xf736  ldstr    aActivelinkcolo// "ActiveLinkColor"
0xf73b  ldarg.0
0xf73c  ldfld    class Microsoft.Reporting.WebForms.IReportViewerStyles Microsoft.Reporting.WebForms.TextButton::m_viewerStyle
0xf741  callvirt instance valuetype [System.Drawing]System.Drawing.Color Microsoft.Reporting.WebForms.IReportViewerStyles::get_LinkActiveColor()
0xf746  call     string [System.Drawing]System.Drawing.ColorTranslator::ToHtml(valuetype [System.Drawing]System.Drawing.Color)
0xf74b  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0xf750  ldloc.0
0xf751  ldstr    aDisabledlinkco// "DisabledLinkColor"
0xf756  ldarg.0
0xf757  ldfld    class Microsoft.Reporting.WebForms.IReportViewerStyles Microsoft.Reporting.WebForms.TextButton::m_viewerStyle
0xf75c  callvirt instance valuetype [System.Drawing]System.Drawing.Color Microsoft.Reporting.WebForms.IReportViewerStyles::get_LinkDisabledColor()
0xf761  call     string [System.Drawing]System.Drawing.ColorTranslator::ToHtml(valuetype [System.Drawing]System.Drawing.Color)
0xf766  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0xf76b  ldloc.0
0xf76c  ldstr    aActivehoverlin// "ActiveHoverLinkColor"
0xf771  ldarg.0
0xf772  ldfld    class Microsoft.Reporting.WebForms.IReportViewerStyles Microsoft.Reporting.WebForms.TextButton::m_viewerStyle
0xf777  callvirt instance valuetype [System.Drawing]System.Drawing.Color Microsoft.Reporting.WebForms.IReportViewerStyles::get_LinkActiveHoverColor()
0xf77c  call     string [System.Drawing]System.Drawing.ColorTranslator::ToHtml(valuetype [System.Drawing]System.Drawing.Color)
0xf781  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddProperty(string, object)
0xf786  ldarg.0
0xf787  ldfld    string Microsoft.Reporting.WebForms.TextButton::m_clientSideClickScript
0xf78c  dup
0xf78d  brtrue.s loc_F7A2
0xf78f  pop
0xf790  ldarg.0
0xf791  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0xf796  callvirt instance class [System.Web]System.Web.UI.ClientScriptManager [System.Web]System.Web.UI.Page::get_ClientScript()
0xf79b  ldarg.0
0xf79c  ldnull
0xf79d  callvirt instance string [System.Web]System.Web.UI.ClientScriptManager::GetPostBackEventReference(class [System.Web]System.Web.UI.Control, string)
0xf7a2  stloc.1
0xf7a3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf7a8  ldstr    aFunction0// "function(){{{0};}}"
0xf7ad  ldloc.1
0xf7ae  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0xf7b3  stloc.2
0xf7b4  ldloc.0
0xf7b5  ldstr    aOnclickscript// "OnClickScript"
0xf7ba  ldloc.2
0xf7bb  callvirt instance void [System.Web.Extensions]System.Web.UI.ScriptComponentDescriptor::AddScriptProperty(string, string)
0xf7c0  ldc.i4.1
0xf7c1  newarr   [System.Web.Extensions]System.Web.UI.ScriptDescriptor
0xf7c6  dup
0xf7c7  ldc.i4.0
0xf7c8  ldloc.0
0xf7c9  stelem.ref
0xf7ca  ret
```
