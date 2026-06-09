# System.Xml.XPath.XPathNavigator::BuildSubtree

- ea: `0xf03e0`
- end: `0xf0612`
- name: `System.Xml.XPath.XPathNavigator::BuildSubtree`
- size: `562`
- prototype: ``
- caller_count: `5`
- callee_count: `22`
- tags: `registry_config`

## callers

- `0xefa50`
- `0xefca0`
- `0xefd30`
- `0xefdc0`
- `0xefe50`

## callees

- `0x214b0`
- `0x21500`
- `0x21510`
- `0x21520`
- `0x21540`
- `0x21570`
- `0x21c30`
- `0x21c40`
- `0x21c60`
- `0x21c90`
- `0x21cf0`
- `0x40790`
- `0x407b0`
- `0x407c0`
- `0x40810`
- `0x40840`
- `0x40860`
- `0x40880`
- `0x40890`
- `0x408d0`
- `0x62370`
- `0xf03e0`

## string_xrefs

- `0xf03f4`: `Xml_InvalidOperation`
- `0xf03e0`: `http://www.w3.org/2000/xmlns/`
- `0xf04b4`: `xmlns`
- `0xf04c8`: `xmlns`
- `0xf05ab`: `xmlns`
- `0xf05bf`: `xmlns`
- `0xf03fe`: `reader`

## pseudocode

```c

```

## disassembly

