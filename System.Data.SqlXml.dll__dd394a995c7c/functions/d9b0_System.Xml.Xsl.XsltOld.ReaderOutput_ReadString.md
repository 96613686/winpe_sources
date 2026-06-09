# System.Xml.Xsl.XsltOld.ReaderOutput::ReadString

- ea: `0xd9b0`
- end: `0xda5c`
- name: `System.Xml.Xsl.XsltOld.ReaderOutput::ReadString`
- size: `172`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x230`
- `0x54d0`
- `0xd9b0`

## string_xrefs

- `0xd9ed`: `Xml_InvalidOperation`
- `0xda40`: `Xml_InvalidOperation`

## pseudocode

```c

```

## disassembly

```asm
0xd9b0  ldsfld   string [mscorlib]System.String::Empty
0xd9b5  stloc.0
0xd9b6  ldarg.0
0xd9b7  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xd9bc  ldc.i4.1
0xd9bd  beq.s    loc_D9D6
0xd9bf  ldarg.0
0xd9c0  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xd9c5  ldc.i4.2
0xd9c6  beq.s    loc_D9D6
0xd9c8  ldarg.0
0xd9c9  ldfld    class System.Xml.Xsl.XsltOld.BuilderInfo System.Xml.Xsl.XsltOld.ReaderOutput::currentInfo
0xd9ce  ldarg.0
0xd9cf  ldfld    class System.Xml.Xsl.XsltOld.BuilderInfo System.Xml.Xsl.XsltOld.ReaderOutput::attributeValue
0xd9d4  bne.un.s loc_D9FD
0xd9d6  ldarg.0
0xd9d7  ldfld    class System.Xml.Xsl.XsltOld.BuilderInfo System.Xml.Xsl.XsltOld.ReaderOutput::mainNode
0xd9dc  callvirt instance bool System.Xml.Xsl.XsltOld.BuilderInfo::get_IsEmptyTag()
0xd9e1  brfalse.s loc_D9E5
0xd9e3  ldloc.0
0xd9e4  ret
0xd9e5  ldarg.0
0xd9e6  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0xd9eb  brtrue.s loc_D9FD
0xd9ed  ldstr    aXmlInvalidoper// "Xml_InvalidOperation"
0xd9f2  call     string System.Xml.Utils.Res::GetString(string name)
0xd9f7  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xd9fc  throw
0xd9fd  ldnull
0xd9fe  stloc.1
0xd9ff  ldc.i4.1
0xda00  stloc.2
0xda01  ldarg.0
0xda02  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xda07  stloc.3
0xda08  ldloc.3
0xda09  ldc.i4.3
0xda0a  beq.s    loc_DA13
0xda0c  ldloc.3
0xda0d  ldc.i4.s 0xD
0xda0f  sub
0xda10  ldc.i4.1
0xda11  bgt.un.s loc_DA50
0xda13  ldloc.2
0xda14  brfalse.s loc_DA21
0xda16  ldarg.0
0xda17  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Value()
0xda1c  stloc.0
0xda1d  ldc.i4.0
0xda1e  stloc.2
0xda1f  br.s     loc_DA38
0xda21  ldloc.1
0xda22  brtrue.s loc_DA2B
0xda24  ldloc.0
0xda25  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0xda2a  stloc.1
0xda2b  ldloc.1
0xda2c  ldarg.0
0xda2d  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Value()
0xda32  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xda37  pop
0xda38  ldarg.0
0xda39  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0xda3e  brtrue.s loc_DA01
0xda40  ldstr    aXmlInvalidoper// "Xml_InvalidOperation"
0xda45  call     string System.Xml.Utils.Res::GetString(string name)
0xda4a  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xda4f  throw
0xda50  ldloc.1
0xda51  brfalse.s loc_DA5A
0xda53  ldloc.1
0xda54  callvirt instance string [mscorlib]System.Object::ToString()
0xda59  ret
0xda5a  ldloc.0
0xda5b  ret
```
