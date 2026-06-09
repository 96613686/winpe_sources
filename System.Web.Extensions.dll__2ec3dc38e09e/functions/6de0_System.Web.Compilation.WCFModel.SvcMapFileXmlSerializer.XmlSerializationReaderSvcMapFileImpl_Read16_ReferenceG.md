# System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::Read16_ReferenceGroup

- ea: `0x6de0`
- end: `0x6e42`
- name: `System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::Read16_ReferenceGroup`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x9770`

## callees

- `0x6de0`
- `0x6e50`

## string_xrefs

- `0x6e36`: `urn:schemas-microsoft-com:xml-wcfservicemap:ReferenceGroup`

## pseudocode

```c

```

## disassembly

```asm
0x6de0  ldnull
0x6de1  stloc.0
0x6de2  ldarg.0
0x6de3  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x6de8  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x6ded  pop
0x6dee  ldarg.0
0x6def  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x6df4  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x6df9  ldc.i4.1
0x6dfa  bne.un.s loc_6E34
0x6dfc  ldarg.0
0x6dfd  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x6e02  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x6e07  ldarg.0
0x6e08  ldfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id1_ReferenceGroup
0x6e0d  bne.un.s loc_6E2D
0x6e0f  ldarg.0
0x6e10  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x6e15  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x6e1a  ldarg.0
0x6e1b  ldfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id2_Item
0x6e20  bne.un.s loc_6E2D
0x6e22  ldarg.0
0x6e23  ldc.i4.1
0x6e24  ldc.i4.1
0x6e25  call     instance class System.Web.Compilation.WCFModel.SvcMapFileImpl System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::Read15_SvcMapFileImpl(bool isNullable, bool checkType)
0x6e2a  stloc.0
0x6e2b  br.s     loc_6E40
0x6e2d  ldarg.0
0x6e2e  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationReader::CreateUnknownNodeException()
0x6e33  throw
0x6e34  ldarg.0
0x6e35  ldnull
0x6e36  ldstr    aUrnSchemasMicr_0// "urn:schemas-microsoft-com:xml-wcfservic"...
0x6e3b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0x6e40  ldloc.0
0x6e41  ret
```
