# System.Web.Script.Services.WebServiceTypeData::CheckIfEnumRestriction

- ea: `0x2f800`
- end: `0x2f896`
- name: `System.Web.Script.Services.WebServiceTypeData::CheckIfEnumRestriction`
- size: `150`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x2f7a0`

## callees

- `0x2f800`

## string_xrefs

- `0x2f875`: `http://www.w3.org/2001/XMLSchema`

## pseudocode

```c

```

## disassembly

```asm
0x2f800  ldarg.0
0x2f801  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection [System.Xml]System.Xml.Schema.XmlSchemaSimpleTypeRestriction::get_Facets()
0x2f806  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObjectEnumerator [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection::GetEnumerator()
0x2f80b  stloc.0
0x2f80c  br.s     loc_2F826
0x2f80e  ldloc.0
0x2f80f  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObject [System.Xml]System.Xml.Schema.XmlSchemaObjectEnumerator::get_Current()
0x2f814  castclass [System.Xml]System.Xml.Schema.XmlSchemaFacet
0x2f819  stloc.1
0x2f81a  ldloc.1
0x2f81b  isinst   [System.Xml]System.Xml.Schema.XmlSchemaEnumerationFacet
0x2f820  brtrue.s loc_2F826
0x2f822  ldc.i4.0
0x2f823  stloc.2
0x2f824  leave.s  loc_2F894
0x2f826  ldloc.0
0x2f827  callvirt instance bool [System.Xml]System.Xml.Schema.XmlSchemaObjectEnumerator::MoveNext()
0x2f82c  brtrue.s loc_2F80E
0x2f82e  leave.s  loc_2F841
0x2f830  ldloc.0
0x2f831  isinst   [mscorlib]System.IDisposable
0x2f836  stloc.3
0x2f837  ldloc.3
0x2f838  brfalse.s loc_2F840
0x2f83a  ldloc.3
0x2f83b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2f840  endfinally
0x2f841  ldarg.0
0x2f842  callvirt instance class [System.Xml]System.Xml.XmlQualifiedName [System.Xml]System.Xml.Schema.XmlSchemaSimpleTypeRestriction::get_BaseTypeName()
0x2f847  ldsfld   class [System.Xml]System.Xml.XmlQualifiedName [System.Xml]System.Xml.XmlQualifiedName::Empty
0x2f84c  call     bool [System.Xml]System.Xml.XmlQualifiedName::op_Inequality(class [System.Xml]System.Xml.XmlQualifiedName, class [System.Xml]System.Xml.XmlQualifiedName)
0x2f851  brfalse.s loc_2F892
0x2f853  ldarg.0
0x2f854  callvirt instance class [System.Xml]System.Xml.XmlQualifiedName [System.Xml]System.Xml.Schema.XmlSchemaSimpleTypeRestriction::get_BaseTypeName()
0x2f859  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Name()
0x2f85e  ldstr    aString_0// "string"
0x2f863  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2f868  brfalse.s loc_2F890
0x2f86a  ldarg.0
0x2f86b  callvirt instance class [System.Xml]System.Xml.XmlQualifiedName [System.Xml]System.Xml.Schema.XmlSchemaSimpleTypeRestriction::get_BaseTypeName()
0x2f870  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Namespace()
0x2f875  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2001/XMLSchema"
0x2f87a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2f87f  brfalse.s loc_2F890
0x2f881  ldarg.0
0x2f882  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaObjectCollection [System.Xml]System.Xml.Schema.XmlSchemaSimpleTypeRestriction::get_Facets()
0x2f887  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x2f88c  ldc.i4.0
0x2f88d  cgt
0x2f88f  ret
0x2f890  ldc.i4.0
0x2f891  ret
0x2f892  ldc.i4.0
0x2f893  ret
0x2f894  ldloc.2
0x2f895  ret
```
