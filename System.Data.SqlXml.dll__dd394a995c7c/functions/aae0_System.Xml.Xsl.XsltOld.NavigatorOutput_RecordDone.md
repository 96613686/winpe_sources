# System.Xml.Xsl.XsltOld.NavigatorOutput::RecordDone

- ea: `0xaae0`
- end: `0xacb8`
- name: `System.Xml.Xsl.XsltOld.NavigatorOutput::RecordDone`
- size: `472`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config`

## callees

- `0x5330`
- `0x5350`
- `0x5370`
- `0x5390`
- `0x5490`
- `0x54d0`
- `0xaae0`
- `0xdf70`
- `0xdf80`
- `0xdf90`
- `0xe1f0`

## string_xrefs

- `0xab8f`: `http://www.w3.org/2000/xmlns/`

## pseudocode

```c

```

## disassembly

```asm
0xaae0  ldarg.1
0xaae1  callvirt instance class System.Xml.Xsl.XsltOld.BuilderInfo System.Xml.Xsl.XsltOld.RecordBuilder::get_MainNode()
0xaae6  stloc.0
0xaae7  ldarg.0
0xaae8  ldarg.0
0xaae9  ldfld    int32 System.Xml.Xsl.XsltOld.NavigatorOutput::documentIndex
0xaaee  ldc.i4.1
0xaaef  add
0xaaf0  stfld    int32 System.Xml.Xsl.XsltOld.NavigatorOutput::documentIndex
0xaaf5  ldloc.0
0xaaf6  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType System.Xml.Xsl.XsltOld.BuilderInfo::get_NodeType()
0xaafb  stloc.1
0xaafc  ldloc.1
0xaafd  ldc.i4.1
0xaafe  sub
0xaaff  switch   loc_AB45, loc_ACB0, loc_AC41, loc_ACB0, loc_ACB0, loc_ACB0, loc_AC67, loc_AC80, loc_ACB0, loc_ACB0, loc_ACB0, loc_ACB0, loc_ACB0, loc_AC54, loc_AC93
0xab40  br       loc_ACB0
0xab45  ldarg.0
0xab46  ldfld    class [System.Xml]System.Xml.XmlRawWriter System.Xml.Xsl.XsltOld.NavigatorOutput::wr
0xab4b  ldloc.0
0xab4c  callvirt instance string System.Xml.Xsl.XsltOld.BuilderInfo::get_Prefix()
0xab51  ldloc.0
0xab52  callvirt instance string System.Xml.Xsl.XsltOld.BuilderInfo::get_LocalName()
0xab57  ldloc.0
0xab58  callvirt instance string System.Xml.Xsl.XsltOld.BuilderInfo::get_NamespaceURI()
0xab5d  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string, string)
0xab62  ldc.i4.0
0xab63  stloc.2
0xab64  br       loc_AC00
0xab69  ldarg.0
0xab6a  ldarg.0
0xab6b  ldfld    int32 System.Xml.Xsl.XsltOld.NavigatorOutput::documentIndex
0xab70  ldc.i4.1
0xab71  add
0xab72  stfld    int32 System.Xml.Xsl.XsltOld.NavigatorOutput::documentIndex
0xab77  ldarg.1
0xab78  callvirt instance class [mscorlib]System.Collections.ArrayList System.Xml.Xsl.XsltOld.RecordBuilder::get_AttributeList()
0xab7d  ldloc.2
0xab7e  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0xab83  castclass System.Xml.Xsl.XsltOld.BuilderInfo
0xab88  stloc.3
0xab89  ldloc.3
0xab8a  callvirt instance string System.Xml.Xsl.XsltOld.BuilderInfo::get_NamespaceURI()
0xab8f  ldstr    aHttpWwwW3Org20_1// "http://www.w3.org/2000/xmlns/"
0xab94  call     bool [mscorlib]System.String::op_Equality(string, string)
0xab99  brfalse.s loc_ABD9
0xab9b  ldloc.3
0xab9c  callvirt instance string System.Xml.Xsl.XsltOld.BuilderInfo::get_Prefix()
0xaba1  callvirt instance int32 [mscorlib]System.String::get_Length()
0xaba6  brtrue.s loc_ABC0
0xaba8  ldarg.0
0xaba9  ldfld    class [System.Xml]System.Xml.XmlRawWriter System.Xml.Xsl.XsltOld.NavigatorOutput::wr
0xabae  ldsfld   string [mscorlib]System.String::Empty
0xabb3  ldloc.3
0xabb4  callvirt instance string System.Xml.Xsl.XsltOld.BuilderInfo::get_Value()
0xabb9  callvirt instance void [System.Xml]System.Xml.XmlRawWriter::WriteNamespaceDeclaration(string, string)
0xabbe  br.s     loc_ABFC
0xabc0  ldarg.0
0xabc1  ldfld    class [System.Xml]System.Xml.XmlRawWriter System.Xml.Xsl.XsltOld.NavigatorOutput::wr
0xabc6  ldloc.3
0xabc7  callvirt instance string System.Xml.Xsl.XsltOld.BuilderInfo::get_LocalName()
0xabcc  ldloc.3
0xabcd  callvirt instance string System.Xml.Xsl.XsltOld.BuilderInfo::get_Value()
0xabd2  callvirt instance void [System.Xml]System.Xml.XmlRawWriter::WriteNamespaceDeclaration(string, string)
0xabd7  br.s     loc_ABFC
0xabd9  ldarg.0
0xabda  ldfld    class [System.Xml]System.Xml.XmlRawWriter System.Xml.Xsl.XsltOld.NavigatorOutput::wr
0xabdf  ldloc.3
0xabe0  callvirt instance string System.Xml.Xsl.XsltOld.BuilderInfo::get_Prefix()
0xabe5  ldloc.3
0xabe6  callvirt instance string System.Xml.Xsl.XsltOld.BuilderInfo::get_LocalName()
0xabeb  ldloc.3
0xabec  callvirt instance string System.Xml.Xsl.XsltOld.BuilderInfo::get_NamespaceURI()
0xabf1  ldloc.3
0xabf2  callvirt instance string System.Xml.Xsl.XsltOld.BuilderInfo::get_Value()
0xabf7  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0xabfc  ldloc.2
0xabfd  ldc.i4.1
0xabfe  add
0xabff  stloc.2
0xac00  ldloc.2
0xac01  ldarg.1
0xac02  callvirt instance int32 System.Xml.Xsl.XsltOld.RecordBuilder::get_AttributeCount()
0xac07  blt      loc_AB69
0xac0c  ldarg.0
0xac0d  ldfld    class [System.Xml]System.Xml.XmlRawWriter System.Xml.Xsl.XsltOld.NavigatorOutput::wr
0xac12  callvirt instance void [System.Xml]System.Xml.XmlRawWriter::StartElementContent()
0xac17  ldloc.0
0xac18  callvirt instance bool System.Xml.Xsl.XsltOld.BuilderInfo::get_IsEmptyTag()
0xac1d  brfalse  loc_ACB0
0xac22  ldarg.0
0xac23  ldfld    class [System.Xml]System.Xml.XmlRawWriter System.Xml.Xsl.XsltOld.NavigatorOutput::wr
0xac28  ldloc.0
0xac29  callvirt instance string System.Xml.Xsl.XsltOld.BuilderInfo::get_Prefix()
0xac2e  ldloc.0
0xac2f  callvirt instance string System.Xml.Xsl.XsltOld.BuilderInfo::get_LocalName()
0xac34  ldloc.0
0xac35  callvirt instance string System.Xml.Xsl.XsltOld.BuilderInfo::get_NamespaceURI()
0xac3a  callvirt instance void [System.Xml]System.Xml.XmlRawWriter::WriteEndElement(string, string, string)
0xac3f  br.s     loc_ACB0
0xac41  ldarg.0
0xac42  ldfld    class [System.Xml]System.Xml.XmlRawWriter System.Xml.Xsl.XsltOld.NavigatorOutput::wr
0xac47  ldloc.0
0xac48  callvirt instance string System.Xml.Xsl.XsltOld.BuilderInfo::get_Value()
0xac4d  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteString(string)
0xac52  br.s     loc_ACB0
0xac54  ldarg.0
0xac55  ldfld    class [System.Xml]System.Xml.XmlRawWriter System.Xml.Xsl.XsltOld.NavigatorOutput::wr
0xac5a  ldloc.0
0xac5b  callvirt instance string System.Xml.Xsl.XsltOld.BuilderInfo::get_Value()
0xac60  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteString(string)
0xac65  br.s     loc_ACB0
0xac67  ldarg.0
0xac68  ldfld    class [System.Xml]System.Xml.XmlRawWriter System.Xml.Xsl.XsltOld.NavigatorOutput::wr
0xac6d  ldloc.0
0xac6e  callvirt instance string System.Xml.Xsl.XsltOld.BuilderInfo::get_LocalName()
0xac73  ldloc.0
0xac74  callvirt instance string System.Xml.Xsl.XsltOld.BuilderInfo::get_Value()
0xac79  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteProcessingInstruction(string, string)
0xac7e  br.s     loc_ACB0
0xac80  ldarg.0
0xac81  ldfld    class [System.Xml]System.Xml.XmlRawWriter System.Xml.Xsl.XsltOld.NavigatorOutput::wr
0xac86  ldloc.0
0xac87  callvirt instance string System.Xml.Xsl.XsltOld.BuilderInfo::get_Value()
0xac8c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteComment(string)
0xac91  br.s     loc_ACB0
0xac93  ldarg.0
0xac94  ldfld    class [System.Xml]System.Xml.XmlRawWriter System.Xml.Xsl.XsltOld.NavigatorOutput::wr
0xac99  ldloc.0
0xac9a  callvirt instance string System.Xml.Xsl.XsltOld.BuilderInfo::get_Prefix()
0xac9f  ldloc.0
0xaca0  callvirt instance string System.Xml.Xsl.XsltOld.BuilderInfo::get_LocalName()
0xaca5  ldloc.0
0xaca6  callvirt instance string System.Xml.Xsl.XsltOld.BuilderInfo::get_NamespaceURI()
0xacab  callvirt instance void [System.Xml]System.Xml.XmlRawWriter::WriteEndElement(string, string, string)
0xacb0  ldarg.1
0xacb1  callvirt instance void System.Xml.Xsl.XsltOld.RecordBuilder::Reset()
0xacb6  ldc.i4.0
0xacb7  ret
```
