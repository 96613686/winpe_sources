# System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationWriterSvcMapFileImpl::Write6_ProxySerializerType

- ea: `0x6bc0`
- end: `0x6c0b`
- name: `System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationWriterSvcMapFileImpl::Write6_ProxySerializerType`
- size: `75`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x6690`

## callees

- `0x6bc0`

## string_xrefs

- `0x6be6`: `XmlSerializer`
- `0x6bfe`: `System.Web.Compilation.WCFModel.ClientOptions.ProxySerializerType`

## pseudocode

```c

```

## disassembly

```asm
0x6bc0  ldnull
0x6bc1  stloc.0
0x6bc2  ldarg.1
0x6bc3  switch   loc_6BD6, loc_6BDE, loc_6BE6
0x6bd4  br.s     loc_6BEE
0x6bd6  ldstr    aAuto// "Auto"
0x6bdb  stloc.0
0x6bdc  br.s     loc_6C09
0x6bde  ldstr    aDatacontractse// "DataContractSerializer"
0x6be3  stloc.0
0x6be4  br.s     loc_6C09
0x6be6  ldstr    aXmlserializer// "XmlSerializer"
0x6beb  stloc.0
0x6bec  br.s     loc_6C09
0x6bee  ldarg.0
0x6bef  ldarg.1
0x6bf0  conv.i8
0x6bf1  stloc.1
0x6bf2  ldloca.s 1
0x6bf4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6bf9  call     instance string [mscorlib]System.Int64::ToString(class [mscorlib]System.IFormatProvider)
0x6bfe  ldstr    aSystemWebCompi_0// "System.Web.Compilation.WCFModel.ClientO"...
0x6c03  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateInvalidEnumValueException(object, string)
0x6c08  throw
0x6c09  ldloc.0
0x6c0a  ret
```
