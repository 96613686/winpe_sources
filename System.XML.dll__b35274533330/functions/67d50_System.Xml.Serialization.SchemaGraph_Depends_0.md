# System.Xml.Serialization.SchemaGraph::Depends_0

- ea: `0x67d50`
- end: `0x68413`
- name: `System.Xml.Serialization.SchemaGraph::Depends_0`
- size: `1731`
- prototype: ``
- caller_count: `2`
- callee_count: `48`
- tags: `registry_config`

## callers

- `0x67cf0`
- `0x67d50`

## callees

- `0x13310`
- `0x13380`
- `0x13450`
- `0x51110`
- `0x51cb0`
- `0x51ce0`
- `0x67c90`
- `0x67cf0`
- `0x67d50`
- `0x74e70`
- `0x84f50`
- `0xd0370`
- `0xd0940`
- `0xd0970`
- `0xd09a0`
- `0xd0bc0`
- `0xd0d30`
- `0xd1560`
- `0xd1590`
- `0xd15b0`
- `0xd1620`
- `0xd1670`
- `0xd1990`
- `0xd19b0`
- `0xd19d0`
- `0xd2160`
- `0xd2a50`
- `0xd2a80`
- `0xd2ab0`
- `0xd2ae0`
- `0xd3560`
- `0xd36a0`
- `0xd36e0`
- `0xd3eb0`
- `0xd3ee0`
- `0xd4040`
- `0xd4050`
- `0xd6510`
- `0xd6540`
- `0xd65b0`
- `0xd65e0`
- `0xd6610`
- `0xd66a0`
- `0xd6760`
- `0xd6790`
- `0xd6820`
- `0xd6850`
- `0xd68e0`

## string_xrefs

- `0x67feb`: `http://www.w3.org/2001/XMLSchema`
- `0x68093`: `http://www.w3.org/2001/XMLSchema`
- `0x683bf`: `http://schemas.xmlsoap.org/wsdl/`

## pseudocode

```c

```

## disassembly

