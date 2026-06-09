# System.Windows.Annotations.Annotation::ReadXml

- ea: `0x1cf2c0`
- end: `0x1cf4ed`
- name: `System.Windows.Annotations.Annotation::ReadXml`
- size: `557`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x38c70`
- `0x1cf2c0`
- `0x1cf6e0`
- `0x1cf740`
- `0x1cf770`
- `0x247570`

## string_xrefs

- `0x1cf2c3`: `reader`
- `0x1cf432`: `InvalidXmlContent`
- `0x1cf496`: `InvalidXmlContent`

## pseudocode

```c

```

## disassembly

```asm
0x1cf2c0  ldarg.1
0x1cf2c1  brtrue.s loc_1CF2CE
0x1cf2c3  ldstr    aReader// "reader"
0x1cf2c8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1cf2cd  throw
0x1cf2ce  ldc.i4.s 0x10
0x1cf2d0  ldc.i4   0xBD1
0x1cf2d5  call     void [WindowsBase]MS.Utility.EventTrace::EasyTraceEvent(valuetype [WindowsBase]MS.Utility.EventTrace/Keyword, valuetype [WindowsBase]MS.Utility.EventTrace/Event)
0x1cf2da  ldnull
0x1cf2db  stloc.0
0x1cf2dc  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x1cf2e1  stloc.0
0x1cf2e2  ldarg.0
0x1cf2e3  ldarg.1
0x1cf2e4  call     instance void System.Windows.Annotations.Annotation::ReadAttributes(class [System.Xml]System.Xml.XmlReader reader)
0x1cf2e9  ldarg.1
0x1cf2ea  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x1cf2ef  brtrue   loc_1CF4D6
0x1cf2f4  ldarg.1
0x1cf2f5  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x1cf2fa  pop
0x1cf2fb  br       loc_1CF4B4
0x1cf300  ldstr    aAnchors// "Anchors"
0x1cf305  ldarg.1
0x1cf306  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1cf30b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1cf310  brfalse.s loc_1CF373
0x1cf312  ldarg.1
0x1cf313  ldstr    aAnchors// "Anchors"
0x1cf318  call     void System.Windows.Annotations.Annotation::CheckForNonNamespaceAttribute(class [System.Xml]System.Xml.XmlReader reader, string elementName)
0x1cf31d  ldarg.1
0x1cf31e  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x1cf323  brtrue.s loc_1CF367
0x1cf325  ldarg.1
0x1cf326  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x1cf32b  pop
0x1cf32c  br.s     loc_1CF34B
0x1cf32e  call     class MS.Internal.Annotations.Serializer System.Windows.Annotations.Annotation::get_ResourceSerializer()
0x1cf333  ldarg.1
0x1cf334  callvirt instance object MS.Internal.Annotations.Serializer::Deserialize(class [System.Xml]System.Xml.XmlReader reader)
0x1cf339  castclass System.Windows.Annotations.AnnotationResource
0x1cf33e  stloc.1
0x1cf33f  ldarg.0
0x1cf340  ldfld    class MS.Internal.Annotations.AnnotationResourceCollection System.Windows.Annotations.Annotation::_anchors
0x1cf345  ldloc.1
0x1cf346  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class System.Windows.Annotations.AnnotationResource>::Add(var<u1>)
0x1cf34b  ldstr    aAnchors// "Anchors"
0x1cf350  ldarg.1
0x1cf351  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1cf356  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1cf35b  brfalse.s loc_1CF32E
0x1cf35d  ldc.i4.s 0xF
0x1cf35f  ldarg.1
0x1cf360  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x1cf365  bne.un.s loc_1CF32E
0x1cf367  ldarg.1
0x1cf368  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x1cf36d  pop
0x1cf36e  br       loc_1CF4B4
0x1cf373  ldstr    aCargos// "Cargos"
0x1cf378  ldarg.1
0x1cf379  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1cf37e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1cf383  brfalse.s loc_1CF3E6
0x1cf385  ldarg.1
0x1cf386  ldstr    aCargos// "Cargos"
0x1cf38b  call     void System.Windows.Annotations.Annotation::CheckForNonNamespaceAttribute(class [System.Xml]System.Xml.XmlReader reader, string elementName)
0x1cf390  ldarg.1
0x1cf391  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x1cf396  brtrue.s loc_1CF3DA
0x1cf398  ldarg.1
0x1cf399  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x1cf39e  pop
0x1cf39f  br.s     loc_1CF3BE
0x1cf3a1  call     class MS.Internal.Annotations.Serializer System.Windows.Annotations.Annotation::get_ResourceSerializer()
0x1cf3a6  ldarg.1
0x1cf3a7  callvirt instance object MS.Internal.Annotations.Serializer::Deserialize(class [System.Xml]System.Xml.XmlReader reader)
0x1cf3ac  castclass System.Windows.Annotations.AnnotationResource
0x1cf3b1  stloc.2
0x1cf3b2  ldarg.0
0x1cf3b3  ldfld    class MS.Internal.Annotations.AnnotationResourceCollection System.Windows.Annotations.Annotation::_cargos
0x1cf3b8  ldloc.2
0x1cf3b9  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class System.Windows.Annotations.AnnotationResource>::Add(var<u1>)
0x1cf3be  ldstr    aCargos// "Cargos"
0x1cf3c3  ldarg.1
0x1cf3c4  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1cf3c9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1cf3ce  brfalse.s loc_1CF3A1
0x1cf3d0  ldc.i4.s 0xF
0x1cf3d2  ldarg.1
0x1cf3d3  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x1cf3d8  bne.un.s loc_1CF3A1
0x1cf3da  ldarg.1
0x1cf3db  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x1cf3e0  pop
0x1cf3e1  br       loc_1CF4B4
0x1cf3e6  ldstr    aAuthors// "Authors"
0x1cf3eb  ldarg.1
0x1cf3ec  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1cf3f1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1cf3f6  brfalse  loc_1CF496
0x1cf3fb  ldarg.1
0x1cf3fc  ldstr    aAuthors// "Authors"
0x1cf401  call     void System.Windows.Annotations.Annotation::CheckForNonNamespaceAttribute(class [System.Xml]System.Xml.XmlReader reader, string elementName)
0x1cf406  ldarg.1
0x1cf407  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x1cf40c  brtrue.s loc_1CF48D
0x1cf40e  ldarg.1
0x1cf40f  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x1cf414  pop
0x1cf415  br.s     loc_1CF471
0x1cf417  ldstr    aStringauthor// "StringAuthor"
0x1cf41c  ldarg.1
0x1cf41d  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1cf422  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1cf427  brfalse.s loc_1CF432
0x1cf429  ldc.i4.1
0x1cf42a  ldarg.1
0x1cf42b  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x1cf430  beq.s    loc_1CF450
0x1cf432  ldstr    aInvalidxmlcont// "InvalidXmlContent"
0x1cf437  ldc.i4.1
0x1cf438  newarr   [mscorlib]System.Object
0x1cf43d  dup
0x1cf43e  ldc.i4.0
0x1cf43f  ldstr    aAnnotation_0// "Annotation"
0x1cf444  stelem.ref
0x1cf445  call     string System.Windows.SR::Get(string id, object[] args)
0x1cf44a  newobj   instance void [System.Xml]System.Xml.XmlException::.ctor(string)
0x1cf44f  throw
0x1cf450  ldloc.0
0x1cf451  ldarg.1
0x1cf452  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::ReadNode(class [System.Xml]System.Xml.XmlReader)
0x1cf457  stloc.3
0x1cf458  ldarg.1
0x1cf459  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x1cf45e  brtrue.s loc_1CF471
0x1cf460  ldarg.0
0x1cf461  ldfld    class [System]System.Collections.ObjectModel.ObservableCollection`1<string> System.Windows.Annotations.Annotation::_authors
0x1cf466  ldloc.3
0x1cf467  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x1cf46c  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::Add(var<u1>)
0x1cf471  ldstr    aAuthors// "Authors"
0x1cf476  ldarg.1
0x1cf477  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1cf47c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1cf481  brfalse.s loc_1CF417
0x1cf483  ldc.i4.s 0xF
0x1cf485  ldarg.1
0x1cf486  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x1cf48b  bne.un.s loc_1CF417
0x1cf48d  ldarg.1
0x1cf48e  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x1cf493  pop
0x1cf494  br.s     loc_1CF4B4
0x1cf496  ldstr    aInvalidxmlcont// "InvalidXmlContent"
0x1cf49b  ldc.i4.1
0x1cf49c  newarr   [mscorlib]System.Object
0x1cf4a1  dup
0x1cf4a2  ldc.i4.0
0x1cf4a3  ldstr    aAnnotation_0// "Annotation"
0x1cf4a8  stelem.ref
0x1cf4a9  call     string System.Windows.SR::Get(string id, object[] args)
0x1cf4ae  newobj   instance void [System.Xml]System.Xml.XmlException::.ctor(string)
0x1cf4b3  throw
0x1cf4b4  ldc.i4.s 0xF
0x1cf4b6  ldarg.1
0x1cf4b7  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x1cf4bc  bne.un   loc_1CF300
0x1cf4c1  ldstr    aAnnotation_0// "Annotation"
0x1cf4c6  ldarg.1
0x1cf4c7  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1cf4cc  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1cf4d1  brfalse  loc_1CF300
0x1cf4d6  ldarg.1
0x1cf4d7  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x1cf4dc  pop
0x1cf4dd  leave.s  loc_1CF4EC
0x1cf4df  ldc.i4.s 0x10
0x1cf4e1  ldc.i4   0xBD2
0x1cf4e6  call     void [WindowsBase]MS.Utility.EventTrace::EasyTraceEvent(valuetype [WindowsBase]MS.Utility.EventTrace/Keyword, valuetype [WindowsBase]MS.Utility.EventTrace/Event)
0x1cf4eb  endfinally
0x1cf4ec  ret
```
