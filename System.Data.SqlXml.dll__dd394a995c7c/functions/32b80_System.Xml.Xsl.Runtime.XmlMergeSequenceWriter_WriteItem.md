# System.Xml.Xsl.Runtime.XmlMergeSequenceWriter::WriteItem

- ea: `0x32b80`
- end: `0x32bd6`
- name: `System.Xml.Xsl.Runtime.XmlMergeSequenceWriter::WriteItem`
- size: `86`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x3780`
- `0x32b80`
- `0x32be0`
- `0x32c10`

## string_xrefs

- `0x32ba1`: `XmlIl_TopLevelAttrNmsp`

## pseudocode

```c

```

## disassembly

```asm
0x32b80  ldarg.1
0x32b81  callvirt instance bool [System.Xml]System.Xml.XPath.XPathItem::get_IsNode()
0x32b86  brfalse.s loc_32BC9
0x32b88  ldarg.1
0x32b89  isinst   [System.Xml]System.Xml.XPath.XPathNavigator
0x32b8e  stloc.0
0x32b8f  ldloc.0
0x32b90  callvirt instance valuetype [System.Xml]System.Xml.XPath.XPathNodeType [System.Xml]System.Xml.XPath.XPathNavigator::get_NodeType()
0x32b95  ldc.i4.2
0x32b96  beq.s    loc_32BA1
0x32b98  ldloc.0
0x32b99  callvirt instance valuetype [System.Xml]System.Xml.XPath.XPathNodeType [System.Xml]System.Xml.XPath.XPathNavigator::get_NodeType()
0x32b9e  ldc.i4.3
0x32b9f  bne.un.s loc_32BBA
0x32ba1  ldstr    aXmlilToplevela// "XmlIl_TopLevelAttrNmsp"
0x32ba6  ldc.i4.1
0x32ba7  newarr   [mscorlib]System.String
0x32bac  dup
0x32bad  ldc.i4.0
0x32bae  ldsfld   string [mscorlib]System.String::Empty
0x32bb3  stelem.ref
0x32bb4  newobj   instance void System.Xml.Xsl.XslTransformException::.ctor(string res, string[] args)
0x32bb9  throw
0x32bba  ldarg.0
0x32bbb  ldloc.0
0x32bbc  call     instance void System.Xml.Xsl.Runtime.XmlMergeSequenceWriter::CopyNode(class [System.Xml]System.Xml.XPath.XPathNavigator nav)
0x32bc1  ldarg.0
0x32bc2  ldc.i4.0
0x32bc3  stfld    bool System.Xml.Xsl.Runtime.XmlMergeSequenceWriter::lastItemWasAtomic
0x32bc8  ret
0x32bc9  ldarg.0
0x32bca  ldarg.1
0x32bcb  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x32bd0  call     instance void System.Xml.Xsl.Runtime.XmlMergeSequenceWriter::WriteString(string value)
0x32bd5  ret
```
