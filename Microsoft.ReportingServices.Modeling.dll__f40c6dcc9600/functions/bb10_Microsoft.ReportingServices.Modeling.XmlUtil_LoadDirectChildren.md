# Microsoft.ReportingServices.Modeling.XmlUtil::LoadDirectChildren

- ea: `0xbb10`
- end: `0xbc4f`
- name: `Microsoft.ReportingServices.Modeling.XmlUtil::LoadDirectChildren`
- size: `319`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xcf60`
- `0xd790`

## callees

- `0x97d0`
- `0xbb10`
- `0x2eda0`

## string_xrefs

- `0xbb2f`: `Unexpected xr state at the end of reading DataSourceView: xr.NodeType == `
- `0xbbf5`: `Unexpected xr state at the end of reading DataSourceView: xr.NodeType == `

## pseudocode

```c

```

## disassembly

```asm
0xbb10  ldarg.0
0xbb11  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xbb16  ldc.i4.1
0xbb17  bne.un.s loc_BB27
0xbb19  ldarg.0
0xbb1a  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xbb1f  ldarg.1
0xbb20  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xbb25  brfalse.s loc_BB7C
0xbb27  ldc.i4.7
0xbb28  newarr   [mscorlib]System.String
0xbb2d  dup
0xbb2e  ldc.i4.0
0xbb2f  ldstr    aUnexpectedXrSt// "Unexpected xr state at the end of readi"...
0xbb34  stelem.ref
0xbb35  dup
0xbb36  ldc.i4.1
0xbb37  ldarg.0
0xbb38  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xbb3d  stloc.0
0xbb3e  ldloca.s 0
0xbb40  constrained. [System.Xml]System.Xml.XmlNodeType
0xbb46  callvirt instance string [mscorlib]System.Object::ToString()
0xbb4b  stelem.ref
0xbb4c  dup
0xbb4d  ldc.i4.2
0xbb4e  ldstr    aExpectedElemen// ", expected Element; xr.LocalName == '"
0xbb53  stelem.ref
0xbb54  dup
0xbb55  ldc.i4.3
0xbb56  ldarg.0
0xbb57  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xbb5c  stelem.ref
0xbb5d  dup
0xbb5e  ldc.i4.4
0xbb5f  ldstr    aExpected// "', expected '"
0xbb64  stelem.ref
0xbb65  dup
0xbb66  ldc.i4.5
0xbb67  ldarg.1
0xbb68  stelem.ref
0xbb69  dup
0xbb6a  ldc.i4.6
0xbb6b  ldstr    asc_3E096// "'"
0xbb70  stelem.ref
0xbb71  call     string [mscorlib]System.String::Concat(string[])
0xbb76  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0xbb7b  throw
0xbb7c  ldarg.0
0xbb7d  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0xbb82  brfalse.s loc_BB8C
0xbb84  ldarg.0
0xbb85  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0xbb8a  pop
0xbb8b  ret
0xbb8c  ldarg.0
0xbb8d  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0xbb92  pop
0xbb93  ldarg.0
0xbb94  callvirt instance int32 [System.Xml]System.Xml.XmlReader::get_Depth()
0xbb99  stloc.1
0xbb9a  ldarg.0
0xbb9b  callvirt instance int32 [System.Xml]System.Xml.XmlReader::get_Depth()
0xbba0  ldloc.1
0xbba1  bne.un.s loc_BBCC
0xbba3  ldarg.0
0xbba4  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xbba9  ldc.i4.1
0xbbaa  bne.un.s loc_BBCC
0xbbac  ldarg.0
0xbbad  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xbbb2  ldarg.2
0xbbb3  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbbb8  brfalse.s loc_BBCC
0xbbba  ldarg.3
0xbbbb  ldarg.0
0xbbbc  callvirt instance bool LoadXmlElementLDC::Invoke(class [System.Xml]System.Xml.XmlReader xr)
0xbbc1  brtrue.s loc_BB9A
0xbbc3  ldarg.0
0xbbc4  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0xbbc9  pop
0xbbca  br.s     loc_BB9A
0xbbcc  ldarg.0
0xbbcd  callvirt instance int32 [System.Xml]System.Xml.XmlReader::get_Depth()
0xbbd2  ldloc.1
0xbbd3  bge.s    loc_BC42
0xbbd5  ldarg.0
0xbbd6  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xbbdb  ldc.i4.s 0xF
0xbbdd  bne.un.s loc_BBED
0xbbdf  ldarg.0
0xbbe0  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xbbe5  ldarg.1
0xbbe6  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xbbeb  brfalse.s loc_BC4E
0xbbed  ldc.i4.7
0xbbee  newarr   [mscorlib]System.String
0xbbf3  dup
0xbbf4  ldc.i4.0
0xbbf5  ldstr    aUnexpectedXrSt// "Unexpected xr state at the end of readi"...
0xbbfa  stelem.ref
0xbbfb  dup
0xbbfc  ldc.i4.1
0xbbfd  ldarg.0
0xbbfe  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xbc03  stloc.0
0xbc04  ldloca.s 0
0xbc06  constrained. [System.Xml]System.Xml.XmlNodeType
0xbc0c  callvirt instance string [mscorlib]System.Object::ToString()
0xbc11  stelem.ref
0xbc12  dup
0xbc13  ldc.i4.2
0xbc14  ldstr    aExpectedEndele// ", expected EndElement; xr.LocalName == "...
0xbc19  stelem.ref
0xbc1a  dup
0xbc1b  ldc.i4.3
0xbc1c  ldarg.0
0xbc1d  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xbc22  stelem.ref
0xbc23  dup
0xbc24  ldc.i4.4
0xbc25  ldstr    aExpected// "', expected '"
0xbc2a  stelem.ref
0xbc2b  dup
0xbc2c  ldc.i4.5
0xbc2d  ldarg.1
0xbc2e  stelem.ref
0xbc2f  dup
0xbc30  ldc.i4.6
0xbc31  ldstr    asc_3E096// "'"
0xbc36  stelem.ref
0xbc37  call     string [mscorlib]System.String::Concat(string[])
0xbc3c  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0xbc41  throw
0xbc42  ldarg.0
0xbc43  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0xbc48  pop
0xbc49  br       loc_BB9A
0xbc4e  ret
```
