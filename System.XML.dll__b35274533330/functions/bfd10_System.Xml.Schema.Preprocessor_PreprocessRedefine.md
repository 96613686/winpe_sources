# System.Xml.Schema.Preprocessor::PreprocessRedefine

- ea: `0xbfd10`
- end: `0xc01ad`
- name: `System.Xml.Schema.Preprocessor::PreprocessRedefine`
- size: `1181`
- prototype: ``
- caller_count: `1`
- callee_count: `38`
- tags: `registry_config, broker_com_uri`

## callers

- `0xbe980`

## callees

- `0x13580`
- `0xae6f0`
- `0xae930`
- `0xae950`
- `0xae9d0`
- `0xbfd10`
- `0xc01b0`
- `0xc0220`
- `0xc0240`
- `0xc03e0`
- `0xc0420`
- `0xc0480`
- `0xc04d0`
- `0xc07e0`
- `0xc0dd0`
- `0xc10f0`
- `0xc15c0`
- `0xc1d00`
- `0xcfd30`
- `0xcfdf0`
- `0xcfe00`
- `0xcfe30`
- `0xcfe50`
- `0xcfed0`
- `0xd0bf0`
- `0xd0c60`
- `0xd3200`
- `0xd3580`
- `0xd35c0`
- `0xd3eb0`
- `0xd40f0`
- `0xd4230`
- `0xd4640`
- `0xd4650`
- `0xd4660`
- `0xd4670`
- `0xd6b30`
- `0xd6ce0`

## string_xrefs

- `0xbfe3d`: `Sch_ComponentRedefineNotFound`
- `0xbff33`: `Sch_ComponentRedefineNotFound`
- `0xc002a`: `Sch_ComponentRedefineNotFound`
- `0xc013c`: `Sch_ComponentRedefineNotFound`
- `0xbffce`: `Sch_ComplexTypeDoubleRedefine`
- `0xc002f`: `<complexType>`
- `0xc0080`: `Sch_SimpleToComplexTypeRedefine`
- `0xc018c`: `Sch_ComplexToSimpleTypeRedefine`

## pseudocode

```c

```

## disassembly

