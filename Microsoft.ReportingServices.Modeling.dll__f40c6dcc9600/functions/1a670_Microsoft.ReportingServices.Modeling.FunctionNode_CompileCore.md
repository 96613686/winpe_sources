# Microsoft.ReportingServices.Modeling.FunctionNode::CompileCore

- ea: `0x1a670`
- end: `0x1a822`
- name: `Microsoft.ReportingServices.Modeling.FunctionNode::CompileCore`
- size: `434`
- prototype: ``
- caller_count: `3`
- callee_count: `25`
- tags: `service_task, broker_com_uri`

## callers

- `0x1a500`
- `0x1a5f0`
- `0x1a830`

## callees

- `0x84f0`
- `0x8530`
- `0x97d0`
- `0x186b0`
- `0x18820`
- `0x18850`
- `0x18fe0`
- `0x19a10`
- `0x19cd0`
- `0x19e80`
- `0x1a3f0`
- `0x1a670`
- `0x1a830`
- `0x1a8a0`
- `0x1ab10`
- `0x1ac10`
- `0x1afb0`
- `0x1dbd0`
- `0x210c0`
- `0x210d0`
- `0x21100`
- `0x21110`
- `0x21120`
- `0x21130`
- `0x212d0`

## string_xrefs

- `0x1a815`: `Result type of the function node does not match the result type of the replacement expression.`

## pseudocode

```c

```

## disassembly

