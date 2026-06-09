# System.Xml.Schema.SchemaCollectionPreprocessor::PreprocessRedefine

- ea: `0xc7350`
- end: `0xc7782`
- name: `System.Xml.Schema.SchemaCollectionPreprocessor::PreprocessRedefine`
- size: `1074`
- prototype: ``
- caller_count: `1`
- callee_count: `32`
- tags: `registry_config, broker_com_uri`

## callers

- `0xc6a30`

## callees

- `0xae6f0`
- `0xae930`
- `0xc7350`
- `0xc7830`
- `0xc7870`
- `0xc78d0`
- `0xc7920`
- `0xc7c30`
- `0xc8230`
- `0xc8550`
- `0xc8a20`
- `0xc9050`
- `0xcfe30`
- `0xcfe50`
- `0xcfed0`
- `0xd0bf0`
- `0xd0c50`
- `0xd0c60`
- `0xd3200`
- `0xd3580`
- `0xd35b0`
- `0xd35c0`
- `0xd3eb0`
- `0xd40f0`
- `0xd4230`
- `0xd4290`
- `0xd4640`
- `0xd4650`
- `0xd4660`
- `0xd4670`
- `0xd6b30`
- `0xd6ce0`

## string_xrefs

- `0xc74f6`: `Sch_ComplexTypeDoubleRedefine`
- `0xc7558`: `Sch_SimpleToComplexTypeRedefine`
- `0xc7622`: `Sch_ComplexToSimpleTypeRedefine`
- `0xc7569`: `Sch_ComplexTypeRedefineNotFound`

## pseudocode

```c

```

## disassembly

