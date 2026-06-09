# System.Web.Script.Services.WebServiceTypeData::GetKnownTypes

- ea: `0x2f8d0`
- end: `0x2fa44`
- name: `System.Web.Script.Services.WebServiceTypeData::GetKnownTypes`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x2ed50`

## callees

- `0x2f630`
- `0x2f6b0`
- `0x2f6c0`
- `0x2f700`
- `0x2f7a0`
- `0x2f8d0`
- `0x2fbb0`

## string_xrefs

- `0x2f90f`: `http://schemas.microsoft.com/2003/10/Serialization/`

## pseudocode

```c

```

## disassembly

```asm
0x2f8d0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class System.Web.Script.Services.WebServiceTypeData>::.ctor()
0x2f8d5  stloc.0
0x2f8d6  newobj   instance void [System.Runtime.Serialization]System.Runtime.Serialization.XsdDataContractExporter::.ctor()
0x2f8db  stloc.1
0x2f8dc  ldloc.1
0x2f8dd  ldarg.0
0x2f8de  callvirt instance void [System.Runtime.Serialization]System.Runtime.Serialization.XsdDataContractExporter::Export(class [mscorlib]System.Type)
0x2f8e3  ldloc.1
0x2f8e4  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaSet [System.Runtime.Serialization]System.Runtime.Serialization.XsdDataContractExporter::get_Schemas()
0x2f8e9  callvirt instance class [mscorlib]System.Collections.ICollection [System.Xml]System.Xml.Schema.XmlSchemaSet::Schemas()
0x2f8ee  stloc.2
0x2f8ef  ldloc.2
0x2f8f0  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x2f8f5  stloc.3
0x2f8f6  br       loc_2FA21
0x2f8fb  ldloc.3
0x2f8fc  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x2f901  castclass [System.Xml]System.Xml.Schema.XmlSchema
0x2f906  stloc.s  4
0x2f908  ldloc.s  4
0x2f90a  callvirt instance string [System.Xml]System.Xml.Schema.XmlSchema::get_TargetNamespace()
0x2f90f  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/2003/10/Se"...
0x2f914  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2f919  brtrue   loc_2FA21
0x2f91e  ldloc.s  4
0x2f920  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection [System.Xml]System.Xml.Schema.XmlSchema::get_Items()
0x2f925  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObjectEnumerator [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection::GetEnumerator()
0x2f92a  stloc.s  5
0x2f92c  br       loc_2F9FE
0x2f931  ldloc.s  5
0x2f933  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObject [System.Xml]System.Xml.Schema.XmlSchemaObjectEnumerator::get_Current()
0x2f938  stloc.s  6
0x2f93a  ldloc.s  6
0x2f93c  isinst   [System.Xml]System.Xml.Schema.XmlSchemaType
0x2f941  stloc.s  7
0x2f943  ldloc.s  4
0x2f945  callvirt instance string [System.Xml]System.Xml.Schema.XmlSchema::get_TargetNamespace()
0x2f94a  call     string [System.Xml]System.Xml.XmlConvert::DecodeName(string)
0x2f94f  stloc.s  8
0x2f951  ldloc.s  7
0x2f953  brfalse  loc_2F9FE
0x2f958  ldloc.s  7
0x2f95a  callvirt instance string [System.Xml]System.Xml.Schema.XmlSchemaType::get_Name()
0x2f95f  ldarg.1
0x2f960  callvirt instance string System.Web.Script.Services.WebServiceTypeData::get_TypeName()
0x2f965  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2f96a  brfalse.s loc_2F97E
0x2f96c  ldloc.s  8
0x2f96e  ldarg.1
0x2f96f  callvirt instance string System.Web.Script.Services.WebServiceTypeData::get_TypeNamespace()
0x2f974  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2f979  brtrue   loc_2F9FE
0x2f97e  ldloc.s  7
0x2f980  callvirt instance string [System.Xml]System.Xml.Schema.XmlSchemaType::get_Name()
0x2f985  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2f98a  brtrue.s loc_2F9FE
0x2f98c  ldnull
0x2f98d  stloc.s  9
0x2f98f  ldloc.s  7
0x2f991  isinst   [System.Xml]System.Xml.Schema.XmlSchemaSimpleType
0x2f996  ldloca.s 0xA
0x2f998  call     bool System.Web.Script.Services.WebServiceTypeData::CheckIfEnum(class [System.Xml]System.Xml.Schema.XmlSchemaSimpleType simpleType, [out] class [System.Xml]System.Xml.Schema.XmlSchemaSimpleTypeRestriction& simpleTypeRestriction)
0x2f99d  brfalse.s loc_2F9C6
0x2f99f  ldloc.s  7
0x2f9a1  callvirt instance string [System.Xml]System.Xml.Schema.XmlSchemaType::get_Name()
0x2f9a6  call     string [System.Xml]System.Xml.XmlConvert::DecodeName(string)
0x2f9ab  ldloc.s  8
0x2f9ad  ldloc.s  7
0x2f9af  callvirt instance class [System.Xml]System.Xml.XmlQualifiedName [System.Xml]System.Xml.Schema.XmlSchemaType::get_QualifiedName()
0x2f9b4  ldloc.s  0xA
0x2f9b6  ldloc.s  7
0x2f9b8  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaAnnotation [System.Xml]System.Xml.Schema.XmlSchemaAnnotated::get_Annotation()
0x2f9bd  call     class System.Web.Script.Services.WebServiceEnumData System.Web.Script.Services.WebServiceTypeData::ImportEnum(string typeName, string typeNamespace, class [System.Xml]System.Xml.XmlQualifiedName typeQualifiedName, class [System.Xml]System.Xml.Schema.XmlSchemaSimpleTypeRestriction restriction, class [System.Xml]System.Xml.Schema.XmlSchemaAnnotation annotation)
0x2f9c2  stloc.s  9
0x2f9c4  br.s     loc_2F9F2
0x2f9c6  ldloc.s  7
0x2f9c8  isinst   [System.Xml]System.Xml.Schema.XmlSchemaComplexType
0x2f9cd  call     bool System.Web.Script.Services.WebServiceTypeData::CheckIfCollection(class [System.Xml]System.Xml.Schema.XmlSchemaComplexType type)
0x2f9d2  brtrue.s loc_2F9FE
0x2f9d4  ldloc.s  7
0x2f9d6  isinst   [System.Xml]System.Xml.Schema.XmlSchemaSimpleType
0x2f9db  brtrue.s loc_2F9F2
0x2f9dd  ldloc.s  7
0x2f9df  callvirt instance string [System.Xml]System.Xml.Schema.XmlSchemaType::get_Name()
0x2f9e4  call     string [System.Xml]System.Xml.XmlConvert::DecodeName(string)
0x2f9e9  ldloc.s  8
0x2f9eb  newobj   instance void System.Web.Script.Services.WebServiceTypeData::.ctor(string name, string ns)
0x2f9f0  stloc.s  9
0x2f9f2  ldloc.s  9
0x2f9f4  brfalse.s loc_2F9FE
0x2f9f6  ldloc.0
0x2f9f7  ldloc.s  9
0x2f9f9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Web.Script.Services.WebServiceTypeData>::Add(var<u1>)
0x2f9fe  ldloc.s  5
0x2fa00  callvirt instance bool [System.Xml]System.Xml.Schema.XmlSchemaObjectEnumerator::MoveNext()
0x2fa05  brtrue   loc_2F931
0x2fa0a  leave.s  loc_2FA21
0x2fa0c  ldloc.s  5
0x2fa0e  isinst   [mscorlib]System.IDisposable
0x2fa13  stloc.s  0xB
0x2fa15  ldloc.s  0xB
0x2fa17  brfalse.s loc_2FA20
0x2fa19  ldloc.s  0xB
0x2fa1b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2fa20  endfinally
0x2fa21  ldloc.3
0x2fa22  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2fa27  brtrue   loc_2F8FB
0x2fa2c  leave.s  loc_2FA42
0x2fa2e  ldloc.3
0x2fa2f  isinst   [mscorlib]System.IDisposable
0x2fa34  stloc.s  0xB
0x2fa36  ldloc.s  0xB
0x2fa38  brfalse.s loc_2FA41
0x2fa3a  ldloc.s  0xB
0x2fa3c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2fa41  endfinally
0x2fa42  ldloc.0
0x2fa43  ret
```
