# System.Xml.Serialization.SoapSchemaExporter::ExportNonXsdPrimitiveMapping

- ea: `0x70430`
- end: `0x70480`
- name: `System.Xml.Serialization.SoapSchemaExporter::ExportNonXsdPrimitiveMapping`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x70370`

## callees

- `0x132e0`
- `0x68c50`
- `0x70210`
- `0x70280`
- `0x702f0`
- `0x70430`
- `0x72be0`
- `0xd6af0`

## string_xrefs

- `0x7043e`: `http://microsoft.com/wsdl/types/`
- `0x7044c`: `http://microsoft.com/wsdl/types/`
- `0x7045a`: `http://microsoft.com/wsdl/types/`
- `0x70475`: `http://microsoft.com/wsdl/types/`

## pseudocode

```c

```

## disassembly

```asm
0x70430  ldarg.1
0x70431  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x70436  callvirt instance class System.Xml.Schema.XmlSchemaType System.Xml.Serialization.TypeDesc::get_DataType()
0x7043b  stloc.0
0x7043c  ldarg.0
0x7043d  ldloc.0
0x7043e  ldstr    aHttpMicrosoftC// "http://microsoft.com/wsdl/types/"
0x70443  call     instance bool System.Xml.Serialization.SoapSchemaExporter::SchemaContainsItem(class System.Xml.Schema.XmlSchemaObject item, string ns)
0x70448  brtrue.s loc_70459
0x7044a  ldarg.0
0x7044b  ldloc.0
0x7044c  ldstr    aHttpMicrosoftC// "http://microsoft.com/wsdl/types/"
0x70451  ldarg.2
0x70452  call     instance void System.Xml.Serialization.SoapSchemaExporter::AddSchemaItem(class System.Xml.Schema.XmlSchemaObject item, string ns, string referencingNs)
0x70457  br.s     loc_70465
0x70459  ldarg.0
0x7045a  ldstr    aHttpMicrosoftC// "http://microsoft.com/wsdl/types/"
0x7045f  ldarg.2
0x70460  call     instance void System.Xml.Serialization.SoapSchemaExporter::AddSchemaImport(string ns, string referencingNs)
0x70465  ldarg.1
0x70466  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x7046b  callvirt instance class System.Xml.Schema.XmlSchemaType System.Xml.Serialization.TypeDesc::get_DataType()
0x70470  callvirt instance string System.Xml.Schema.XmlSchemaType::get_Name()
0x70475  ldstr    aHttpMicrosoftC// "http://microsoft.com/wsdl/types/"
0x7047a  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0x7047f  ret
```
