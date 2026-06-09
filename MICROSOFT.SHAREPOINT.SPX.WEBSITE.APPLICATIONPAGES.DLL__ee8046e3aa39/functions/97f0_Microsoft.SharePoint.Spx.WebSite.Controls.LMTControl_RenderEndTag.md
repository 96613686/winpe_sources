# Microsoft.SharePoint.Spx.WebSite.Controls.LMTControl::RenderEndTag

- ea: `0x97f0`
- end: `0x987d`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.LMTControl::RenderEndTag`
- size: `141`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x7b20`
- `0x97f0`

## string_xrefs

- `0x97f3`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x97f0  ldarg.1
0x97f1  brtrue.s loc_97FE
0x97f3  ldstr    aWriter// "writer"
0x97f8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x97fd  throw
0x97fe  ldsfld   valuetype [System.Web]System.Web.UI.WebControls.Unit [System.Web]System.Web.UI.WebControls.Unit::Empty
0x9803  stloc.0
0x9804  ldloca.s 0
0x9806  ldarg.0
0x9807  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.Unit [System.Web]System.Web.UI.WebControls.WebControl::get_Width()
0x980c  box      [System.Web]System.Web.UI.WebControls.Unit
0x9811  constrained. [System.Web]System.Web.UI.WebControls.Unit
0x9817  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x981c  brtrue.s loc_9875
0x981e  ldsfld   valuetype [System.Web]System.Web.UI.WebControls.Unit [System.Web]System.Web.UI.WebControls.Unit::Empty
0x9823  stloc.1
0x9824  ldloca.s 1
0x9826  ldarg.0
0x9827  callvirt instance valuetype [System.Web]System.Web.UI.WebControls.Unit [System.Web]System.Web.UI.WebControls.WebControl::get_Height()
0x982c  box      [System.Web]System.Web.UI.WebControls.Unit
0x9831  constrained. [System.Web]System.Web.UI.WebControls.Unit
0x9837  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x983c  brtrue.s loc_9875
0x983e  ldarg.0
0x983f  call     instance bool [System.Web]System.Web.UI.Control::get_DesignMode()
0x9844  brtrue.s loc_9875
0x9846  ldarg.0
0x9847  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x984c  brfalse.s loc_9875
0x984e  ldarg.0
0x984f  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x9854  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x9859  callvirt instance class [System.Web]System.Web.HttpBrowserCapabilities [System.Web]System.Web.HttpRequest::get_Browser()
0x985e  callvirt instance string [System.Web]System.Web.Configuration.HttpCapabilitiesBase::get_Browser()
0x9863  ldstr    aFirefox// "Firefox"
0x9868  callvirt instance bool [mscorlib]System.String::Contains(string)
0x986d  brfalse.s loc_9875
0x986f  ldarg.1
0x9870  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x9875  ldarg.0
0x9876  ldarg.1
0x9877  call     instance void Microsoft.SharePoint.Spx.WebSite.Controls.FloatableControl::RenderEndTag(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x987c  ret
```
