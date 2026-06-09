# System.Web.Script.Services.WebServiceTypeData::get_ActualTypeAnnotationName

- ea: `0x2f640`
- end: `0x2f667`
- name: `System.Web.Script.Services.WebServiceTypeData::get_ActualTypeAnnotationName`
- size: `39`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2fad0`

## callees

- `0x2f640`

## string_xrefs

- `0x2f652`: `http://schemas.microsoft.com/2003/10/Serialization/`

## pseudocode

```c

```

## disassembly

```asm
0x2f640  ldsfld   class [System.Xml]System.Xml.XmlQualifiedName System.Web.Script.Services.WebServiceTypeData::actualTypeAnnotationName
0x2f645  ldnull
0x2f646  call     bool [System.Xml]System.Xml.XmlQualifiedName::op_Equality(class [System.Xml]System.Xml.XmlQualifiedName, class [System.Xml]System.Xml.XmlQualifiedName)
0x2f64b  brfalse.s loc_2F661
0x2f64d  ldstr    aActualtype// "ActualType"
0x2f652  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/2003/10/Se"...
0x2f657  newobj   instance void [System.Xml]System.Xml.XmlQualifiedName::.ctor(string, string)
0x2f65c  stsfld   class [System.Xml]System.Xml.XmlQualifiedName System.Web.Script.Services.WebServiceTypeData::actualTypeAnnotationName
0x2f661  ldsfld   class [System.Xml]System.Xml.XmlQualifiedName System.Web.Script.Services.WebServiceTypeData::actualTypeAnnotationName
0x2f666  ret
```
