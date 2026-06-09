# Microsoft.ReportingServices.Modeling.ModelGeneration.SetEntityAttributesRule::Microsoft.ReportingServices.Modeling.ModelGeneration.ITableProcessingRule.Process

- ea: `0x2b290`
- end: `0x2b478`
- name: `Microsoft.ReportingServices.Modeling.ModelGeneration.SetEntityAttributesRule::Microsoft.ReportingServices.Modeling.ModelGeneration.ITableProcessingRule.Process`
- size: `488`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: `service_task, broker_com_uri`

## callees

- `0xf170`
- `0xf190`
- `0x11710`
- `0x25590`
- `0x278e0`
- `0x27920`
- `0x29700`
- `0x29710`
- `0x29740`
- `0x2a090`
- `0x2b290`
- `0x2b480`
- `0x2b4c0`
- `0x2b520`
- `0x2b6c0`
- `0x2b9c0`
- `0x2d480`
- `0x2d650`
- `0x2d670`
- `0x2d690`
- `0x3a190`
- `0x3a1a0`
- `0x3a1b0`
- `0x3a1c0`

## pseudocode

```c

```

## disassembly

```asm
0x2b290  ldarg.2
0x2b291  callvirt instance class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.ModelGeneration.ExistingTableBindingInfo::get_Entity()
0x2b296  stloc.0
0x2b297  ldloc.0
0x2b298  brtrue.s loc_2B2AF
0x2b29a  ldarg.0
0x2b29b  ldc.i4.1
0x2b29c  newarr   [mscorlib]System.String
0x2b2a1  dup
0x2b2a2  ldc.i4.0
0x2b2a3  call     string Microsoft.ReportingServices.Modeling.ModelGeneration.SR::get_Rules_EntityDoesNotExist()
0x2b2a8  stelem.ref
0x2b2a9  call     instance class Microsoft.ReportingServices.Modeling.ModelGeneration.RuleProcessResult Microsoft.ReportingServices.Modeling.ModelGeneration.ProcessingRule::ProcessSkipped(string[] messages)
0x2b2ae  ret
0x2b2af  ldarg.2
0x2b2b0  callvirt instance bool Microsoft.ReportingServices.Modeling.ModelGeneration.ExistingBindingInfo::get_EvaluateDependentRules()
0x2b2b5  brtrue.s loc_2B2BF
0x2b2b7  ldarg.0
0x2b2b8  ldloc.0
0x2b2b9  call     instance class Microsoft.ReportingServices.Modeling.ModelGeneration.RuleProcessResult Microsoft.ReportingServices.Modeling.ModelGeneration.ProcessingRule::ProcessDependentRulesSkipped(class Microsoft.ReportingServices.Modeling.ModelItem item)
0x2b2be  ret
0x2b2bf  ldloc.0
0x2b2c0  call     valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.SRObjectDescriptor::FromScope(class Microsoft.ReportingServices.Modeling.IValidationScope scope)
0x2b2c5  stloc.1
0x2b2c6  ldarg.0
0x2b2c7  ldloc.0
0x2b2c8  call     instance class Microsoft.ReportingServices.Modeling.AttributeReferenceCollection Microsoft.ReportingServices.Modeling.ModelGeneration.SetEntityAttributesRule::GetAttributesCollection(class Microsoft.ReportingServices.Modeling.ModelEntity entity)
0x2b2cd  stloc.2
0x2b2ce  ldloc.2
0x2b2cf  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.AttributeReference>::get_Count()
0x2b2d4  ldc.i4.0
0x2b2d5  bgt.s    loc_2B2E5
0x2b2d7  ldarg.0
0x2b2d8  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.ReportingServices.Modeling.ModelEntity, class CandidateFields> Microsoft.ReportingServices.Modeling.ModelGeneration.SetEntityAttributesRule::m_entityCandidateFields
0x2b2dd  ldloc.0
0x2b2de  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.ReportingServices.Modeling.ModelEntity, class CandidateFields>::ContainsKey(var<u1>)
0x2b2e3  brfalse.s loc_2B301
0x2b2e5  ldarg.0
0x2b2e6  ldc.i4.1
0x2b2e7  newarr   [mscorlib]System.String
0x2b2ec  dup
0x2b2ed  ldc.i4.0
0x2b2ee  ldarg.0
0x2b2ef  ldfld    valuetype Microsoft.ReportingServices.Modeling.ModelGeneration.EntityAttributesAssignment Microsoft.ReportingServices.Modeling.ModelGeneration.SetEntityAttributesRule::m_assignTo
0x2b2f4  ldloc.1
0x2b2f5  call     string Microsoft.ReportingServices.Modeling.ModelGeneration.SR::SetEntityAttributesRule_AlreadySet(valuetype Microsoft.ReportingServices.Modeling.ModelGeneration.EntityAttributesAssignment assignedCollection, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName)
0x2b2fa  stelem.ref
0x2b2fb  call     instance class Microsoft.ReportingServices.Modeling.ModelGeneration.RuleProcessResult Microsoft.ReportingServices.Modeling.ModelGeneration.ProcessingRule::ProcessSkipped(string[] messages)
0x2b300  ret
0x2b301  ldarg.0
0x2b302  ldarg.0
0x2b303  ldarg.1
0x2b304  call     instance class [mscorlib]System.Collections.Generic.List`1<class ColumnGroupScore> Microsoft.ReportingServices.Modeling.ModelGeneration.SetEntityAttributesRule::GetColumnGroupsSortedByScore(class Microsoft.ReportingServices.Modeling.DsvTable table)
0x2b309  ldloc.0
0x2b30a  call     instance class CandidateFields Microsoft.ReportingServices.Modeling.ModelGeneration.SetEntityAttributesRule::SelectCandidateFields(class [mscorlib]System.Collections.Generic.IEnumerable`1<class ColumnGroupScore> columnGroupsList, class Microsoft.ReportingServices.Modeling.ModelEntity entity)
0x2b30f  stloc.3
0x2b310  ldloc.3
0x2b311  callvirt instance int32 CandidateFields::get_FieldCount()
0x2b316  brtrue.s loc_2B358
0x2b318  ldarg.0
0x2b319  ldloc.2
0x2b31a  ldloc.3
0x2b31b  ldloc.0
0x2b31c  ldarg.1
0x2b31d  call     instance bool Microsoft.ReportingServices.Modeling.ModelGeneration.SetEntityAttributesRule::TryFallback(class Microsoft.ReportingServices.Modeling.AttributeReferenceCollection attribs, class CandidateFields candidateFields, class Microsoft.ReportingServices.Modeling.ModelEntity entity, class Microsoft.ReportingServices.Modeling.DsvTable table)
0x2b322  brtrue.s loc_2B358
0x2b324  ldarg.0
0x2b325  ldfld    valuetype Microsoft.ReportingServices.Modeling.ModelGeneration.EntityAttributesAssignment Microsoft.ReportingServices.Modeling.ModelGeneration.SetEntityAttributesRule::m_assignTo
0x2b32a  brtrue.s loc_2B342
0x2b32c  ldarg.0
0x2b32d  ldc.i4.1
0x2b32e  newarr   [mscorlib]System.String
0x2b333  dup
0x2b334  ldc.i4.0
0x2b335  ldloc.1
0x2b336  call     string Microsoft.ReportingServices.Modeling.ModelGeneration.SR::SetEntityAttributesRule_EntityHasNoFields(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName)
0x2b33b  stelem.ref
0x2b33c  call     instance class Microsoft.ReportingServices.Modeling.ModelGeneration.RuleProcessResult Microsoft.ReportingServices.Modeling.ModelGeneration.ProcessingRule::ProcessFailed(string[] messages)
0x2b341  ret
0x2b342  ldarg.0
0x2b343  ldc.i4.1
0x2b344  newarr   [mscorlib]System.String
0x2b349  dup
0x2b34a  ldc.i4.0
0x2b34b  ldloc.1
0x2b34c  call     string Microsoft.ReportingServices.Modeling.ModelGeneration.SR::SetEntityAttributesRule_EntityHasNoFields(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName)
0x2b351  stelem.ref
0x2b352  call     instance class Microsoft.ReportingServices.Modeling.ModelGeneration.RuleProcessResult Microsoft.ReportingServices.Modeling.ModelGeneration.ProcessingRule::ProcessSkipped(string[] messages)
0x2b357  ret
0x2b358  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Modeling.ModelItem>::.ctor()
0x2b35d  stloc.s  4
0x2b35f  ldloc.s  4
0x2b361  ldloc.0
0x2b362  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Modeling.ModelItem>::Add(var<u1>)
0x2b367  ldloc.3
0x2b368  callvirt instance int32 CandidateFields::get_FieldCount()
0x2b36d  ldloc.3
0x2b36e  callvirt instance int32 CandidateFields::get_AttributeCount()
0x2b373  bne.un.s loc_2B3B1
0x2b375  ldloc.3
0x2b376  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.ReportingServices.Modeling.ModelAttribute> CandidateFields::get_Attributes()
0x2b37b  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.ReportingServices.Modeling.ModelAttribute>::GetEnumerator()
0x2b380  stloc.s  5
0x2b382  br.s     loc_2B39A
0x2b384  ldloc.s  5
0x2b386  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.ReportingServices.Modeling.ModelAttribute>::get_Current()
0x2b38b  stloc.s  6
0x2b38d  ldloc.2
0x2b38e  ldloc.s  6
0x2b390  newobj   instance void Microsoft.ReportingServices.Modeling.AttributeReference::.ctor(class Microsoft.ReportingServices.Modeling.ModelAttribute attribute)
0x2b395  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.AttributeReference>::Add(var<u1>)
0x2b39a  ldloc.s  5
0x2b39c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2b3a1  brtrue.s loc_2B384
0x2b3a3  leave.s  loc_2B3BE
0x2b3a5  ldloc.s  5
0x2b3a7  brfalse.s loc_2B3B0
0x2b3a9  ldloc.s  5
0x2b3ab  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2b3b0  endfinally
0x2b3b1  ldarg.0
0x2b3b2  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.ReportingServices.Modeling.ModelEntity, class CandidateFields> Microsoft.ReportingServices.Modeling.ModelGeneration.SetEntityAttributesRule::m_entityCandidateFields
0x2b3b7  ldloc.0
0x2b3b8  ldloc.3
0x2b3b9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.ReportingServices.Modeling.ModelEntity, class CandidateFields>::Add(var<u1>, !!T0)
0x2b3be  ldarg.0
0x2b3bf  ldflda   valuetype [mscorlib]System.Nullable`1<bool> Microsoft.ReportingServices.Modeling.ModelGeneration.SetEntityAttributesRule::m_enableDrillthrough
0x2b3c4  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x2b3c9  brtrue.s loc_2B3D8
0x2b3cb  ldarg.0
0x2b3cc  ldflda   valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.AttributeContextualName> Microsoft.ReportingServices.Modeling.ModelGeneration.SetEntityAttributesRule::m_contextualName
0x2b3d1  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.AttributeContextualName>::get_HasValue()
0x2b3d6  brfalse.s loc_2B44E
0x2b3d8  ldloc.3
0x2b3d9  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.ReportingServices.Modeling.ModelAttribute> CandidateFields::get_Attributes()
0x2b3de  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.ReportingServices.Modeling.ModelAttribute>::GetEnumerator()
0x2b3e3  stloc.s  5
0x2b3e5  br.s     loc_2B437
0x2b3e7  ldloc.s  5
0x2b3e9  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.ReportingServices.Modeling.ModelAttribute>::get_Current()
0x2b3ee  stloc.s  7
0x2b3f0  ldarg.0
0x2b3f1  ldflda   valuetype [mscorlib]System.Nullable`1<bool> Microsoft.ReportingServices.Modeling.ModelGeneration.SetEntityAttributesRule::m_enableDrillthrough
0x2b3f6  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x2b3fb  brfalse.s loc_2B40F
0x2b3fd  ldloc.s  7
0x2b3ff  ldarg.0
0x2b400  ldflda   valuetype [mscorlib]System.Nullable`1<bool> Microsoft.ReportingServices.Modeling.ModelGeneration.SetEntityAttributesRule::m_enableDrillthrough
0x2b405  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x2b40a  callvirt instance void Microsoft.ReportingServices.Modeling.ModelAttribute::set_EnableDrillthrough(bool value)
0x2b40f  ldarg.0
0x2b410  ldflda   valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.AttributeContextualName> Microsoft.ReportingServices.Modeling.ModelGeneration.SetEntityAttributesRule::m_contextualName
0x2b415  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.AttributeContextualName>::get_HasValue()
0x2b41a  brfalse.s loc_2B42E
0x2b41c  ldloc.s  7
0x2b41e  ldarg.0
0x2b41f  ldflda   valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.AttributeContextualName> Microsoft.ReportingServices.Modeling.ModelGeneration.SetEntityAttributesRule::m_contextualName
0x2b424  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.AttributeContextualName>::get_Value()
0x2b429  callvirt instance void Microsoft.ReportingServices.Modeling.ModelAttribute::set_ContextualName(valuetype Microsoft.ReportingServices.Modeling.AttributeContextualName value)
0x2b42e  ldloc.s  4
0x2b430  ldloc.s  7
0x2b432  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Modeling.ModelItem>::Add(var<u1>)
0x2b437  ldloc.s  5
0x2b439  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2b43e  brtrue.s loc_2B3E7
0x2b440  leave.s  loc_2B44E
0x2b442  ldloc.s  5
0x2b444  brfalse.s loc_2B44D
0x2b446  ldloc.s  5
0x2b448  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2b44d  endfinally
0x2b44e  ldc.i4.1
0x2b44f  ldnull
0x2b450  ldloc.s  4
0x2b452  ldc.i4.1
0x2b453  newarr   [mscorlib]System.String
0x2b458  dup
0x2b459  ldc.i4.0
0x2b45a  ldarg.0
0x2b45b  ldfld    valuetype Microsoft.ReportingServices.Modeling.ModelGeneration.EntityAttributesAssignment Microsoft.ReportingServices.Modeling.ModelGeneration.SetEntityAttributesRule::m_assignTo
0x2b460  ldarg.0
0x2b461  ldloc.3
0x2b462  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.ReportingServices.Modeling.ModelField> CandidateFields::get_Fields()
0x2b467  call     instance string Microsoft.ReportingServices.Modeling.ModelGeneration.SetEntityAttributesRule::GetFieldNameList(class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.ReportingServices.Modeling.ModelField> fields)
0x2b46c  call     string Microsoft.ReportingServices.Modeling.ModelGeneration.SR::SetEntityAttributesRule_SetEntityAttributes(valuetype Microsoft.ReportingServices.Modeling.ModelGeneration.EntityAttributesAssignment assignedCollection, string attributeNames)
0x2b471  stelem.ref
0x2b472  newobj   instance void Microsoft.ReportingServices.Modeling.ModelGeneration.RuleProcessResult::.ctor(bool success, class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.ReportingServices.Modeling.ModelItem> itemsCreated, class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.ReportingServices.Modeling.ModelItem> itemsModified, string[] messages)
0x2b477  ret
```
