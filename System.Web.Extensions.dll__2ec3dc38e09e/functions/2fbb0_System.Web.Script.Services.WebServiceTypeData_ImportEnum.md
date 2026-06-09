# System.Web.Script.Services.WebServiceTypeData::ImportEnum

- ea: `0x2fbb0`
- end: `0x2fcad`
- name: `System.Web.Script.Services.WebServiceTypeData::ImportEnum`
- size: `253`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x2f8d0`

## callees

- `0x2ef60`
- `0x2f670`
- `0x2f8a0`
- `0x2fad0`
- `0x2fb20`
- `0x2fbb0`

## string_xrefs

- `0x2fbb7`: `http://www.w3.org/2001/XMLSchema`

## pseudocode

```c

```

## disassembly

```asm
0x2fbb0  ldarg.s  4
0x2fbb2  ldstr    aInt// "int"
0x2fbb7  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2001/XMLSchema"
0x2fbbc  newobj   instance void [System.Xml]System.Xml.XmlQualifiedName::.ctor(string, string)
0x2fbc1  ldarg.2
0x2fbc2  call     class [System.Xml]System.Xml.XmlQualifiedName System.Web.Script.Services.WebServiceTypeData::ImportActualType(class [System.Xml]System.Xml.Schema.XmlSchemaAnnotation annotation, class [System.Xml]System.Xml.XmlQualifiedName defaultTypeName, class [System.Xml]System.Xml.XmlQualifiedName typeName)
0x2fbc7  stloc.0
0x2fbc8  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<class [System.Xml]System.Xml.XmlQualifiedName, class [mscorlib]System.Type> System.Web.Script.Services.WebServiceTypeData::_nameToType
0x2fbcd  ldloc.0
0x2fbce  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<class [System.Xml]System.Xml.XmlQualifiedName, class [mscorlib]System.Type>::get_Item(void)
0x2fbd3  stloc.1
0x2fbd4  ldloc.1
0x2fbd5  ldtoken  [mscorlib]System.UInt64
0x2fbda  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2fbdf  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2fbe4  stloc.2
0x2fbe5  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x2fbea  stloc.3
0x2fbeb  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<int64>::.ctor()
0x2fbf0  stloc.s  4
0x2fbf2  ldarg.3
0x2fbf3  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection [System.Xml]System.Xml.Schema.XmlSchemaSimpleTypeRestriction::get_Facets()
0x2fbf8  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObjectEnumerator [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection::GetEnumerator()
0x2fbfd  stloc.s  5
0x2fbff  br.s     loc_2FC77
0x2fc01  ldloc.s  5
0x2fc03  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObject [System.Xml]System.Xml.Schema.XmlSchemaObjectEnumerator::get_Current()
0x2fc08  castclass [System.Xml]System.Xml.Schema.XmlSchemaFacet
0x2fc0d  stloc.s  6
0x2fc0f  ldloc.s  6
0x2fc11  isinst   [System.Xml]System.Xml.Schema.XmlSchemaEnumerationFacet
0x2fc16  stloc.s  7
0x2fc18  ldarg.2
0x2fc19  ldloc.s  7
0x2fc1b  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaAnnotation [System.Xml]System.Xml.Schema.XmlSchemaAnnotated::get_Annotation()
0x2fc20  call     class [System.Xml]System.Xml.XmlQualifiedName System.Web.Script.Services.WebServiceTypeData::get_EnumerationValueAnnotationName()
0x2fc25  call     class [System.Xml]System.Xml.XmlElement System.Web.Script.Services.WebServiceTypeData::ImportAnnotation(class [System.Xml]System.Xml.Schema.XmlSchemaAnnotation annotation, class [System.Xml]System.Xml.XmlQualifiedName annotationQualifiedName)
0x2fc2a  call     string System.Web.Script.Services.WebServiceTypeData::GetInnerText(class [System.Xml]System.Xml.XmlQualifiedName typeName, class [System.Xml]System.Xml.XmlElement xmlElement)
0x2fc2f  stloc.s  8
0x2fc31  ldloc.s  8
0x2fc33  brtrue.s loc_2FC40
0x2fc35  ldloc.3
0x2fc36  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x2fc3b  conv.i8
0x2fc3c  stloc.s  9
0x2fc3e  br.s     loc_2FC61
0x2fc40  ldloc.2
0x2fc41  brfalse.s loc_2FC53
0x2fc43  ldloc.s  8
0x2fc45  call     class [mscorlib]System.Globalization.NumberFormatInfo [mscorlib]System.Globalization.NumberFormatInfo::get_InvariantInfo()
0x2fc4a  call     unsigned int64 [mscorlib]System.UInt64::Parse(string, class [mscorlib]System.IFormatProvider)
0x2fc4f  stloc.s  9
0x2fc51  br.s     loc_2FC61
0x2fc53  ldloc.s  8
0x2fc55  call     class [mscorlib]System.Globalization.NumberFormatInfo [mscorlib]System.Globalization.NumberFormatInfo::get_InvariantInfo()
0x2fc5a  call     int64 [mscorlib]System.Int64::Parse(string, class [mscorlib]System.IFormatProvider)
0x2fc5f  stloc.s  9
0x2fc61  ldloc.3
0x2fc62  ldloc.s  7
0x2fc64  callvirt instance string [System.Xml]System.Xml.Schema.XmlSchemaFacet::get_Value()
0x2fc69  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x2fc6e  ldloc.s  4
0x2fc70  ldloc.s  9
0x2fc72  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int64>::Add(var<u1>)
0x2fc77  ldloc.s  5
0x2fc79  callvirt instance bool [System.Xml]System.Xml.Schema.XmlSchemaObjectEnumerator::MoveNext()
0x2fc7e  brtrue.s loc_2FC01
0x2fc80  leave.s  loc_2FC97
0x2fc82  ldloc.s  5
0x2fc84  isinst   [mscorlib]System.IDisposable
0x2fc89  stloc.s  0xA
0x2fc8b  ldloc.s  0xA
0x2fc8d  brfalse.s loc_2FC96
0x2fc8f  ldloc.s  0xA
0x2fc91  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2fc96  endfinally
0x2fc97  ldarg.0
0x2fc98  ldarg.1
0x2fc99  ldloc.3
0x2fc9a  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<string>::ToArray()
0x2fc9f  ldloc.s  4
0x2fca1  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<int64>::ToArray()
0x2fca6  ldloc.2
0x2fca7  newobj   instance void System.Web.Script.Services.WebServiceEnumData::.ctor(string typeName, string typeNamespace, string[] names, int64[] values, bool isULong)
0x2fcac  ret
```
