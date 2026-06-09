# System.Xml.Xsl.XsltOld.CallTemplateAction::Execute

- ea: `0x5630`
- end: `0x56c9`
- name: `System.Xml.Xsl.XsltOld.CallTemplateAction::Execute`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x545d0`

## callees

- `0x4160`
- `0x4170`
- `0x41d0`
- `0x43e0`
- `0x5630`
- `0xc490`
- `0xcb10`
- `0xcb20`
- `0xd400`
- `0x10e80`

## string_xrefs

- `0x56a3`: `Xslt_InvalidCallTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x5630  ldarg.2
0x5631  callvirt instance int32 System.Xml.Xsl.XsltOld.ActionFrame::get_State()
0x5636  stloc.1
0x5637  ldloc.1
0x5638  switch   loc_564E, loc_56C8, loc_5679, loc_56C2
0x564d  ret
0x564e  ldarg.1
0x564f  callvirt instance void System.Xml.Xsl.XsltOld.Processor::ResetParams()
0x5654  ldarg.0
0x5655  ldfld    class [mscorlib]System.Collections.ArrayList System.Xml.Xsl.XsltOld.ContainerAction::containedActions
0x565a  brfalse.s loc_5679
0x565c  ldarg.0
0x565d  ldfld    class [mscorlib]System.Collections.ArrayList System.Xml.Xsl.XsltOld.ContainerAction::containedActions
0x5662  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x5667  ldc.i4.0
0x5668  ble.s    loc_5679
0x566a  ldarg.1
0x566b  ldarg.2
0x566c  callvirt instance void System.Xml.Xsl.XsltOld.Processor::PushActionFrame(class System.Xml.Xsl.XsltOld.ActionFrame container)
0x5671  ldarg.2
0x5672  ldc.i4.2
0x5673  callvirt instance void System.Xml.Xsl.XsltOld.ActionFrame::set_State(int32 value)
0x5678  ret
0x5679  ldarg.1
0x567a  callvirt instance class System.Xml.Xsl.XsltOld.Stylesheet System.Xml.Xsl.XsltOld.Processor::get_Stylesheet()
0x567f  ldarg.0
0x5680  ldfld    class [System.Xml]System.Xml.XmlQualifiedName System.Xml.Xsl.XsltOld.CallTemplateAction::name
0x5685  callvirt instance class System.Xml.Xsl.XsltOld.TemplateAction System.Xml.Xsl.XsltOld.Stylesheet::FindTemplate(class [System.Xml]System.Xml.XmlQualifiedName name)
0x568a  stloc.0
0x568b  ldloc.0
0x568c  brfalse.s loc_56A3
0x568e  ldarg.2
0x568f  ldc.i4.3
0x5690  callvirt instance void System.Xml.Xsl.XsltOld.ActionFrame::set_State(int32 value)
0x5695  ldarg.1
0x5696  ldloc.0
0x5697  ldarg.2
0x5698  callvirt instance class [System.Xml]System.Xml.XPath.XPathNodeIterator System.Xml.Xsl.XsltOld.ActionFrame::get_NodeSet()
0x569d  callvirt instance void System.Xml.Xsl.XsltOld.Processor::PushActionFrame(class System.Xml.Xsl.XsltOld.Action action, class [System.Xml]System.Xml.XPath.XPathNodeIterator nodeSet)
0x56a2  ret
0x56a3  ldstr    aXsltInvalidcal// "Xslt_InvalidCallTemplate"
0x56a8  ldc.i4.1
0x56a9  newarr   [mscorlib]System.String
0x56ae  dup
0x56af  ldc.i4.0
0x56b0  ldarg.0
0x56b1  ldfld    class [System.Xml]System.Xml.XmlQualifiedName System.Xml.Xsl.XsltOld.CallTemplateAction::name
0x56b6  callvirt instance string [mscorlib]System.Object::ToString()
0x56bb  stelem.ref
0x56bc  call     class [System.Xml]System.Xml.Xsl.XsltException [System.Xml]System.Xml.Xsl.XsltException::Create(string, string[])
0x56c1  throw
0x56c2  ldarg.2
0x56c3  callvirt instance void System.Xml.Xsl.XsltOld.ActionFrame::Finished()
0x56c8  ret
```
