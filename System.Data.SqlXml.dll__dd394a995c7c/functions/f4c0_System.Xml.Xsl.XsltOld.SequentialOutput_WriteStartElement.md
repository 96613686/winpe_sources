# System.Xml.Xsl.XsltOld.SequentialOutput::WriteStartElement

- ea: `0xf4c0`
- end: `0xf67f`
- name: `System.Xml.Xsl.XsltOld.SequentialOutput::WriteStartElement`
- size: `447`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config`

## callers

- `0xfaf0`

## callees

- `0x5330`
- `0x5350`
- `0x5370`
- `0x54b0`
- `0x54c0`
- `0x54d0`
- `0x54e0`
- `0x9720`
- `0x9740`
- `0xbcc0`
- `0xbce0`
- `0xbde0`
- `0xdf70`
- `0xdf80`
- `0xdf90`
- `0xdfa0`
- `0xf4c0`
- `0xf750`
- `0xfca0`
- `0xff40`
- `0x10050`
- `0x100c0`
- `0x100d0`
- `0x13080`
- `0x130a0`
- `0x130e0`

## pseudocode

```c

```

## disassembly

```asm
0xf4c0  ldarg.1
0xf4c1  callvirt instance class System.Xml.Xsl.XsltOld.BuilderInfo System.Xml.Xsl.XsltOld.RecordBuilder::get_MainNode()
0xf4c6  stloc.0
0xf4c7  ldnull
0xf4c8  stloc.1
0xf4c9  ldarg.0
0xf4ca  ldfld    bool System.Xml.Xsl.XsltOld.SequentialOutput::isHtmlOutput
0xf4cf  brfalse.s loc_F519
0xf4d1  ldloc.0
0xf4d2  callvirt instance string System.Xml.Xsl.XsltOld.BuilderInfo::get_Prefix()
0xf4d7  callvirt instance int32 [mscorlib]System.String::get_Length()
0xf4dc  brtrue   loc_F563
0xf4e1  ldloc.0
0xf4e2  ldfld    class System.Xml.Xsl.XsltOld.HtmlElementProps System.Xml.Xsl.XsltOld.BuilderInfo::htmlProps
0xf4e7  stloc.1
0xf4e8  ldloc.1
0xf4e9  brtrue.s loc_F4FF
0xf4eb  ldloc.0
0xf4ec  ldfld    bool System.Xml.Xsl.XsltOld.BuilderInfo::search
0xf4f1  brfalse.s loc_F4FF
0xf4f3  ldloc.0
0xf4f4  callvirt instance string System.Xml.Xsl.XsltOld.BuilderInfo::get_LocalName()
0xf4f9  call     class System.Xml.Xsl.XsltOld.HtmlElementProps System.Xml.Xsl.XsltOld.HtmlElementProps::GetProps(string name)
0xf4fe  stloc.1
0xf4ff  ldarg.1
0xf500  callvirt instance class System.Xml.Xsl.XsltOld.OutputScopeManager System.Xml.Xsl.XsltOld.RecordBuilder::get_Manager()
0xf505  callvirt instance class System.Xml.Xsl.XsltOld.OutputScope System.Xml.Xsl.XsltOld.OutputScopeManager::get_CurrentElementScope()
0xf50a  ldloc.1
0xf50b  callvirt instance void System.Xml.Xsl.XsltOld.OutputScope::set_HtmlElementProps(class System.Xml.Xsl.XsltOld.HtmlElementProps value)
0xf510  ldloc.0
0xf511  ldc.i4.0
0xf512  callvirt instance void System.Xml.Xsl.XsltOld.BuilderInfo::set_IsEmptyTag(bool value)
0xf517  br.s     loc_F563
0xf519  ldarg.0
0xf51a  ldfld    bool System.Xml.Xsl.XsltOld.SequentialOutput::isXmlOutput
0xf51f  brfalse.s loc_F563
0xf521  ldloc.0
0xf522  callvirt instance int32 System.Xml.Xsl.XsltOld.BuilderInfo::get_Depth()
0xf527  brtrue.s loc_F563
0xf529  ldarg.0
0xf52a  ldfld    bool System.Xml.Xsl.XsltOld.SequentialOutput::secondRoot
0xf52f  brfalse.s loc_F55C
0xf531  ldarg.0
0xf532  ldfld    class System.Xml.Xsl.XsltOld.XsltOutput System.Xml.Xsl.XsltOld.SequentialOutput::output
0xf537  callvirt instance string System.Xml.Xsl.XsltOld.XsltOutput::get_DoctypeSystem()
0xf53c  brtrue.s loc_F54B
0xf53e  ldarg.0
0xf53f  ldfld    class System.Xml.Xsl.XsltOld.XsltOutput System.Xml.Xsl.XsltOld.SequentialOutput::output
0xf544  callvirt instance bool System.Xml.Xsl.XsltOld.XsltOutput::get_Standalone()
0xf549  brfalse.s loc_F55C
0xf54b  ldstr    aXsltMultiplero// "Xslt_MultipleRoots"
0xf550  ldc.i4.0
0xf551  newarr   [mscorlib]System.String
0xf556  call     class [System.Xml]System.Xml.Xsl.XsltException [System.Xml]System.Xml.Xsl.XsltException::Create(string, string[])
0xf55b  throw
0xf55c  ldarg.0
0xf55d  ldc.i4.1
0xf55e  stfld    bool System.Xml.Xsl.XsltOld.SequentialOutput::secondRoot
0xf563  ldarg.0
0xf564  ldfld    bool System.Xml.Xsl.XsltOld.SequentialOutput::outputDoctype
0xf569  brfalse.s loc_F579
0xf56b  ldarg.0
0xf56c  ldloc.0
0xf56d  call     instance void System.Xml.Xsl.XsltOld.SequentialOutput::WriteDoctype(class System.Xml.Xsl.XsltOld.BuilderInfo mainNode)
0xf572  ldarg.0
0xf573  ldc.i4.0
0xf574  stfld    bool System.Xml.Xsl.XsltOld.SequentialOutput::outputDoctype
0xf579  ldarg.0
0xf57a  ldfld    class [mscorlib]System.Collections.Hashtable System.Xml.Xsl.XsltOld.SequentialOutput::cdataElements
0xf57f  brfalse.s loc_F5B8
0xf581  ldarg.0
0xf582  ldfld    class [mscorlib]System.Collections.Hashtable System.Xml.Xsl.XsltOld.SequentialOutput::cdataElements
0xf587  ldloc.0
0xf588  callvirt instance string System.Xml.Xsl.XsltOld.BuilderInfo::get_LocalName()
0xf58d  ldloc.0
0xf58e  callvirt instance string System.Xml.Xsl.XsltOld.BuilderInfo::get_NamespaceURI()
0xf593  newobj   instance void [System.Xml]System.Xml.XmlQualifiedName::.ctor(string, string)
0xf598  callvirt instance bool [mscorlib]System.Collections.Hashtable::Contains(object)
0xf59d  brfalse.s loc_F5B8
0xf59f  ldarg.0
0xf5a0  ldfld    bool System.Xml.Xsl.XsltOld.SequentialOutput::isXmlOutput
0xf5a5  brfalse.s loc_F5B8
0xf5a7  ldarg.1
0xf5a8  callvirt instance class System.Xml.Xsl.XsltOld.OutputScopeManager System.Xml.Xsl.XsltOld.RecordBuilder::get_Manager()
0xf5ad  callvirt instance class System.Xml.Xsl.XsltOld.OutputScope System.Xml.Xsl.XsltOld.OutputScopeManager::get_CurrentElementScope()
0xf5b2  ldc.i4.1
0xf5b3  callvirt instance void System.Xml.Xsl.XsltOld.OutputScope::set_ToCData(bool value)
0xf5b8  ldarg.0
0xf5b9  ldarg.1
0xf5ba  call     instance void System.Xml.Xsl.XsltOld.SequentialOutput::Indent(class System.Xml.Xsl.XsltOld.RecordBuilder record)
0xf5bf  ldarg.0
0xf5c0  ldc.i4.s 0x3C
0xf5c2  callvirt instance void System.Xml.Xsl.XsltOld.SequentialOutput::Write(char outputChar)
0xf5c7  ldarg.0
0xf5c8  ldloc.0
0xf5c9  callvirt instance string System.Xml.Xsl.XsltOld.BuilderInfo::get_Prefix()
0xf5ce  ldloc.0
0xf5cf  callvirt instance string System.Xml.Xsl.XsltOld.BuilderInfo::get_LocalName()
0xf5d4  call     instance void System.Xml.Xsl.XsltOld.SequentialOutput::WriteName(string prefix, string name)
0xf5d9  ldarg.0
0xf5da  ldarg.1
0xf5db  callvirt instance class [mscorlib]System.Collections.ArrayList System.Xml.Xsl.XsltOld.RecordBuilder::get_AttributeList()
0xf5e0  ldarg.1
0xf5e1  callvirt instance int32 System.Xml.Xsl.XsltOld.RecordBuilder::get_AttributeCount()
0xf5e6  ldloc.1
0xf5e7  call     instance void System.Xml.Xsl.XsltOld.SequentialOutput::WriteAttributes(class [mscorlib]System.Collections.ArrayList list, int32 count, class System.Xml.Xsl.XsltOld.HtmlElementProps htmlElementsProps)
0xf5ec  ldloc.0
0xf5ed  callvirt instance bool System.Xml.Xsl.XsltOld.BuilderInfo::get_IsEmptyTag()
0xf5f2  brfalse.s loc_F601
0xf5f4  ldarg.0
0xf5f5  ldstr    asc_59C9A// " />"
0xf5fa  callvirt instance void System.Xml.Xsl.XsltOld.SequentialOutput::Write(string outputText)
0xf5ff  br.s     loc_F609
0xf601  ldarg.0
0xf602  ldc.i4.s 0x3E
0xf604  callvirt instance void System.Xml.Xsl.XsltOld.SequentialOutput::Write(char outputChar)
0xf609  ldloc.1
0xf60a  brfalse.s loc_F67E
0xf60c  ldloc.1
0xf60d  callvirt instance bool System.Xml.Xsl.XsltOld.HtmlElementProps::get_Head()
0xf612  brfalse.s loc_F67E
0xf614  ldloc.0
0xf615  dup
0xf616  callvirt instance int32 System.Xml.Xsl.XsltOld.BuilderInfo::get_Depth()
0xf61b  stloc.2
0xf61c  ldloc.2
0xf61d  ldc.i4.1
0xf61e  add
0xf61f  callvirt instance void System.Xml.Xsl.XsltOld.BuilderInfo::set_Depth(int32 value)
0xf624  ldarg.0
0xf625  ldarg.1
0xf626  call     instance void System.Xml.Xsl.XsltOld.SequentialOutput::Indent(class System.Xml.Xsl.XsltOld.RecordBuilder record)
0xf62b  ldloc.0
0xf62c  dup
0xf62d  callvirt instance int32 System.Xml.Xsl.XsltOld.BuilderInfo::get_Depth()
0xf632  stloc.2
0xf633  ldloc.2
0xf634  ldc.i4.1
0xf635  sub
0xf636  callvirt instance void System.Xml.Xsl.XsltOld.BuilderInfo::set_Depth(int32 value)
0xf63b  ldarg.0
0xf63c  ldstr    aMetaHttpEquivC// "<META http-equiv=\"Content-Type\" conte"...
0xf641  callvirt instance void System.Xml.Xsl.XsltOld.SequentialOutput::Write(string outputText)
0xf646  ldarg.0
0xf647  ldarg.0
0xf648  ldfld    class System.Xml.Xsl.XsltOld.XsltOutput System.Xml.Xsl.XsltOld.SequentialOutput::output
0xf64d  callvirt instance string System.Xml.Xsl.XsltOld.XsltOutput::get_MediaType()
0xf652  callvirt instance void System.Xml.Xsl.XsltOld.SequentialOutput::Write(string outputText)
0xf657  ldarg.0
0xf658  ldstr    aCharset// "; charset="
0xf65d  callvirt instance void System.Xml.Xsl.XsltOld.SequentialOutput::Write(string outputText)
0xf662  ldarg.0
0xf663  ldarg.0
0xf664  ldfld    class [mscorlib]System.Text.Encoding System.Xml.Xsl.XsltOld.SequentialOutput::encoding
0xf669  callvirt instance string [mscorlib]System.Text.Encoding::get_WebName()
0xf66e  callvirt instance void System.Xml.Xsl.XsltOld.SequentialOutput::Write(string outputText)
0xf673  ldarg.0
0xf674  ldstr    asc_59D0C// "\">"
0xf679  callvirt instance void System.Xml.Xsl.XsltOld.SequentialOutput::Write(string outputText)
0xf67e  ret
```
