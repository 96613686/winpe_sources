# Microsoft.ReportingServices.Modeling.SemanticQuery::Compile_2

- ea: `0x23da0`
- end: `0x23f41`
- name: `Microsoft.ReportingServices.Modeling.SemanticQuery::Compile_2`
- size: `417`
- prototype: ``
- caller_count: `3`
- callee_count: `27`
- tags: `service_task, broker_com_uri`

## callers

- `0x17f30`
- `0x23a50`
- `0x23d80`

## callees

- `0x8070`
- `0x84f0`
- `0x8570`
- `0x8590`
- `0x96e0`
- `0x9f10`
- `0x19a00`
- `0x224b0`
- `0x23370`
- `0x23380`
- `0x23390`
- `0x23b00`
- `0x23da0`
- `0x23f50`
- `0x25070`
- `0x25090`
- `0x250b0`
- `0x25590`
- `0x25a40`
- `0x25a90`
- `0x25b70`
- `0x25bb0`
- `0x25be0`
- `0x2e7c0`
- `0x37f30`
- `0x37fe0`
- `0x38040`

## pseudocode

```c

```

## disassembly

```asm
0x23da0  ldarg.1
0x23da1  ldarg.0
0x23da2  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::PushScope(class Microsoft.ReportingServices.Modeling.IValidationScope scope)
0x23da7  ldarg.0
0x23da8  ldarg.1
0x23da9  call     instance void Microsoft.ReportingServices.Modeling.SemanticQuery::CompileParameters(class Microsoft.ReportingServices.Modeling.CompilationContext ctx)
0x23dae  ldarg.0
0x23daf  ldarg.1
0x23db0  callvirt instance bool Microsoft.ReportingServices.Modeling.CompilationContext::get_ShouldPersist()
0x23db5  call     instance void Microsoft.ReportingServices.Modeling.ExtensibleModelingObject::Compile(bool shouldPersist)
0x23dba  ldarg.1
0x23dbb  callvirt instance bool Microsoft.ReportingServices.Modeling.ValidationContext::get_HasInvalidRefs()
0x23dc0  brfalse.s loc_23DEA
0x23dc2  ldarg.1
0x23dc3  callvirt instance bool Microsoft.ReportingServices.Modeling.CompilationContext::get_ShouldSubset()
0x23dc8  brfalse.s loc_23DEA
0x23dca  ldarg.0
0x23dcb  call     bool Microsoft.ReportingServices.Modeling.SemanticQuery::SubsetQuery(class Microsoft.ReportingServices.Modeling.SemanticQuery query)
0x23dd0  brtrue.s loc_23DEA
0x23dd2  ldarg.1
0x23dd3  ldc.i4.s 0x58
0x23dd5  ldarg.0
0x23dd6  call     valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.SRObjectDescriptor::FromScope(class Microsoft.ReportingServices.Modeling.IValidationScope scope)
0x23ddb  call     string Microsoft.ReportingServices.Modeling.SRErrors::EmptySemanticQuery(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName)
0x23de0  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x23de5  leave    loc_23F40
0x23dea  ldarg.0
0x23deb  ldfld    class MeasureGroupCollection Microsoft.ReportingServices.Modeling.SemanticQuery::m_measureGroups
0x23df0  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class Microsoft.ReportingServices.Modeling.CheckedCollection`1<class Microsoft.ReportingServices.Modeling.MeasureGroup>::GetEnumerator()
0x23df5  stloc.0
0x23df6  br.s     loc_23E05
0x23df8  ldloca.s 0
0x23dfa  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Modeling.MeasureGroup>::get_Current()
0x23dff  ldarg.1
0x23e00  callvirt instance void Microsoft.ReportingServices.Modeling.MeasureGroup::ApplySecurityFilters(class Microsoft.ReportingServices.Modeling.CompilationContext ctx)
0x23e05  ldloca.s 0
0x23e07  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Modeling.MeasureGroup>::MoveNext()
0x23e0c  brtrue.s loc_23DF8
0x23e0e  leave.s  loc_23E1E
0x23e10  ldloca.s 0
0x23e12  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Modeling.MeasureGroup>
0x23e18  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x23e1d  endfinally
0x23e1e  ldarg.0
0x23e1f  ldfld    class Microsoft.ReportingServices.Modeling.SemanticModel Microsoft.ReportingServices.Modeling.SemanticQuery::m_model
0x23e24  brtrue.s loc_23E31
0x23e26  call     string Microsoft.ReportingServices.Modeling.DevExceptionMessages::get_SemanticQuery_NullModel()
0x23e2b  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x23e30  throw
0x23e31  ldarg.0
0x23e32  ldfld    class HierarchyCollection Microsoft.ReportingServices.Modeling.SemanticQuery::m_hierarchies
0x23e37  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.Hierarchy>::get_Count()
0x23e3c  ldc.i4.1
0x23e3d  bgt.s    loc_23E4D
0x23e3f  ldarg.0
0x23e40  ldfld    class MeasureGroupCollection Microsoft.ReportingServices.Modeling.SemanticQuery::m_measureGroups
0x23e45  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.MeasureGroup>::get_Count()
0x23e4a  ldc.i4.1
0x23e4b  ble.s    loc_23E94
0x23e4d  ldarg.0
0x23e4e  ldfld    class HierarchyCollection Microsoft.ReportingServices.Modeling.SemanticQuery::m_hierarchies
0x23e53  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.Hierarchy>::get_Count()
0x23e58  ldc.i4.1
0x23e59  ble.s    loc_23E6E
0x23e5b  ldarg.1
0x23e5c  ldc.i4.s 0x59
0x23e5e  ldarg.1
0x23e5f  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x23e64  call     string Microsoft.ReportingServices.Modeling.SRErrors::MultipleHierarchies(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName)
0x23e69  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x23e6e  ldarg.0
0x23e6f  ldfld    class MeasureGroupCollection Microsoft.ReportingServices.Modeling.SemanticQuery::m_measureGroups
0x23e74  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.MeasureGroup>::get_Count()
0x23e79  ldc.i4.1
0x23e7a  ble.s    loc_23E8F
0x23e7c  ldarg.1
0x23e7d  ldc.i4.s 0x5A
0x23e7f  ldarg.1
0x23e80  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x23e85  call     string Microsoft.ReportingServices.Modeling.SRErrors::MultipleMeasureGroups(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName)
0x23e8a  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x23e8f  leave    loc_23F40
0x23e94  ldarg.0
0x23e95  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.ReportingServices.Modeling.Expression> Microsoft.ReportingServices.Modeling.SemanticQuery::GetAllResultExpressions()
0x23e9a  call     T0x2B0000F1
0x23e9f  brfalse.s loc_23EB9
0x23ea1  ldarg.1
0x23ea2  ldc.i4.s 0x58
0x23ea4  ldarg.1
0x23ea5  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x23eaa  call     string Microsoft.ReportingServices.Modeling.SRErrors::EmptySemanticQuery(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName)
0x23eaf  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x23eb4  leave    loc_23F40
0x23eb9  ldarg.1
0x23eba  ldarg.0
0x23ebb  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.ReportingServices.Modeling.Grouping> Microsoft.ReportingServices.Modeling.SemanticQuery::GetAllGroupings()
0x23ec0  ldc.i4.s 0x5B
0x23ec2  ldnull
0x23ec3  ldftn    string Microsoft.ReportingServices.Modeling.SRErrors::DuplicateGroupingName(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, string groupingName)
0x23ec9  newobj   instance void SRDuplicateNameMethod::.ctor(object object, native int method)
0x23ece  callvirt T0x2B0000F2
0x23ed3  pop
0x23ed4  ldarg.1
0x23ed5  ldarg.0
0x23ed6  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.ReportingServices.Modeling.Expression> Microsoft.ReportingServices.Modeling.SemanticQuery::GetAllTopLevelExpressions()
0x23edb  ldc.i4.s 0x5C
0x23edd  ldnull
0x23ede  ldftn    string Microsoft.ReportingServices.Modeling.SRErrors::DuplicateExpressionName(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, string expressionName)
0x23ee4  newobj   instance void SRDuplicateNameMethod::.ctor(object object, native int method)
0x23ee9  callvirt T0x2B0000F3
0x23eee  pop
0x23eef  ldarg.0
0x23ef0  ldfld    class Microsoft.ReportingServices.Modeling.ExpressionCollection Microsoft.ReportingServices.Modeling.SemanticQuery::m_calculatedAttrs
0x23ef5  ldarg.1
0x23ef6  ldsfld   valuetype Microsoft.ReportingServices.Modeling.ExpressionCompilationFlags Microsoft.ReportingServices.Modeling.ExpressionCompilationFlags::CalculatedAttribute
0x23efb  callvirt instance valuetype Microsoft.ReportingServices.Modeling.ResultType[] Microsoft.ReportingServices.Modeling.ExpressionCollection::Compile(class Microsoft.ReportingServices.Modeling.CompilationContext ctx, valuetype Microsoft.ReportingServices.Modeling.ExpressionCompilationFlags flags)
0x23f00  pop
0x23f01  ldarg.0
0x23f02  ldfld    class HierarchyCollection Microsoft.ReportingServices.Modeling.SemanticQuery::m_hierarchies
0x23f07  ldarg.1
0x23f08  callvirt instance void HierarchyCollection::Compile(class Microsoft.ReportingServices.Modeling.CompilationContext ctx)
0x23f0d  ldarg.0
0x23f0e  ldfld    class MeasureGroupCollection Microsoft.ReportingServices.Modeling.SemanticQuery::m_measureGroups
0x23f13  ldarg.1
0x23f14  callvirt instance void MeasureGroupCollection::Compile(class Microsoft.ReportingServices.Modeling.CompilationContext ctx)
0x23f19  ldarg.1
0x23f1a  callvirt instance bool Microsoft.ReportingServices.Modeling.CompilationContext::get_ShouldReplaceParameterRefs()
0x23f1f  brfalse.s loc_23F2C
0x23f21  ldarg.0
0x23f22  ldfld    class ParameterCollection Microsoft.ReportingServices.Modeling.SemanticQuery::m_parameters
0x23f27  callvirt instance void ParameterCollection::ClearPostCompile()
0x23f2c  leave.s  loc_23F35
0x23f2e  ldarg.1
0x23f2f  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::PopScope()
0x23f34  endfinally
0x23f35  ldarg.0
0x23f36  ldfld    class Microsoft.ReportingServices.Modeling.XmlNamespacePrefixCollection Microsoft.ReportingServices.Modeling.SemanticQuery::m_namespacePrefixes
0x23f3b  callvirt instance void Microsoft.ReportingServices.Modeling.XmlNamespacePrefixCollection::MakeReadOnly()
0x23f40  ret
```
