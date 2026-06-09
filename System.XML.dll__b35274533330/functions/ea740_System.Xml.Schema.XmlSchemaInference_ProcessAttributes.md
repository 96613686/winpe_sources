# System.Xml.Schema.XmlSchemaInference::ProcessAttributes

- ea: `0xea740`
- end: `0xea986`
- name: `System.Xml.Schema.XmlSchemaInference::ProcessAttributes`
- size: `582`
- prototype: ``
- caller_count: `1`
- callee_count: `33`
- tags: `registry_config`

## callers

- `0xe9810`

## callees

- `0x12c50`
- `0x13380`
- `0x21500`
- `0x21510`
- `0x21520`
- `0x21540`
- `0x21c30`
- `0xd1890`
- `0xd18b0`
- `0xd1990`
- `0xd19a0`
- `0xd19d0`
- `0xd1a40`
- `0xd2170`
- `0xd2a20`
- `0xd2ab0`
- `0xd2ac0`
- `0xd2af0`
- `0xd3d00`
- `0xd3d10`
- `0xd3e90`
- `0xd3f00`
- `0xd64f0`
- `0xd6520`
- `0xd6540`
- `0xd6580`
- `0xd6bb0`
- `0xe91d0`
- `0xea0e0`
- `0xea740`
- `0xeac20`
- `0xec730`
- `0xec790`

## string_xrefs

- `0xea77c`: `http://www.w3.org/2000/xmlns/`
- `0xea793`: `xmlns`
- `0xea758`: `http://www.w3.org/2001/XMLSchema`
- `0xea7d3`: `http://www.w3.org/2001/XMLSchema-instance`

## pseudocode

```c

```

## disassembly

