# System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationWriterSvcMapFileImpl::Write7_ReferencedAssembly

- ea: `0x6b40`
- end: `0x6bb2`
- name: `System.Web.Compilation.WCFModel.SvcMapFileXmlSerializer.XmlSerializationWriterSvcMapFileImpl::Write7_ReferencedAssembly`
- size: `114`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6690`

## callees

- `0x3120`
- `0x6b40`

## string_xrefs

- `0x6b8a`: `urn:schemas-microsoft-com:xml-wcfservicemap`

## pseudocode

```c

```

## disassembly

```asm
0x6b40  ldarg.3
0x6b41  brtrue.s loc_6B50
0x6b43  ldarg.s  4
0x6b45  brfalse.s loc_6B4F
0x6b47  ldarg.0
0x6b48  ldarg.1
0x6b49  ldarg.2
0x6b4a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x6b4f  ret
0x6b50  ldarg.s  5
0x6b52  brtrue.s loc_6B75
0x6b54  ldarg.3
0x6b55  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x6b5a  stloc.0
0x6b5b  ldloc.0
0x6b5c  ldtoken  System.Web.Compilation.WCFModel.ReferencedAssembly
0x6b61  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6b66  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x6b6b  brtrue.s loc_6B75
0x6b6d  ldarg.0
0x6b6e  ldarg.3
0x6b6f  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x6b74  throw
0x6b75  ldarg.0
0x6b76  ldarg.1
0x6b77  ldarg.2
0x6b78  ldarg.3
0x6b79  ldc.i4.0
0x6b7a  ldnull
0x6b7b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x6b80  ldarg.s  5
0x6b82  brfalse.s loc_6B94
0x6b84  ldarg.0
0x6b85  ldstr    aReferencedasse_0// "ReferencedAssembly"
0x6b8a  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:xml-wcfservic"...
0x6b8f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x6b94  ldarg.0
0x6b95  ldstr    aAssemblyname_0// "AssemblyName"
0x6b9a  ldstr    asc_3D8E0// ""
0x6b9f  ldarg.3
0x6ba0  callvirt instance string System.Web.Compilation.WCFModel.ReferencedAssembly::get_AssemblyName()
0x6ba5  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x6baa  ldarg.0
0x6bab  ldarg.3
0x6bac  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x6bb1  ret
```
