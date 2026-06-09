# System.Xml.Xsl.Runtime.XmlQueryOutput::StartCopy_0

- ea: `0x30150`
- end: `0x302dc`
- name: `System.Xml.Xsl.Runtime.XmlQueryOutput::StartCopy_0`
- size: `396`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `registry_config`

## callers

- `0x2ffc0`
- `0x300a0`

## callees

- `0x3780`
- `0x2d620`
- `0x2f640`
- `0x2f9c0`
- `0x2fac0`
- `0x2fb10`
- `0x2fb40`
- `0x2fbc0`
- `0x2fcf0`
- `0x2fe10`
- `0x2fe40`
- `0x2fe50`
- `0x2fe90`
- `0x2fee0`
- `0x2fef0`
- `0x30020`
- `0x30150`
- `0x30750`

## string_xrefs

- `0x30238`: `XmlIl_NmspAfterAttr`

## pseudocode

```c

```

## disassembly

```asm
0x30150  ldc.i4.0
0x30151  stloc.0
0x30152  ldarg.1
0x30153  callvirt instance valuetype [System.Xml]System.Xml.XPath.XPathNodeType [System.Xml]System.Xml.XPath.XPathNavigator::get_NodeType()
0x30158  stloc.1
0x30159  ldloc.1
0x3015a  switch   loc_30299, loc_30188, loc_301C4, loc_3021E, loc_30279, loc_30279, loc_30279, loc_302BC, loc_302A2
0x30183  br       loc_302DA
0x30188  ldarg.2
0x30189  brfalse.s loc_301A5
0x3018b  ldarg.0
0x3018c  ldarg.1
0x3018d  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_Prefix()
0x30192  ldarg.1
0x30193  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_LocalName()
0x30198  ldarg.1
0x30199  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_NamespaceURI()
0x3019e  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string, string)
0x301a3  br.s     loc_301BD
0x301a5  ldarg.0
0x301a6  ldarg.1
0x301a7  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_Prefix()
0x301ac  ldarg.1
0x301ad  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_LocalName()
0x301b2  ldarg.1
0x301b3  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_NamespaceURI()
0x301b8  call     instance void System.Xml.Xsl.Runtime.XmlQueryOutput::WriteStartElementUnchecked(string prefix, string localName, string ns)
0x301bd  ldc.i4.1
0x301be  stloc.0
0x301bf  br       loc_302DA
0x301c4  ldarg.2
0x301c5  brfalse.s loc_301E1
0x301c7  ldarg.0
0x301c8  ldarg.1
0x301c9  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_Prefix()
0x301ce  ldarg.1
0x301cf  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_LocalName()
0x301d4  ldarg.1
0x301d5  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_NamespaceURI()
0x301da  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartAttribute(string, string, string)
0x301df  br.s     loc_301F9
0x301e1  ldarg.0
0x301e2  ldarg.1
0x301e3  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_Prefix()
0x301e8  ldarg.1
0x301e9  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_LocalName()
0x301ee  ldarg.1
0x301ef  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_NamespaceURI()
0x301f4  call     instance void System.Xml.Xsl.Runtime.XmlQueryOutput::WriteStartAttributeUnchecked(string prefix, string localName, string ns)
0x301f9  ldarg.0
0x301fa  ldarg.1
0x301fb  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x30200  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteString(string)
0x30205  ldarg.2
0x30206  brfalse.s loc_30213
0x30208  ldarg.0
0x30209  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndAttribute()
0x3020e  br       loc_302DA
0x30213  ldarg.0
0x30214  call     instance void System.Xml.Xsl.Runtime.XmlQueryOutput::WriteEndAttributeUnchecked()
0x30219  br       loc_302DA
0x3021e  ldarg.2
0x3021f  brfalse.s loc_30265
0x30221  ldarg.0
0x30222  call     instance class [System.Xml]System.Xml.XmlRawWriter System.Xml.Xsl.Runtime.XmlQueryOutput::get_Writer()
0x30227  isinst   System.Xml.Xsl.Runtime.XmlAttributeCache
0x3022c  stloc.2
0x3022d  ldloc.2
0x3022e  brfalse.s loc_30251
0x30230  ldloc.2
0x30231  callvirt instance int32 System.Xml.Xsl.Runtime.XmlAttributeCache::get_Count()
0x30236  brfalse.s loc_30251
0x30238  ldstr    aXmlilNmspafter// "XmlIl_NmspAfterAttr"
0x3023d  ldc.i4.1
0x3023e  newarr   [mscorlib]System.String
0x30243  dup
0x30244  ldc.i4.0
0x30245  ldsfld   string [mscorlib]System.String::Empty
0x3024a  stelem.ref
0x3024b  newobj   instance void System.Xml.Xsl.XslTransformException::.ctor(string res, string[] args)
0x30250  throw
0x30251  ldarg.0
0x30252  ldarg.1
0x30253  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_LocalName()
0x30258  ldarg.1
0x30259  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x3025e  call     instance void System.Xml.Xsl.Runtime.XmlQueryOutput::WriteNamespaceDeclaration(string prefix, string ns)
0x30263  br.s     loc_302DA
0x30265  ldarg.0
0x30266  ldarg.1
0x30267  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_LocalName()
0x3026c  ldarg.1
0x3026d  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x30272  call     instance void System.Xml.Xsl.Runtime.XmlQueryOutput::WriteNamespaceDeclarationUnchecked(string prefix, string ns)
0x30277  br.s     loc_302DA
0x30279  ldarg.2
0x3027a  brfalse.s loc_3028B
0x3027c  ldarg.0
0x3027d  ldarg.1
0x3027e  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x30283  ldc.i4.0
0x30284  call     instance void System.Xml.Xsl.Runtime.XmlQueryOutput::WriteString(string text, bool disableOutputEscaping)
0x30289  br.s     loc_302DA
0x3028b  ldarg.0
0x3028c  ldarg.1
0x3028d  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x30292  call     instance void System.Xml.Xsl.Runtime.XmlQueryOutput::WriteStringUnchecked(string text)
0x30297  br.s     loc_302DA
0x30299  ldarg.0
0x3029a  ldc.i4.0
0x3029b  call     instance void System.Xml.Xsl.Runtime.XmlQueryOutput::ThrowInvalidStateError(valuetype [System.Xml]System.Xml.XPath.XPathNodeType constructorType)
0x302a0  br.s     loc_302DA
0x302a2  ldarg.0
0x302a3  call     instance void System.Xml.Xsl.Runtime.XmlQueryOutput::WriteStartComment()
0x302a8  ldarg.0
0x302a9  ldarg.1
0x302aa  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x302af  call     instance void System.Xml.Xsl.Runtime.XmlQueryOutput::WriteCommentString(string text)
0x302b4  ldarg.0
0x302b5  call     instance void System.Xml.Xsl.Runtime.XmlQueryOutput::WriteEndComment()
0x302ba  br.s     loc_302DA
0x302bc  ldarg.0
0x302bd  ldarg.1
0x302be  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_LocalName()
0x302c3  call     instance void System.Xml.Xsl.Runtime.XmlQueryOutput::WriteStartProcessingInstruction(string target)
0x302c8  ldarg.0
0x302c9  ldarg.1
0x302ca  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x302cf  call     instance void System.Xml.Xsl.Runtime.XmlQueryOutput::WriteProcessingInstructionString(string text)
0x302d4  ldarg.0
0x302d5  call     instance void System.Xml.Xsl.Runtime.XmlQueryOutput::WriteEndProcessingInstruction()
0x302da  ldloc.0
0x302db  ret
```
