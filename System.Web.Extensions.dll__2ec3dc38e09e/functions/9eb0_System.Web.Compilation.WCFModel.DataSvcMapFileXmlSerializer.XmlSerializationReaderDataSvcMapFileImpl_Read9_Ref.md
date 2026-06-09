# System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::Read9_ReferenceGroup

- ea: `0x9eb0`
- end: `0x9f12`
- name: `System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::Read9_ReferenceGroup`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xb2b0`

## callees

- `0x9eb0`
- `0x9f20`

## string_xrefs

- `0x9f06`: `urn:schemas-microsoft-com:xml-dataservicemap:ReferenceGroup`

## pseudocode

```c

```

## disassembly

```asm
0x9eb0  ldnull
0x9eb1  stloc.0
0x9eb2  ldarg.0
0x9eb3  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x9eb8  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x9ebd  pop
0x9ebe  ldarg.0
0x9ebf  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x9ec4  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x9ec9  ldc.i4.1
0x9eca  bne.un.s loc_9F04
0x9ecc  ldarg.0
0x9ecd  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x9ed2  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x9ed7  ldarg.0
0x9ed8  ldfld    string System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::id1_ReferenceGroup
0x9edd  bne.un.s loc_9EFD
0x9edf  ldarg.0
0x9ee0  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x9ee5  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x9eea  ldarg.0
0x9eeb  ldfld    string System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::id2_Item
0x9ef0  bne.un.s loc_9EFD
0x9ef2  ldarg.0
0x9ef3  ldc.i4.1
0x9ef4  ldc.i4.1
0x9ef5  call     instance class System.Web.Compilation.WCFModel.DataSvcMapFileImpl System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationReaderDataSvcMapFileImpl::Read8_DataSvcMapFileImpl(bool isNullable, bool checkType)
0x9efa  stloc.0
0x9efb  br.s     loc_9F10
0x9efd  ldarg.0
0x9efe  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationReader::CreateUnknownNodeException()
0x9f03  throw
0x9f04  ldarg.0
0x9f05  ldnull
0x9f06  ldstr    aUrnSchemasMicr_12// "urn:schemas-microsoft-com:xml-dataservi"...
0x9f0b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0x9f10  ldloc.0
0x9f11  ret
```
