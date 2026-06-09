# System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationWriterDataSvcMapFileImpl::Write4_MetadataType

- ea: `0x9d40`
- end: `0x9dbb`
- name: `System.Web.Compilation.WCFModel.DataSvcMapFileXmlSerializer.XmlSerializationWriterDataSvcMapFileImpl::Write4_MetadataType`
- size: `123`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x9c00`

## callees

- `0x9d40`

## string_xrefs

- `0x9dae`: `System.Web.Compilation.WCFModel.MetadataFile.MetadataType`

## pseudocode

```c

```

## disassembly

```asm
0x9d40  ldnull
0x9d41  stloc.0
0x9d42  ldarg.1
0x9d43  switch   loc_9D66, loc_9D6E, loc_9D76, loc_9D7E, loc_9D86, loc_9D8E, loc_9D96
0x9d64  br.s     loc_9D9E
0x9d66  ldstr    aUnknown// "Unknown"
0x9d6b  stloc.0
0x9d6c  br.s     loc_9DB9
0x9d6e  ldstr    aDisco_0// "Disco"
0x9d73  stloc.0
0x9d74  br.s     loc_9DB9
0x9d76  ldstr    aWsdl_0// "Wsdl"
0x9d7b  stloc.0
0x9d7c  br.s     loc_9DB9
0x9d7e  ldstr    aSchema_0// "Schema"
0x9d83  stloc.0
0x9d84  br.s     loc_9DB9
0x9d86  ldstr    aPolicy// "Policy"
0x9d8b  stloc.0
0x9d8c  br.s     loc_9DB9
0x9d8e  ldstr    aXml_0// "Xml"
0x9d93  stloc.0
0x9d94  br.s     loc_9DB9
0x9d96  ldstr    aEdmx// "Edmx"
0x9d9b  stloc.0
0x9d9c  br.s     loc_9DB9
0x9d9e  ldarg.0
0x9d9f  ldarg.1
0x9da0  conv.i8
0x9da1  stloc.1
0x9da2  ldloca.s 1
0x9da4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9da9  call     instance string [mscorlib]System.Int64::ToString(class [mscorlib]System.IFormatProvider)
0x9dae  ldstr    aSystemWebCompi// "System.Web.Compilation.WCFModel.Metadat"...
0x9db3  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateInvalidEnumValueException(object, string)
0x9db8  throw
0x9db9  ldloc.0
0x9dba  ret
```