```asm
0xf03e0  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/xmlns/"
0xf03e5  stloc.0
0xf03e6  ldarg.1
0xf03e7  callvirt instance valuetype System.Xml.ReadState System.Xml.XmlReader::get_ReadState()
0xf03ec  stloc.1
0xf03ed  ldloc.1
0xf03ee  brfalse.s loc_F0409
0xf03f0  ldloc.1
0xf03f1  ldc.i4.1
0xf03f2  beq.s    loc_F0409
0xf03f4  ldstr    aXmlInvalidoper// "Xml_InvalidOperation"
0xf03f9  call     string System.Xml.Res::GetString(string name)
0xf03fe  ldstr    aReader// "reader"
0xf0403  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0xf0408  throw
0xf0409  ldc.i4.0
0xf040a  stloc.2
0xf040b  ldloc.1
0xf040c  brtrue.s loc_F041B
0xf040e  ldarg.1
0xf040f  callvirt instance bool System.Xml.XmlReader::Read()
0xf0414  brtrue.s loc_F0417
0xf0416  ret
0xf0417  ldloc.2
0xf0418  ldc.i4.1
0xf0419  add
0xf041a  stloc.2
0xf041b  ldarg.1
0xf041c  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlReader::get_NodeType()
0xf0421  stloc.s  4
0xf0423  ldloc.s  4
0xf0425  switch   loc_F0602, loc_F0477, loc_F058F, loc_F0540, loc_F0540, loc_F0587, loc_F0602, loc_F0573, loc_F0562, loc_F0602, loc_F0602, loc_F0602, loc_F0602, loc_F0551, loc_F0551, loc_F0531, loc_F0602, loc_F0602
0xf0472  br       loc_F0602
0xf0477  ldarg.2
0xf0478  ldarg.1
0xf0479  callvirt instance string System.Xml.XmlReader::get_Prefix()
0xf047e  ldarg.1
0xf047f  callvirt instance string System.Xml.XmlReader::get_LocalName()
0xf0484  ldarg.1
0xf0485  callvirt instance string System.Xml.XmlReader::get_NamespaceURI()
0xf048a  callvirt instance void System.Xml.XmlWriter::WriteStartElement(string prefix, string localName, string ns)
0xf048f  ldarg.1
0xf0490  callvirt instance bool System.Xml.XmlReader::get_IsEmptyElement()
0xf0495  stloc.3
0xf0496  br.s     loc_F050B
0xf0498  ldarg.1
0xf0499  callvirt instance string System.Xml.XmlReader::get_NamespaceURI()
0xf049e  ldloc.0
0xf049f  bne.un.s loc_F04E1
0xf04a1  ldarg.1
0xf04a2  callvirt instance string System.Xml.XmlReader::get_Prefix()
0xf04a7  callvirt instance int32 [mscorlib]System.String::get_Length()
0xf04ac  brtrue.s loc_F04C7
0xf04ae  ldarg.2
0xf04af  ldstr    asc_1284AE// ""
0xf04b4  ldstr    aXmlns// "xmlns"
0xf04b9  ldloc.0
0xf04ba  ldarg.1
0xf04bb  callvirt instance string System.Xml.XmlReader::get_Value()
0xf04c0  callvirt instance void System.Xml.XmlWriter::WriteAttributeString(string prefix, string localName, string ns, string value)
0xf04c5  br.s     loc_F050B
0xf04c7  ldarg.2
0xf04c8  ldstr    aXmlns// "xmlns"
0xf04cd  ldarg.1
0xf04ce  callvirt instance string System.Xml.XmlReader::get_LocalName()
0xf04d3  ldloc.0
0xf04d4  ldarg.1
0xf04d5  callvirt instance string System.Xml.XmlReader::get_Value()
0xf04da  callvirt instance void System.Xml.XmlWriter::WriteAttributeString(string prefix, string localName, string ns, string value)
0xf04df  br.s     loc_F050B
0xf04e1  ldarg.2
0xf04e2  ldarg.1
0xf04e3  callvirt instance string System.Xml.XmlReader::get_Prefix()
0xf04e8  ldarg.1
0xf04e9  callvirt instance string System.Xml.XmlReader::get_LocalName()
0xf04ee  ldarg.1
0xf04ef  callvirt instance string System.Xml.XmlReader::get_NamespaceURI()
0xf04f4  callvirt instance void System.Xml.XmlWriter::WriteStartAttribute(string prefix, string localName, string ns)
0xf04f9  ldarg.2
0xf04fa  ldarg.1
0xf04fb  callvirt instance string System.Xml.XmlReader::get_Value()
0xf0500  callvirt instance void System.Xml.XmlWriter::WriteString(string text)
0xf0505  ldarg.2
0xf0506  callvirt instance void System.Xml.XmlWriter::WriteEndAttribute()
0xf050b  ldarg.1
0xf050c  callvirt instance bool System.Xml.XmlReader::MoveToNextAttribute()
0xf0511  brtrue.s loc_F0498
0xf0513  ldarg.1
0xf0514  callvirt instance bool System.Xml.XmlReader::MoveToElement()
0xf0519  pop
0xf051a  ldloc.3
0xf051b  brfalse.s loc_F0528
0xf051d  ldarg.2
0xf051e  callvirt instance void System.Xml.XmlWriter::WriteEndElement()
0xf0523  br       loc_F0602
0xf0528  ldloc.2
0xf0529  ldc.i4.1
0xf052a  add
0xf052b  stloc.2
0xf052c  br       loc_F0602
0xf0531  ldarg.2
0xf0532  callvirt instance void System.Xml.XmlWriter::WriteFullEndElement()
0xf0537  ldloc.2
0xf0538  ldc.i4.1
0xf0539  sub
0xf053a  stloc.2
0xf053b  br       loc_F0602
0xf0540  ldarg.2
0xf0541  ldarg.1
0xf0542  callvirt instance string System.Xml.XmlReader::get_Value()
0xf0547  callvirt instance void System.Xml.XmlWriter::WriteString(string text)
0xf054c  br       loc_F0602
0xf0551  ldarg.2
0xf0552  ldarg.1
0xf0553  callvirt instance string System.Xml.XmlReader::get_Value()
0xf0558  callvirt instance void System.Xml.XmlWriter::WriteString(string text)
0xf055d  br       loc_F0602
0xf0562  ldarg.2
0xf0563  ldarg.1
0xf0564  callvirt instance string System.Xml.XmlReader::get_Value()
0xf0569  callvirt instance void System.Xml.XmlWriter::WriteComment(string text)
0xf056e  br       loc_F0602
0xf0573  ldarg.2
0xf0574  ldarg.1
0xf0575  callvirt instance string System.Xml.XmlReader::get_LocalName()
0xf057a  ldarg.1
0xf057b  callvirt instance string System.Xml.XmlReader::get_Value()
0xf0580  callvirt instance void System.Xml.XmlWriter::WriteProcessingInstruction(string name, string text)
0xf0585  br.s     loc_F0602
0xf0587  ldarg.1
0xf0588  callvirt instance void System.Xml.XmlReader::ResolveEntity()
0xf058d  br.s     loc_F0602
0xf058f  ldarg.1
0xf0590  callvirt instance string System.Xml.XmlReader::get_NamespaceURI()
0xf0595  ldloc.0
0xf0596  bne.un.s loc_F05D8
0xf0598  ldarg.1
0xf0599  callvirt instance string System.Xml.XmlReader::get_Prefix()
0xf059e  callvirt instance int32 [mscorlib]System.String::get_Length()
0xf05a3  brtrue.s loc_F05BE
0xf05a5  ldarg.2
0xf05a6  ldstr    asc_1284AE// ""
0xf05ab  ldstr    aXmlns// "xmlns"
0xf05b0  ldloc.0
0xf05b1  ldarg.1
0xf05b2  callvirt instance string System.Xml.XmlReader::get_Value()
0xf05b7  callvirt instance void System.Xml.XmlWriter::WriteAttributeString(string prefix, string localName, string ns, string value)
0xf05bc  br.s     loc_F0602
0xf05be  ldarg.2
0xf05bf  ldstr    aXmlns// "xmlns"
0xf05c4  ldarg.1
0xf05c5  callvirt instance string System.Xml.XmlReader::get_LocalName()
0xf05ca  ldloc.0
0xf05cb  ldarg.1
0xf05cc  callvirt instance string System.Xml.XmlReader::get_Value()
0xf05d1  callvirt instance void System.Xml.XmlWriter::WriteAttributeString(string prefix, string localName, string ns, string value)
0xf05d6  br.s     loc_F0602
0xf05d8  ldarg.2
0xf05d9  ldarg.1
0xf05da  callvirt instance string System.Xml.XmlReader::get_Prefix()
0xf05df  ldarg.1
0xf05e0  callvirt instance string System.Xml.XmlReader::get_LocalName()
0xf05e5  ldarg.1
0xf05e6  callvirt instance string System.Xml.XmlReader::get_NamespaceURI()
0xf05eb  callvirt instance void System.Xml.XmlWriter::WriteStartAttribute(string prefix, string localName, string ns)
0xf05f0  ldarg.2
0xf05f1  ldarg.1
0xf05f2  callvirt instance string System.Xml.XmlReader::get_Value()
0xf05f7  callvirt instance void System.Xml.XmlWriter::WriteString(string text)
0xf05fc  ldarg.2
0xf05fd  callvirt instance void System.Xml.XmlWriter::WriteEndAttribute()
0xf0602  ldarg.1
0xf0603  callvirt instance bool System.Xml.XmlReader::Read()
0xf0608  brfalse.s loc_F0611
0xf060a  ldloc.2
0xf060b  ldc.i4.0
0xf060c  bgt      loc_F041B
0xf0611  ret
```
