# Microsoft.SharePoint.Spx.WebSite.Controls.SiteInformationControl::RenderEndTag

- ea: `0x133f0`
- end: `0x1345d`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.SiteInformationControl::RenderEndTag`
- size: `109`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x7b20`
- `0x133f0`

## string_xrefs

- `0x133f3`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x133f0  ldarg.1
0x133f1  brtrue.s loc_133FE
0x133f3  ldstr    aWriter// "writer"
0x133f8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x133fd  throw
0x133fe  ldsfld   valuetype [System.Web]System.Web.UI.WebControls.Unit [System.Web]System.Web.UI.WebControls.Unit::Empty
0x13403  stloc.0
0x13404  ldloca.s 0
0x13406  ldarg.0
0x13407  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.Unit [System.Web]System.Web.UI.WebControls.WebControl::get_Width()
0x1340c  box      [System.Web]System.Web.UI.WebControls.Unit
0x13411  constrained. [System.Web]System.Web.UI.WebControls.Unit
0x13417  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x1341c  brtrue.s loc_13455
0x1341e  ldarg.0
0x1341f  call     instance bool [System.Web]System.Web.UI.Control::get_DesignMode()
0x13424  brtrue.s loc_13455
0x13426  ldarg.0
0x13427  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x1342c  brfalse.s loc_13455
0x1342e  ldarg.0
0x1342f  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x13434  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x13439  callvirt instance class [System.Web]System.Web.HttpBrowserCapabilities [System.Web]System.Web.HttpRequest::get_Browser()
0x1343e  callvirt instance string [System.Web]System.Web.Configuration.HttpCapabilitiesBase::get_Browser()
0x13443  ldstr    aFirefox// "Firefox"
0x13448  callvirt instance bool [mscorlib]System.String::Contains(string)
0x1344d  brfalse.s loc_13455
0x1344f  ldarg.1
0x13450  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x13455  ldarg.0
0x13456  ldarg.1
0x13457  call     instance void Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::RenderEndTag(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x1345c  ret
```