```asm
0x67d50  ldarg.1
0x67d51  brfalse.s loc_67D61
0x67d53  ldarg.0
0x67d54  ldfld    class [mscorlib]System.Collections.Hashtable System.Xml.Serialization.SchemaGraph::scope
0x67d59  ldarg.1
0x67d5a  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x67d5f  brfalse.s loc_67D62
0x67d61  ret
0x67d62  ldarg.1
0x67d63  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x67d68  stloc.0
0x67d69  ldtoken  System.Xml.Schema.XmlSchemaType
0x67d6e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x67d73  ldloc.0
0x67d74  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x67d79  brfalse  loc_6805C
0x67d7e  ldsfld   class System.Xml.XmlQualifiedName System.Xml.XmlQualifiedName::Empty
0x67d83  stloc.1
0x67d84  ldnull
0x67d85  stloc.2
0x67d86  ldnull
0x67d87  stloc.3
0x67d88  ldnull
0x67d89  stloc.s  4
0x67d8b  ldarg.1
0x67d8c  isinst   System.Xml.Schema.XmlSchemaComplexType
0x67d91  brfalse  loc_67ED0
0x67d96  ldarg.1
0x67d97  castclass System.Xml.Schema.XmlSchemaComplexType
0x67d9c  stloc.s  5
0x67d9e  ldloc.s  5
0x67da0  callvirt instance class System.Xml.Schema.XmlSchemaContentModel System.Xml.Schema.XmlSchemaComplexType::get_ContentModel()
0x67da5  brfalse  loc_67E6B
0x67daa  ldloc.s  5
0x67dac  callvirt instance class System.Xml.Schema.XmlSchemaContentModel System.Xml.Schema.XmlSchemaComplexType::get_ContentModel()
0x67db1  callvirt instance class System.Xml.Schema.XmlSchemaContent System.Xml.Schema.XmlSchemaContentModel::get_Content()
0x67db6  stloc.s  6
0x67db8  ldloc.s  6
0x67dba  isinst   System.Xml.Schema.XmlSchemaComplexContentRestriction
0x67dbf  brfalse.s loc_67DE1
0x67dc1  ldloc.s  6
0x67dc3  castclass System.Xml.Schema.XmlSchemaComplexContentRestriction
0x67dc8  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaComplexContentRestriction::get_BaseTypeName()
0x67dcd  stloc.1
0x67dce  ldloc.s  6
0x67dd0  castclass System.Xml.Schema.XmlSchemaComplexContentRestriction
0x67dd5  callvirt instance class System.Xml.Schema.XmlSchemaObjectCollection System.Xml.Schema.XmlSchemaComplexContentRestriction::get_Attributes()
0x67dda  stloc.s  4
0x67ddc  br       loc_67E7C
0x67de1  ldloc.s  6
0x67de3  isinst   System.Xml.Schema.XmlSchemaSimpleContentRestriction
0x67de8  brfalse.s loc_67E19
0x67dea  ldloc.s  6
0x67dec  castclass System.Xml.Schema.XmlSchemaSimpleContentRestriction
0x67df1  stloc.s  7
0x67df3  ldloc.s  7
0x67df5  callvirt instance class System.Xml.Schema.XmlSchemaSimpleType System.Xml.Schema.XmlSchemaSimpleContentRestriction::get_BaseType()
0x67dfa  brfalse.s loc_67E06
0x67dfc  ldloc.s  7
0x67dfe  callvirt instance class System.Xml.Schema.XmlSchemaSimpleType System.Xml.Schema.XmlSchemaSimpleContentRestriction::get_BaseType()
0x67e03  stloc.2
0x67e04  br.s     loc_67E0E
0x67e06  ldloc.s  7
0x67e08  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaSimpleContentRestriction::get_BaseTypeName()
0x67e0d  stloc.1
0x67e0e  ldloc.s  7
0x67e10  callvirt instance class System.Xml.Schema.XmlSchemaObjectCollection System.Xml.Schema.XmlSchemaSimpleContentRestriction::get_Attributes()
0x67e15  stloc.s  4
0x67e17  br.s     loc_67E7C
0x67e19  ldloc.s  6
0x67e1b  isinst   System.Xml.Schema.XmlSchemaComplexContentExtension
0x67e20  brfalse.s loc_67E46
0x67e22  ldloc.s  6
0x67e24  castclass System.Xml.Schema.XmlSchemaComplexContentExtension
0x67e29  stloc.s  8
0x67e2b  ldloc.s  8
0x67e2d  callvirt instance class System.Xml.Schema.XmlSchemaObjectCollection System.Xml.Schema.XmlSchemaComplexContentExtension::get_Attributes()
0x67e32  stloc.s  4
0x67e34  ldloc.s  8
0x67e36  callvirt instance class System.Xml.Schema.XmlSchemaParticle System.Xml.Schema.XmlSchemaComplexContentExtension::get_Particle()
0x67e3b  stloc.3
0x67e3c  ldloc.s  8
0x67e3e  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaComplexContentExtension::get_BaseTypeName()
0x67e43  stloc.1
0x67e44  br.s     loc_67E7C
0x67e46  ldloc.s  6
0x67e48  isinst   System.Xml.Schema.XmlSchemaSimpleContentExtension
0x67e4d  brfalse.s loc_67E7C
0x67e4f  ldloc.s  6
0x67e51  castclass System.Xml.Schema.XmlSchemaSimpleContentExtension
0x67e56  stloc.s  9
0x67e58  ldloc.s  9
0x67e5a  callvirt instance class System.Xml.Schema.XmlSchemaObjectCollection System.Xml.Schema.XmlSchemaSimpleContentExtension::get_Attributes()
0x67e5f  stloc.s  4
0x67e61  ldloc.s  9
0x67e63  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaSimpleContentExtension::get_BaseTypeName()
0x67e68  stloc.1
0x67e69  br.s     loc_67E7C
0x67e6b  ldloc.s  5
0x67e6d  callvirt instance class System.Xml.Schema.XmlSchemaObjectCollection System.Xml.Schema.XmlSchemaComplexType::get_Attributes()
0x67e72  stloc.s  4
0x67e74  ldloc.s  5
0x67e76  callvirt instance class System.Xml.Schema.XmlSchemaParticle System.Xml.Schema.XmlSchemaComplexType::get_Particle()
0x67e7b  stloc.3
0x67e7c  ldloc.3
0x67e7d  isinst   System.Xml.Schema.XmlSchemaGroupRef
0x67e82  brfalse.s loc_67EB9
0x67e84  ldloc.3
0x67e85  castclass System.Xml.Schema.XmlSchemaGroupRef
0x67e8a  stloc.s  0xA
0x67e8c  ldarg.0
0x67e8d  ldfld    class System.Xml.Serialization.XmlSchemas System.Xml.Serialization.SchemaGraph::schemas
0x67e92  ldloc.s  0xA
0x67e94  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaGroupRef::get_RefName()
0x67e99  ldtoken  System.Xml.Schema.XmlSchemaGroup
0x67e9e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x67ea3  ldc.i4.0
0x67ea4  callvirt instance object System.Xml.Serialization.XmlSchemas::Find(class System.Xml.XmlQualifiedName name, class [mscorlib]System.Type type, bool checkCache)
0x67ea9  castclass System.Xml.Schema.XmlSchemaGroup
0x67eae  callvirt instance class System.Xml.Schema.XmlSchemaGroupBase System.Xml.Schema.XmlSchemaGroup::get_Particle()
0x67eb3  stloc.3
0x67eb4  br       loc_67FDA
0x67eb9  ldloc.3
0x67eba  isinst   System.Xml.Schema.XmlSchemaGroupBase
0x67ebf  brfalse  loc_67FDA
0x67ec4  ldloc.3
0x67ec5  castclass System.Xml.Schema.XmlSchemaGroupBase
0x67eca  stloc.3
0x67ecb  br       loc_67FDA
0x67ed0  ldarg.1
0x67ed1  isinst   System.Xml.Schema.XmlSchemaSimpleType
0x67ed6  brfalse  loc_67FDA
0x67edb  ldarg.1
0x67edc  castclass System.Xml.Schema.XmlSchemaSimpleType
0x67ee1  stloc.s  0xB
0x67ee3  ldloc.s  0xB
0x67ee5  callvirt instance class System.Xml.Schema.XmlSchemaSimpleTypeContent System.Xml.Schema.XmlSchemaSimpleType::get_Content()
0x67eea  stloc.s  0xC
0x67eec  ldloc.s  0xC
0x67eee  isinst   System.Xml.Schema.XmlSchemaSimpleTypeRestriction
0x67ef3  brfalse.s loc_67F14
0x67ef5  ldloc.s  0xC
0x67ef7  castclass System.Xml.Schema.XmlSchemaSimpleTypeRestriction
0x67efc  callvirt instance class System.Xml.Schema.XmlSchemaSimpleType System.Xml.Schema.XmlSchemaSimpleTypeRestriction::get_BaseType()
0x67f01  stloc.2
0x67f02  ldloc.s  0xC
0x67f04  castclass System.Xml.Schema.XmlSchemaSimpleTypeRestriction
0x67f09  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaSimpleTypeRestriction::get_BaseTypeName()
0x67f0e  stloc.1
0x67f0f  br       loc_67FDA
0x67f14  ldloc.s  0xC
0x67f16  isinst   System.Xml.Schema.XmlSchemaSimpleTypeList
0x67f1b  brfalse.s loc_67F61
0x67f1d  ldloc.s  0xC
0x67f1f  castclass System.Xml.Schema.XmlSchemaSimpleTypeList
0x67f24  stloc.s  0xD
0x67f26  ldloc.s  0xD
0x67f28  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaSimpleTypeList::get_ItemTypeName()
0x67f2d  ldnull
0x67f2e  call     bool System.Xml.XmlQualifiedName::op_Inequality(class System.Xml.XmlQualifiedName a, class System.Xml.XmlQualifiedName b)
0x67f33  brfalse.s loc_67F4B
0x67f35  ldloc.s  0xD
0x67f37  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaSimpleTypeList::get_ItemTypeName()
0x67f3c  callvirt instance bool System.Xml.XmlQualifiedName::get_IsEmpty()
0x67f41  brtrue.s loc_67F4B
0x67f43  ldloc.s  0xD
0x67f45  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaSimpleTypeList::get_ItemTypeName()
0x67f4a  stloc.1
0x67f4b  ldloc.s  0xD
0x67f4d  callvirt instance class System.Xml.Schema.XmlSchemaSimpleType System.Xml.Schema.XmlSchemaSimpleTypeList::get_ItemType()
0x67f52  brfalse  loc_67FDA
0x67f57  ldloc.s  0xD
0x67f59  callvirt instance class System.Xml.Schema.XmlSchemaSimpleType System.Xml.Schema.XmlSchemaSimpleTypeList::get_ItemType()
0x67f5e  stloc.2
0x67f5f  br.s     loc_67FDA
0x67f61  ldloc.s  0xC
0x67f63  isinst   System.Xml.Schema.XmlSchemaSimpleTypeRestriction
0x67f68  brfalse.s loc_67F79
0x67f6a  ldloc.s  0xC
0x67f6c  castclass System.Xml.Schema.XmlSchemaSimpleTypeRestriction
0x67f71  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaSimpleTypeRestriction::get_BaseTypeName()
0x67f76  stloc.1
0x67f77  br.s     loc_67FDA
0x67f79  ldloc.0
0x67f7a  ldtoken  System.Xml.Schema.XmlSchemaSimpleTypeUnion
0x67f7f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x67f84  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x67f89  brfalse.s loc_67FDA
0x67f8b  ldarg.1
0x67f8c  castclass System.Xml.Schema.XmlSchemaSimpleTypeUnion
0x67f91  callvirt instance class System.Xml.XmlQualifiedName[] System.Xml.Schema.XmlSchemaSimpleTypeUnion::get_MemberTypes()
0x67f96  stloc.s  0xE
0x67f98  ldloc.s  0xE
0x67f9a  brfalse.s loc_67FDA
0x67f9c  ldc.i4.0
0x67f9d  stloc.s  0xF
0x67f9f  br.s     loc_67FD2
0x67fa1  ldarg.0
0x67fa2  ldfld    class System.Xml.Serialization.XmlSchemas System.Xml.Serialization.SchemaGraph::schemas
0x67fa7  ldloc.s  0xE
0x67fa9  ldloc.s  0xF
0x67fab  ldelem.ref
0x67fac  ldtoken  System.Xml.Schema.XmlSchemaType
0x67fb1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x67fb6  ldc.i4.0
0x67fb7  callvirt instance object System.Xml.Serialization.XmlSchemas::Find(class System.Xml.XmlQualifiedName name, class [mscorlib]System.Type type, bool checkCache)
0x67fbc  castclass System.Xml.Schema.XmlSchemaType
0x67fc1  stloc.s  0x10
0x67fc3  ldarg.0
0x67fc4  ldarg.2
0x67fc5  ldloc.s  0x10
0x67fc7  call     instance void System.Xml.Serialization.SchemaGraph::AddRef(class [mscorlib]System.Collections.ArrayList list, class System.Xml.Schema.XmlSchemaObject o)
0x67fcc  ldloc.s  0xF
0x67fce  ldc.i4.1
0x67fcf  add
0x67fd0  stloc.s  0xF
0x67fd2  ldloc.s  0xF
0x67fd4  ldloc.s  0xE
0x67fd6  ldlen
0x67fd7  conv.i4
0x67fd8  blt.s    loc_67FA1
0x67fda  ldloc.2
0x67fdb  brtrue.s loc_68014
0x67fdd  ldloc.1
0x67fde  callvirt instance bool System.Xml.XmlQualifiedName::get_IsEmpty()
0x67fe3  brtrue.s loc_68014
0x67fe5  ldloc.1
0x67fe6  callvirt instance string System.Xml.XmlQualifiedName::get_Namespace()
0x67feb  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x67ff0  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x67ff5  brfalse.s loc_68014
0x67ff7  ldarg.0
0x67ff8  ldfld    class System.Xml.Serialization.XmlSchemas System.Xml.Serialization.SchemaGraph::schemas
0x67ffd  ldloc.1
0x67ffe  ldtoken  System.Xml.Schema.XmlSchemaType
0x68003  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x68008  ldc.i4.0
0x68009  callvirt instance object System.Xml.Serialization.XmlSchemas::Find(class System.Xml.XmlQualifiedName name, class [mscorlib]System.Type type, bool checkCache)
0x6800e  castclass System.Xml.Schema.XmlSchemaType
0x68013  stloc.2
0x68014  ldloc.2
0x68015  brfalse.s loc_6801F
0x68017  ldarg.0
0x68018  ldarg.2
0x68019  ldloc.2
0x6801a  call     instance void System.Xml.Serialization.SchemaGraph::AddRef(class [mscorlib]System.Collections.ArrayList list, class System.Xml.Schema.XmlSchemaObject o)
0x6801f  ldloc.3
0x68020  brfalse.s loc_6802A
0x68022  ldarg.0
0x68023  ldloc.3
0x68024  ldarg.2
0x68025  call     instance void System.Xml.Serialization.SchemaGraph::Depends(class System.Xml.Schema.XmlSchemaObject item, class [mscorlib]System.Collections.ArrayList refs)
0x6802a  ldloc.s  4
0x6802c  brfalse  loc_68373
0x68031  ldc.i4.0
0x68032  stloc.s  0x11
0x68034  br.s     loc_6804C
0x68036  ldarg.0
0x68037  ldloc.s  4
0x68039  ldloc.s  0x11
0x6803b  callvirt instance class System.Xml.Schema.XmlSchemaObject System.Xml.Schema.XmlSchemaObjectCollection::get_Item(int32 index)
0x68040  ldarg.2
0x68041  call     instance void System.Xml.Serialization.SchemaGraph::Depends(class System.Xml.Schema.XmlSchemaObject item, class [mscorlib]System.Collections.ArrayList refs)
0x68046  ldloc.s  0x11
0x68048  ldc.i4.1
0x68049  add
0x6804a  stloc.s  0x11
0x6804c  ldloc.s  0x11
0x6804e  ldloc.s  4
0x68050  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x68055  blt.s    loc_68036
0x68057  br       loc_68373
0x6805c  ldloc.0
0x6805d  ldtoken  System.Xml.Schema.XmlSchemaElement
0x68062  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x68067  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x6806c  brfalse  loc_6815F
0x68071  ldarg.1
0x68072  castclass System.Xml.Schema.XmlSchemaElement
0x68077  stloc.s  0x12
0x68079  ldloc.s  0x12
0x6807b  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaElement::get_SubstitutionGroup()
0x68080  callvirt instance bool System.Xml.XmlQualifiedName::get_IsEmpty()
0x68085  brtrue.s loc_680CC
0x68087  ldloc.s  0x12
0x68089  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaElement::get_SubstitutionGroup()
0x6808e  callvirt instance string System.Xml.XmlQualifiedName::get_Namespace()
0x68093  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x68098  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x6809d  brfalse.s loc_680CC
0x6809f  ldarg.0
0x680a0  ldfld    class System.Xml.Serialization.XmlSchemas System.Xml.Serialization.SchemaGraph::schemas
0x680a5  ldloc.s  0x12
0x680a7  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaElement::get_SubstitutionGroup()
0x680ac  ldtoken  System.Xml.Schema.XmlSchemaElement
0x680b1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x680b6  ldc.i4.0
0x680b7  callvirt instance object System.Xml.Serialization.XmlSchemas::Find(class System.Xml.XmlQualifiedName name, class [mscorlib]System.Type type, bool checkCache)
0x680bc  castclass System.Xml.Schema.XmlSchemaElement
0x680c1  stloc.s  0x13
  ... truncated ...
```
