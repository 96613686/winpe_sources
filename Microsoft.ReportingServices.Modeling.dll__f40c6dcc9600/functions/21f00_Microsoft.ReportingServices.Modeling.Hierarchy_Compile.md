# Microsoft.ReportingServices.Modeling.Hierarchy::Compile

- ea: `0x21f00`
- end: `0x2207f`
- name: `Microsoft.ReportingServices.Modeling.Hierarchy::Compile`
- size: `383`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: `service_task, broker_com_uri`

## callers

- `0x22220`

## callees

- `0x84f0`
- `0x8500`
- `0x8540`
- `0x8720`
- `0x8740`
- `0x97d0`
- `0x9d20`
- `0x139d0`
- `0x186b0`
- `0x18fe0`
- `0x1a350`
- `0x21f00`
- `0x22080`
- `0x232e0`
- `0x24160`
- `0x24190`
- `0x241d0`
- `0x24510`
- `0x25110`
- `0x25430`
- `0x25590`
- `0x25a90`
- `0x25b70`
- `0x25bb0`
- `0x25be0`
- `0x37ad0`

## pseudocode

```c

```

## disassembly

```asm
0x21f00  ldarg.0
0x21f01  ldfld    class Microsoft.ReportingServices.Modeling.SemanticQuery Microsoft.ReportingServices.Modeling.Hierarchy::m_query
0x21f06  brtrue.s loc_21F13
0x21f08  ldstr    aMQueryIsNull// "m_query is null"
0x21f0d  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x21f12  throw
0x21f13  ldarg.1
0x21f14  ldarg.0
0x21f15  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::PushScope(class Microsoft.ReportingServices.Modeling.IValidationScope scope)
0x21f1a  ldarg.0
0x21f1b  ldarg.1
0x21f1c  callvirt instance bool Microsoft.ReportingServices.Modeling.CompilationContext::get_ShouldPersist()
0x21f21  call     instance void Microsoft.ReportingServices.Modeling.ModelingObject::Compile(bool shouldPersist)
0x21f26  ldarg.0
0x21f27  ldfld    class Microsoft.ReportingServices.Modeling.IQueryEntityInternal Microsoft.ReportingServices.Modeling.Hierarchy::m_baseEntity
0x21f2c  brtrue.s loc_21F4B
0x21f2e  ldarg.1
0x21f2f  ldc.i4.s 0x5D
0x21f31  ldstr    aBaseentity// "BaseEntity"
0x21f36  ldarg.1
0x21f37  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x21f3c  call     string Microsoft.ReportingServices.Modeling.SRErrors::MissingBaseEntity(string propertyName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName)
0x21f41  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x21f46  leave    loc_2207E
0x21f4b  ldarg.1
0x21f4c  callvirt instance bool Microsoft.ReportingServices.Modeling.CompilationContext::get_ShouldCheckInvalidRefsDuringCompilation()
0x21f51  brfalse.s loc_21FB3
0x21f53  ldarg.0
0x21f54  ldfld    class Microsoft.ReportingServices.Modeling.IQueryEntityInternal Microsoft.ReportingServices.Modeling.Hierarchy::m_baseEntity
0x21f59  callvirt instance bool Microsoft.ReportingServices.Modeling.IQueryEntity::get_IsInvalidRefTarget()
0x21f5e  brfalse.s loc_21FB3
0x21f60  ldarg.0
0x21f61  ldfld    class Microsoft.ReportingServices.Modeling.IQueryEntityInternal Microsoft.ReportingServices.Modeling.Hierarchy::m_baseEntity
0x21f66  callvirt instance class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.IQueryEntity::get_ModelEntity()
0x21f6b  brfalse.s loc_21FA8
0x21f6d  ldarg.1
0x21f6e  ldc.i4.s 0x11
0x21f70  ldstr    aBaseentityEnti// "BaseEntity.EntityID"
0x21f75  ldarg.1
0x21f76  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x21f7b  ldarg.0
0x21f7c  ldfld    class Microsoft.ReportingServices.Modeling.IQueryEntityInternal Microsoft.ReportingServices.Modeling.Hierarchy::m_baseEntity
0x21f81  callvirt instance class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.IQueryEntity::get_ModelEntity()
0x21f86  callvirt instance valuetype Microsoft.ReportingServices.Modeling.QName Microsoft.ReportingServices.Modeling.ModelItem::get_ID()
0x21f8b  stloc.0
0x21f8c  ldloca.s 0
0x21f8e  constrained. Microsoft.ReportingServices.Modeling.QName
0x21f94  callvirt instance string [mscorlib]System.Object::ToString()
0x21f99  call     string Microsoft.ReportingServices.Modeling.SRErrors::ItemNotFound(string propertyName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, string reference)
0x21f9e  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x21fa3  leave    loc_2207E
0x21fa8  ldstr    aNullOrUnrecogn_0// "Null or unrecognized IQueryEntity"
0x21fad  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x21fb2  throw
0x21fb3  ldarg.0
0x21fb4  ldfld    class Microsoft.ReportingServices.Modeling.IQueryEntityInternal Microsoft.ReportingServices.Modeling.Hierarchy::m_baseEntity
0x21fb9  callvirt instance class Microsoft.ReportingServices.Modeling.SemanticModel Microsoft.ReportingServices.Modeling.IQueryEntity::get_Model()
0x21fbe  ldarg.0
0x21fbf  ldfld    class Microsoft.ReportingServices.Modeling.SemanticQuery Microsoft.ReportingServices.Modeling.Hierarchy::m_query
0x21fc4  callvirt instance class Microsoft.ReportingServices.Modeling.SemanticModel Microsoft.ReportingServices.Modeling.SemanticQuery::get_Model()
0x21fc9  beq.s    loc_21FF3
0x21fcb  ldarg.1
0x21fcc  ldc.i4.s 0x75
0x21fce  ldstr    aBaseentity// "BaseEntity"
0x21fd3  ldarg.1
0x21fd4  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x21fd9  ldarg.0
0x21fda  ldfld    class Microsoft.ReportingServices.Modeling.IQueryEntityInternal Microsoft.ReportingServices.Modeling.Hierarchy::m_baseEntity
0x21fdf  call     valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.SRObjectDescriptor::FromScope(class Microsoft.ReportingServices.Modeling.IValidationScope scope)
0x21fe4  call     string Microsoft.ReportingServices.Modeling.SRErrors::WrongSemanticModel_QueryItem(string propertyName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor referencedTypeAndName)
0x21fe9  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x21fee  leave    loc_2207E
0x21ff3  ldarg.1
0x21ff4  ldarg.0
0x21ff5  ldfld    class Microsoft.ReportingServices.Modeling.IQueryEntityInternal Microsoft.ReportingServices.Modeling.Hierarchy::m_baseEntity
0x21ffa  callvirt instance void Microsoft.ReportingServices.Modeling.CompilationContext::PushContextEntity(class Microsoft.ReportingServices.Modeling.IQueryEntity entity)
0x21fff  ldarg.0
0x22000  ldfld    class GroupingCollection Microsoft.ReportingServices.Modeling.Hierarchy::m_groupings
0x22005  ldarg.1
0x22006  callvirt instance void GroupingCollection::Compile(class Microsoft.ReportingServices.Modeling.CompilationContext ctx)
0x2200b  ldarg.1
0x2200c  callvirt instance bool Microsoft.ReportingServices.Modeling.CompilationContext::get_ShouldApplySecurityFilters()
0x22011  brfalse.s loc_22054
0x22013  ldarg.0
0x22014  ldarg.1
0x22015  call     instance class Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.Modeling.Hierarchy::TryGetSecurityFilterCondition(class Microsoft.ReportingServices.Modeling.CompilationContext ctx)
0x2201a  stloc.1
0x2201b  ldloc.1
0x2201c  brfalse.s loc_22054
0x2201e  ldarg.0
0x2201f  ldfld    class Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.Modeling.Hierarchy::m_filter
0x22024  brtrue.s loc_2202F
0x22026  ldarg.0
0x22027  ldloc.1
0x22028  stfld    class Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.Modeling.Hierarchy::m_filter
0x2202d  br.s     loc_22054
0x2202f  ldarg.0
0x22030  ldc.i4.s 0xD
0x22032  ldc.i4.2
0x22033  newarr   Microsoft.ReportingServices.Modeling.Expression
0x22038  dup
0x22039  ldc.i4.0
0x2203a  ldloc.1
0x2203b  stelem.ref
0x2203c  dup
0x2203d  ldc.i4.1
0x2203e  ldarg.0
0x2203f  ldfld    class Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.Modeling.Hierarchy::m_filter
0x22044  stelem.ref
0x22045  newobj   instance void Microsoft.ReportingServices.Modeling.FunctionNode::.ctor(valuetype Microsoft.ReportingServices.Modeling.FunctionName functionName, class Microsoft.ReportingServices.Modeling.Expression[] arguments)
0x2204a  newobj   instance void Microsoft.ReportingServices.Modeling.Expression::.ctor(class Microsoft.ReportingServices.Modeling.ExpressionNode node)
0x2204f  stfld    class Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.Modeling.Hierarchy::m_filter
0x22054  ldarg.0
0x22055  ldfld    class Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.Modeling.Hierarchy::m_filter
0x2205a  brfalse.s loc_2206E
0x2205c  ldarg.0
0x2205d  ldfld    class Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.Modeling.Hierarchy::m_filter
0x22062  ldarg.1
0x22063  ldsfld   valuetype Microsoft.ReportingServices.Modeling.ExpressionCompilationFlags Microsoft.ReportingServices.Modeling.ExpressionCompilationFlags::Filter
0x22068  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.ResultType> Microsoft.ReportingServices.Modeling.Expression::Compile(class Microsoft.ReportingServices.Modeling.CompilationContext ctx, valuetype Microsoft.ReportingServices.Modeling.ExpressionCompilationFlags flags)
0x2206d  pop
0x2206e  leave.s  loc_2207E
0x22070  ldarg.1
0x22071  callvirt instance void Microsoft.ReportingServices.Modeling.CompilationContext::PopContextEntity()
0x22076  endfinally
0x22077  ldarg.1
0x22078  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::PopScope()
0x2207d  endfinally
0x2207e  ret
```
