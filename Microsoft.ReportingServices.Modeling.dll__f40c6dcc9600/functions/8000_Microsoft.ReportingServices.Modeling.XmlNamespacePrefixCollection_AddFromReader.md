# Microsoft.ReportingServices.Modeling.XmlNamespacePrefixCollection::AddFromReader

- ea: `0x8000`
- end: `0x8069`
- name: `Microsoft.ReportingServices.Modeling.XmlNamespacePrefixCollection::AddFromReader`
- size: `105`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x16d60`
- `0x234c0`

## callees

- `0x8000`
- `0xa0a0`
- `0xa7b0`
- `0xa7c0`
- `0xa7d0`
- `0xa7e0`
- `0xa7f0`

## string_xrefs

- `0x800f`: `http://www.w3.org/2000/xmlns/`
- `0x8027`: `xmlns`

## pseudocode

```c

```

## disassembly

```asm
0x8000  ldarg.1
0x8001  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_NodeType()
0x8006  ldc.i4.2
0x8007  bne.un.s loc_801B
0x8009  ldarg.1
0x800a  callvirt instance string Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_NamespaceURI()
0x800f  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/xmlns/"
0x8014  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x8019  brfalse.s loc_8021
0x801b  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor()
0x8020  throw
0x8021  ldarg.1
0x8022  callvirt instance string Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_Prefix()
0x8027  ldstr    aXmlns// "xmlns"
0x802c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8031  brtrue.s loc_803B
0x8033  ldarg.1
0x8034  callvirt instance string Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_Prefix()
0x8039  br.s     loc_8041
0x803b  ldarg.1
0x803c  callvirt instance string Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_LocalName()
0x8041  stloc.0
0x8042  ldarg.1
0x8043  callvirt instance string Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_Value()
0x8048  stloc.1
0x8049  ldloc.0
0x804a  callvirt instance int32 [mscorlib]System.String::get_Length()
0x804f  ldc.i4.0
0x8050  ble.s    loc_8068
0x8052  ldarg.0
0x8053  ldloc.0
0x8054  call     instance bool class [mscorlib]System.Collections.ObjectModel.KeyedCollection`2<string, valuetype Microsoft.ReportingServices.Modeling.QName>::Contains(var<u1>)
0x8059  brtrue.s loc_8068
0x805b  ldarg.0
0x805c  ldloc.0
0x805d  ldloc.1
0x805e  newobj   instance void Microsoft.ReportingServices.Modeling.QName::.ctor(string name, string ns)
0x8063  call     instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<valuetype Microsoft.ReportingServices.Modeling.QName>::Add(var<u1>)
0x8068  ret
```
