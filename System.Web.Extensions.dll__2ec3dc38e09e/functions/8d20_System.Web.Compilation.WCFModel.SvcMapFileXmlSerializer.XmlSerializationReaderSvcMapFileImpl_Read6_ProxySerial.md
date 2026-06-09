# System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::Read6_ProxySerializerType

- ea: `0x8d20`
- end: `0x8d61`
- name: `System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationReaderSvcMapFileImpl::Read6_ProxySerializerType`
- size: `65`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x7c10`

## callees

- `0x8d20`

## string_xrefs

- `0x8d3b`: `XmlSerializer`

## pseudocode

```c

```

## disassembly

```asm
0x8d20  ldarg.1
0x8d21  ldstr    aAuto// "Auto"
0x8d26  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8d2b  brtrue.s loc_8D49
0x8d2d  ldarg.1
0x8d2e  ldstr    aDatacontractse// "DataContractSerializer"
0x8d33  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8d38  brtrue.s loc_8D4B
0x8d3a  ldarg.1
0x8d3b  ldstr    aXmlserializer// "XmlSerializer"
0x8d40  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8d45  brtrue.s loc_8D4D
0x8d47  br.s     loc_8D4F
0x8d49  ldc.i4.0
0x8d4a  ret
0x8d4b  ldc.i4.1
0x8d4c  ret
0x8d4d  ldc.i4.2
0x8d4e  ret
0x8d4f  ldarg.0
0x8d50  ldarg.1
0x8d51  ldtoken  ProxySerializerType
0x8d56  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8d5b  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationReader::CreateUnknownConstantException(string, class [mscorlib]System.Type)
0x8d60  throw
```