```asm
0x1a670  ldarg.2
0x1a671  ldnull
0x1a672  stind.ref
0x1a673  ldarg.3
0x1a674  ldnull
0x1a675  stind.ref
0x1a676  ldarg.0
0x1a677  call     instance class Microsoft.ReportingServices.Modeling.FunctionInfo Microsoft.ReportingServices.Modeling.FunctionNode::GetApproxFunctionInfo()
0x1a67c  stloc.0
0x1a67d  ldarg.1
0x1a67e  callvirt instance bool Microsoft.ReportingServices.Modeling.CompilationContext::get_ShouldNormalize()
0x1a683  brfalse.s loc_1A6DE
0x1a685  ldloc.0
0x1a686  brfalse.s loc_1A6DE
0x1a688  ldloc.0
0x1a689  callvirt instance valuetype Microsoft.ReportingServices.Modeling.FunctionName Microsoft.ReportingServices.Modeling.FunctionInfo::get_FunctionName()
0x1a68e  ldc.i4.s 0x3E
0x1a690  bne.un.s loc_1A6DE
0x1a692  ldarg.0
0x1a693  ldfld    class Microsoft.ReportingServices.Modeling.ExpressionCollection Microsoft.ReportingServices.Modeling.FunctionNode::m_arguments
0x1a698  ldc.i4.0
0x1a699  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.Expression>::get_Item(!!T0)
0x1a69e  stloc.3
0x1a69f  ldarg.0
0x1a6a0  ldfld    class Microsoft.ReportingServices.Modeling.ExpressionCollection Microsoft.ReportingServices.Modeling.FunctionNode::m_arguments
0x1a6a5  ldc.i4.1
0x1a6a6  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.Expression>::get_Item(!!T0)
0x1a6ab  stloc.s  4
0x1a6ad  ldloc.3
0x1a6ae  callvirt instance class Microsoft.ReportingServices.Modeling.ExpressionPath Microsoft.ReportingServices.Modeling.Expression::get_Path()
0x1a6b3  callvirt instance bool class Microsoft.ReportingServices.Modeling.CheckedCollection`1<class Microsoft.ReportingServices.Modeling.PathItem>::get_IsEmpty()
0x1a6b8  brfalse.s loc_1A6DE
0x1a6ba  ldloc.3
0x1a6bb  callvirt instance class Microsoft.ReportingServices.Modeling.FunctionNode Microsoft.ReportingServices.Modeling.Expression::get_NodeAsFunction()
0x1a6c0  brfalse.s loc_1A6DE
0x1a6c2  ldloc.3
0x1a6c3  callvirt instance class Microsoft.ReportingServices.Modeling.FunctionNode Microsoft.ReportingServices.Modeling.Expression::get_NodeAsFunction()
0x1a6c8  callvirt instance valuetype Microsoft.ReportingServices.Modeling.FunctionName Microsoft.ReportingServices.Modeling.FunctionNode::get_FunctionName()
0x1a6cd  ldc.i4.s 0x3E
0x1a6cf  bne.un.s loc_1A6DE
0x1a6d1  ldarg.0
0x1a6d2  ldarg.1
0x1a6d3  ldloc.3
0x1a6d4  ldloc.s  4
0x1a6d6  ldarg.2
0x1a6d7  ldarg.3
0x1a6d8  call     instance class Microsoft.ReportingServices.Modeling.FunctionInfo Microsoft.ReportingServices.Modeling.FunctionNode::CombineFiltersAndCompile(class Microsoft.ReportingServices.Modeling.CompilationContext ctx, class Microsoft.ReportingServices.Modeling.Expression outerFilterItemsArg, class Microsoft.ReportingServices.Modeling.Expression outerFilterCondArg, [out] class Microsoft.ReportingServices.Modeling.Expression& replacementExpr, [out] class Microsoft.ReportingServices.Modeling.IQueryEntity& firstEntityKeyTarget)
0x1a6dd  ret
0x1a6de  ldarg.0
0x1a6df  ldfld    class Microsoft.ReportingServices.Modeling.ExpressionCollection Microsoft.ReportingServices.Modeling.FunctionNode::m_arguments
0x1a6e4  ldarg.1
0x1a6e5  ldsfld   valuetype Microsoft.ReportingServices.Modeling.ExpressionCompilationFlags Microsoft.ReportingServices.Modeling.ExpressionCompilationFlags::None
0x1a6ea  ldarg.3
0x1a6eb  callvirt instance valuetype Microsoft.ReportingServices.Modeling.ResultType[] Microsoft.ReportingServices.Modeling.ExpressionCollection::Compile(class Microsoft.ReportingServices.Modeling.CompilationContext ctx, valuetype Microsoft.ReportingServices.Modeling.ExpressionCompilationFlags flags, [out] class Microsoft.ReportingServices.Modeling.IQueryEntity& firstEntityKeyTarget)
0x1a6f0  stloc.1
0x1a6f1  ldloc.1
0x1a6f2  brtrue.s loc_1A6F6
0x1a6f4  ldnull
0x1a6f5  ret
0x1a6f6  ldarg.0
0x1a6f7  ldfld    valuetype Microsoft.ReportingServices.Modeling.FunctionName Microsoft.ReportingServices.Modeling.FunctionNode::m_functionName
0x1a6fc  ldloc.1
0x1a6fd  ldarg.0
0x1a6fe  ldfld    class Microsoft.ReportingServices.Modeling.ExpressionCollection Microsoft.ReportingServices.Modeling.FunctionNode::m_arguments
0x1a703  ldarg.1
0x1a704  call     class Microsoft.ReportingServices.Modeling.FunctionInfo Microsoft.ReportingServices.Modeling.FunctionInfo::Resolve(valuetype Microsoft.ReportingServices.Modeling.FunctionName functionName, valuetype Microsoft.ReportingServices.Modeling.ResultType[] arguments, class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.ReportingServices.Modeling.Expression> argumentExprs, class Microsoft.ReportingServices.Modeling.ValidationContext ctx)
0x1a709  stloc.2
0x1a70a  ldloc.2
0x1a70b  brfalse  loc_1A820
0x1a710  ldloc.2
0x1a711  callvirt instance valuetype Microsoft.ReportingServices.Modeling.FunctionName Microsoft.ReportingServices.Modeling.FunctionInfo::get_FunctionName()
0x1a716  ldarg.0
0x1a717  ldfld    valuetype Microsoft.ReportingServices.Modeling.FunctionName Microsoft.ReportingServices.Modeling.FunctionNode::m_functionName
0x1a71c  bne.un.s loc_1A75F
0x1a71e  ldloc.2
0x1a71f  callvirt instance bool Microsoft.ReportingServices.Modeling.FunctionInfo::get_RepeatingArguments()
0x1a724  brtrue.s loc_1A73E
0x1a726  ldloc.2
0x1a727  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<valuetype Microsoft.ReportingServices.Modeling.ResultType> Microsoft.ReportingServices.Modeling.FunctionInfo::get_Arguments()
0x1a72c  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<valuetype Microsoft.ReportingServices.Modeling.ResultType>::get_Count()
0x1a731  ldarg.0
0x1a732  ldfld    class Microsoft.ReportingServices.Modeling.ExpressionCollection Microsoft.ReportingServices.Modeling.FunctionNode::m_arguments
0x1a737  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.Expression>::get_Count()
0x1a73c  bne.un.s loc_1A75F
0x1a73e  ldloc.2
0x1a73f  callvirt instance bool Microsoft.ReportingServices.Modeling.FunctionInfo::get_RepeatingArguments()
0x1a744  brfalse.s loc_1A76A
0x1a746  ldarg.0
0x1a747  ldfld    class Microsoft.ReportingServices.Modeling.ExpressionCollection Microsoft.ReportingServices.Modeling.FunctionNode::m_arguments
0x1a74c  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.Expression>::get_Count()
0x1a751  ldloc.2
0x1a752  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<valuetype Microsoft.ReportingServices.Modeling.ResultType> Microsoft.ReportingServices.Modeling.FunctionInfo::get_Arguments()
0x1a757  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<valuetype Microsoft.ReportingServices.Modeling.ResultType>::get_Count()
0x1a75c  rem
0x1a75d  brfalse.s loc_1A76A
0x1a75f  ldstr    aFunctionResolu// "Function resolution returned wrong func"...
0x1a764  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1a769  throw
0x1a76a  ldarg.0
0x1a76b  ldloc.2
0x1a76c  ldarg.1
0x1a76d  call     instance bool Microsoft.ReportingServices.Modeling.FunctionNode::CheckArgsRange(class Microsoft.ReportingServices.Modeling.FunctionInfo fInfo, class Microsoft.ReportingServices.Modeling.CompilationContext ctx)
0x1a772  brtrue.s loc_1A776
0x1a774  ldnull
0x1a775  ret
0x1a776  ldloc.2
0x1a777  callvirt instance valuetype Microsoft.ReportingServices.Modeling.FunctionName Microsoft.ReportingServices.Modeling.FunctionInfo::get_FunctionName()
0x1a77c  ldc.i4.s 0x40
0x1a77e  bne.un.s loc_1A78B
0x1a780  ldarg.2
0x1a781  ldarg.0
0x1a782  ldarg.1
0x1a783  call     instance class Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.Modeling.FunctionNode::ResolveAggregateAndCompile(class Microsoft.ReportingServices.Modeling.CompilationContext ctx)
0x1a788  stind.ref
0x1a789  br.s     loc_1A79D
0x1a78b  ldloc.2
0x1a78c  callvirt instance bool Microsoft.ReportingServices.Modeling.FunctionInfo::get_IsStatic()
0x1a791  brfalse.s loc_1A79D
0x1a793  ldarg.2
0x1a794  ldarg.0
0x1a795  ldarg.1
0x1a796  ldloc.2
0x1a797  call     instance class Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.Modeling.FunctionNode::ResolveStaticAndCompile(class Microsoft.ReportingServices.Modeling.CompilationContext ctx, class Microsoft.ReportingServices.Modeling.FunctionInfo fInfo)
0x1a79c  stind.ref
0x1a79d  ldarg.1
0x1a79e  callvirt instance bool Microsoft.ReportingServices.Modeling.CompilationContext::get_ShouldNormalize()
0x1a7a3  brfalse.s loc_1A820
0x1a7a5  ldarg.2
0x1a7a6  ldind.ref
0x1a7a7  brtrue.s loc_1A820
0x1a7a9  ldloc.2
0x1a7aa  callvirt instance valuetype Microsoft.ReportingServices.Modeling.ResultType Microsoft.ReportingServices.Modeling.FunctionInfo::get_ReturnType()
0x1a7af  stloc.s  5
0x1a7b1  ldloca.s 5
0x1a7b3  call     instance valuetype Microsoft.ReportingServices.Modeling.DataType Microsoft.ReportingServices.Modeling.ResultType::get_DataType()
0x1a7b8  ldc.i4.8
0x1a7b9  bne.un.s loc_1A820
0x1a7bb  ldloc.2
0x1a7bc  callvirt instance bool Microsoft.ReportingServices.Modeling.FunctionInfo::get_IsScalar()
0x1a7c1  brfalse.s loc_1A820
0x1a7c3  ldarg.1
0x1a7c4  callvirt instance bool Microsoft.ReportingServices.Modeling.CompilationContext::get_ShouldPersist()
0x1a7c9  brtrue.s loc_1A7D6
0x1a7cb  ldstr    aNormalizeWitho// "Normalize without persist."
0x1a7d0  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1a7d5  throw
0x1a7d6  ldarg.2
0x1a7d7  newobj   instance void Microsoft.ReportingServices.Modeling.NullNode::.ctor()
0x1a7dc  newobj   instance void Microsoft.ReportingServices.Modeling.Expression::.ctor(class Microsoft.ReportingServices.Modeling.ExpressionNode node)
0x1a7e1  stind.ref
0x1a7e2  ldloc.2
0x1a7e3  callvirt instance valuetype Microsoft.ReportingServices.Modeling.ResultType Microsoft.ReportingServices.Modeling.FunctionInfo::get_ReturnType()
0x1a7e8  stloc.s  5
0x1a7ea  ldarg.2
0x1a7eb  ldind.ref
0x1a7ec  ldarg.1
0x1a7ed  ldsfld   valuetype Microsoft.ReportingServices.Modeling.ExpressionCompilationFlags Microsoft.ReportingServices.Modeling.ExpressionCompilationFlags::None
0x1a7f2  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.ResultType> Microsoft.ReportingServices.Modeling.Expression::Compile(class Microsoft.ReportingServices.Modeling.CompilationContext ctx, valuetype Microsoft.ReportingServices.Modeling.ExpressionCompilationFlags flags)
0x1a7f7  stloc.s  6
0x1a7f9  ldloca.s 6
0x1a7fb  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.ResultType>::get_HasValue()
0x1a800  brtrue.s loc_1A805
0x1a802  ldc.i4.1
0x1a803  br.s     loc_1A813
0x1a805  ldloc.s  5
0x1a807  ldloca.s 6
0x1a809  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.ResultType>::GetValueOrDefault()
0x1a80e  call     bool Microsoft.ReportingServices.Modeling.ResultType::op_Inequality(valuetype Microsoft.ReportingServices.Modeling.ResultType x, valuetype Microsoft.ReportingServices.Modeling.ResultType y)
0x1a813  brfalse.s loc_1A820
0x1a815  ldstr    aResultTypeOfTh// "Result type of the function node does n"...
0x1a81a  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1a81f  throw
0x1a820  ldloc.2
0x1a821  ret
```
