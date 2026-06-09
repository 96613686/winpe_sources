# System.Xml.Xsl.Xslt.QilGenerator::GetNsVar

- ea: `0x16a10`
- end: `0x16b61`
- name: `System.Xml.Xsl.Xslt.QilGenerator::GetNsVar`
- size: `337`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x16b70`
- `0x1a7c0`

## callees

- `0x16a10`
- `0x35920`
- `0x35940`
- `0x37100`
- `0x37390`
- `0x37740`
- `0x37750`
- `0x37790`
- `0x377c0`
- `0x37a60`
- `0x37c50`
- `0x38ce0`

## string_xrefs

- `0x16b30`: `urn:schemas-microsoft-com:xslt-debug`

## pseudocode

```c

```

## disassembly

```asm
0x16a10  ldarg.0
0x16a11  ldfld    class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Xslt.QilGenerator::nsVars
0x16a16  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.Xml.Xsl.Qil.QilNode> System.Xml.Xsl.Qil.QilNode::GetEnumerator()
0x16a1b  stloc.1
0x16a1c  br       loc_16AE7
0x16a21  ldloc.1
0x16a22  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.Xml.Xsl.Qil.QilNode>::get_Current()
0x16a27  castclass System.Xml.Xsl.Qil.QilIterator
0x16a2c  stloc.2
0x16a2d  ldloc.2
0x16a2e  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilIterator::get_Binding()
0x16a33  castclass System.Xml.Xsl.Qil.QilList
0x16a38  stloc.3
0x16a39  ldloc.3
0x16a3a  callvirt instance int32 System.Xml.Xsl.Qil.QilNode::get_Count()
0x16a3f  ldarg.1
0x16a40  callvirt instance int32 System.Xml.Xsl.Qil.QilNode::get_Count()
0x16a45  bne.un   loc_16AE7
0x16a4a  ldc.i4.1
0x16a4b  stloc.s  4
0x16a4d  ldc.i4.0
0x16a4e  stloc.s  5
0x16a50  br.s     loc_16AD1
0x16a52  ldarg.1
0x16a53  ldloc.s  5
0x16a55  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x16a5a  castclass System.Xml.Xsl.Qil.QilBinary
0x16a5f  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilBinary::get_Right()
0x16a64  castclass System.Xml.Xsl.Qil.QilLiteral
0x16a69  callvirt instance object System.Xml.Xsl.Qil.QilLiteral::get_Value()
0x16a6e  ldloc.3
0x16a6f  ldloc.s  5
0x16a71  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x16a76  castclass System.Xml.Xsl.Qil.QilBinary
0x16a7b  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilBinary::get_Right()
0x16a80  castclass System.Xml.Xsl.Qil.QilLiteral
0x16a85  callvirt instance object System.Xml.Xsl.Qil.QilLiteral::get_Value()
0x16a8a  bne.un.s loc_16AC6
0x16a8c  ldarg.1
0x16a8d  ldloc.s  5
0x16a8f  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x16a94  castclass System.Xml.Xsl.Qil.QilBinary
0x16a99  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilBinary::get_Left()
0x16a9e  castclass System.Xml.Xsl.Qil.QilLiteral
0x16aa3  callvirt instance object System.Xml.Xsl.Qil.QilLiteral::get_Value()
0x16aa8  ldloc.3
0x16aa9  ldloc.s  5
0x16aab  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilNode::get_Item(int32 index)
0x16ab0  castclass System.Xml.Xsl.Qil.QilBinary
0x16ab5  callvirt instance class System.Xml.Xsl.Qil.QilNode System.Xml.Xsl.Qil.QilBinary::get_Left()
0x16aba  castclass System.Xml.Xsl.Qil.QilLiteral
0x16abf  callvirt instance object System.Xml.Xsl.Qil.QilLiteral::get_Value()
0x16ac4  beq.s    loc_16ACB
0x16ac6  ldc.i4.0
0x16ac7  stloc.s  4
0x16ac9  br.s     loc_16ADE
0x16acb  ldloc.s  5
0x16acd  ldc.i4.1
0x16ace  add
0x16acf  stloc.s  5
0x16ad1  ldloc.s  5
0x16ad3  ldarg.1
0x16ad4  callvirt instance int32 System.Xml.Xsl.Qil.QilNode::get_Count()
0x16ad9  blt      loc_16A52
0x16ade  ldloc.s  4
0x16ae0  brfalse.s loc_16AE7
0x16ae2  ldloc.2
0x16ae3  stloc.s  6
0x16ae5  leave.s  loc_16B5E
0x16ae7  ldloc.1
0x16ae8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x16aed  brtrue   loc_16A21
0x16af2  leave.s  loc_16AFE
0x16af4  ldloc.1
0x16af5  brfalse.s loc_16AFD
0x16af7  ldloc.1
0x16af8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x16afd  endfinally
0x16afe  ldarg.0
0x16aff  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x16b04  ldarg.1
0x16b05  callvirt instance class System.Xml.Xsl.Qil.QilIterator System.Xml.Xsl.Qil.QilPatternFactory::Let(class System.Xml.Xsl.Qil.QilNode binding)
0x16b0a  stloc.0
0x16b0b  ldloc.0
0x16b0c  ldarg.0
0x16b0d  ldfld    class System.Xml.Xsl.Xslt.XsltQilFactory System.Xml.Xsl.Xslt.QilGenerator::f
0x16b12  ldstr    aNs// "ns"
0x16b17  ldarg.0
0x16b18  ldfld    class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Xslt.QilGenerator::nsVars
0x16b1d  callvirt instance int32 System.Xml.Xsl.Qil.QilNode::get_Count()
0x16b22  stloc.s  7
0x16b24  ldloca.s 7
0x16b26  call     instance string [mscorlib]System.Int32::ToString()
0x16b2b  call     string [mscorlib]System.String::Concat(string, string)
0x16b30  ldstr    aUrnSchemasMicr_0// "urn:schemas-microsoft-com:xslt-debug"
0x16b35  callvirt instance class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Qil.QilPatternFactory::QName(string local, string uri)
0x16b3a  callvirt instance string [mscorlib]System.Object::ToString()
0x16b3f  callvirt instance void System.Xml.Xsl.Qil.QilReference::set_DebugName(string value)
0x16b44  ldarg.0
0x16b45  ldfld    class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Xslt.QilGenerator::gloVars
0x16b4a  ldloc.0
0x16b4b  callvirt instance void System.Xml.Xsl.Qil.QilNode::Add(class System.Xml.Xsl.Qil.QilNode node)
0x16b50  ldarg.0
0x16b51  ldfld    class System.Xml.Xsl.Qil.QilList System.Xml.Xsl.Xslt.QilGenerator::nsVars
0x16b56  ldloc.0
0x16b57  callvirt instance void System.Xml.Xsl.Qil.QilNode::Add(class System.Xml.Xsl.Qil.QilNode node)
0x16b5c  ldloc.0
0x16b5d  ret
0x16b5e  ldloc.s  6
0x16b60  ret
```
