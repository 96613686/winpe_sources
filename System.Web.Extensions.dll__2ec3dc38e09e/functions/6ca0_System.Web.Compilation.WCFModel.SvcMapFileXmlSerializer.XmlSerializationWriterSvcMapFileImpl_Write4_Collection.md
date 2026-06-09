# System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationWriterSvcMapFileImpl::Write4_CollectionCategory

- ea: `0x6ca0`
- end: `0x6ceb`
- name: `System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationWriterSvcMapFileImpl::Write4_CollectionCategory`
- size: `75`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x6c10`

## callees

- `0x6ca0`

## string_xrefs

- `0x6cde`: `System.Web.Compilation.WCFModel.ReferencedCollectionType.CollectionCategory`

## pseudocode

```c

```

## disassembly

```asm
0x6ca0  ldnull
0x6ca1  stloc.0
0x6ca2  ldarg.1
0x6ca3  switch   loc_6CB6, loc_6CBE, loc_6CC6
0x6cb4  br.s     loc_6CCE
0x6cb6  ldstr    aUnknown// "Unknown"
0x6cbb  stloc.0
0x6cbc  br.s     loc_6CE9
0x6cbe  ldstr    aList// "List"
0x6cc3  stloc.0
0x6cc4  br.s     loc_6CE9
0x6cc6  ldstr    aDictionary// "Dictionary"
0x6ccb  stloc.0
0x6ccc  br.s     loc_6CE9
0x6cce  ldarg.0
0x6ccf  ldarg.1
0x6cd0  conv.i8
0x6cd1  stloc.1
0x6cd2  ldloca.s 1
0x6cd4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6cd9  call     instance string [mscorlib]System.Int64::ToString(class [mscorlib]System.IFormatProvider)
0x6cde  ldstr    aSystemWebCompi_1// "System.Web.Compilation.WCFModel.Referen"...
0x6ce3  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateInvalidEnumValueException(object, string)
0x6ce8  throw
0x6ce9  ldloc.0
0x6cea  ret
```
