# System.Web.UI.UpdatePanel::RenderChildren

- ea: `0x19be0`
- end: `0x19c77`
- name: `System.Web.UI.UpdatePanel::RenderChildren`
- size: `151`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x10c20`
- `0x198b0`
- `0x19be0`

## string_xrefs

- `0x19c09`: `updatePanel`

## pseudocode

```c

```

## disassembly

```asm
0x19be0  ldarg.0
0x19be1  ldfld    bool System.Web.UI.UpdatePanel::_asyncPostBackMode
0x19be6  brfalse.s loc_19C26
0x19be8  ldarg.0
0x19be9  ldfld    bool System.Web.UI.UpdatePanel::_rendered
0x19bee  brfalse.s loc_19BF1
0x19bf0  ret
0x19bf1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x19bf6  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.IFormatProvider)
0x19bfb  newobj   instance void [System.Web]System.Web.UI.HtmlTextWriter::.ctor(class [mscorlib]System.IO.TextWriter)
0x19c00  stloc.0
0x19c01  ldarg.0
0x19c02  ldloc.0
0x19c03  call     instance void [System.Web]System.Web.UI.Control::RenderChildren(class [System.Web]System.Web.UI.HtmlTextWriter)
0x19c08  ldarg.1
0x19c09  ldstr    aUpdatepanel// "updatePanel"
0x19c0e  ldarg.0
0x19c0f  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x19c14  ldloc.0
0x19c15  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x19c1a  callvirt instance string [mscorlib]System.Object::ToString()
0x19c1f  call     void System.Web.UI.PageRequestManager::EncodeString(class [mscorlib]System.IO.TextWriter writer, string type, string id, string content)
0x19c24  br.s     loc_19C6F
0x19c26  ldarg.1
0x19c27  ldc.i4.s 0x11
0x19c29  ldarg.0
0x19c2a  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x19c2f  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::AddAttribute(valuetype [System.Web]System.Web.UI.HtmlTextWriterAttribute, string)
0x19c34  ldarg.0
0x19c35  ldfld    class [System.Web]System.Web.UI.AttributeCollection System.Web.UI.UpdatePanel::_attributes
0x19c3a  brfalse.s loc_19C48
0x19c3c  ldarg.0
0x19c3d  ldfld    class [System.Web]System.Web.UI.AttributeCollection System.Web.UI.UpdatePanel::_attributes
0x19c42  ldarg.1
0x19c43  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::AddAttributes(class [System.Web]System.Web.UI.HtmlTextWriter)
0x19c48  ldarg.0
0x19c49  call     instance valuetype System.Web.UI.UpdatePanelRenderMode System.Web.UI.UpdatePanel::get_RenderMode()
0x19c4e  brtrue.s loc_19C5A
0x19c50  ldarg.1
0x19c51  ldc.i4.s 0x19
0x19c53  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x19c58  br.s     loc_19C62
0x19c5a  ldarg.1
0x19c5b  ldc.i4.s 0x4C
0x19c5d  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderBeginTag(valuetype [System.Web]System.Web.UI.HtmlTextWriterTag)
0x19c62  ldarg.0
0x19c63  ldarg.1
0x19c64  call     instance void [System.Web]System.Web.UI.Control::RenderChildren(class [System.Web]System.Web.UI.HtmlTextWriter)
0x19c69  ldarg.1
0x19c6a  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::RenderEndTag()
0x19c6f  ldarg.0
0x19c70  ldc.i4.1
0x19c71  stfld    bool System.Web.UI.UpdatePanel::_rendered
0x19c76  ret
```
