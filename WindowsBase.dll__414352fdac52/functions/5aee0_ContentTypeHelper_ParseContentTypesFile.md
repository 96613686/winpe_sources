# ContentTypeHelper::ParseContentTypesFile

- ea: `0x5aee0`
- end: `0x5b08d`
- name: `ContentTypeHelper::ParseContentTypesFile`
- size: `429`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x5ab70`

## callees

- `0x1f140`
- `0x1f530`
- `0x2c100`
- `0x5aee0`
- `0x5b090`
- `0x5b290`
- `0x5b340`

## string_xrefs

- `0x5b031`: `TypesXmlDoesNotMatchSchema`

## pseudocode

```c

```

## disassembly

```asm
0x5aee0  ldarg.0
0x5aee1  ldarg.1
0x5aee2  call     instance class [mscorlib]System.IO.Stream ContentTypeHelper::OpenContentTypeStream(class MS.Internal.IO.Zip.ZipFileInfoCollection zipFiles)
0x5aee7  stloc.0
0x5aee8  ldloc.0
0x5aee9  brtrue.s loc_5AEEC
0x5aeeb  ret
0x5aeec  ldloc.0
0x5aeed  stloc.1
0x5aeee  ldloc.0
0x5aeef  newobj   instance void [System.Xml]System.Xml.XmlTextReader::.ctor(class [mscorlib]System.IO.Stream)
0x5aef4  stloc.2
0x5aef5  ldloc.2
0x5aef6  ldc.i4.2
0x5aef7  callvirt instance void [System.Xml]System.Xml.XmlTextReader::set_WhitespaceHandling(valuetype [System.Xml]System.Xml.WhitespaceHandling)
0x5aefc  ldloc.2
0x5aefd  ldc.i4.1
0x5aefe  callvirt instance void [System.Xml]System.Xml.XmlTextReader::set_ProhibitDtd(bool)
0x5af03  ldloc.2
0x5af04  call     void MS.Internal.IO.Packaging.PackagingUtilities::PerformInitailReadAndVerifyEncoding(class [System.Xml]System.Xml.XmlTextReader reader)
0x5af09  ldloc.2
0x5af0a  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x5af0f  pop
0x5af10  ldloc.2
0x5af11  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x5af16  ldc.i4.1
0x5af17  bne.un   loc_5B05B
0x5af1c  ldloc.2
0x5af1d  callvirt instance int32 [System.Xml]System.Xml.XmlReader::get_Depth()
0x5af22  brtrue   loc_5B05B
0x5af27  ldloc.2
0x5af28  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x5af2d  ldsfld   string ContentTypeHelper::TypesNamespaceUri
0x5af32  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x5af37  brtrue   loc_5B05B
0x5af3c  ldloc.2
0x5af3d  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x5af42  ldsfld   string ContentTypeHelper::TypesTagName
0x5af47  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x5af4c  brtrue   loc_5B05B
0x5af51  ldloc.2
0x5af52  call     int32 MS.Internal.IO.Packaging.PackagingUtilities::GetNonXmlnsAttributeCount(class [System.Xml]System.Xml.XmlReader reader)
0x5af57  ldc.i4.0
0x5af58  ble      loc_5B04E
0x5af5d  ldstr    aTypestaghasext// "TypesTagHasExtraAttributes"
0x5af62  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x5af67  ldnull
0x5af68  ldloc.2
0x5af69  callvirt instance int32 [System.Xml]System.Xml.XmlTextReader::get_LineNumber()
0x5af6e  ldloc.2
0x5af6f  callvirt instance int32 [System.Xml]System.Xml.XmlTextReader::get_LinePosition()
0x5af74  newobj   instance void [System.Xml]System.Xml.XmlException::.ctor(string, class [mscorlib]System.Exception, int32, int32)
0x5af79  throw
0x5af7a  ldloc.2
0x5af7b  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x5af80  pop
0x5af81  ldloc.2
0x5af82  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x5af87  brfalse  loc_5B04E
0x5af8c  ldloc.2
0x5af8d  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x5af92  ldc.i4.1
0x5af93  bne.un.s loc_5AFCE
0x5af95  ldloc.2
0x5af96  callvirt instance int32 [System.Xml]System.Xml.XmlReader::get_Depth()
0x5af9b  ldc.i4.1
0x5af9c  bne.un.s loc_5AFCE
0x5af9e  ldloc.2
0x5af9f  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x5afa4  ldsfld   string ContentTypeHelper::TypesNamespaceUri
0x5afa9  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x5afae  brtrue.s loc_5AFCE
0x5afb0  ldloc.2
0x5afb1  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x5afb6  ldsfld   string ContentTypeHelper::DefaultTagName
0x5afbb  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x5afc0  brtrue.s loc_5AFCE
0x5afc2  ldarg.0
0x5afc3  ldloc.2
0x5afc4  call     instance void ContentTypeHelper::ProcessDefaultTagAttributes(class [System.Xml]System.Xml.XmlTextReader reader)
0x5afc9  br       loc_5B04E
0x5afce  ldloc.2
0x5afcf  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x5afd4  ldc.i4.1
0x5afd5  bne.un.s loc_5B00D
0x5afd7  ldloc.2
0x5afd8  callvirt instance int32 [System.Xml]System.Xml.XmlReader::get_Depth()
0x5afdd  ldc.i4.1
0x5afde  bne.un.s loc_5B00D
0x5afe0  ldloc.2
0x5afe1  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x5afe6  ldsfld   string ContentTypeHelper::TypesNamespaceUri
0x5afeb  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x5aff0  brtrue.s loc_5B00D
0x5aff2  ldloc.2
0x5aff3  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x5aff8  ldsfld   string ContentTypeHelper::OverrideTagName
0x5affd  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x5b002  brtrue.s loc_5B00D
0x5b004  ldarg.0
0x5b005  ldloc.2
0x5b006  call     instance void ContentTypeHelper::ProcessOverrideTagAttributes(class [System.Xml]System.Xml.XmlTextReader reader)
0x5b00b  br.s     loc_5B04E
0x5b00d  ldloc.2
0x5b00e  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x5b013  ldc.i4.s 0xF
0x5b015  bne.un.s loc_5B031
0x5b017  ldloc.2
0x5b018  callvirt instance int32 [System.Xml]System.Xml.XmlReader::get_Depth()
0x5b01d  brtrue.s loc_5B031
0x5b01f  ldloc.2
0x5b020  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x5b025  ldsfld   string ContentTypeHelper::TypesTagName
0x5b02a  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x5b02f  brfalse.s loc_5B04E
0x5b031  ldstr    aTypesxmldoesno// "TypesXmlDoesNotMatchSchema"
0x5b036  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x5b03b  ldnull
0x5b03c  ldloc.2
0x5b03d  callvirt instance int32 [System.Xml]System.Xml.XmlTextReader::get_LineNumber()
0x5b042  ldloc.2
0x5b043  callvirt instance int32 [System.Xml]System.Xml.XmlTextReader::get_LinePosition()
0x5b048  newobj   instance void [System.Xml]System.Xml.XmlException::.ctor(string, class [mscorlib]System.Exception, int32, int32)
0x5b04d  throw
0x5b04e  ldloc.2
0x5b04f  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x5b054  brtrue   loc_5AF7A
0x5b059  leave.s  loc_5B08C
0x5b05b  ldstr    aTypeselementex// "TypesElementExpected"
0x5b060  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x5b065  ldnull
0x5b066  ldloc.2
0x5b067  callvirt instance int32 [System.Xml]System.Xml.XmlTextReader::get_LineNumber()
0x5b06c  ldloc.2
0x5b06d  callvirt instance int32 [System.Xml]System.Xml.XmlTextReader::get_LinePosition()
0x5b072  newobj   instance void [System.Xml]System.Xml.XmlException::.ctor(string, class [mscorlib]System.Exception, int32, int32)
0x5b077  throw
0x5b078  ldloc.2
0x5b079  brfalse.s loc_5B081
0x5b07b  ldloc.2
0x5b07c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5b081  endfinally
0x5b082  ldloc.1
0x5b083  brfalse.s loc_5B08B
0x5b085  ldloc.1
0x5b086  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5b08b  endfinally
0x5b08c  ret
```
