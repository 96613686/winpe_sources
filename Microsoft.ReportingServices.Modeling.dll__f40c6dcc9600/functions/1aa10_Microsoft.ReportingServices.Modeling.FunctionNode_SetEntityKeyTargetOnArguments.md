# Microsoft.ReportingServices.Modeling.FunctionNode::SetEntityKeyTargetOnArguments

- ea: `0x1aa10`
- end: `0x1aac9`
- name: `Microsoft.ReportingServices.Modeling.FunctionNode::SetEntityKeyTargetOnArguments`
- size: `185`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1a660`
- `0x1a9a0`

## callees

- `0x84f0`
- `0x97d0`
- `0x18a30`
- `0x18a90`
- `0x19cd0`
- `0x19d30`
- `0x1aa10`
- `0x24170`
- `0x24fd0`
- `0x25a90`
- `0x25b70`

## string_xrefs

- `0x1aa25`: `m_arguments must be compiled if ctx.ShouldPersist is true.`

## pseudocode

```c

```

## disassembly

```asm
0x1aa10  ldarg.2
0x1aa11  callvirt instance bool Microsoft.ReportingServices.Modeling.CompilationContext::get_ShouldPersist()
0x1aa16  brfalse.s loc_1AA30
0x1aa18  ldarg.0
0x1aa19  ldfld    class Microsoft.ReportingServices.Modeling.ExpressionCollection Microsoft.ReportingServices.Modeling.FunctionNode::m_arguments
0x1aa1e  callvirt instance bool class Microsoft.ReportingServices.Modeling.CheckedCollection`1<class Microsoft.ReportingServices.Modeling.Expression>::get_IsReadOnly()
0x1aa23  brtrue.s loc_1AA30
0x1aa25  ldstr    aMArgumentsMust// "m_arguments must be compiled if ctx.Sho"...
0x1aa2a  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1aa2f  throw
0x1aa30  ldc.i4.0
0x1aa31  stloc.0
0x1aa32  br       loc_1AAB7
0x1aa37  ldarg.0
0x1aa38  ldfld    class Microsoft.ReportingServices.Modeling.ExpressionCollection Microsoft.ReportingServices.Modeling.FunctionNode::m_arguments
0x1aa3d  ldloc.0
0x1aa3e  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.Expression>::get_Item(!!T0)
0x1aa43  callvirt instance valuetype Microsoft.ReportingServices.Modeling.ResultType Microsoft.ReportingServices.Modeling.Expression::GetResultType()
0x1aa48  stloc.1
0x1aa49  ldloca.s 1
0x1aa4b  call     instance valuetype Microsoft.ReportingServices.Modeling.DataType Microsoft.ReportingServices.Modeling.ResultType::get_DataType()
0x1aa50  ldc.i4.7
0x1aa51  beq.s    loc_1AA5D
0x1aa53  ldloca.s 1
0x1aa55  call     instance valuetype Microsoft.ReportingServices.Modeling.DataType Microsoft.ReportingServices.Modeling.ResultType::get_DataType()
0x1aa5a  ldc.i4.8
0x1aa5b  bne.un.s loc_1AAB3
0x1aa5d  ldloca.s 1
0x1aa5f  call     instance class Microsoft.ReportingServices.Modeling.IQueryEntity Microsoft.ReportingServices.Modeling.ResultType::get_EntityKeyTarget()
0x1aa64  brtrue.s loc_1AA7B
0x1aa66  ldarg.0
0x1aa67  ldfld    class Microsoft.ReportingServices.Modeling.ExpressionCollection Microsoft.ReportingServices.Modeling.FunctionNode::m_arguments
0x1aa6c  ldloc.0
0x1aa6d  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.Expression>::get_Item(!!T0)
0x1aa72  ldarg.1
0x1aa73  ldarg.2
0x1aa74  callvirt instance void Microsoft.ReportingServices.Modeling.Expression::SetEntityKeyTarget(class Microsoft.ReportingServices.Modeling.IQueryEntity entityKeyTarget, class Microsoft.ReportingServices.Modeling.CompilationContext ctx)
0x1aa79  br.s     loc_1AAB3
0x1aa7b  ldloca.s 1
0x1aa7d  call     instance class Microsoft.ReportingServices.Modeling.IQueryEntity Microsoft.ReportingServices.Modeling.ResultType::get_EntityKeyTarget()
0x1aa82  ldarg.1
0x1aa83  beq.s    loc_1AAB3
0x1aa85  ldarg.2
0x1aa86  ldc.i4.s 0x55
0x1aa88  ldarg.2
0x1aa89  callvirt instance valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.ValidationContext::get_CurrentObjectDescriptor()
0x1aa8e  ldarg.0
0x1aa8f  ldfld    valuetype Microsoft.ReportingServices.Modeling.FunctionName Microsoft.ReportingServices.Modeling.FunctionNode::m_functionName
0x1aa94  ldloc.0
0x1aa95  ldc.i4.1
0x1aa96  add
0x1aa97  ldloca.s 1
0x1aa99  call     instance class Microsoft.ReportingServices.Modeling.IQueryEntity Microsoft.ReportingServices.Modeling.ResultType::get_EntityKeyTarget()
0x1aa9e  callvirt instance string Microsoft.ReportingServices.Modeling.IQueryEntity::get_Name()
0x1aaa3  ldarg.1
0x1aaa4  callvirt instance string Microsoft.ReportingServices.Modeling.IQueryEntity::get_Name()
0x1aaa9  call     string Microsoft.ReportingServices.Modeling.SRErrors::EntityKeyTypeMismatch(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName, valuetype Microsoft.ReportingServices.Modeling.FunctionName functionName, int32 argumentIndex, string entity1Name, string entity2Name)
0x1aaae  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x1aab3  ldloc.0
0x1aab4  ldc.i4.1
0x1aab5  add
0x1aab6  stloc.0
0x1aab7  ldloc.0
0x1aab8  ldarg.0
0x1aab9  ldfld    class Microsoft.ReportingServices.Modeling.ExpressionCollection Microsoft.ReportingServices.Modeling.FunctionNode::m_arguments
0x1aabe  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.Expression>::get_Count()
0x1aac3  blt      loc_1AA37
0x1aac8  ret
```
