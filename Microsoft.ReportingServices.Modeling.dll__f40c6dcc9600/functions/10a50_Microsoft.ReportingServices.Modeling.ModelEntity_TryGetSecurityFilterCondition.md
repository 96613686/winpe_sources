# Microsoft.ReportingServices.Modeling.ModelEntity::TryGetSecurityFilterCondition

- ea: `0x10a50`
- end: `0x10cc4`
- name: `Microsoft.ReportingServices.Modeling.ModelEntity::TryGetSecurityFilterCondition`
- size: `628`
- prototype: ``
- caller_count: `3`
- callee_count: `27`
- tags: `service_task, broker_com_uri`

## callers

- `0x10570`
- `0x10a50`
- `0x171b0`

## callees

- `0x8540`
- `0x8610`
- `0x8620`
- `0x87b0`
- `0x87f0`
- `0x97d0`
- `0x106b0`
- `0x10830`
- `0x10860`
- `0x10960`
- `0x10a50`
- `0x10cd0`
- `0x11790`
- `0x117a0`
- `0x12520`
- `0x186b0`
- `0x186c0`
- `0x189a0`
- `0x189b0`
- `0x18fe0`
- `0x1a350`
- `0x1b290`
- `0x1c3d0`
- `0x253d0`
- `0x25590`
- `0x25a60`
- `0x25b70`

## string_xrefs

- `0x10a6b`: `TryGetSecurityFilterCondition: ctx.ShouldApplySecurityFilters must be true.`
- `0x10a7e`: `TryGetSecurityFilterCondition: ctxIncludeSecurityFilter is null.`
- `0x10a91`: `TryGetSecurityFilterCondition is called on a lazy cloned entity.`
- `0x10c9e`: `TryGetSecurityFilterCondition: securityFilterCondition has failed to compile but ctx.HasErrors is false.`

## pseudocode

```c

```

## disassembly

