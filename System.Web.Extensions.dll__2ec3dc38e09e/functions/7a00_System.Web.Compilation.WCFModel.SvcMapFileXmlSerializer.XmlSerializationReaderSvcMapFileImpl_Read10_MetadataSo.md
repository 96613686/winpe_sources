# System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::Read10_MetadataSource

- ea: `0x7a00`
- end: `0x7c09`
- name: `System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::Read10_MetadataSource`
- size: `521`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x6e50`

## callees

- `0x2ce0`
- `0x2d80`
- `0x2db0`
- `0x2de0`
- `0x7a00`

## string_xrefs

- `0x7b43`: `:Address, :Protocol, :SourceId`

## pseudocode

```c

```

## disassembly

```asm
0x7a00  ldarg.2
0x7a01  brtrue.s loc_7A06
0x7a03  ldnull
0x7a04  br.s     loc_7A0C
0x7a06  ldarg.0
0x7a07  call     instance class [System.Xml]System.Xml.XmlQualifiedName [System.Xml]System.Xml.Serialization.XmlSerializationReader::GetXsiType()
0x7a0c  stloc.0
0x7a0d  ldc.i4.0
0x7a0e  stloc.1
0x7a0f  ldarg.1
0x7a10  brfalse.s loc_7A19
0x7a12  ldarg.0
0x7a13  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x7a18  stloc.1
0x7a19  ldarg.2
0x7a1a  brfalse.s loc_7A49
0x7a1c  ldloc.0
0x7a1d  ldnull
0x7a1e  call     bool [System.Xml]System.Xml.XmlQualifiedName::op_Equality(class [System.Xml]System.Xml.XmlQualifiedName, class [System.Xml]System.Xml.XmlQualifiedName)
0x7a23  brtrue.s loc_7A49
0x7a25  ldloc.0
0x7a26  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Name()
0x7a2b  ldarg.0
0x7a2c  ldfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id8_MetadataSource
0x7a31  bne.un.s loc_7A41
0x7a33  ldloc.0
0x7a34  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Namespace()
0x7a39  ldarg.0
0x7a3a  ldfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id2_Item
0x7a3f  beq.s    loc_7A49
0x7a41  ldarg.0
0x7a42  ldloc.0
0x7a43  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationReader::CreateUnknownTypeException(class [System.Xml]System.Xml.XmlQualifiedName)
0x7a48  throw
0x7a49  ldloc.1
0x7a4a  brfalse.s loc_7A4E
0x7a4c  ldnull
0x7a4d  ret
0x7a4e  newobj   instance void System.Web.Compilation.WCFModel.MetadataSource::.ctor()
0x7a53  stloc.2
0x7a54  ldc.i4.3
0x7a55  newarr   [mscorlib]System.Boolean
0x7a5a  stloc.3
0x7a5b  br       loc_7B4D
0x7a60  ldloc.3
0x7a61  ldc.i4.0
0x7a62  ldelem.u1
0x7a63  brtrue.s loc_7AA5
0x7a65  ldarg.0
0x7a66  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7a6b  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x7a70  ldarg.0
0x7a71  ldfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id20_Address
0x7a76  bne.un.s loc_7AA5
0x7a78  ldarg.0
0x7a79  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7a7e  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x7a83  ldarg.0
0x7a84  ldfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id5_Item
0x7a89  bne.un.s loc_7AA5
0x7a8b  ldloc.2
0x7a8c  ldarg.0
0x7a8d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7a92  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Value()
0x7a97  callvirt instance void System.Web.Compilation.WCFModel.MetadataSource::set_Address(string value)
0x7a9c  ldloc.3
0x7a9d  ldc.i4.0
0x7a9e  ldc.i4.1
0x7a9f  stelem.i1
0x7aa0  br       loc_7B4D
0x7aa5  ldloc.3
0x7aa6  ldc.i4.1
0x7aa7  ldelem.u1
0x7aa8  brtrue.s loc_7AE7
0x7aaa  ldarg.0
0x7aab  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7ab0  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x7ab5  ldarg.0
0x7ab6  ldfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id21_Protocol
0x7abb  bne.un.s loc_7AE7
0x7abd  ldarg.0
0x7abe  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7ac3  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x7ac8  ldarg.0
0x7ac9  ldfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id5_Item
0x7ace  bne.un.s loc_7AE7
0x7ad0  ldloc.2
0x7ad1  ldarg.0
0x7ad2  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7ad7  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Value()
0x7adc  callvirt instance void System.Web.Compilation.WCFModel.MetadataSource::set_Protocol(string value)
0x7ae1  ldloc.3
0x7ae2  ldc.i4.1
0x7ae3  ldc.i4.1
0x7ae4  stelem.i1
0x7ae5  br.s     loc_7B4D
0x7ae7  ldloc.3
0x7ae8  ldc.i4.2
0x7ae9  ldelem.u1
0x7aea  brtrue.s loc_7B2E
0x7aec  ldarg.0
0x7aed  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7af2  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x7af7  ldarg.0
0x7af8  ldfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id18_SourceId
0x7afd  bne.un.s loc_7B2E
0x7aff  ldarg.0
0x7b00  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7b05  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x7b0a  ldarg.0
0x7b0b  ldfld    string System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::id5_Item
0x7b10  bne.un.s loc_7B2E
0x7b12  ldloc.2
0x7b13  ldarg.0
0x7b14  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7b19  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Value()
0x7b1e  call     int32 [System.Xml]System.Xml.XmlConvert::ToInt32(string)
0x7b23  callvirt instance void System.Web.Compilation.WCFModel.MetadataSource::set_SourceId(int32 value)
0x7b28  ldloc.3
0x7b29  ldc.i4.2
0x7b2a  ldc.i4.1
0x7b2b  stelem.i1
0x7b2c  br.s     loc_7B4D
0x7b2e  ldarg.0
0x7b2f  ldarg.0
0x7b30  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7b35  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x7b3a  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::IsXmlnsAttribute(string)
0x7b3f  brtrue.s loc_7B4D
0x7b41  ldarg.0
0x7b42  ldloc.2
0x7b43  ldstr    aAddressProtoco// ":Address, :Protocol, :SourceId"
0x7b48  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0x7b4d  ldarg.0
0x7b4e  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7b53  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToNextAttribute()
0x7b58  brtrue   loc_7A60
0x7b5d  ldarg.0
0x7b5e  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7b63  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToElement()
0x7b68  pop
0x7b69  ldarg.0
0x7b6a  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7b6f  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x7b74  brfalse.s loc_7B83
0x7b76  ldarg.0
0x7b77  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7b7c  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x7b81  ldloc.2
0x7b82  ret
0x7b83  ldarg.0
0x7b84  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7b89  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x7b8e  ldarg.0
0x7b8f  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7b94  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x7b99  pop
0x7b9a  ldc.i4.0
0x7b9b  stloc.s  4
0x7b9d  ldarg.0
0x7b9e  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0x7ba3  stloc.s  5
0x7ba5  br.s     loc_7BE5
0x7ba7  ldarg.0
0x7ba8  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7bad  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x7bb2  ldc.i4.1
0x7bb3  bne.un.s loc_7BC3
0x7bb5  ldarg.0
0x7bb6  ldloc.2
0x7bb7  ldstr    asc_3D8E0// ""
0x7bbc  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0x7bc1  br.s     loc_7BCF
0x7bc3  ldarg.0
0x7bc4  ldloc.2
0x7bc5  ldstr    asc_3D8E0// ""
0x7bca  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0x7bcf  ldarg.0
0x7bd0  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7bd5  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x7bda  pop
0x7bdb  ldarg.0
0x7bdc  ldloca.s 4
0x7bde  ldloca.s 5
0x7be0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::CheckReaderCount(int32&, int32&)
0x7be5  ldarg.0
0x7be6  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7beb  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x7bf0  ldc.i4.s 0xF
0x7bf2  beq.s    loc_7C01
0x7bf4  ldarg.0
0x7bf5  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x7bfa  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x7bff  brtrue.s loc_7BA7
0x7c01  ldarg.0
0x7c02  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadEndElement()
0x7c07  ldloc.2
0x7c08  ret
```
