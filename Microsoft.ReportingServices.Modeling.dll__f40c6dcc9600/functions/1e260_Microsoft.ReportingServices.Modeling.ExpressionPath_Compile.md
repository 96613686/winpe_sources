# Microsoft.ReportingServices.Modeling.ExpressionPath::Compile

- ea: `0x1e260`
- end: `0x1e3e6`
- name: `Microsoft.ReportingServices.Modeling.ExpressionPath::Compile`
- size: `390`
- prototype: ``
- caller_count: `3`
- callee_count: `21`
- tags: `service_task, broker_com_uri`

## callers

- `0x118c0`
- `0x17e10`
- `0x19220`

## callees

- `0x84f0`
- `0x8530`
- `0x8630`
- `0x8720`
- `0x8740`
- `0x97d0`
- `0x1de40`
- `0x1de50`
- `0x1e0d0`
- `0x1e260`
- `0x1e3f0`
- `0x1ea80`
- `0x1eab0`
- `0x1eac0`
- `0x1eb20`
- `0x1eb30`
- `0x24190`
- `0x25450`
- `0x25590`
- `0x25a90`
- `0x25b70`

## string_xrefs

- `0x1e2b9`: `Can not process path item with null target entity.`

## pseudocode

```c

```

## disassembly

```asm
0x1e260  ldarg.0
0x1e261  call     instance int32 Microsoft.ReportingServices.Modeling.ExpressionPath::get_Length()
0x1e266  newobj   instance void Microsoft.ReportingServices.Modeling.ExpressionPath::.ctor(int32 capacity)
0x1e26b  stloc.0
0x1e26c  ldarg.1
0x1e26d  callvirt instance class Microsoft.ReportingServices.Modeling.IQueryEntity Microsoft.ReportingServices.Modeling.CompilationContext::get_ContextEntity()
0x1e272  stloc.1
0x1e273  ldarg.0
0x1e274  call     instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class Microsoft.ReportingServices.Modeling.CheckedCollection`1<class Microsoft.ReportingServices.Modeling.PathItem>::GetEnumerator()
0x1e279  stloc.2
0x1e27a  br       loc_1E394
0x1e27f  ldloca.s 2
0x1e281  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Modeling.PathItem>::get_Current()
0x1e286  stloc.3
0x1e287  ldloc.3
0x1e288  ldarg.1
0x1e289  ldc.i4.0
0x1e28a  callvirt instance bool Microsoft.ReportingServices.Modeling.PathItem::CheckInvalidRefs(class Microsoft.ReportingServices.Modeling.CompilationContext ctx, bool forceCheck)
0x1e28f  brtrue.s loc_1E29C
0x1e291  ldarg.3
0x1e292  ldnull
0x1e293  stind.ref
0x1e294  ldnull
0x1e295  stloc.s  4
0x1e297  leave    loc_1E3E3
0x1e29c  ldloc.3
0x1e29d  callvirt instance class Microsoft.ReportingServices.Modeling.IQueryEntity Microsoft.ReportingServices.Modeling.PathItem::get_TargetEntity()
0x1e2a2  brtrue.s loc_1E2C4
0x1e2a4  ldloc.3
0x1e2a5  ldarg.1
0x1e2a6  ldc.i4.1
0x1e2a7  callvirt instance bool Microsoft.ReportingServices.Modeling.PathItem::CheckInvalidRefs(class Microsoft.ReportingServices.Modeling.CompilationContext ctx, bool forceCheck)
0x1e2ac  brtrue.s loc_1E2B9
0x1e2ae  ldarg.3
0x1e2af  ldnull
0x1e2b0  stind.ref
0x1e2b1  ldnull
0x1e2b2  stloc.s  4
0x1e2b4  leave    loc_1E3E3
0x1e2b9  ldstr    aCanNotProcessP// "Can not process path item with null tar"...
0x1e2be  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1e2c3  throw
0x1e2c4  ldloc.1
0x1e2c5  brfalse  loc_1E356
0x1e2ca  ldloc.3
0x1e2cb  callvirt instance class Microsoft.ReportingServices.Modeling.IQueryEntity Microsoft.ReportingServices.Modeling.PathItem::get_SourceEntity()
0x1e2d0  brfalse.s loc_1E314
0x1e2d2  ldloc.3
0x1e2d3  callvirt instance class Microsoft.ReportingServices.Modeling.IQueryEntity Microsoft.ReportingServices.Modeling.PathItem::get_SourceEntity()
0x1e2d8  callvirt instance class Microsoft.ReportingServices.Modeling.SemanticModel Microsoft.ReportingServices.Modeling.IQueryEntity::get_Model()
0x1e2dd  ldloc.1
0x1e2de  callvirt instance class Microsoft.ReportingServices.Modeling.SemanticModel Microsoft.ReportingServices.Modeling.IQueryEntity::get_Model()
0x1e2e3  beq.s    loc_1E314
0x1e2e5  ldarg.1
0x1e2e6  ldc.i4.s 0x75
0x1e2e8  ldloc.3
0x1e2e9  callvirt instance string Microsoft.ReportingServices.Modeling.PathItem::get_PropertyName()
0x1e2ee  ldarg.1
0x1e2ef  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x1e2f4  ldloc.3
0x1e2f5  callvirt instance class Microsoft.ReportingServices.Modeling.IQueryEntity Microsoft.ReportingServices.Modeling.PathItem::get_SourceEntity()
0x1e2fa  call     valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.SRObjectDescriptor::FromScope(class Microsoft.ReportingServices.Modeling.IValidationScope scope)
0x1e2ff  call     string Microsoft.ReportingServices.Modeling.SRErrors::WrongSemanticModel_QueryItemMultipleProperties(string propertyName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor referencedTypeAndName)
0x1e304  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x1e309  ldarg.3
0x1e30a  ldnull
0x1e30b  stind.ref
0x1e30c  ldnull
0x1e30d  stloc.s  4
0x1e30f  leave    loc_1E3E3
0x1e314  ldloc.3
0x1e315  callvirt instance class Microsoft.ReportingServices.Modeling.IQueryEntity Microsoft.ReportingServices.Modeling.PathItem::get_TargetEntity()
0x1e31a  callvirt instance class Microsoft.ReportingServices.Modeling.SemanticModel Microsoft.ReportingServices.Modeling.IQueryEntity::get_Model()
0x1e31f  ldloc.1
0x1e320  callvirt instance class Microsoft.ReportingServices.Modeling.SemanticModel Microsoft.ReportingServices.Modeling.IQueryEntity::get_Model()
0x1e325  beq.s    loc_1E356
0x1e327  ldarg.1
0x1e328  ldc.i4.s 0x75
0x1e32a  ldloc.3
0x1e32b  callvirt instance string Microsoft.ReportingServices.Modeling.PathItem::get_PropertyName()
0x1e330  ldarg.1
0x1e331  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x1e336  ldloc.3
0x1e337  callvirt instance class Microsoft.ReportingServices.Modeling.IQueryEntity Microsoft.ReportingServices.Modeling.PathItem::get_TargetEntity()
0x1e33c  call     valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.SRObjectDescriptor::FromScope(class Microsoft.ReportingServices.Modeling.IValidationScope scope)
0x1e341  call     string Microsoft.ReportingServices.Modeling.SRErrors::WrongSemanticModel_QueryItemMultipleProperties(string propertyName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor referencedTypeAndName)
0x1e346  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x1e34b  ldarg.3
0x1e34c  ldnull
0x1e34d  stind.ref
0x1e34e  ldnull
0x1e34f  stloc.s  4
0x1e351  leave    loc_1E3E3
0x1e356  ldloc.1
0x1e357  ldloc.3
0x1e358  callvirt instance class Microsoft.ReportingServices.Modeling.IQueryEntity Microsoft.ReportingServices.Modeling.PathItem::get_SourceEntity()
0x1e35d  ldloc.0
0x1e35e  call     bool Microsoft.ReportingServices.Modeling.ExpressionPath::ResolvePath(class Microsoft.ReportingServices.Modeling.IQueryEntity sourceEntity, class Microsoft.ReportingServices.Modeling.IQueryEntity targetEntity, class Microsoft.ReportingServices.Modeling.ExpressionPath resolvedPath)
0x1e363  brfalse.s loc_1E375
0x1e365  ldloc.0
0x1e366  ldloc.3
0x1e367  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.PathItem>::Add(var<u1>)
0x1e36c  ldloc.3
0x1e36d  callvirt instance class Microsoft.ReportingServices.Modeling.IQueryEntity Microsoft.ReportingServices.Modeling.PathItem::get_TargetEntity()
0x1e372  stloc.1
0x1e373  br.s     loc_1E394
0x1e375  ldarg.1
0x1e376  ldloc.1
0x1e377  callvirt instance void Microsoft.ReportingServices.Modeling.CompilationContext::PushContextEntity(class Microsoft.ReportingServices.Modeling.IQueryEntity entity)
0x1e37c  ldloc.3
0x1e37d  ldarg.1
0x1e37e  callvirt instance void Microsoft.ReportingServices.Modeling.PathItem::AddOutOfContextError(class Microsoft.ReportingServices.Modeling.CompilationContext ctx)
0x1e383  leave.s  loc_1E38C
0x1e385  ldarg.1
0x1e386  callvirt instance void Microsoft.ReportingServices.Modeling.CompilationContext::PopContextEntity()
0x1e38b  endfinally
0x1e38c  ldarg.3
0x1e38d  ldnull
0x1e38e  stind.ref
0x1e38f  ldnull
0x1e390  stloc.s  4
0x1e392  leave.s  loc_1E3E3
0x1e394  ldloca.s 2
0x1e396  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Modeling.PathItem>::MoveNext()
0x1e39b  brtrue   loc_1E27F
0x1e3a0  leave.s  loc_1E3B0
0x1e3a2  ldloca.s 2
0x1e3a4  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Modeling.PathItem>
0x1e3aa  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1e3af  endfinally
0x1e3b0  ldarg.2
0x1e3b1  brfalse.s loc_1E3BF
0x1e3b3  ldloc.1
0x1e3b4  ldarg.2
0x1e3b5  ldloc.0
0x1e3b6  call     bool Microsoft.ReportingServices.Modeling.ExpressionPath::ResolvePath(class Microsoft.ReportingServices.Modeling.IQueryEntity sourceEntity, class Microsoft.ReportingServices.Modeling.IQueryEntity targetEntity, class Microsoft.ReportingServices.Modeling.ExpressionPath resolvedPath)
0x1e3bb  brfalse.s loc_1E3BF
0x1e3bd  ldarg.2
0x1e3be  stloc.1
0x1e3bf  ldarg.3
0x1e3c0  ldloc.1
0x1e3c1  stind.ref
0x1e3c2  ldarg.1
0x1e3c3  callvirt instance bool Microsoft.ReportingServices.Modeling.CompilationContext::get_ShouldPersist()
0x1e3c8  brfalse.s loc_1E3E1
0x1e3ca  ldarg.1
0x1e3cb  callvirt instance bool Microsoft.ReportingServices.Modeling.CompilationContext::get_ShouldNormalize()
0x1e3d0  brfalse.s loc_1E3D9
0x1e3d2  ldarg.0
0x1e3d3  ldloc.0
0x1e3d4  call     instance void Microsoft.ReportingServices.Modeling.ExpressionPath::ReplaceWith(class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.ReportingServices.Modeling.PathItem> items)
0x1e3d9  ldarg.0
0x1e3da  call     instance void class Microsoft.ReportingServices.Modeling.CheckedCollection`1<class Microsoft.ReportingServices.Modeling.PathItem>::SetReadOnlyIndicator()
0x1e3df  ldloc.0
0x1e3e0  ret
0x1e3e1  ldloc.0
0x1e3e2  ret
0x1e3e3  ldloc.s  4
0x1e3e5  ret
```