```asm
0x10a50  ldarg.1
0x10a51  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<class Microsoft.ReportingServices.Modeling.IQueryEntity, class Microsoft.ReportingServices.Modeling.Expression> Microsoft.ReportingServices.Modeling.CompilationContext::get_SecurityFilters()
0x10a56  ldarg.0
0x10a57  ldloca.s 0
0x10a59  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<class Microsoft.ReportingServices.Modeling.IQueryEntity, class Microsoft.ReportingServices.Modeling.Expression>::TryGetValue(var<u1>, !!T0)
0x10a5e  brtrue   loc_10CC2
0x10a63  ldarg.1
0x10a64  callvirt instance bool Microsoft.ReportingServices.Modeling.CompilationContext::get_ShouldApplySecurityFilters()
0x10a69  brtrue.s loc_10A76
0x10a6b  ldstr    aTrygetsecurity// "TryGetSecurityFilterCondition: ctx.Shou"...
0x10a70  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x10a75  throw
0x10a76  ldarg.1
0x10a77  callvirt instance class [mscorlib]System.Predicate`1<class Microsoft.ReportingServices.Modeling.ModelItem> Microsoft.ReportingServices.Modeling.CompilationContext::get_IncludeSecurityFilter()
0x10a7c  brtrue.s loc_10A89
0x10a7e  ldstr    aTrygetsecurity_0// "TryGetSecurityFilterCondition: ctxInclu"...
0x10a83  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x10a88  throw
0x10a89  ldarg.0
0x10a8a  call     instance class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.ModelEntity::get_BaseItem()
0x10a8f  brfalse.s loc_10A9C
0x10a91  ldstr    aTrygetsecurity_1// "TryGetSecurityFilterCondition is called"...
0x10a96  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x10a9b  throw
0x10a9c  ldarg.1
0x10a9d  ldarg.0
0x10a9e  ldloca.s 1
0x10aa0  callvirt instance bool Microsoft.ReportingServices.Modeling.CompilationContext::StartSecurityFilterGeneration(class Microsoft.ReportingServices.Modeling.IQueryEntity entity, [out] class [System]System.Collections.Generic.Stack`1<class Microsoft.ReportingServices.Modeling.Expression>& savedExpressionStack)
0x10aa5  brtrue.s loc_10ABC
0x10aa7  ldarg.1
0x10aa8  ldc.i4.s 0x74
0x10aaa  ldarg.0
0x10aab  call     valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.SRObjectDescriptor::FromScope(class Microsoft.ReportingServices.Modeling.IValidationScope scope)
0x10ab0  call     string Microsoft.ReportingServices.Modeling.SRErrors::LoopInSecurityFilters(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor entityTypeAndName)
0x10ab5  callvirt instance void Microsoft.ReportingServices.Modeling.ValidationContext::AddScopedError(valuetype Microsoft.ReportingServices.Modeling.ModelingErrorCode code, string message)
0x10aba  ldnull
0x10abb  ret
0x10abc  nop
0x10abd  ldarg.0
0x10abe  call     instance class Microsoft.ReportingServices.Modeling.AttributeReferenceCollection Microsoft.ReportingServices.Modeling.ModelEntity::get_SecurityFilters()
0x10ac3  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.AttributeReference>::get_Count()
0x10ac8  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Modeling.AttributeReference>::.ctor(int32)
0x10acd  stloc.2
0x10ace  ldc.i4.0
0x10acf  stloc.s  4
0x10ad1  br.s     loc_10B0B
0x10ad3  ldarg.1
0x10ad4  callvirt instance class [mscorlib]System.Predicate`1<class Microsoft.ReportingServices.Modeling.ModelItem> Microsoft.ReportingServices.Modeling.CompilationContext::get_IncludeSecurityFilter()
0x10ad9  ldarg.0
0x10ada  call     instance class Microsoft.ReportingServices.Modeling.AttributeReferenceCollection Microsoft.ReportingServices.Modeling.ModelEntity::get_SecurityFilters()
0x10adf  ldloc.s  4
0x10ae1  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.AttributeReference>::get_Item(!!T0)
0x10ae6  callvirt instance class Microsoft.ReportingServices.Modeling.ModelAttribute Microsoft.ReportingServices.Modeling.AttributeReference::get_Attribute()
0x10aeb  callvirt instance bool class [mscorlib]System.Predicate`1<class Microsoft.ReportingServices.Modeling.ModelItem>::Invoke(var<u1>)
0x10af0  brfalse.s loc_10B05
0x10af2  ldloc.2
0x10af3  ldarg.0
0x10af4  call     instance class Microsoft.ReportingServices.Modeling.AttributeReferenceCollection Microsoft.ReportingServices.Modeling.ModelEntity::get_SecurityFilters()
0x10af9  ldloc.s  4
0x10afb  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.AttributeReference>::get_Item(!!T0)
0x10b00  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Modeling.AttributeReference>::Add(var<u1>)
0x10b05  ldloc.s  4
0x10b07  ldc.i4.1
0x10b08  add
0x10b09  stloc.s  4
0x10b0b  ldloc.s  4
0x10b0d  ldarg.0
0x10b0e  call     instance class Microsoft.ReportingServices.Modeling.AttributeReferenceCollection Microsoft.ReportingServices.Modeling.ModelEntity::get_SecurityFilters()
0x10b13  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.AttributeReference>::get_Count()
0x10b18  blt.s    loc_10AD3
0x10b1a  ldarg.0
0x10b1b  call     instance class Microsoft.ReportingServices.Modeling.AttributeReferenceCollection Microsoft.ReportingServices.Modeling.ModelEntity::get_SecurityFilters()
0x10b20  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.AttributeReference>::get_Count()
0x10b25  ldc.i4.0
0x10b26  ble.s    loc_10B33
0x10b28  ldloc.2
0x10b29  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Modeling.AttributeReference>::get_Count()
0x10b2e  ldc.i4.0
0x10b2f  ceq
0x10b31  br.s     loc_10B34
0x10b33  ldc.i4.0
0x10b34  stloc.3
0x10b35  ldloc.2
0x10b36  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Modeling.AttributeReference>::get_Count()
0x10b3b  ldc.i4.0
0x10b3c  ble      loc_10BE3
0x10b41  ldloc.2
0x10b42  ldc.i4.0
0x10b43  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Modeling.AttributeReference>::get_Item(!!T0)
0x10b48  call     bool Microsoft.ReportingServices.Modeling.ModelEntity::IsLiteralTrue(class Microsoft.ReportingServices.Modeling.AttributeReference securityFilter)
0x10b4d  brtrue   loc_10BDF
0x10b52  ldloc.2
0x10b53  ldc.i4.0
0x10b54  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Modeling.AttributeReference>::get_Item(!!T0)
0x10b59  callvirt instance class Microsoft.ReportingServices.Modeling.ModelAttribute Microsoft.ReportingServices.Modeling.AttributeReference::get_Attribute()
0x10b5e  newobj   instance void Microsoft.ReportingServices.Modeling.AttributeRefNode::.ctor(class Microsoft.ReportingServices.Modeling.IQueryAttribute attribute)
0x10b63  ldloc.2
0x10b64  ldc.i4.0
0x10b65  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Modeling.AttributeReference>::get_Item(!!T0)
0x10b6a  callvirt instance class Microsoft.ReportingServices.Modeling.ExpressionPath Microsoft.ReportingServices.Modeling.AttributeReference::get_Path()
0x10b6f  newobj   instance void Microsoft.ReportingServices.Modeling.Expression::.ctor(class Microsoft.ReportingServices.Modeling.ExpressionNode node, class Microsoft.ReportingServices.Modeling.ExpressionPath path)
0x10b74  stloc.0
0x10b75  ldc.i4.1
0x10b76  stloc.s  5
0x10b78  br.s     loc_10BD3
0x10b7a  ldloc.2
0x10b7b  ldloc.s  5
0x10b7d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Modeling.AttributeReference>::get_Item(!!T0)
0x10b82  call     bool Microsoft.ReportingServices.Modeling.ModelEntity::IsLiteralTrue(class Microsoft.ReportingServices.Modeling.AttributeReference securityFilter)
0x10b87  brtrue.s loc_10BC9
0x10b89  ldc.i4.s 0xE
0x10b8b  ldc.i4.2
0x10b8c  newarr   Microsoft.ReportingServices.Modeling.Expression
0x10b91  dup
0x10b92  ldc.i4.0
0x10b93  ldloc.0
0x10b94  stelem.ref
0x10b95  dup
0x10b96  ldc.i4.1
0x10b97  ldloc.2
0x10b98  ldloc.s  5
0x10b9a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Modeling.AttributeReference>::get_Item(!!T0)
0x10b9f  callvirt instance class Microsoft.ReportingServices.Modeling.ModelAttribute Microsoft.ReportingServices.Modeling.AttributeReference::get_Attribute()
0x10ba4  newobj   instance void Microsoft.ReportingServices.Modeling.AttributeRefNode::.ctor(class Microsoft.ReportingServices.Modeling.IQueryAttribute attribute)
0x10ba9  ldloc.2
0x10baa  ldloc.s  5
0x10bac  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Modeling.AttributeReference>::get_Item(!!T0)
0x10bb1  callvirt instance class Microsoft.ReportingServices.Modeling.ExpressionPath Microsoft.ReportingServices.Modeling.AttributeReference::get_Path()
0x10bb6  newobj   instance void Microsoft.ReportingServices.Modeling.Expression::.ctor(class Microsoft.ReportingServices.Modeling.ExpressionNode node, class Microsoft.ReportingServices.Modeling.ExpressionPath path)
0x10bbb  stelem.ref
0x10bbc  newobj   instance void Microsoft.ReportingServices.Modeling.FunctionNode::.ctor(valuetype Microsoft.ReportingServices.Modeling.FunctionName functionName, class Microsoft.ReportingServices.Modeling.Expression[] arguments)
0x10bc1  newobj   instance void Microsoft.ReportingServices.Modeling.Expression::.ctor(class Microsoft.ReportingServices.Modeling.ExpressionNode node)
0x10bc6  stloc.0
0x10bc7  br.s     loc_10BCD
0x10bc9  ldnull
0x10bca  stloc.0
0x10bcb  br.s     loc_10C21
0x10bcd  ldloc.s  5
0x10bcf  ldc.i4.1
0x10bd0  add
0x10bd1  stloc.s  5
0x10bd3  ldloc.s  5
0x10bd5  ldloc.2
0x10bd6  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Modeling.AttributeReference>::get_Count()
0x10bdb  blt.s    loc_10B7A
0x10bdd  br.s     loc_10C21
0x10bdf  ldnull
0x10be0  stloc.0
0x10be1  br.s     loc_10C21
0x10be3  ldarg.0
0x10be4  call     instance class Microsoft.ReportingServices.Modeling.AttributeReference Microsoft.ReportingServices.Modeling.ModelEntity::get_DefaultSecurityFilter()
0x10be9  brfalse.s loc_10C0E
0x10beb  ldarg.0
0x10bec  call     instance class Microsoft.ReportingServices.Modeling.AttributeReference Microsoft.ReportingServices.Modeling.ModelEntity::get_DefaultSecurityFilter()
0x10bf1  callvirt instance class Microsoft.ReportingServices.Modeling.ModelAttribute Microsoft.ReportingServices.Modeling.AttributeReference::get_Attribute()
0x10bf6  newobj   instance void Microsoft.ReportingServices.Modeling.AttributeRefNode::.ctor(class Microsoft.ReportingServices.Modeling.IQueryAttribute attribute)
0x10bfb  ldarg.0
0x10bfc  call     instance class Microsoft.ReportingServices.Modeling.AttributeReference Microsoft.ReportingServices.Modeling.ModelEntity::get_DefaultSecurityFilter()
0x10c01  callvirt instance class Microsoft.ReportingServices.Modeling.ExpressionPath Microsoft.ReportingServices.Modeling.AttributeReference::get_Path()
0x10c06  newobj   instance void Microsoft.ReportingServices.Modeling.Expression::.ctor(class Microsoft.ReportingServices.Modeling.ExpressionNode node, class Microsoft.ReportingServices.Modeling.ExpressionPath path)
0x10c0b  stloc.0
0x10c0c  br.s     loc_10C21
0x10c0e  ldloc.3
0x10c0f  brfalse.s loc_10C1F
0x10c11  ldc.i4.0
0x10c12  newobj   instance void Microsoft.ReportingServices.Modeling.LiteralNode::.ctor(bool value)
0x10c17  newobj   instance void Microsoft.ReportingServices.Modeling.Expression::.ctor(class Microsoft.ReportingServices.Modeling.ExpressionNode node)
0x10c1c  stloc.0
0x10c1d  br.s     loc_10C21
0x10c1f  ldnull
0x10c20  stloc.0
0x10c21  ldarg.0
0x10c22  call     instance class Microsoft.ReportingServices.Modeling.EntityInheritance Microsoft.ReportingServices.Modeling.ModelEntity::get_Inheritance()
0x10c27  brfalse.s loc_10C6D
0x10c29  ldarg.0
0x10c2a  call     instance class Microsoft.ReportingServices.Modeling.EntityInheritance Microsoft.ReportingServices.Modeling.ModelEntity::get_Inheritance()
0x10c2f  callvirt instance class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.EntityInheritance::get_InheritsFrom()
0x10c34  ldarg.1
0x10c35  callvirt instance class Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.Modeling.ModelEntity::TryGetSecurityFilterCondition(class Microsoft.ReportingServices.Modeling.CompilationContext ctx)
0x10c3a  stloc.s  6
0x10c3c  ldloc.s  6
0x10c3e  brfalse.s loc_10C6D
0x10c40  ldloc.s  6
0x10c42  callvirt instance class Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.Modeling.Expression::Clone()
0x10c47  stloc.s  6
0x10c49  ldloc.0
0x10c4a  brtrue.s loc_10C51
0x10c4c  ldloc.s  6
0x10c4e  stloc.0
0x10c4f  br.s     loc_10C6D
0x10c51  ldc.i4.s 0xD
0x10c53  ldc.i4.2
0x10c54  newarr   Microsoft.ReportingServices.Modeling.Expression
0x10c59  dup
0x10c5a  ldc.i4.0
0x10c5b  ldloc.0
0x10c5c  stelem.ref
0x10c5d  dup
0x10c5e  ldc.i4.1
0x10c5f  ldloc.s  6
0x10c61  stelem.ref
0x10c62  newobj   instance void Microsoft.ReportingServices.Modeling.FunctionNode::.ctor(valuetype Microsoft.ReportingServices.Modeling.FunctionName functionName, class Microsoft.ReportingServices.Modeling.Expression[] arguments)
0x10c67  newobj   instance void Microsoft.ReportingServices.Modeling.Expression::.ctor(class Microsoft.ReportingServices.Modeling.ExpressionNode node)
0x10c6c  stloc.0
0x10c6d  ldloc.0
0x10c6e  brfalse.s loc_10CAB
0x10c70  ldloc.0
0x10c71  ldarg.1
0x10c72  ldsfld   valuetype Microsoft.ReportingServices.Modeling.ExpressionCompilationFlags Microsoft.ReportingServices.Modeling.ExpressionCompilationFlags::None
0x10c77  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.ResultType> Microsoft.ReportingServices.Modeling.Expression::Compile(class Microsoft.ReportingServices.Modeling.CompilationContext ctx, valuetype Microsoft.ReportingServices.Modeling.ExpressionCompilationFlags flags)
0x10c7c  stloc.s  7
0x10c7e  ldloca.s 7
0x10c80  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.Modeling.ResultType>::get_HasValue()
0x10c85  brfalse.s loc_10C96
0x10c87  ldloc.0
0x10c88  callvirt instance class Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.Modeling.Expression::Clone()
0x10c8d  stloc.0
0x10c8e  ldloc.0
0x10c8f  callvirt instance void Microsoft.ReportingServices.Modeling.Expression::MarkAsSkipSecurityFilters()
0x10c94  br.s     loc_10CAB
0x10c96  ldarg.1
0x10c97  callvirt instance bool Microsoft.ReportingServices.Modeling.ValidationContext::get_HasErrors()
0x10c9c  brtrue.s loc_10CA9
0x10c9e  ldstr    aTrygetsecurity_2// "TryGetSecurityFilterCondition: security"...
0x10ca3  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x10ca8  throw
0x10ca9  ldnull
0x10caa  stloc.0
0x10cab  ldarg.1
0x10cac  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<class Microsoft.ReportingServices.Modeling.IQueryEntity, class Microsoft.ReportingServices.Modeling.Expression> Microsoft.ReportingServices.Modeling.CompilationContext::get_SecurityFilters()
0x10cb1  ldarg.0
0x10cb2  ldloc.0
0x10cb3  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<class Microsoft.ReportingServices.Modeling.IQueryEntity, class Microsoft.ReportingServices.Modeling.Expression>::Add(var<u1>, !!T0)
0x10cb8  leave.s  loc_10CC2
0x10cba  ldarg.1
0x10cbb  ldloc.1
0x10cbc  callvirt instance void Microsoft.ReportingServices.Modeling.CompilationContext::EndSecurityFilterGeneration(class [System]System.Collections.Generic.Stack`1<class Microsoft.ReportingServices.Modeling.Expression> savedExpressionStack)
0x10cc1  endfinally
0x10cc2  ldloc.0
0x10cc3  ret
```
