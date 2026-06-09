# System.Xml.Serialization.XmlSchemaExporter::ExportNonXsdPrimitiveMapping

- ea: `0x7f680`
- end: `0x7f6d6`
- name: `System.Xml.Serialization.XmlSchemaExporter::ExportNonXsdPrimitiveMapping`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x7fb70`

## callees

- `0x132e0`
- `0x68c10`
- `0x68c50`
- `0x72be0`
- `0x7f340`
- `0x7f3f0`
- `0x7f480`
- `0x7f680`
- `0xd6af0`

## string_xrefs

- `0x7f693`: `http://microsoft.com/wsdl/types/`
- `0x7f6a1`: `http://microsoft.com/wsdl/types/`
- `0x7f6cb`: `http://microsoft.com/wsdl/types/`

## pseudocode

```c

```

## disassembly

```asm
0x7f680  ldarg.1
0x7f681  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x7f686  callvirt instance class System.Xml.Schema.XmlSchemaType System.Xml.Serialization.TypeDesc::get_DataType()
0x7f68b  castclass System.Xml.Schema.XmlSchemaSimpleType
0x7f690  stloc.0
0x7f691  ldarg.0
0x7f692  ldloc.0
0x7f693  ldstr    aHttpMicrosoftC// "http://microsoft.com/wsdl/types/"
0x7f698  call     instance bool System.Xml.Serialization.XmlSchemaExporter::SchemaContainsItem(class System.Xml.Schema.XmlSchemaObject item, string ns)
0x7f69d  brtrue.s loc_7F6AE
0x7f69f  ldarg.0
0x7f6a0  ldloc.0
0x7f6a1  ldstr    aHttpMicrosoftC// "http://microsoft.com/wsdl/types/"
0x7f6a6  ldarg.2
0x7f6a7  call     instance void System.Xml.Serialization.XmlSchemaExporter::AddSchemaItem(class System.Xml.Schema.XmlSchemaObject item, string ns, string referencingNs)
0x7f6ac  br.s     loc_7F6BB
0x7f6ae  ldarg.0
0x7f6af  ldarg.1
0x7f6b0  callvirt instance string System.Xml.Serialization.TypeMapping::get_Namespace()
0x7f6b5  ldarg.2
0x7f6b6  call     instance void System.Xml.Serialization.XmlSchemaExporter::AddSchemaImport(string ns, string referencingNs)
0x7f6bb  ldarg.1
0x7f6bc  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x7f6c1  callvirt instance class System.Xml.Schema.XmlSchemaType System.Xml.Serialization.TypeDesc::get_DataType()
0x7f6c6  callvirt instance string System.Xml.Schema.XmlSchemaType::get_Name()
0x7f6cb  ldstr    aHttpMicrosoftC// "http://microsoft.com/wsdl/types/"
0x7f6d0  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0x7f6d5  ret
```
