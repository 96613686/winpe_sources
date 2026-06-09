# System.Xml.Serialization.XmlSchemaExporter::ExportSpecialMapping

- ea: `0x7f6e0`
- end: `0x7faef`
- name: `System.Xml.Serialization.XmlSchemaExporter::ExportSpecialMapping`
- size: `1039`
- prototype: ``
- caller_count: `4`
- callee_count: `42`
- tags: `registry_config`

## callers

- `0x7ec00`
- `0x7f500`
- `0x7f5b0`
- `0x80580`

## callees

- `0x132e0`
- `0x13310`
- `0x13380`
- `0x13450`
- `0x622f0`
- `0x62370`
- `0x68c50`
- `0x69ee0`
- `0x69f30`
- `0x6a050`
- `0x6a060`
- `0x6a070`
- `0x6a0c0`
- `0x6a110`
- `0x72c10`
- `0x72c70`
- `0x7f3f0`
- `0x7f6e0`
- `0x84b80`
- `0x84c90`
- `0x84cc0`
- `0xcfd30`
- `0xcfe50`
- `0xd04b0`
- `0xd04d0`
- `0xd0680`
- `0xd0830`
- `0xd1890`
- `0xd19c0`
- `0xd1a00`
- `0xd2a60`
- `0xd2ab0`
- `0xd2ac0`
- `0xd2af0`
- `0xd2d60`
- `0xd36a0`
- `0xd3f00`
- `0xd4230`
- `0xd44a0`
- `0xd46e0`
- `0xd5350`
- `0xd6bd0`

## string_xrefs

- `0x7f820`: `http://www.w3.org/2001/XMLSchema`
- `0x7f8e2`: `http://www.w3.org/2001/XMLSchema`
- `0x7fa7e`: `http://www.w3.org/2001/XMLSchema`
- `0x7fabf`: `http://www.w3.org/2001/XMLSchema`
- `0x7fada`: `XmlInternalError`
- `0x7fa34`: `XmlDuplicateNamespace`

## pseudocode

```c

```

## disassembly

