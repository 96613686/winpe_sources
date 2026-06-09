# System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationWriterSvcMapFileImpl::Write12_MetadataType

- ea: `0x6560`
- end: `0x65db`
- name: `System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationWriterSvcMapFileImpl::Write12_MetadataType`
- size: `123`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x6420`

## callees

- `0x6560`

## string_xrefs

- `0x65ce`: `System.Web.Compilation.WCFModel.MetadataFile.MetadataType`

## pseudocode

```c

```

## disassembly

```asm
0x6560  ldnull
0x6561  stloc.0
0x6562  ldarg.1
0x6563  switch   loc_6586, loc_658E, loc_6596, loc_659E, loc_65A6, loc_65AE, loc_65B6
0x6584  br.s     loc_65BE
0x6586  ldstr    aUnknown// "Unknown"
0x658b  stloc.0
0x658c  br.s     loc_65D9
0x658e  ldstr    aDisco_0// "Disco"
0x6593  stloc.0
0x6594  br.s     loc_65D9
0x6596  ldstr    aWsdl_0// "Wsdl"
0x659b  stloc.0
0x659c  br.s     loc_65D9
0x659e  ldstr    aSchema_0// "Schema"
0x65a3  stloc.0
0x65a4  br.s     loc_65D9
0x65a6  ldstr    aPolicy// "Policy"
0x65ab  stloc.0
0x65ac  br.s     loc_65D9
0x65ae  ldstr    aXml_0// "Xml"
0x65b3  stloc.0
0x65b4  br.s     loc_65D9
0x65b6  ldstr    aEdmx// "Edmx"
0x65bb  stloc.0
0x65bc  br.s     loc_65D9
0x65be  ldarg.0
0x65bf  ldarg.1
0x65c0  conv.i8
0x65c1  stloc.1
0x65c2  ldloca.s 1
0x65c4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x65c9  call     instance string [mscorlib]System.Int64::ToString(class [mscorlib]System.IFormatProvider)
0x65ce  ldstr    aSystemWebCompi// "System.Web.Compilation.WCFModel.Metadat"...
0x65d3  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateInvalidEnumValueException(object, string)
0x65d8  throw
0x65d9  ldloc.0
0x65da  ret
```