```asm
0xc7350  ldc.i4.0
0xc7351  stloc.0
0xc7352  br       loc_C7641
0xc7357  ldarg.0
0xc7358  ldarg.1
0xc7359  callvirt instance class System.Xml.Schema.XmlSchemaObjectCollection System.Xml.Schema.XmlSchemaRedefine::get_Items()
0xc735e  ldloc.0
0xc735f  callvirt instance class System.Xml.Schema.XmlSchemaObject System.Xml.Schema.XmlSchemaObjectCollection::get_Item(int32 index)
0xc7364  ldarg.1
0xc7365  call     instance void System.Xml.Schema.SchemaCollectionPreprocessor::SetParent(class System.Xml.Schema.XmlSchemaObject child, class System.Xml.Schema.XmlSchemaObject parent)
0xc736a  ldarg.1
0xc736b  callvirt instance class System.Xml.Schema.XmlSchemaObjectCollection System.Xml.Schema.XmlSchemaRedefine::get_Items()
0xc7370  ldloc.0
0xc7371  callvirt instance class System.Xml.Schema.XmlSchemaObject System.Xml.Schema.XmlSchemaObjectCollection::get_Item(int32 index)
0xc7376  isinst   System.Xml.Schema.XmlSchemaGroup
0xc737b  stloc.1
0xc737c  ldloc.1
0xc737d  brfalse  loc_C7406
0xc7382  ldarg.0
0xc7383  ldloc.1
0xc7384  call     instance void System.Xml.Schema.SchemaCollectionPreprocessor::PreprocessGroup(class System.Xml.Schema.XmlSchemaGroup group)
0xc7389  ldarg.1
0xc738a  callvirt instance class System.Xml.Schema.XmlSchemaObjectTable System.Xml.Schema.XmlSchemaRedefine::get_Groups()
0xc738f  ldloc.1
0xc7390  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaGroup::get_QualifiedName()
0xc7395  callvirt instance class System.Xml.Schema.XmlSchemaObject System.Xml.Schema.XmlSchemaObjectTable::get_Item(class System.Xml.XmlQualifiedName name)
0xc739a  brfalse.s loc_C73AD
0xc739c  ldarg.0
0xc739d  ldstr    aSchGroupdouble// "Sch_GroupDoubleRedefine"
0xc73a2  ldloc.1
0xc73a3  call     instance void System.Xml.Schema.BaseProcessor::SendValidationEvent(string code, class System.Xml.Schema.XmlSchemaObject source)
0xc73a8  br       loc_C763D
0xc73ad  ldarg.0
0xc73ae  ldarg.1
0xc73af  callvirt instance class System.Xml.Schema.XmlSchemaObjectTable System.Xml.Schema.XmlSchemaRedefine::get_Groups()
0xc73b4  ldloc.1
0xc73b5  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaGroup::get_QualifiedName()
0xc73ba  ldloc.1
0xc73bb  call     instance void System.Xml.Schema.BaseProcessor::AddToTable(class System.Xml.Schema.XmlSchemaObjectTable table, class System.Xml.XmlQualifiedName qname, class System.Xml.Schema.XmlSchemaObject item)
0xc73c0  ldloc.1
0xc73c1  ldarg.1
0xc73c2  callvirt instance class System.Xml.Schema.XmlSchema System.Xml.Schema.XmlSchemaExternal::get_Schema()
0xc73c7  callvirt instance class System.Xml.Schema.XmlSchemaObjectTable System.Xml.Schema.XmlSchema::get_Groups()
0xc73cc  ldloc.1
0xc73cd  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaGroup::get_QualifiedName()
0xc73d2  callvirt instance class System.Xml.Schema.XmlSchemaObject System.Xml.Schema.XmlSchemaObjectTable::get_Item(class System.Xml.XmlQualifiedName name)
0xc73d7  castclass System.Xml.Schema.XmlSchemaGroup
0xc73dc  callvirt instance void System.Xml.Schema.XmlSchemaGroup::set_Redefined(class System.Xml.Schema.XmlSchemaGroup value)
0xc73e1  ldloc.1
0xc73e2  callvirt instance class System.Xml.Schema.XmlSchemaGroup System.Xml.Schema.XmlSchemaGroup::get_Redefined()
0xc73e7  brfalse.s loc_C73F5
0xc73e9  ldarg.0
0xc73ea  ldloc.1
0xc73eb  call     instance void System.Xml.Schema.SchemaCollectionPreprocessor::CheckRefinedGroup(class System.Xml.Schema.XmlSchemaGroup group)
0xc73f0  br       loc_C763D
0xc73f5  ldarg.0
0xc73f6  ldstr    aSchGroupredefi// "Sch_GroupRedefineNotFound"
0xc73fb  ldloc.1
0xc73fc  call     instance void System.Xml.Schema.BaseProcessor::SendValidationEvent(string code, class System.Xml.Schema.XmlSchemaObject source)
0xc7401  br       loc_C763D
0xc7406  ldarg.1
0xc7407  callvirt instance class System.Xml.Schema.XmlSchemaObjectCollection System.Xml.Schema.XmlSchemaRedefine::get_Items()
0xc740c  ldloc.0
0xc740d  callvirt instance class System.Xml.Schema.XmlSchemaObject System.Xml.Schema.XmlSchemaObjectCollection::get_Item(int32 index)
0xc7412  isinst   System.Xml.Schema.XmlSchemaAttributeGroup
0xc7417  brfalse  loc_C74B2
0xc741c  ldarg.1
0xc741d  callvirt instance class System.Xml.Schema.XmlSchemaObjectCollection System.Xml.Schema.XmlSchemaRedefine::get_Items()
0xc7422  ldloc.0
0xc7423  callvirt instance class System.Xml.Schema.XmlSchemaObject System.Xml.Schema.XmlSchemaObjectCollection::get_Item(int32 index)
0xc7428  castclass System.Xml.Schema.XmlSchemaAttributeGroup
0xc742d  stloc.2
0xc742e  ldarg.0
0xc742f  ldloc.2
0xc7430  call     instance void System.Xml.Schema.SchemaCollectionPreprocessor::PreprocessAttributeGroup(class System.Xml.Schema.XmlSchemaAttributeGroup attributeGroup)
0xc7435  ldarg.1
0xc7436  callvirt instance class System.Xml.Schema.XmlSchemaObjectTable System.Xml.Schema.XmlSchemaRedefine::get_AttributeGroups()
0xc743b  ldloc.2
0xc743c  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaAttributeGroup::get_QualifiedName()
0xc7441  callvirt instance class System.Xml.Schema.XmlSchemaObject System.Xml.Schema.XmlSchemaObjectTable::get_Item(class System.Xml.XmlQualifiedName name)
0xc7446  brfalse.s loc_C7459
0xc7448  ldarg.0
0xc7449  ldstr    aSchAttrgroupdo// "Sch_AttrGroupDoubleRedefine"
0xc744e  ldloc.2
0xc744f  call     instance void System.Xml.Schema.BaseProcessor::SendValidationEvent(string code, class System.Xml.Schema.XmlSchemaObject source)
0xc7454  br       loc_C763D
0xc7459  ldarg.0
0xc745a  ldarg.1
0xc745b  callvirt instance class System.Xml.Schema.XmlSchemaObjectTable System.Xml.Schema.XmlSchemaRedefine::get_AttributeGroups()
0xc7460  ldloc.2
0xc7461  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaAttributeGroup::get_QualifiedName()
0xc7466  ldloc.2
0xc7467  call     instance void System.Xml.Schema.BaseProcessor::AddToTable(class System.Xml.Schema.XmlSchemaObjectTable table, class System.Xml.XmlQualifiedName qname, class System.Xml.Schema.XmlSchemaObject item)
0xc746c  ldloc.2
0xc746d  ldarg.1
0xc746e  callvirt instance class System.Xml.Schema.XmlSchema System.Xml.Schema.XmlSchemaExternal::get_Schema()
0xc7473  callvirt instance class System.Xml.Schema.XmlSchemaObjectTable System.Xml.Schema.XmlSchema::get_AttributeGroups()
0xc7478  ldloc.2
0xc7479  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaAttributeGroup::get_QualifiedName()
0xc747e  callvirt instance class System.Xml.Schema.XmlSchemaObject System.Xml.Schema.XmlSchemaObjectTable::get_Item(class System.Xml.XmlQualifiedName name)
0xc7483  castclass System.Xml.Schema.XmlSchemaAttributeGroup
0xc7488  callvirt instance void System.Xml.Schema.XmlSchemaAttributeGroup::set_Redefined(class System.Xml.Schema.XmlSchemaAttributeGroup value)
0xc748d  ldloc.2
0xc748e  callvirt instance class System.Xml.Schema.XmlSchemaAttributeGroup System.Xml.Schema.XmlSchemaAttributeGroup::get_Redefined()
0xc7493  brfalse.s loc_C74A1
0xc7495  ldarg.0
0xc7496  ldloc.2
0xc7497  call     instance void System.Xml.Schema.SchemaCollectionPreprocessor::CheckRefinedAttributeGroup(class System.Xml.Schema.XmlSchemaAttributeGroup attributeGroup)
0xc749c  br       loc_C763D
0xc74a1  ldarg.0
0xc74a2  ldstr    aSchAttrgroupre// "Sch_AttrGroupRedefineNotFound"
0xc74a7  ldloc.2
0xc74a8  call     instance void System.Xml.Schema.BaseProcessor::SendValidationEvent(string code, class System.Xml.Schema.XmlSchemaObject source)
0xc74ad  br       loc_C763D
0xc74b2  ldarg.1
0xc74b3  callvirt instance class System.Xml.Schema.XmlSchemaObjectCollection System.Xml.Schema.XmlSchemaRedefine::get_Items()
0xc74b8  ldloc.0
0xc74b9  callvirt instance class System.Xml.Schema.XmlSchemaObject System.Xml.Schema.XmlSchemaObjectCollection::get_Item(int32 index)
0xc74be  isinst   System.Xml.Schema.XmlSchemaComplexType
0xc74c3  brfalse  loc_C7579
0xc74c8  ldarg.1
0xc74c9  callvirt instance class System.Xml.Schema.XmlSchemaObjectCollection System.Xml.Schema.XmlSchemaRedefine::get_Items()
0xc74ce  ldloc.0
0xc74cf  callvirt instance class System.Xml.Schema.XmlSchemaObject System.Xml.Schema.XmlSchemaObjectCollection::get_Item(int32 index)
0xc74d4  castclass System.Xml.Schema.XmlSchemaComplexType
0xc74d9  stloc.3
0xc74da  ldarg.0
0xc74db  ldloc.3
0xc74dc  ldc.i4.0
0xc74dd  call     instance void System.Xml.Schema.SchemaCollectionPreprocessor::PreprocessComplexType(class System.Xml.Schema.XmlSchemaComplexType complexType, bool local)
0xc74e2  ldarg.1
0xc74e3  callvirt instance class System.Xml.Schema.XmlSchemaObjectTable System.Xml.Schema.XmlSchemaRedefine::get_SchemaTypes()
0xc74e8  ldloc.3
0xc74e9  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaType::get_QualifiedName()
0xc74ee  callvirt instance class System.Xml.Schema.XmlSchemaObject System.Xml.Schema.XmlSchemaObjectTable::get_Item(class System.Xml.XmlQualifiedName name)
0xc74f3  brfalse.s loc_C7506
0xc74f5  ldarg.0
0xc74f6  ldstr    aSchComplextype// "Sch_ComplexTypeDoubleRedefine"
0xc74fb  ldloc.3
0xc74fc  call     instance void System.Xml.Schema.BaseProcessor::SendValidationEvent(string code, class System.Xml.Schema.XmlSchemaObject source)
0xc7501  br       loc_C763D
0xc7506  ldarg.0
0xc7507  ldarg.1
0xc7508  callvirt instance class System.Xml.Schema.XmlSchemaObjectTable System.Xml.Schema.XmlSchemaRedefine::get_SchemaTypes()
0xc750d  ldloc.3
0xc750e  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaType::get_QualifiedName()
0xc7513  ldloc.3
0xc7514  call     instance void System.Xml.Schema.BaseProcessor::AddToTable(class System.Xml.Schema.XmlSchemaObjectTable table, class System.Xml.XmlQualifiedName qname, class System.Xml.Schema.XmlSchemaObject item)
0xc7519  ldarg.1
0xc751a  callvirt instance class System.Xml.Schema.XmlSchema System.Xml.Schema.XmlSchemaExternal::get_Schema()
0xc751f  callvirt instance class System.Xml.Schema.XmlSchemaObjectTable System.Xml.Schema.XmlSchema::get_SchemaTypes()
0xc7524  ldloc.3
0xc7525  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaType::get_QualifiedName()
0xc752a  callvirt instance class System.Xml.Schema.XmlSchemaObject System.Xml.Schema.XmlSchemaObjectTable::get_Item(class System.Xml.XmlQualifiedName name)
0xc752f  castclass System.Xml.Schema.XmlSchemaType
0xc7534  stloc.s  4
0xc7536  ldloc.s  4
0xc7538  brfalse.s loc_C7568
0xc753a  ldloc.s  4
0xc753c  isinst   System.Xml.Schema.XmlSchemaComplexType
0xc7541  brfalse.s loc_C7557
0xc7543  ldloc.3
0xc7544  ldloc.s  4
0xc7546  callvirt instance void System.Xml.Schema.XmlSchemaType::set_Redefined(class System.Xml.Schema.XmlSchemaType value)
0xc754b  ldarg.0
0xc754c  ldloc.3
0xc754d  call     instance void System.Xml.Schema.SchemaCollectionPreprocessor::CheckRefinedComplexType(class System.Xml.Schema.XmlSchemaComplexType ctype)
0xc7552  br       loc_C763D
0xc7557  ldarg.0
0xc7558  ldstr    aSchSimpletocom// "Sch_SimpleToComplexTypeRedefine"
0xc755d  ldloc.3
0xc755e  call     instance void System.Xml.Schema.BaseProcessor::SendValidationEvent(string code, class System.Xml.Schema.XmlSchemaObject source)
0xc7563  br       loc_C763D
0xc7568  ldarg.0
0xc7569  ldstr    aSchComplextype_0// "Sch_ComplexTypeRedefineNotFound"
0xc756e  ldloc.3
0xc756f  call     instance void System.Xml.Schema.BaseProcessor::SendValidationEvent(string code, class System.Xml.Schema.XmlSchemaObject source)
0xc7574  br       loc_C763D
0xc7579  ldarg.1
0xc757a  callvirt instance class System.Xml.Schema.XmlSchemaObjectCollection System.Xml.Schema.XmlSchemaRedefine::get_Items()
0xc757f  ldloc.0
0xc7580  callvirt instance class System.Xml.Schema.XmlSchemaObject System.Xml.Schema.XmlSchemaObjectCollection::get_Item(int32 index)
0xc7585  isinst   System.Xml.Schema.XmlSchemaSimpleType
0xc758a  brfalse  loc_C763D
0xc758f  ldarg.1
0xc7590  callvirt instance class System.Xml.Schema.XmlSchemaObjectCollection System.Xml.Schema.XmlSchemaRedefine::get_Items()
0xc7595  ldloc.0
0xc7596  callvirt instance class System.Xml.Schema.XmlSchemaObject System.Xml.Schema.XmlSchemaObjectCollection::get_Item(int32 index)
0xc759b  castclass System.Xml.Schema.XmlSchemaSimpleType
0xc75a0  stloc.s  5
0xc75a2  ldarg.0
0xc75a3  ldloc.s  5
0xc75a5  ldc.i4.0
0xc75a6  call     instance void System.Xml.Schema.SchemaCollectionPreprocessor::PreprocessSimpleType(class System.Xml.Schema.XmlSchemaSimpleType simpleType, bool local)
0xc75ab  ldarg.1
0xc75ac  callvirt instance class System.Xml.Schema.XmlSchemaObjectTable System.Xml.Schema.XmlSchemaRedefine::get_SchemaTypes()
0xc75b1  ldloc.s  5
0xc75b3  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaType::get_QualifiedName()
0xc75b8  callvirt instance class System.Xml.Schema.XmlSchemaObject System.Xml.Schema.XmlSchemaObjectTable::get_Item(class System.Xml.XmlQualifiedName name)
0xc75bd  brfalse.s loc_C75CE
0xc75bf  ldarg.0
0xc75c0  ldstr    aSchSimpletyped// "Sch_SimpleTypeDoubleRedefine"
0xc75c5  ldloc.s  5
0xc75c7  call     instance void System.Xml.Schema.BaseProcessor::SendValidationEvent(string code, class System.Xml.Schema.XmlSchemaObject source)
0xc75cc  br.s     loc_C763D
0xc75ce  ldarg.0
0xc75cf  ldarg.1
0xc75d0  callvirt instance class System.Xml.Schema.XmlSchemaObjectTable System.Xml.Schema.XmlSchemaRedefine::get_SchemaTypes()
0xc75d5  ldloc.s  5
0xc75d7  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaType::get_QualifiedName()
0xc75dc  ldloc.s  5
0xc75de  call     instance void System.Xml.Schema.BaseProcessor::AddToTable(class System.Xml.Schema.XmlSchemaObjectTable table, class System.Xml.XmlQualifiedName qname, class System.Xml.Schema.XmlSchemaObject item)
0xc75e3  ldarg.1
0xc75e4  callvirt instance class System.Xml.Schema.XmlSchema System.Xml.Schema.XmlSchemaExternal::get_Schema()
0xc75e9  callvirt instance class System.Xml.Schema.XmlSchemaObjectTable System.Xml.Schema.XmlSchema::get_SchemaTypes()
0xc75ee  ldloc.s  5
0xc75f0  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaType::get_QualifiedName()
0xc75f5  callvirt instance class System.Xml.Schema.XmlSchemaObject System.Xml.Schema.XmlSchemaObjectTable::get_Item(class System.Xml.XmlQualifiedName name)
0xc75fa  castclass System.Xml.Schema.XmlSchemaType
0xc75ff  stloc.s  6
0xc7601  ldloc.s  6
0xc7603  brfalse.s loc_C7630
0xc7605  ldloc.s  6
0xc7607  isinst   System.Xml.Schema.XmlSchemaSimpleType
0xc760c  brfalse.s loc_C7621
0xc760e  ldloc.s  5
0xc7610  ldloc.s  6
0xc7612  callvirt instance void System.Xml.Schema.XmlSchemaType::set_Redefined(class System.Xml.Schema.XmlSchemaType value)
0xc7617  ldarg.0
0xc7618  ldloc.s  5
0xc761a  call     instance void System.Xml.Schema.SchemaCollectionPreprocessor::CheckRefinedSimpleType(class System.Xml.Schema.XmlSchemaSimpleType stype)
0xc761f  br.s     loc_C763D
0xc7621  ldarg.0
0xc7622  ldstr    aSchComplextosi// "Sch_ComplexToSimpleTypeRedefine"
0xc7627  ldloc.s  5
0xc7629  call     instance void System.Xml.Schema.BaseProcessor::SendValidationEvent(string code, class System.Xml.Schema.XmlSchemaObject source)
0xc762e  br.s     loc_C763D
0xc7630  ldarg.0
0xc7631  ldstr    aSchSimpletyper_1// "Sch_SimpleTypeRedefineNotFound"
0xc7636  ldloc.s  5
0xc7638  call     instance void System.Xml.Schema.BaseProcessor::SendValidationEvent(string code, class System.Xml.Schema.XmlSchemaObject source)
0xc763d  ldloc.0
0xc763e  ldc.i4.1
0xc763f  add
0xc7640  stloc.0
0xc7641  ldloc.0
0xc7642  ldarg.1
0xc7643  callvirt instance class System.Xml.Schema.XmlSchemaObjectCollection System.Xml.Schema.XmlSchemaRedefine::get_Items()
0xc7648  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0xc764d  blt      loc_C7357
0xc7652  ldarg.1
0xc7653  callvirt instance class System.Xml.Schema.XmlSchemaObjectTable System.Xml.Schema.XmlSchemaRedefine::get_Groups()
0xc7658  callvirt instance class [mscorlib]System.Collections.IDictionaryEnumerator System.Xml.Schema.XmlSchemaObjectTable::GetEnumerator()
0xc765d  stloc.s  7
0xc765f  br.s     loc_C7697
0xc7661  ldloc.s  7
0xc7663  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xc7668  unbox.any [mscorlib]System.Collections.DictionaryEntry
0xc766d  stloc.s  8
0xc766f  ldarg.1
0xc7670  callvirt instance class System.Xml.Schema.XmlSchema System.Xml.Schema.XmlSchemaExternal::get_Schema()
0xc7675  callvirt instance class System.Xml.Schema.XmlSchemaObjectTable System.Xml.Schema.XmlSchema::get_Groups()
0xc767a  ldloca.s 8
0xc767c  call     instance object [mscorlib]System.Collections.DictionaryEntry::get_Key()
0xc7681  castclass System.Xml.XmlQualifiedName
0xc7686  ldloca.s 8
0xc7688  call     instance object [mscorlib]System.Collections.DictionaryEntry::get_Value()
0xc768d  castclass System.Xml.Schema.XmlSchemaObject
0xc7692  callvirt instance void System.Xml.Schema.XmlSchemaObjectTable::Insert(class System.Xml.XmlQualifiedName name, class System.Xml.Schema.XmlSchemaObject value)
0xc7697  ldloc.s  7
0xc7699  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xc769e  brtrue.s loc_C7661
0xc76a0  leave.s  loc_C76B7
0xc76a2  ldloc.s  7
0xc76a4  isinst   [mscorlib]System.IDisposable
0xc76a9  stloc.s  9
0xc76ab  ldloc.s  9
0xc76ad  brfalse.s loc_C76B6
0xc76af  ldloc.s  9
0xc76b1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc76b6  endfinally
0xc76b7  ldarg.1
0xc76b8  callvirt instance class System.Xml.Schema.XmlSchemaObjectTable System.Xml.Schema.XmlSchemaRedefine::get_AttributeGroups()
0xc76bd  callvirt instance class [mscorlib]System.Collections.IDictionaryEnumerator System.Xml.Schema.XmlSchemaObjectTable::GetEnumerator()
0xc76c2  stloc.s  0xA
0xc76c4  br.s     loc_C76FC
0xc76c6  ldloc.s  0xA
0xc76c8  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xc76cd  unbox.any [mscorlib]System.Collections.DictionaryEntry
0xc76d2  stloc.s  0xB
0xc76d4  ldarg.1
0xc76d5  callvirt instance class System.Xml.Schema.XmlSchema System.Xml.Schema.XmlSchemaExternal::get_Schema()
0xc76da  callvirt instance class System.Xml.Schema.XmlSchemaObjectTable System.Xml.Schema.XmlSchema::get_AttributeGroups()
0xc76df  ldloca.s 0xB
0xc76e1  call     instance object [mscorlib]System.Collections.DictionaryEntry::get_Key()
0xc76e6  castclass System.Xml.XmlQualifiedName
0xc76eb  ldloca.s 0xB
0xc76ed  call     instance object [mscorlib]System.Collections.DictionaryEntry::get_Value()
0xc76f2  castclass System.Xml.Schema.XmlSchemaObject
0xc76f7  callvirt instance void System.Xml.Schema.XmlSchemaObjectTable::Insert(class System.Xml.XmlQualifiedName name, class System.Xml.Schema.XmlSchemaObject value)
  ... truncated ...
```