```asm
0x7f6e0  ldarg.1
0x7f6e1  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x7f6e6  callvirt instance valuetype System.Xml.Serialization.TypeKind System.Xml.Serialization.TypeDesc::get_Kind()
0x7f6eb  stloc.0
0x7f6ec  ldloc.0
0x7f6ed  ldc.i4.s 9
0x7f6ef  beq.s    loc_7F6FB
0x7f6f1  ldloc.0
0x7f6f2  ldc.i4.s 0xB
0x7f6f4  beq.s    loc_7F765
0x7f6f6  br       loc_7FADA
0x7f6fb  newobj   instance void System.Xml.Schema.XmlSchemaComplexType::.ctor()
0x7f700  stloc.1
0x7f701  ldloc.1
0x7f702  ldarg.1
0x7f703  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x7f708  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsMixed()
0x7f70d  callvirt instance void System.Xml.Schema.XmlSchemaType::set_IsMixed(bool value)
0x7f712  newobj   instance void System.Xml.Schema.XmlSchemaSequence::.ctor()
0x7f717  stloc.2
0x7f718  newobj   instance void System.Xml.Schema.XmlSchemaAny::.ctor()
0x7f71d  stloc.3
0x7f71e  ldarg.3
0x7f71f  brfalse.s loc_7F743
0x7f721  ldloc.1
0x7f722  newobj   instance void System.Xml.Schema.XmlSchemaAnyAttribute::.ctor()
0x7f727  callvirt instance void System.Xml.Schema.XmlSchemaComplexType::set_AnyAttribute(class System.Xml.Schema.XmlSchemaAnyAttribute value)
0x7f72c  ldloc.1
0x7f72d  ldc.i4.1
0x7f72e  callvirt instance void System.Xml.Schema.XmlSchemaType::set_IsMixed(bool value)
0x7f733  ldloc.3
0x7f734  ldc.i4.m1
0x7f735  ldc.i4.m1
0x7f736  ldc.i4.m1
0x7f737  ldc.i4.0
0x7f738  ldc.i4.0
0x7f739  newobj   instance void [mscorlib]System.Decimal::.ctor(int32, int32, int32, bool, unsigned int8)
0x7f73e  callvirt instance void System.Xml.Schema.XmlSchemaParticle::set_MaxOccurs(valuetype [mscorlib]System.Decimal value)
0x7f743  ldloc.2
0x7f744  callvirt instance class System.Xml.Schema.XmlSchemaObjectCollection System.Xml.Schema.XmlSchemaGroupBase::get_Items()
0x7f749  ldloc.3
0x7f74a  callvirt instance int32 System.Xml.Schema.XmlSchemaObjectCollection::Add(class System.Xml.Schema.XmlSchemaObject item)
0x7f74f  pop
0x7f750  ldloc.1
0x7f751  ldloc.2
0x7f752  callvirt instance void System.Xml.Schema.XmlSchemaComplexType::set_Particle(class System.Xml.Schema.XmlSchemaParticle value)
0x7f757  ldarg.s  4
0x7f759  brfalse.s loc_7F763
0x7f75b  ldarg.s  4
0x7f75d  ldloc.1
0x7f75e  callvirt instance void System.Xml.Schema.XmlSchemaElement::set_SchemaType(class System.Xml.Schema.XmlSchemaType value)
0x7f763  ldloc.1
0x7f764  ret
0x7f765  ldarg.1
0x7f766  castclass System.Xml.Serialization.SerializableMapping
0x7f76b  stloc.s  4
0x7f76d  ldloc.s  4
0x7f76f  callvirt instance bool System.Xml.Serialization.SerializableMapping::get_IsAny()
0x7f774  brfalse  loc_7F891
0x7f779  newobj   instance void System.Xml.Schema.XmlSchemaComplexType::.ctor()
0x7f77e  stloc.s  5
0x7f780  ldloc.s  5
0x7f782  ldarg.1
0x7f783  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x7f788  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsMixed()
0x7f78d  callvirt instance void System.Xml.Schema.XmlSchemaType::set_IsMixed(bool value)
0x7f792  newobj   instance void System.Xml.Schema.XmlSchemaSequence::.ctor()
0x7f797  stloc.s  6
0x7f799  newobj   instance void System.Xml.Schema.XmlSchemaAny::.ctor()
0x7f79e  stloc.s  7
0x7f7a0  ldarg.3
0x7f7a1  brfalse.s loc_7F7C8
0x7f7a3  ldloc.s  5
0x7f7a5  newobj   instance void System.Xml.Schema.XmlSchemaAnyAttribute::.ctor()
0x7f7aa  callvirt instance void System.Xml.Schema.XmlSchemaComplexType::set_AnyAttribute(class System.Xml.Schema.XmlSchemaAnyAttribute value)
0x7f7af  ldloc.s  5
0x7f7b1  ldc.i4.1
0x7f7b2  callvirt instance void System.Xml.Schema.XmlSchemaType::set_IsMixed(bool value)
0x7f7b7  ldloc.s  7
0x7f7b9  ldc.i4.m1
0x7f7ba  ldc.i4.m1
0x7f7bb  ldc.i4.m1
0x7f7bc  ldc.i4.0
0x7f7bd  ldc.i4.0
0x7f7be  newobj   instance void [mscorlib]System.Decimal::.ctor(int32, int32, int32, bool, unsigned int8)
0x7f7c3  callvirt instance void System.Xml.Schema.XmlSchemaParticle::set_MaxOccurs(valuetype [mscorlib]System.Decimal value)
0x7f7c8  ldloc.s  4
0x7f7ca  callvirt instance string System.Xml.Serialization.SerializableMapping::get_NamespaceList()
0x7f7cf  callvirt instance int32 [mscorlib]System.String::get_Length()
0x7f7d4  ldc.i4.0
0x7f7d5  ble.s    loc_7F7E5
0x7f7d7  ldloc.s  7
0x7f7d9  ldloc.s  4
0x7f7db  callvirt instance string System.Xml.Serialization.SerializableMapping::get_NamespaceList()
0x7f7e0  callvirt instance void System.Xml.Schema.XmlSchemaAny::set_Namespace(string value)
0x7f7e5  ldloc.s  7
0x7f7e7  ldc.i4.2
0x7f7e8  callvirt instance void System.Xml.Schema.XmlSchemaAny::set_ProcessContents(valuetype System.Xml.Schema.XmlSchemaContentProcessing value)
0x7f7ed  ldloc.s  4
0x7f7ef  callvirt instance class System.Xml.Schema.XmlSchemaSet System.Xml.Serialization.SerializableMapping::get_Schemas()
0x7f7f4  brfalse.s loc_7F869
0x7f7f6  ldloc.s  4
0x7f7f8  callvirt instance class System.Xml.Schema.XmlSchemaSet System.Xml.Serialization.SerializableMapping::get_Schemas()
0x7f7fd  callvirt instance class [mscorlib]System.Collections.ICollection System.Xml.Schema.XmlSchemaSet::Schemas()
0x7f802  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x7f807  stloc.s  8
0x7f809  br.s     loc_7F849
0x7f80b  ldloc.s  8
0x7f80d  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x7f812  castclass System.Xml.Schema.XmlSchema
0x7f817  stloc.s  9
0x7f819  ldloc.s  9
0x7f81b  callvirt instance string System.Xml.Schema.XmlSchema::get_TargetNamespace()
0x7f820  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x7f825  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x7f82a  brfalse.s loc_7F849
0x7f82c  ldarg.0
0x7f82d  ldfld    class System.Xml.Serialization.XmlSchemas System.Xml.Serialization.XmlSchemaExporter::schemas
0x7f832  ldloc.s  9
0x7f834  ldc.i4.1
0x7f835  callvirt instance int32 System.Xml.Serialization.XmlSchemas::Add(class System.Xml.Schema.XmlSchema schema, bool delay)
0x7f83a  pop
0x7f83b  ldarg.0
0x7f83c  ldloc.s  9
0x7f83e  callvirt instance string System.Xml.Schema.XmlSchema::get_TargetNamespace()
0x7f843  ldarg.2
0x7f844  call     instance void System.Xml.Serialization.XmlSchemaExporter::AddSchemaImport(string ns, string referencingNs)
0x7f849  ldloc.s  8
0x7f84b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x7f850  brtrue.s loc_7F80B
0x7f852  leave.s  loc_7F869
0x7f854  ldloc.s  8
0x7f856  isinst   [mscorlib]System.IDisposable
0x7f85b  stloc.s  0xA
0x7f85d  ldloc.s  0xA
0x7f85f  brfalse.s loc_7F868
0x7f861  ldloc.s  0xA
0x7f863  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7f868  endfinally
0x7f869  ldloc.s  6
0x7f86b  callvirt instance class System.Xml.Schema.XmlSchemaObjectCollection System.Xml.Schema.XmlSchemaGroupBase::get_Items()
0x7f870  ldloc.s  7
0x7f872  callvirt instance int32 System.Xml.Schema.XmlSchemaObjectCollection::Add(class System.Xml.Schema.XmlSchemaObject item)
0x7f877  pop
0x7f878  ldloc.s  5
0x7f87a  ldloc.s  6
0x7f87c  callvirt instance void System.Xml.Schema.XmlSchemaComplexType::set_Particle(class System.Xml.Schema.XmlSchemaParticle value)
0x7f881  ldarg.s  4
0x7f883  brfalse.s loc_7F88E
0x7f885  ldarg.s  4
0x7f887  ldloc.s  5
0x7f889  callvirt instance void System.Xml.Schema.XmlSchemaElement::set_SchemaType(class System.Xml.Schema.XmlSchemaType value)
0x7f88e  ldloc.s  5
0x7f890  ret
0x7f891  ldloc.s  4
0x7f893  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Serialization.SerializableMapping::get_XsiType()
0x7f898  ldnull
0x7f899  call     bool System.Xml.XmlQualifiedName::op_Inequality(class System.Xml.XmlQualifiedName a, class System.Xml.XmlQualifiedName b)
0x7f89e  brtrue.s loc_7F8AC
0x7f8a0  ldloc.s  4
0x7f8a2  callvirt instance class System.Xml.Schema.XmlSchemaType System.Xml.Serialization.SerializableMapping::get_XsdType()
0x7f8a7  brfalse  loc_7F9A6
0x7f8ac  ldloc.s  4
0x7f8ae  callvirt instance class System.Xml.Schema.XmlSchemaType System.Xml.Serialization.SerializableMapping::get_XsdType()
0x7f8b3  stloc.s  0xB
0x7f8b5  ldloc.s  4
0x7f8b7  callvirt instance class System.Xml.Schema.XmlSchemaSet System.Xml.Serialization.SerializableMapping::get_Schemas()
0x7f8bc  callvirt instance class [mscorlib]System.Collections.ICollection System.Xml.Schema.XmlSchemaSet::Schemas()
0x7f8c1  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x7f8c6  stloc.s  0xC
0x7f8c8  br       loc_7F94D
0x7f8cd  ldloc.s  0xC
0x7f8cf  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x7f8d4  castclass System.Xml.Schema.XmlSchema
0x7f8d9  stloc.s  0xD
0x7f8db  ldloc.s  0xD
0x7f8dd  callvirt instance string System.Xml.Schema.XmlSchema::get_TargetNamespace()
0x7f8e2  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x7f8e7  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x7f8ec  brfalse.s loc_7F94D
0x7f8ee  ldarg.0
0x7f8ef  ldfld    class System.Xml.Serialization.XmlSchemas System.Xml.Serialization.XmlSchemaExporter::schemas
0x7f8f4  ldloc.s  0xD
0x7f8f6  ldc.i4.1
0x7f8f7  callvirt instance int32 System.Xml.Serialization.XmlSchemas::Add(class System.Xml.Schema.XmlSchema schema, bool delay)
0x7f8fc  pop
0x7f8fd  ldarg.0
0x7f8fe  ldloc.s  0xD
0x7f900  callvirt instance string System.Xml.Schema.XmlSchema::get_TargetNamespace()
0x7f905  ldarg.2
0x7f906  call     instance void System.Xml.Serialization.XmlSchemaExporter::AddSchemaImport(string ns, string referencingNs)
0x7f90b  ldloc.s  4
0x7f90d  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Serialization.SerializableMapping::get_XsiType()
0x7f912  callvirt instance bool System.Xml.XmlQualifiedName::get_IsEmpty()
0x7f917  brtrue.s loc_7F94D
0x7f919  ldloc.s  4
0x7f91b  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Serialization.SerializableMapping::get_XsiType()
0x7f920  callvirt instance string System.Xml.XmlQualifiedName::get_Namespace()
0x7f925  ldloc.s  0xD
0x7f927  callvirt instance string System.Xml.Schema.XmlSchema::get_TargetNamespace()
0x7f92c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7f931  brfalse.s loc_7F94D
0x7f933  ldloc.s  0xD
0x7f935  callvirt instance class System.Xml.Schema.XmlSchemaObjectTable System.Xml.Schema.XmlSchema::get_SchemaTypes()
0x7f93a  ldloc.s  4
0x7f93c  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Serialization.SerializableMapping::get_XsiType()
0x7f941  callvirt instance class System.Xml.Schema.XmlSchemaObject System.Xml.Schema.XmlSchemaObjectTable::get_Item(class System.Xml.XmlQualifiedName name)
0x7f946  castclass System.Xml.Schema.XmlSchemaType
0x7f94b  stloc.s  0xB
0x7f94d  ldloc.s  0xC
0x7f94f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x7f954  brtrue   loc_7F8CD
0x7f959  leave.s  loc_7F970
0x7f95b  ldloc.s  0xC
0x7f95d  isinst   [mscorlib]System.IDisposable
0x7f962  stloc.s  0xA
0x7f964  ldloc.s  0xA
0x7f966  brfalse.s loc_7F96F
0x7f968  ldloc.s  0xA
0x7f96a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7f96f  endfinally
0x7f970  ldarg.s  4
0x7f972  brfalse.s loc_7F999
0x7f974  ldarg.s  4
0x7f976  ldloc.s  4
0x7f978  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Serialization.SerializableMapping::get_XsiType()
0x7f97d  callvirt instance void System.Xml.Schema.XmlSchemaElement::set_SchemaTypeName(class System.Xml.XmlQualifiedName value)
0x7f982  ldarg.s  4
0x7f984  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaElement::get_SchemaTypeName()
0x7f989  callvirt instance bool System.Xml.XmlQualifiedName::get_IsEmpty()
0x7f98e  brfalse.s loc_7F999
0x7f990  ldarg.s  4
0x7f992  ldloc.s  0xB
0x7f994  callvirt instance void System.Xml.Schema.XmlSchemaElement::set_SchemaType(class System.Xml.Schema.XmlSchemaType value)
0x7f999  ldloc.s  4
0x7f99b  ldarg.s  4
0x7f99d  ldarg.2
0x7f99e  callvirt instance void System.Xml.Serialization.SerializableMapping::CheckDuplicateElement(class System.Xml.Schema.XmlSchemaElement element, string elementNs)
0x7f9a3  ldloc.s  0xB
0x7f9a5  ret
0x7f9a6  ldloc.s  4
0x7f9a8  callvirt instance class System.Xml.Schema.XmlSchema System.Xml.Serialization.SerializableMapping::get_Schema()
0x7f9ad  brfalse  loc_7FA69
0x7f9b2  newobj   instance void System.Xml.Schema.XmlSchemaComplexType::.ctor()
0x7f9b7  stloc.s  0xE
0x7f9b9  newobj   instance void System.Xml.Schema.XmlSchemaAny::.ctor()
0x7f9be  stloc.s  0xF
0x7f9c0  newobj   instance void System.Xml.Schema.XmlSchemaSequence::.ctor()
0x7f9c5  stloc.s  0x10
0x7f9c7  ldloc.s  0x10
0x7f9c9  callvirt instance class System.Xml.Schema.XmlSchemaObjectCollection System.Xml.Schema.XmlSchemaGroupBase::get_Items()
0x7f9ce  ldloc.s  0xF
0x7f9d0  callvirt instance int32 System.Xml.Schema.XmlSchemaObjectCollection::Add(class System.Xml.Schema.XmlSchemaObject item)
0x7f9d5  pop
0x7f9d6  ldloc.s  0xE
0x7f9d8  ldloc.s  0x10
0x7f9da  callvirt instance void System.Xml.Schema.XmlSchemaComplexType::set_Particle(class System.Xml.Schema.XmlSchemaParticle value)
0x7f9df  ldloc.s  4
0x7f9e1  callvirt instance class System.Xml.Schema.XmlSchema System.Xml.Serialization.SerializableMapping::get_Schema()
0x7f9e6  callvirt instance string System.Xml.Schema.XmlSchema::get_TargetNamespace()
0x7f9eb  stloc.s  0x11
0x7f9ed  ldloc.s  0xF
0x7f9ef  ldloc.s  0x11
0x7f9f1  brfalse.s loc_7F9F7
0x7f9f3  ldloc.s  0x11
0x7f9f5  br.s     loc_7F9FC
0x7f9f7  ldstr    asc_1284AE// ""
0x7f9fc  callvirt instance void System.Xml.Schema.XmlSchemaAny::set_Namespace(string value)
0x7fa01  ldarg.0
0x7fa02  ldfld    class System.Xml.Serialization.XmlSchemas System.Xml.Serialization.XmlSchemaExporter::schemas
0x7fa07  ldloc.s  0x11
0x7fa09  callvirt instance class System.Xml.Schema.XmlSchema System.Xml.Serialization.XmlSchemas::get_Item(string ns)
0x7fa0e  stloc.s  0x12
0x7fa10  ldloc.s  0x12
0x7fa12  brtrue.s loc_7FA29
0x7fa14  ldarg.0
0x7fa15  ldfld    class System.Xml.Serialization.XmlSchemas System.Xml.Serialization.XmlSchemaExporter::schemas
0x7fa1a  ldloc.s  4
0x7fa1c  callvirt instance class System.Xml.Schema.XmlSchema System.Xml.Serialization.SerializableMapping::get_Schema()
0x7fa21  callvirt instance int32 System.Xml.Serialization.XmlSchemas::Add(class System.Xml.Schema.XmlSchema schema)
0x7fa26  pop
0x7fa27  br.s     loc_7FA4F
0x7fa29  ldloc.s  0x12
0x7fa2b  ldloc.s  4
0x7fa2d  callvirt instance class System.Xml.Schema.XmlSchema System.Xml.Serialization.SerializableMapping::get_Schema()
0x7fa32  beq.s    loc_7FA4F
0x7fa34  ldstr    aXmlduplicatena// "XmlDuplicateNamespace"
0x7fa39  ldc.i4.1
0x7fa3a  newarr   [mscorlib]System.Object
0x7fa3f  dup
0x7fa40  ldc.i4.0
0x7fa41  ldloc.s  0x11
0x7fa43  stelem.ref
0x7fa44  call     string System.Xml.Res::GetString(string name, object[] args)
0x7fa49  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7fa4e  throw
0x7fa4f  ldarg.s  4
0x7fa51  brfalse.s loc_7FA5C
0x7fa53  ldarg.s  4
0x7fa55  ldloc.s  0xE
  ... truncated ...
```