```asm
0xbfd10  ldarg.1
0xbfd11  ldfld    class System.Xml.Schema.XmlSchemaRedefine System.Xml.Schema.RedefineEntry::redefine
0xbfd16  stloc.0
0xbfd17  ldloc.0
0xbfd18  callvirt instance class System.Xml.Schema.XmlSchema System.Xml.Schema.XmlSchemaExternal::get_Schema()
0xbfd1d  stloc.1
0xbfd1e  ldarg.0
0xbfd1f  ldloc.0
0xbfd20  call     class System.Xml.Schema.XmlSchema System.Xml.Schema.Preprocessor::GetParentSchema(class System.Xml.Schema.XmlSchemaObject currentSchemaObject)
0xbfd25  stfld    class System.Xml.Schema.XmlSchema System.Xml.Schema.Preprocessor::currentSchema
0xbfd2a  ldarg.0
0xbfd2b  ldarg.0
0xbfd2c  ldfld    class System.Xml.Schema.XmlSchema System.Xml.Schema.Preprocessor::currentSchema
0xbfd31  call     instance void System.Xml.Schema.Preprocessor::SetSchemaDefaults(class System.Xml.Schema.XmlSchema schema)
0xbfd36  ldloc.1
0xbfd37  callvirt instance bool System.Xml.Schema.XmlSchema::get_IsRedefined()
0xbfd3c  brfalse.s loc_BFD4C
0xbfd3e  ldarg.0
0xbfd3f  ldstr    aSchMultiplered// "Sch_MultipleRedefine"
0xbfd44  ldloc.0
0xbfd45  ldc.i4.1
0xbfd46  call     instance void System.Xml.Schema.BaseProcessor::SendValidationEvent(string code, class System.Xml.Schema.XmlSchemaObject source, valuetype System.Xml.Schema.XmlSeverityType severity)
0xbfd4b  ret
0xbfd4c  ldloc.1
0xbfd4d  ldc.i4.1
0xbfd4e  callvirt instance void System.Xml.Schema.XmlSchema::set_IsRedefined(bool value)
0xbfd53  ldarg.1
0xbfd54  ldfld    class System.Xml.Schema.XmlSchema System.Xml.Schema.RedefineEntry::schemaToUpdate
0xbfd59  stloc.2
0xbfd5a  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0xbfd5f  stloc.3
0xbfd60  ldarg.0
0xbfd61  ldloc.1
0xbfd62  ldloc.3
0xbfd63  call     instance void System.Xml.Schema.Preprocessor::GetIncludedSet(class System.Xml.Schema.XmlSchema schema, class [mscorlib]System.Collections.ArrayList includesList)
0xbfd68  ldloc.2
0xbfd69  callvirt instance string System.Xml.Schema.XmlSchema::get_TargetNamespace()
0xbfd6e  brfalse.s loc_BFD78
0xbfd70  ldloc.2
0xbfd71  callvirt instance string System.Xml.Schema.XmlSchema::get_TargetNamespace()
0xbfd76  br.s     loc_BFD7D
0xbfd78  ldsfld   string [mscorlib]System.String::Empty
0xbfd7d  stloc.s  4
0xbfd7f  ldloc.0
0xbfd80  callvirt instance class System.Xml.Schema.XmlSchemaObjectCollection System.Xml.Schema.XmlSchemaRedefine::get_Items()
0xbfd85  stloc.s  5
0xbfd87  ldc.i4.0
0xbfd88  stloc.s  6
0xbfd8a  br       loc_C019E
0xbfd8f  ldarg.0
0xbfd90  ldloc.s  5
0xbfd92  ldloc.s  6
0xbfd94  callvirt instance class System.Xml.Schema.XmlSchemaObject System.Xml.Schema.XmlSchemaObjectCollection::get_Item(int32 index)
0xbfd99  ldloc.0
0xbfd9a  call     instance void System.Xml.Schema.Preprocessor::SetParent(class System.Xml.Schema.XmlSchemaObject child, class System.Xml.Schema.XmlSchemaObject parent)
0xbfd9f  ldloc.s  5
0xbfda1  ldloc.s  6
0xbfda3  callvirt instance class System.Xml.Schema.XmlSchemaObject System.Xml.Schema.XmlSchemaObjectCollection::get_Item(int32 index)
0xbfda8  isinst   System.Xml.Schema.XmlSchemaGroup
0xbfdad  stloc.s  7
0xbfdaf  ldloc.s  7
0xbfdb1  brfalse  loc_BFE89
0xbfdb6  ldarg.0
0xbfdb7  ldloc.s  7
0xbfdb9  call     instance void System.Xml.Schema.Preprocessor::PreprocessGroup(class System.Xml.Schema.XmlSchemaGroup group)
0xbfdbe  ldloc.s  7
0xbfdc0  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaGroup::get_QualifiedName()
0xbfdc5  ldloc.s  4
0xbfdc7  callvirt instance void System.Xml.XmlQualifiedName::SetNamespace(string ns)
0xbfdcc  ldloc.0
0xbfdcd  callvirt instance class System.Xml.Schema.XmlSchemaObjectTable System.Xml.Schema.XmlSchemaRedefine::get_Groups()
0xbfdd2  ldloc.s  7
0xbfdd4  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaGroup::get_QualifiedName()
0xbfdd9  callvirt instance class System.Xml.Schema.XmlSchemaObject System.Xml.Schema.XmlSchemaObjectTable::get_Item(class System.Xml.XmlQualifiedName name)
0xbfdde  brfalse.s loc_BFDF2
0xbfde0  ldarg.0
0xbfde1  ldstr    aSchGroupdouble// "Sch_GroupDoubleRedefine"
0xbfde6  ldloc.s  7
0xbfde8  call     instance void System.Xml.Schema.BaseProcessor::SendValidationEvent(string code, class System.Xml.Schema.XmlSchemaObject source)
0xbfded  br       loc_C0198
0xbfdf2  ldarg.0
0xbfdf3  ldloc.0
0xbfdf4  callvirt instance class System.Xml.Schema.XmlSchemaObjectTable System.Xml.Schema.XmlSchemaRedefine::get_Groups()
0xbfdf9  ldloc.s  7
0xbfdfb  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaGroup::get_QualifiedName()
0xbfe00  ldloc.s  7
0xbfe02  call     instance void System.Xml.Schema.BaseProcessor::AddToTable(class System.Xml.Schema.XmlSchemaObjectTable table, class System.Xml.XmlQualifiedName qname, class System.Xml.Schema.XmlSchemaObject item)
0xbfe07  ldloc.2
0xbfe08  callvirt instance class System.Xml.Schema.XmlSchemaObjectTable System.Xml.Schema.XmlSchema::get_Groups()
0xbfe0d  ldloc.s  7
0xbfe0f  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaGroup::get_QualifiedName()
0xbfe14  callvirt instance class System.Xml.Schema.XmlSchemaObject System.Xml.Schema.XmlSchemaObjectTable::get_Item(class System.Xml.XmlQualifiedName name)
0xbfe19  castclass System.Xml.Schema.XmlSchemaGroup
0xbfe1e  stloc.s  8
0xbfe20  ldloc.s  8
0xbfe22  call     class System.Xml.Schema.XmlSchema System.Xml.Schema.Preprocessor::GetParentSchema(class System.Xml.Schema.XmlSchemaObject currentSchemaObject)
0xbfe27  stloc.s  9
0xbfe29  ldloc.s  8
0xbfe2b  brfalse.s loc_BFE3C
0xbfe2d  ldloc.s  9
0xbfe2f  ldloc.1
0xbfe30  beq.s    loc_BFE5F
0xbfe32  ldloc.3
0xbfe33  ldloc.s  9
0xbfe35  callvirt instance bool [mscorlib]System.Collections.ArrayList::Contains(object)
0xbfe3a  brtrue.s loc_BFE5F
0xbfe3c  ldarg.0
0xbfe3d  ldstr    aSchComponentre// "Sch_ComponentRedefineNotFound"
0xbfe42  ldstr    aGroup_0// "<group>"
0xbfe47  ldloc.s  7
0xbfe49  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaGroup::get_QualifiedName()
0xbfe4e  callvirt instance string [mscorlib]System.Object::ToString()
0xbfe53  ldloc.s  7
0xbfe55  call     instance void System.Xml.Schema.BaseProcessor::SendValidationEvent(string code, string msg1, string msg2, class System.Xml.Schema.XmlSchemaObject source)
0xbfe5a  br       loc_C0198
0xbfe5f  ldloc.s  7
0xbfe61  ldloc.s  8
0xbfe63  callvirt instance void System.Xml.Schema.XmlSchemaGroup::set_Redefined(class System.Xml.Schema.XmlSchemaGroup value)
0xbfe68  ldloc.2
0xbfe69  callvirt instance class System.Xml.Schema.XmlSchemaObjectTable System.Xml.Schema.XmlSchema::get_Groups()
0xbfe6e  ldloc.s  7
0xbfe70  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaGroup::get_QualifiedName()
0xbfe75  ldloc.s  7
0xbfe77  callvirt instance void System.Xml.Schema.XmlSchemaObjectTable::Insert(class System.Xml.XmlQualifiedName name, class System.Xml.Schema.XmlSchemaObject value)
0xbfe7c  ldarg.0
0xbfe7d  ldloc.s  7
0xbfe7f  call     instance void System.Xml.Schema.Preprocessor::CheckRefinedGroup(class System.Xml.Schema.XmlSchemaGroup group)
0xbfe84  br       loc_C0198
0xbfe89  ldloc.s  5
0xbfe8b  ldloc.s  6
0xbfe8d  callvirt instance class System.Xml.Schema.XmlSchemaObject System.Xml.Schema.XmlSchemaObjectCollection::get_Item(int32 index)
0xbfe92  isinst   System.Xml.Schema.XmlSchemaAttributeGroup
0xbfe97  brfalse  loc_BFF7F
0xbfe9c  ldloc.s  5
0xbfe9e  ldloc.s  6
0xbfea0  callvirt instance class System.Xml.Schema.XmlSchemaObject System.Xml.Schema.XmlSchemaObjectCollection::get_Item(int32 index)
0xbfea5  castclass System.Xml.Schema.XmlSchemaAttributeGroup
0xbfeaa  stloc.s  0xA
0xbfeac  ldarg.0
0xbfead  ldloc.s  0xA
0xbfeaf  call     instance void System.Xml.Schema.Preprocessor::PreprocessAttributeGroup(class System.Xml.Schema.XmlSchemaAttributeGroup attributeGroup)
0xbfeb4  ldloc.s  0xA
0xbfeb6  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaAttributeGroup::get_QualifiedName()
0xbfebb  ldloc.s  4
0xbfebd  callvirt instance void System.Xml.XmlQualifiedName::SetNamespace(string ns)
0xbfec2  ldloc.0
0xbfec3  callvirt instance class System.Xml.Schema.XmlSchemaObjectTable System.Xml.Schema.XmlSchemaRedefine::get_AttributeGroups()
0xbfec8  ldloc.s  0xA
0xbfeca  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaAttributeGroup::get_QualifiedName()
0xbfecf  callvirt instance class System.Xml.Schema.XmlSchemaObject System.Xml.Schema.XmlSchemaObjectTable::get_Item(class System.Xml.XmlQualifiedName name)
0xbfed4  brfalse.s loc_BFEE8
0xbfed6  ldarg.0
0xbfed7  ldstr    aSchAttrgroupdo// "Sch_AttrGroupDoubleRedefine"
0xbfedc  ldloc.s  0xA
0xbfede  call     instance void System.Xml.Schema.BaseProcessor::SendValidationEvent(string code, class System.Xml.Schema.XmlSchemaObject source)
0xbfee3  br       loc_C0198
0xbfee8  ldarg.0
0xbfee9  ldloc.0
0xbfeea  callvirt instance class System.Xml.Schema.XmlSchemaObjectTable System.Xml.Schema.XmlSchemaRedefine::get_AttributeGroups()
0xbfeef  ldloc.s  0xA
0xbfef1  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaAttributeGroup::get_QualifiedName()
0xbfef6  ldloc.s  0xA
0xbfef8  call     instance void System.Xml.Schema.BaseProcessor::AddToTable(class System.Xml.Schema.XmlSchemaObjectTable table, class System.Xml.XmlQualifiedName qname, class System.Xml.Schema.XmlSchemaObject item)
0xbfefd  ldloc.2
0xbfefe  callvirt instance class System.Xml.Schema.XmlSchemaObjectTable System.Xml.Schema.XmlSchema::get_AttributeGroups()
0xbff03  ldloc.s  0xA
0xbff05  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaAttributeGroup::get_QualifiedName()
0xbff0a  callvirt instance class System.Xml.Schema.XmlSchemaObject System.Xml.Schema.XmlSchemaObjectTable::get_Item(class System.Xml.XmlQualifiedName name)
0xbff0f  castclass System.Xml.Schema.XmlSchemaAttributeGroup
0xbff14  stloc.s  0xB
0xbff16  ldloc.s  0xB
0xbff18  call     class System.Xml.Schema.XmlSchema System.Xml.Schema.Preprocessor::GetParentSchema(class System.Xml.Schema.XmlSchemaObject currentSchemaObject)
0xbff1d  stloc.s  0xC
0xbff1f  ldloc.s  0xB
0xbff21  brfalse.s loc_BFF32
0xbff23  ldloc.s  0xC
0xbff25  ldloc.1
0xbff26  beq.s    loc_BFF55
0xbff28  ldloc.3
0xbff29  ldloc.s  0xC
0xbff2b  callvirt instance bool [mscorlib]System.Collections.ArrayList::Contains(object)
0xbff30  brtrue.s loc_BFF55
0xbff32  ldarg.0
0xbff33  ldstr    aSchComponentre// "Sch_ComponentRedefineNotFound"
0xbff38  ldstr    aAttributegroup_0// "<attributeGroup>"
0xbff3d  ldloc.s  0xA
0xbff3f  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaAttributeGroup::get_QualifiedName()
0xbff44  callvirt instance string [mscorlib]System.Object::ToString()
0xbff49  ldloc.s  0xA
0xbff4b  call     instance void System.Xml.Schema.BaseProcessor::SendValidationEvent(string code, string msg1, string msg2, class System.Xml.Schema.XmlSchemaObject source)
0xbff50  br       loc_C0198
0xbff55  ldloc.s  0xA
0xbff57  ldloc.s  0xB
0xbff59  callvirt instance void System.Xml.Schema.XmlSchemaAttributeGroup::set_Redefined(class System.Xml.Schema.XmlSchemaAttributeGroup value)
0xbff5e  ldloc.2
0xbff5f  callvirt instance class System.Xml.Schema.XmlSchemaObjectTable System.Xml.Schema.XmlSchema::get_AttributeGroups()
0xbff64  ldloc.s  0xA
0xbff66  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaAttributeGroup::get_QualifiedName()
0xbff6b  ldloc.s  0xA
0xbff6d  callvirt instance void System.Xml.Schema.XmlSchemaObjectTable::Insert(class System.Xml.XmlQualifiedName name, class System.Xml.Schema.XmlSchemaObject value)
0xbff72  ldarg.0
0xbff73  ldloc.s  0xA
0xbff75  call     instance void System.Xml.Schema.Preprocessor::CheckRefinedAttributeGroup(class System.Xml.Schema.XmlSchemaAttributeGroup attributeGroup)
0xbff7a  br       loc_C0198
0xbff7f  ldloc.s  5
0xbff81  ldloc.s  6
0xbff83  callvirt instance class System.Xml.Schema.XmlSchemaObject System.Xml.Schema.XmlSchemaObjectCollection::get_Item(int32 index)
0xbff88  isinst   System.Xml.Schema.XmlSchemaComplexType
0xbff8d  brfalse  loc_C0091
0xbff92  ldloc.s  5
0xbff94  ldloc.s  6
0xbff96  callvirt instance class System.Xml.Schema.XmlSchemaObject System.Xml.Schema.XmlSchemaObjectCollection::get_Item(int32 index)
0xbff9b  castclass System.Xml.Schema.XmlSchemaComplexType
0xbffa0  stloc.s  0xD
0xbffa2  ldarg.0
0xbffa3  ldloc.s  0xD
0xbffa5  ldc.i4.0
0xbffa6  call     instance void System.Xml.Schema.Preprocessor::PreprocessComplexType(class System.Xml.Schema.XmlSchemaComplexType complexType, bool local)
0xbffab  ldloc.s  0xD
0xbffad  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaType::get_QualifiedName()
0xbffb2  ldloc.s  4
0xbffb4  callvirt instance void System.Xml.XmlQualifiedName::SetNamespace(string ns)
0xbffb9  ldloc.0
0xbffba  callvirt instance class System.Xml.Schema.XmlSchemaObjectTable System.Xml.Schema.XmlSchemaRedefine::get_SchemaTypes()
0xbffbf  ldloc.s  0xD
0xbffc1  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaType::get_QualifiedName()
0xbffc6  callvirt instance class System.Xml.Schema.XmlSchemaObject System.Xml.Schema.XmlSchemaObjectTable::get_Item(class System.Xml.XmlQualifiedName name)
0xbffcb  brfalse.s loc_BFFDF
0xbffcd  ldarg.0
0xbffce  ldstr    aSchComplextype// "Sch_ComplexTypeDoubleRedefine"
0xbffd3  ldloc.s  0xD
0xbffd5  call     instance void System.Xml.Schema.BaseProcessor::SendValidationEvent(string code, class System.Xml.Schema.XmlSchemaObject source)
0xbffda  br       loc_C0198
0xbffdf  ldarg.0
0xbffe0  ldloc.0
0xbffe1  callvirt instance class System.Xml.Schema.XmlSchemaObjectTable System.Xml.Schema.XmlSchemaRedefine::get_SchemaTypes()
0xbffe6  ldloc.s  0xD
0xbffe8  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaType::get_QualifiedName()
0xbffed  ldloc.s  0xD
0xbffef  call     instance void System.Xml.Schema.BaseProcessor::AddToTable(class System.Xml.Schema.XmlSchemaObjectTable table, class System.Xml.XmlQualifiedName qname, class System.Xml.Schema.XmlSchemaObject item)
0xbfff4  ldloc.2
0xbfff5  callvirt instance class System.Xml.Schema.XmlSchemaObjectTable System.Xml.Schema.XmlSchema::get_SchemaTypes()
0xbfffa  ldloc.s  0xD
0xbfffc  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaType::get_QualifiedName()
0xc0001  callvirt instance class System.Xml.Schema.XmlSchemaObject System.Xml.Schema.XmlSchemaObjectTable::get_Item(class System.Xml.XmlQualifiedName name)
0xc0006  castclass System.Xml.Schema.XmlSchemaType
0xc000b  stloc.s  0xE
0xc000d  ldloc.s  0xE
0xc000f  call     class System.Xml.Schema.XmlSchema System.Xml.Schema.Preprocessor::GetParentSchema(class System.Xml.Schema.XmlSchemaObject currentSchemaObject)
0xc0014  stloc.s  0xF
0xc0016  ldloc.s  0xE
0xc0018  brfalse.s loc_C0029
0xc001a  ldloc.s  0xF
0xc001c  ldloc.1
0xc001d  beq.s    loc_C004C
0xc001f  ldloc.3
0xc0020  ldloc.s  0xF
0xc0022  callvirt instance bool [mscorlib]System.Collections.ArrayList::Contains(object)
0xc0027  brtrue.s loc_C004C
0xc0029  ldarg.0
0xc002a  ldstr    aSchComponentre// "Sch_ComponentRedefineNotFound"
0xc002f  ldstr    aComplextype_0// "<complexType>"
0xc0034  ldloc.s  0xD
0xc0036  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaType::get_QualifiedName()
0xc003b  callvirt instance string [mscorlib]System.Object::ToString()
0xc0040  ldloc.s  0xD
0xc0042  call     instance void System.Xml.Schema.BaseProcessor::SendValidationEvent(string code, string msg1, string msg2, class System.Xml.Schema.XmlSchemaObject source)
0xc0047  br       loc_C0198
0xc004c  ldloc.s  0xE
0xc004e  isinst   System.Xml.Schema.XmlSchemaComplexType
0xc0053  brfalse.s loc_C007F
0xc0055  ldloc.s  0xD
0xc0057  ldloc.s  0xE
0xc0059  callvirt instance void System.Xml.Schema.XmlSchemaType::set_Redefined(class System.Xml.Schema.XmlSchemaType value)
0xc005e  ldloc.2
0xc005f  callvirt instance class System.Xml.Schema.XmlSchemaObjectTable System.Xml.Schema.XmlSchema::get_SchemaTypes()
0xc0064  ldloc.s  0xD
0xc0066  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaType::get_QualifiedName()
0xc006b  ldloc.s  0xD
0xc006d  callvirt instance void System.Xml.Schema.XmlSchemaObjectTable::Insert(class System.Xml.XmlQualifiedName name, class System.Xml.Schema.XmlSchemaObject value)
0xc0072  ldarg.0
0xc0073  ldloc.s  0xD
0xc0075  call     instance void System.Xml.Schema.Preprocessor::CheckRefinedComplexType(class System.Xml.Schema.XmlSchemaComplexType ctype)
0xc007a  br       loc_C0198
0xc007f  ldarg.0
0xc0080  ldstr    aSchSimpletocom// "Sch_SimpleToComplexTypeRedefine"
0xc0085  ldloc.s  0xD
0xc0087  call     instance void System.Xml.Schema.BaseProcessor::SendValidationEvent(string code, class System.Xml.Schema.XmlSchemaObject source)
0xc008c  br       loc_C0198
0xc0091  ldloc.s  5
0xc0093  ldloc.s  6
0xc0095  callvirt instance class System.Xml.Schema.XmlSchemaObject System.Xml.Schema.XmlSchemaObjectCollection::get_Item(int32 index)
0xc009a  isinst   System.Xml.Schema.XmlSchemaSimpleType
0xc009f  brfalse  loc_C0198
0xc00a4  ldloc.s  5
0xc00a6  ldloc.s  6
0xc00a8  callvirt instance class System.Xml.Schema.XmlSchemaObject System.Xml.Schema.XmlSchemaObjectCollection::get_Item(int32 index)
0xc00ad  castclass System.Xml.Schema.XmlSchemaSimpleType
0xc00b2  stloc.s  0x10
0xc00b4  ldarg.0
  ... truncated ...
```
