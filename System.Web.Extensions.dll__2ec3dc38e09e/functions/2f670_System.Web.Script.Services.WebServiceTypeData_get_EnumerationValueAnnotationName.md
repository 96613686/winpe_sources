# System.Web.Script.Services.WebServiceTypeData::get_EnumerationValueAnnotationName

- ea: `0x2f670`
- end: `0x2f697`
- name: `System.Web.Script.Services.WebServiceTypeData::get_EnumerationValueAnnotationName`
- size: `39`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2fbb0`

## callees

- `0x2f670`

## string_xrefs

- `0x2f682`: `http://schemas.microsoft.com/2003/10/Serialization/`

## pseudocode

```c

```

## disassembly

```asm
0x2f670  ldsfld   class [System.Xml]System.Xml.XmlQualifiedName System.Web.Script.Services.WebServiceTypeData::enumerationValueAnnotationName
0x2f675  ldnull
0x2f676  call     bool [System.Xml]System.Xml.XmlQualifiedName::op_Equality(class [System.Xml]System.Xml.XmlQualifiedName, class [System.Xml]System.Xml.XmlQualifiedName)
0x2f67b  brfalse.s loc_2F691
0x2f67d  ldstr    aEnumerationval// "EnumerationValue"
0x2f682  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/2003/10/Se"...
0x2f687  newobj   instance void [System.Xml]System.Xml.XmlQualifiedName::.ctor(string, string)
0x2f68c  stsfld   class [System.Xml]System.Xml.XmlQualifiedName System.Web.Script.Services.WebServiceTypeData::enumerationValueAnnotationName
0x2f691  ldsfld   class [System.Xml]System.Xml.XmlQualifiedName System.Web.Script.Services.WebServiceTypeData::enumerationValueAnnotationName
0x2f696  ret
```