```asm
0xea740  newobj   instance void System.Xml.Schema.XmlSchemaObjectCollection::.ctor()
0xea745  stloc.0
0xea746  ldarg.2
0xea747  isinst   System.Xml.Schema.XmlSchemaComplexType
0xea74c  stloc.1
0xea74d  ldarg.0
0xea74e  ldfld    class System.Xml.XmlReader System.Xml.Schema.XmlSchemaInference::xtr
0xea753  callvirt instance string System.Xml.XmlReader::get_NamespaceURI()
0xea758  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0xea75d  call     bool [mscorlib]System.String::op_Equality(string, string)
0xea762  brfalse.s loc_EA771
0xea764  ldstr    aSchinfSchema// "SchInf_schema"
0xea769  ldc.i4.0
0xea76a  ldc.i4.0
0xea76b  newobj   instance void System.Xml.Schema.XmlSchemaInferenceException::.ctor(string res, int32 lineNumber, int32 linePosition)
0xea770  throw
0xea771  ldarg.0
0xea772  ldfld    class System.Xml.XmlReader System.Xml.Schema.XmlSchemaInference::xtr
0xea777  callvirt instance string System.Xml.XmlReader::get_NamespaceURI()
0xea77c  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/xmlns/"
0xea781  call     bool [mscorlib]System.String::op_Equality(string, string)
0xea786  brfalse.s loc_EA7C8
0xea788  ldarg.0
0xea789  ldfld    class System.Xml.XmlReader System.Xml.Schema.XmlSchemaInference::xtr
0xea78e  callvirt instance string System.Xml.XmlReader::get_Prefix()
0xea793  ldstr    aXmlns// "xmlns"
0xea798  call     bool [mscorlib]System.String::op_Equality(string, string)
0xea79d  brfalse  loc_EA967
0xea7a2  ldarg.0
0xea7a3  ldfld    class System.Xml.XmlNamespaceManager System.Xml.Schema.XmlSchemaInference::NamespaceManager
0xea7a8  ldarg.0
0xea7a9  ldfld    class System.Xml.XmlReader System.Xml.Schema.XmlSchemaInference::xtr
0xea7ae  callvirt instance string System.Xml.XmlReader::get_LocalName()
0xea7b3  ldarg.0
0xea7b4  ldfld    class System.Xml.XmlReader System.Xml.Schema.XmlSchemaInference::xtr
0xea7b9  callvirt instance string System.Xml.XmlReader::get_Value()
0xea7be  callvirt instance void System.Xml.XmlNamespaceManager::AddNamespace(string prefix, string uri)
0xea7c3  br       loc_EA967
0xea7c8  ldarg.0
0xea7c9  ldfld    class System.Xml.XmlReader System.Xml.Schema.XmlSchemaInference::xtr
0xea7ce  callvirt instance string System.Xml.XmlReader::get_NamespaceURI()
0xea7d3  ldstr    aHttpWwwW3Org20_1// "http://www.w3.org/2001/XMLSchema-instan"...
0xea7d8  call     bool [mscorlib]System.String::op_Equality(string, string)
0xea7dd  brfalse.s loc_EA841
0xea7df  ldarg.0
0xea7e0  ldfld    class System.Xml.XmlReader System.Xml.Schema.XmlSchemaInference::xtr
0xea7e5  callvirt instance string System.Xml.XmlReader::get_LocalName()
0xea7ea  stloc.2
0xea7eb  ldloc.2
0xea7ec  ldstr    aNil// "nil"
0xea7f1  call     bool [mscorlib]System.String::op_Equality(string, string)
0xea7f6  brfalse.s loc_EA805
0xea7f8  ldarg.1
0xea7f9  ldind.ref
0xea7fa  ldc.i4.1
0xea7fb  callvirt instance void System.Xml.Schema.XmlSchemaElement::set_IsNillable(bool value)
0xea800  br       loc_EA967
0xea805  ldloc.2
0xea806  ldstr    aType// "type"
0xea80b  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xea810  brfalse  loc_EA967
0xea815  ldloc.2
0xea816  ldstr    aSchemalocation// "schemaLocation"
0xea81b  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xea820  brfalse  loc_EA967
0xea825  ldloc.2
0xea826  ldstr    aNonamespacesch// "noNamespaceSchemaLocation"
0xea82b  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xea830  brfalse  loc_EA967
0xea835  ldstr    aSchNotxsiattri// "Sch_NotXsiAttribute"
0xea83a  ldloc.2
0xea83b  newobj   instance void System.Xml.Schema.XmlSchemaInferenceException::.ctor(string res, string arg)
0xea840  throw
0xea841  ldloc.1
0xea842  brfalse.s loc_EA84C
0xea844  ldloc.1
0xea845  call     class System.Xml.Schema.XmlSchemaComplexType System.Xml.Schema.XmlSchemaComplexType::get_AnyType()
0xea84a  bne.un.s loc_EA85A
0xea84c  newobj   instance void System.Xml.Schema.XmlSchemaComplexType::.ctor()
0xea851  stloc.1
0xea852  ldarg.1
0xea853  ldind.ref
0xea854  ldloc.1
0xea855  callvirt instance void System.Xml.Schema.XmlSchemaElement::set_SchemaType(class System.Xml.Schema.XmlSchemaType value)
0xea85a  ldnull
0xea85b  stloc.3
0xea85c  ldarg.2
0xea85d  brfalse.s loc_EA8C4
0xea85f  ldarg.2
0xea860  callvirt instance class System.Xml.Schema.XmlSchemaDatatype System.Xml.Schema.XmlSchemaType::get_Datatype()
0xea865  brfalse.s loc_EA8C4
0xea867  ldarg.1
0xea868  ldind.ref
0xea869  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaElement::get_SchemaTypeName()
0xea86e  callvirt instance bool System.Xml.XmlQualifiedName::get_IsEmpty()
0xea873  brtrue.s loc_EA8C4
0xea875  newobj   instance void System.Xml.Schema.XmlSchemaSimpleContent::.ctor()
0xea87a  stloc.s  4
0xea87c  ldloc.1
0xea87d  ldloc.s  4
0xea87f  callvirt instance void System.Xml.Schema.XmlSchemaComplexType::set_ContentModel(class System.Xml.Schema.XmlSchemaContentModel value)
0xea884  newobj   instance void System.Xml.Schema.XmlSchemaSimpleContentExtension::.ctor()
0xea889  stloc.s  5
0xea88b  ldloc.s  4
0xea88d  ldloc.s  5
0xea88f  callvirt instance void System.Xml.Schema.XmlSchemaContentModel::set_Content(class System.Xml.Schema.XmlSchemaContent value)
0xea894  ldloc.s  5
0xea896  ldarg.1
0xea897  ldind.ref
0xea898  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaElement::get_SchemaTypeName()
0xea89d  callvirt instance void System.Xml.Schema.XmlSchemaSimpleContentExtension::set_BaseTypeName(class System.Xml.XmlQualifiedName value)
0xea8a2  ldloc.s  5
0xea8a4  ldarg.1
0xea8a5  ldind.ref
0xea8a6  callvirt instance int32 System.Xml.Schema.XmlSchemaObject::get_LineNumber()
0xea8ab  callvirt instance void System.Xml.Schema.XmlSchemaObject::set_LineNumber(int32 value)
0xea8b0  ldarg.1
0xea8b1  ldind.ref
0xea8b2  ldc.i4.0
0xea8b3  callvirt instance void System.Xml.Schema.XmlSchemaObject::set_LineNumber(int32 value)
0xea8b8  ldarg.1
0xea8b9  ldind.ref
0xea8ba  ldsfld   class System.Xml.XmlQualifiedName System.Xml.XmlQualifiedName::Empty
0xea8bf  callvirt instance void System.Xml.Schema.XmlSchemaElement::set_SchemaTypeName(class System.Xml.XmlQualifiedName value)
0xea8c4  ldloc.1
0xea8c5  callvirt instance class System.Xml.Schema.XmlSchemaContentModel System.Xml.Schema.XmlSchemaComplexType::get_ContentModel()
0xea8ca  brfalse.s loc_EA91A
0xea8cc  ldarg.0
0xea8cd  ldloc.1
0xea8ce  call     instance class System.Xml.Schema.XmlSchemaSimpleContentExtension System.Xml.Schema.XmlSchemaInference::CheckSimpleContentExtension(class System.Xml.Schema.XmlSchemaComplexType ct)
0xea8d3  stloc.s  6
0xea8d5  ldarg.0
0xea8d6  ldarg.0
0xea8d7  ldfld    class System.Xml.XmlReader System.Xml.Schema.XmlSchemaInference::xtr
0xea8dc  callvirt instance string System.Xml.XmlReader::get_LocalName()
0xea8e1  ldarg.0
0xea8e2  ldfld    class System.Xml.XmlReader System.Xml.Schema.XmlSchemaInference::xtr
0xea8e7  callvirt instance string System.Xml.XmlReader::get_Prefix()
0xea8ec  ldarg.0
0xea8ed  ldfld    class System.Xml.XmlReader System.Xml.Schema.XmlSchemaInference::xtr
0xea8f2  callvirt instance string System.Xml.XmlReader::get_NamespaceURI()
0xea8f7  ldarg.0
0xea8f8  ldfld    class System.Xml.XmlReader System.Xml.Schema.XmlSchemaInference::xtr
0xea8fd  callvirt instance string System.Xml.XmlReader::get_Value()
0xea902  ldarg.3
0xea903  ldarg.s  4
0xea905  ldloc.s  6
0xea907  callvirt instance class System.Xml.Schema.XmlSchemaObjectCollection System.Xml.Schema.XmlSchemaSimpleContentExtension::get_Attributes()
0xea90c  ldloc.1
0xea90d  callvirt instance class System.Xml.Schema.XmlSchemaObjectTable System.Xml.Schema.XmlSchemaComplexType::get_AttributeUses()
0xea912  call     instance class System.Xml.Schema.XmlSchemaAttribute System.Xml.Schema.XmlSchemaInference::AddAttribute(string localName, string prefix, string childURI, string attrValue, bool bCreatingNewType, class System.Xml.Schema.XmlSchema parentSchema, class System.Xml.Schema.XmlSchemaObjectCollection addLocation, class System.Xml.Schema.XmlSchemaObjectTable compiledAttributes)
0xea917  stloc.3
0xea918  br.s     loc_EA95C
0xea91a  ldarg.0
0xea91b  ldarg.0
0xea91c  ldfld    class System.Xml.XmlReader System.Xml.Schema.XmlSchemaInference::xtr
0xea921  callvirt instance string System.Xml.XmlReader::get_LocalName()
0xea926  ldarg.0
0xea927  ldfld    class System.Xml.XmlReader System.Xml.Schema.XmlSchemaInference::xtr
0xea92c  callvirt instance string System.Xml.XmlReader::get_Prefix()
0xea931  ldarg.0
0xea932  ldfld    class System.Xml.XmlReader System.Xml.Schema.XmlSchemaInference::xtr
0xea937  callvirt instance string System.Xml.XmlReader::get_NamespaceURI()
0xea93c  ldarg.0
0xea93d  ldfld    class System.Xml.XmlReader System.Xml.Schema.XmlSchemaInference::xtr
0xea942  callvirt instance string System.Xml.XmlReader::get_Value()
0xea947  ldarg.3
0xea948  ldarg.s  4
0xea94a  ldloc.1
0xea94b  callvirt instance class System.Xml.Schema.XmlSchemaObjectCollection System.Xml.Schema.XmlSchemaComplexType::get_Attributes()
0xea950  ldloc.1
0xea951  callvirt instance class System.Xml.Schema.XmlSchemaObjectTable System.Xml.Schema.XmlSchemaComplexType::get_AttributeUses()
0xea956  call     instance class System.Xml.Schema.XmlSchemaAttribute System.Xml.Schema.XmlSchemaInference::AddAttribute(string localName, string prefix, string childURI, string attrValue, bool bCreatingNewType, class System.Xml.Schema.XmlSchema parentSchema, class System.Xml.Schema.XmlSchemaObjectCollection addLocation, class System.Xml.Schema.XmlSchemaObjectTable compiledAttributes)
0xea95b  stloc.3
0xea95c  ldloc.3
0xea95d  brfalse.s loc_EA967
0xea95f  ldloc.0
0xea960  ldloc.3
0xea961  callvirt instance int32 System.Xml.Schema.XmlSchemaObjectCollection::Add(class System.Xml.Schema.XmlSchemaObject item)
0xea966  pop
0xea967  ldarg.0
0xea968  ldfld    class System.Xml.XmlReader System.Xml.Schema.XmlSchemaInference::xtr
0xea96d  callvirt instance bool System.Xml.XmlReader::MoveToNextAttribute()
0xea972  brtrue   loc_EA74D
0xea977  ldarg.3
0xea978  brtrue.s loc_EA985
0xea97a  ldloc.1
0xea97b  brfalse.s loc_EA985
0xea97d  ldarg.0
0xea97e  ldloc.1
0xea97f  ldloc.0
0xea980  call     instance void System.Xml.Schema.XmlSchemaInference::MakeExistingAttributesOptional(class System.Xml.Schema.XmlSchemaComplexType ct, class System.Xml.Schema.XmlSchemaObjectCollection attributesInInstance)
0xea985  ret
```
