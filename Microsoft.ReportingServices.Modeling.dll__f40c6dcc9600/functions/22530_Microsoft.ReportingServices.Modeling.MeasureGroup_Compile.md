# Microsoft.ReportingServices.Modeling.MeasureGroup::Compile

- ea: `0x22530`
- end: `0x22697`
- name: `Microsoft.ReportingServices.Modeling.MeasureGroup::Compile`
- size: `359`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `service_task, broker_com_uri`

## callers

- `0x22840`

## callees

- `0x84f0`
- `0x8500`
- `0x8720`
- `0x8740`
- `0x97d0`
- `0x9d20`
- `0x139d0`
- `0x19a00`
- `0x21ce0`
- `0x22530`
- `0x226a0`
- `0x232e0`
- `0x23300`
- `0x24160`
- `0x24190`
- `0x241d0`
- `0x24530`
- `0x25130`
- `0x251f0`
- `0x25210`
- `0x25450`
- `0x25590`
- `0x25a90`
- `0x25b70`

## pseudocode

```c

```

## disassembly

```asm
0x22530  ldarg.0
0x22531  ldarg.1
0x22532  callvirt instance bool Microsoft.ReportingServices.Modeling.CompilationContext::get_ShouldPersist()
0x22537  call     instance void Microsoft.ReportingServices.Modeling.ModelingObject::Compile(bool shouldPersist)
0x2253c  ldarg.0
0x2253d  ldfld    class Microsoft.ReportingServices.Modeling.IQueryEntityInternal Microsoft.ReportingServices.Modeling.MeasureGroup::m_baseEntity
0x22542  brtrue.s loc_2255D
0x22544  ldarg.1
0x22545  ldc.i4.s 0x5D
0x22547  ldstr    aMeasuregroupBa_0// "MeasureGroup.BaseEntity"
0x2254c  ldarg.1
0x2254d  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x22552  call     string Microsoft.ReportingServices.Modeling.SRErrors::MissingBaseEntity_MultipleProperties(string propertyName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName)
0x22557  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x2255c  ret
0x2255d  ldarg.1
0x2255e  callvirt instance bool Microsoft.ReportingServices.Modeling.CompilationContext::get_ShouldCheckInvalidRefsDuringCompilation()
0x22563  brfalse.s loc_225C1
0x22565  ldarg.0
0x22566  ldfld    class Microsoft.ReportingServices.Modeling.IQueryEntityInternal Microsoft.ReportingServices.Modeling.MeasureGroup::m_baseEntity
0x2256b  callvirt instance bool Microsoft.ReportingServices.Modeling.IQueryEntity::get_IsInvalidRefTarget()
0x22570  brfalse.s loc_225C1
0x22572  ldarg.0
0x22573  ldfld    class Microsoft.ReportingServices.Modeling.IQueryEntityInternal Microsoft.ReportingServices.Modeling.MeasureGroup::m_baseEntity
0x22578  callvirt instance class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.IQueryEntity::get_ModelEntity()
0x2257d  brfalse.s loc_225B6
0x2257f  ldarg.1
0x22580  ldc.i4.s 0x11
0x22582  ldstr    aMeasuregroupBa// "MeasureGroup.BaseEntity.EntityID"
0x22587  ldarg.1
0x22588  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x2258d  ldarg.0
0x2258e  ldfld    class Microsoft.ReportingServices.Modeling.IQueryEntityInternal Microsoft.ReportingServices.Modeling.MeasureGroup::m_baseEntity
0x22593  callvirt instance class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.IQueryEntity::get_ModelEntity()
0x22598  callvirt instance valuetype Microsoft.ReportingServices.Modeling.QName Microsoft.ReportingServices.Modeling.ModelItem::get_ID()
0x2259d  stloc.0
0x2259e  ldloca.s 0
0x225a0  constrained. Microsoft.ReportingServices.Modeling.QName
0x225a6  callvirt instance string [mscorlib]System.Object::ToString()
0x225ab  call     string Microsoft.ReportingServices.Modeling.SRErrors::ItemNotFound_MultipleProperties(string propertyName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, string reference)
0x225b0  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x225b5  ret
0x225b6  ldstr    aNullOrUnrecogn_0// "Null or unrecognized IQueryEntity"
0x225bb  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x225c0  throw
0x225c1  ldarg.0
0x225c2  ldfld    class Microsoft.ReportingServices.Modeling.IQueryEntityInternal Microsoft.ReportingServices.Modeling.MeasureGroup::m_baseEntity
0x225c7  callvirt instance class Microsoft.ReportingServices.Modeling.SemanticModel Microsoft.ReportingServices.Modeling.IQueryEntity::get_Model()
0x225cc  ldarg.0
0x225cd  ldfld    class Microsoft.ReportingServices.Modeling.SemanticQuery Microsoft.ReportingServices.Modeling.MeasureGroup::m_query
0x225d2  callvirt instance class Microsoft.ReportingServices.Modeling.SemanticModel Microsoft.ReportingServices.Modeling.SemanticQuery::get_Model()
0x225d7  beq.s    loc_225FD
0x225d9  ldarg.1
0x225da  ldc.i4.s 0x75
0x225dc  ldstr    aMeasuregroupBa_0// "MeasureGroup.BaseEntity"
0x225e1  ldarg.1
0x225e2  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x225e7  ldarg.0
0x225e8  ldfld    class Microsoft.ReportingServices.Modeling.IQueryEntityInternal Microsoft.ReportingServices.Modeling.MeasureGroup::m_baseEntity
0x225ed  call     valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.SRObjectDescriptor::FromScope(class Microsoft.ReportingServices.Modeling.IValidationScope scope)
0x225f2  call     string Microsoft.ReportingServices.Modeling.SRErrors::WrongSemanticModel_QueryItemMultipleProperties(string propertyName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor referencedTypeAndName)
0x225f7  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x225fc  ret
0x225fd  ldarg.0
0x225fe  ldfld    class Microsoft.ReportingServices.Modeling.SemanticQuery Microsoft.ReportingServices.Modeling.MeasureGroup::m_query
0x22603  callvirt instance class HierarchyCollection Microsoft.ReportingServices.Modeling.SemanticQuery::get_Hierarchies()
0x22608  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.Hierarchy>::get_Count()
0x2260d  ldc.i4.0
0x2260e  ble.s    loc_22647
0x22610  ldarg.0
0x22611  ldfld    class Microsoft.ReportingServices.Modeling.IQueryEntityInternal Microsoft.ReportingServices.Modeling.MeasureGroup::m_baseEntity
0x22616  ldarg.0
0x22617  ldfld    class Microsoft.ReportingServices.Modeling.SemanticQuery Microsoft.ReportingServices.Modeling.MeasureGroup::m_query
0x2261c  callvirt instance class HierarchyCollection Microsoft.ReportingServices.Modeling.SemanticQuery::get_Hierarchies()
0x22621  ldc.i4.0
0x22622  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.Hierarchy>::get_Item(!!T0)
0x22627  callvirt instance class Microsoft.ReportingServices.Modeling.IQueryEntity Microsoft.ReportingServices.Modeling.Hierarchy::get_BaseEntity()
0x2262c  beq.s    loc_22647
0x2262e  ldarg.1
0x2262f  ldc.i4.s 0x63
0x22631  ldstr    aMeasuregroupBa_0// "MeasureGroup.BaseEntity"
0x22636  ldarg.1
0x22637  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x2263c  call     string Microsoft.ReportingServices.Modeling.SRErrors::BaseEntityMismatch(string propertyName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName)
0x22641  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x22646  ret
0x22647  ldarg.0
0x22648  ldfld    class Microsoft.ReportingServices.Modeling.ExpressionCollection Microsoft.ReportingServices.Modeling.MeasureGroup::m_measures
0x2264d  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.Expression>::get_Count()
0x22652  brtrue.s loc_22668
0x22654  ldarg.1
0x22655  ldc.i4.s 0x64
0x22657  ldarg.1
0x22658  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x2265d  call     string Microsoft.ReportingServices.Modeling.SRErrors::MissingMeasures(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName)
0x22662  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x22667  ret
0x22668  ldarg.1
0x22669  ldarg.0
0x2266a  ldfld    class Microsoft.ReportingServices.Modeling.IQueryEntityInternal Microsoft.ReportingServices.Modeling.MeasureGroup::m_baseEntity
0x2266f  callvirt instance void Microsoft.ReportingServices.Modeling.CompilationContext::PushContextEntity(class Microsoft.ReportingServices.Modeling.IQueryEntity entity)
0x22674  ldarg.0
0x22675  ldfld    class Microsoft.ReportingServices.Modeling.ExpressionCollection Microsoft.ReportingServices.Modeling.MeasureGroup::m_measures
0x2267a  ldarg.1
0x2267b  ldsfld   valuetype Microsoft.ReportingServices.Modeling.ExpressionCompilationFlags Microsoft.ReportingServices.Modeling.ExpressionCompilationFlags::Measure
0x22680  callvirt instance valuetype Microsoft.ReportingServices.Modeling.ResultType[] Microsoft.ReportingServices.Modeling.ExpressionCollection::Compile(class Microsoft.ReportingServices.Modeling.CompilationContext ctx, valuetype Microsoft.ReportingServices.Modeling.ExpressionCompilationFlags flags)
0x22685  pop
0x22686  ldarg.0
0x22687  ldarg.1
0x22688  call     instance void Microsoft.ReportingServices.Modeling.MeasureGroup::CompileSubtotalSets(class Microsoft.ReportingServices.Modeling.CompilationContext ctx)
0x2268d  leave.s  loc_22696
0x2268f  ldarg.1
0x22690  callvirt instance void Microsoft.ReportingServices.Modeling.CompilationContext::PopContextEntity()
0x22695  endfinally
0x22696  ret
```
