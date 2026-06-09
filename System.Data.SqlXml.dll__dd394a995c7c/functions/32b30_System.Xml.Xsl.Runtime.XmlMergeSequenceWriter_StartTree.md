# System.Xml.Xsl.Runtime.XmlMergeSequenceWriter::StartTree

- ea: `0x32b30`
- end: `0x32b64`
- name: `System.Xml.Xsl.Runtime.XmlMergeSequenceWriter::StartTree`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x3780`
- `0x32b30`

## string_xrefs

- `0x32b38`: `XmlIl_TopLevelAttrNmsp`

## pseudocode

```c

```

## disassembly

```asm
0x32b30  ldarg.1
0x32b31  ldc.i4.2
0x32b32  beq.s    loc_32B38
0x32b34  ldarg.1
0x32b35  ldc.i4.3
0x32b36  bne.un.s loc_32B51
0x32b38  ldstr    aXmlilToplevela// "XmlIl_TopLevelAttrNmsp"
0x32b3d  ldc.i4.1
0x32b3e  newarr   [mscorlib]System.String
0x32b43  dup
0x32b44  ldc.i4.0
0x32b45  ldsfld   string [mscorlib]System.String::Empty
0x32b4a  stelem.ref
0x32b4b  newobj   instance void System.Xml.Xsl.XslTransformException::.ctor(string res, string[] args)
0x32b50  throw
0x32b51  ldarg.0
0x32b52  ldfld    class [System.Xml]System.Xml.XmlRawWriter System.Xml.Xsl.Runtime.XmlMergeSequenceWriter::xwrt
0x32b57  ldarg.2
0x32b58  callvirt instance void [System.Xml]System.Xml.XmlRawWriter::set_NamespaceResolver(class [System.Xml]System.Xml.IXmlNamespaceResolver)
0x32b5d  ldarg.0
0x32b5e  ldfld    class [System.Xml]System.Xml.XmlRawWriter System.Xml.Xsl.Runtime.XmlMergeSequenceWriter::xwrt
0x32b63  ret
```
