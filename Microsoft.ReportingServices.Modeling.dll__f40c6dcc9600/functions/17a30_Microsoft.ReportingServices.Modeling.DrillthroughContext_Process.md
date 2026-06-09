# Microsoft.ReportingServices.Modeling.DrillthroughContext::Process

- ea: `0x17a30`
- end: `0x17b96`
- name: `Microsoft.ReportingServices.Modeling.DrillthroughContext::Process`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `service_task, broker_com_uri`

## callers

- `0x23f50`

## callees

- `0x8a30`
- `0x8b40`
- `0x8e00`
- `0x97d0`
- `0x9eb0`
- `0x17a30`
- `0x17ba0`
- `0x17d40`
- `0x17eb0`
- `0x186b0`
- `0x18870`
- `0x19ea0`
- `0x1a350`
- `0x1bb50`
- `0x21950`
- `0x21970`
- `0x21cd0`
- `0x21d30`
- `0x21d40`
- `0x23300`
- `0x35290`
- `0x35670`

## pseudocode

```c

```

## disassembly

```asm
0x17a30  ldarg.0
0x17a31  ldarg.2
0x17a32  ldloca.s 0
0x17a34  call     instance bool Microsoft.ReportingServices.Modeling.DrillthroughContext::CompileSelectedItems(class Microsoft.ReportingServices.Modeling.CompilationContext compileCtx, [out] class Microsoft.ReportingServices.Modeling.Grouping& parentGrouping)
0x17a39  brtrue.s loc_17A3C
0x17a3b  ret
0x17a3c  ldarg.0
0x17a3d  ldfld    class Microsoft.ReportingServices.Modeling.SemanticQuery Microsoft.ReportingServices.Modeling.DrillthroughContext::m_sourceQuery
0x17a42  call     class Microsoft.ReportingServices.Modeling.IQueryEntity Microsoft.ReportingServices.Modeling.DrillthroughContext::GetBaseEntity(class Microsoft.ReportingServices.Modeling.SemanticQuery query)
0x17a47  stloc.1
0x17a48  ldarg.1
0x17a49  call     class Microsoft.ReportingServices.Modeling.IQueryEntity Microsoft.ReportingServices.Modeling.DrillthroughContext::GetBaseEntity(class Microsoft.ReportingServices.Modeling.SemanticQuery query)
0x17a4e  stloc.2
0x17a4f  ldloc.0
0x17a50  brfalse.s loc_17A76
0x17a52  ldloc.0
0x17a53  callvirt instance bool Microsoft.ReportingServices.Modeling.Grouping::get_IsEntityGrouping()
0x17a58  brtrue.s loc_17A65
0x17a5a  ldstr    aUnexpectedNonE// "Unexpected non-entity parent grouping"
0x17a5f  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x17a64  throw
0x17a65  ldloc.0
0x17a66  callvirt instance class Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.Modeling.Grouping::get_Expression()
0x17a6b  callvirt instance class Microsoft.ReportingServices.Modeling.EntityRefNode Microsoft.ReportingServices.Modeling.Expression::get_NodeAsEntityRef()
0x17a70  callvirt instance class Microsoft.ReportingServices.Modeling.IQueryEntity Microsoft.ReportingServices.Modeling.EntityRefNode::get_Entity()
0x17a75  stloc.1
0x17a76  ldarg.0
0x17a77  ldarg.2
0x17a78  ldloc.1
0x17a79  ldloc.2
0x17a7a  call     instance bool Microsoft.ReportingServices.Modeling.DrillthroughContext::CompileSelectedPath(class Microsoft.ReportingServices.Modeling.CompilationContext compileCtx, class Microsoft.ReportingServices.Modeling.IQueryEntity sourceEntity, class Microsoft.ReportingServices.Modeling.IQueryEntity targetEntity)
0x17a7f  brtrue.s loc_17A82
0x17a81  ret
0x17a82  ldarg.0
0x17a83  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Modeling.Expression> Microsoft.ReportingServices.Modeling.DrillthroughContext::m_selectedItems
0x17a88  ldarg.0
0x17a89  ldfld    class Microsoft.ReportingServices.Modeling.ExpressionPath Microsoft.ReportingServices.Modeling.DrillthroughContext::m_selectedPath
0x17a8e  call     class [mscorlib]System.Collections.Generic.List`1<class FilteredPath> CalculateBranchesAlgorithm::Calculate(class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Modeling.Expression> selectedItems, class Microsoft.ReportingServices.Modeling.ExpressionPath selectedPath)
0x17a93  ldarg.1
0x17a94  newobj   instance void Microsoft.ReportingServices.Modeling.ExpressionCopyManager::.ctor(class Microsoft.ReportingServices.Modeling.SemanticQuery targetQuery)
0x17a99  stloc.3
0x17a9a  ldloc.0
0x17a9b  ldarg.0
0x17a9c  ldfld    class Microsoft.ReportingServices.Modeling.SemanticQuery Microsoft.ReportingServices.Modeling.DrillthroughContext::m_sourceQuery
0x17aa1  ldarg.0
0x17aa2  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.ReportingServices.Modeling.Grouping, string> Microsoft.ReportingServices.Modeling.DrillthroughContext::m_groupingValues
0x17aa7  ldarg.2
0x17aa8  ldloc.3
0x17aa9  call     class Microsoft.ReportingServices.Modeling.Expression ProcessBranchesAlgorithm::Process(class [mscorlib]System.Collections.Generic.List`1<class FilteredPath> branches, class Microsoft.ReportingServices.Modeling.Grouping parentGrouping, class Microsoft.ReportingServices.Modeling.SemanticQuery sourceQuery, class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.ReportingServices.Modeling.Grouping, string> groupingValues, class Microsoft.ReportingServices.Modeling.CompilationContext compileCtx, class Microsoft.ReportingServices.Modeling.ExpressionCopyManager copyManager)
0x17aae  stloc.s  4
0x17ab0  ldloc.s  4
0x17ab2  brfalse  loc_17B39
0x17ab7  ldarg.1
0x17ab8  callvirt instance class HierarchyCollection Microsoft.ReportingServices.Modeling.SemanticQuery::get_Hierarchies()
0x17abd  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.Hierarchy>::get_Count()
0x17ac2  brtrue.s loc_17AD5
0x17ac4  ldarg.1
0x17ac5  callvirt instance class HierarchyCollection Microsoft.ReportingServices.Modeling.SemanticQuery::get_Hierarchies()
0x17aca  ldloc.2
0x17acb  newobj   instance void Microsoft.ReportingServices.Modeling.Hierarchy::.ctor(class Microsoft.ReportingServices.Modeling.IQueryEntity baseEntity)
0x17ad0  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.Hierarchy>::Add(var<u1>)
0x17ad5  ldarg.1
0x17ad6  callvirt instance class HierarchyCollection Microsoft.ReportingServices.Modeling.SemanticQuery::get_Hierarchies()
0x17adb  ldc.i4.0
0x17adc  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.Hierarchy>::get_Item(!!T0)
0x17ae1  callvirt instance class Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.Modeling.Hierarchy::get_Filter()
0x17ae6  brtrue.s loc_17AFD
0x17ae8  ldarg.1
0x17ae9  callvirt instance class HierarchyCollection Microsoft.ReportingServices.Modeling.SemanticQuery::get_Hierarchies()
0x17aee  ldc.i4.0
0x17aef  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.Hierarchy>::get_Item(!!T0)
0x17af4  ldloc.s  4
0x17af6  callvirt instance void Microsoft.ReportingServices.Modeling.Hierarchy::set_Filter(class Microsoft.ReportingServices.Modeling.Expression value)
0x17afb  br.s     loc_17B39
0x17afd  ldarg.1
0x17afe  callvirt instance class HierarchyCollection Microsoft.ReportingServices.Modeling.SemanticQuery::get_Hierarchies()
0x17b03  ldc.i4.0
0x17b04  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.Hierarchy>::get_Item(!!T0)
0x17b09  ldc.i4.s 0xD
0x17b0b  ldc.i4.2
0x17b0c  newarr   Microsoft.ReportingServices.Modeling.Expression
0x17b11  dup
0x17b12  ldc.i4.0
0x17b13  ldarg.1
0x17b14  callvirt instance class HierarchyCollection Microsoft.ReportingServices.Modeling.SemanticQuery::get_Hierarchies()
0x17b19  ldc.i4.0
0x17b1a  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.Hierarchy>::get_Item(!!T0)
0x17b1f  callvirt instance class Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.Modeling.Hierarchy::get_Filter()
0x17b24  stelem.ref
0x17b25  dup
0x17b26  ldc.i4.1
0x17b27  ldloc.s  4
0x17b29  stelem.ref
0x17b2a  newobj   instance void Microsoft.ReportingServices.Modeling.FunctionNode::.ctor(valuetype Microsoft.ReportingServices.Modeling.FunctionName functionName, class Microsoft.ReportingServices.Modeling.Expression[] arguments)
0x17b2f  newobj   instance void Microsoft.ReportingServices.Modeling.Expression::.ctor(class Microsoft.ReportingServices.Modeling.ExpressionNode node)
0x17b34  callvirt instance void Microsoft.ReportingServices.Modeling.Hierarchy::set_Filter(class Microsoft.ReportingServices.Modeling.Expression value)
0x17b39  ldarg.0
0x17b3a  ldfld    class Microsoft.ReportingServices.Modeling.SemanticQuery Microsoft.ReportingServices.Modeling.DrillthroughContext::m_sourceQuery
0x17b3f  callvirt instance class Microsoft.ReportingServices.Modeling.CustomPropertyCollection Microsoft.ReportingServices.Modeling.ExtensibleModelingObject::get_CustomProperties()
0x17b44  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class Microsoft.ReportingServices.Modeling.CheckedCollection`1<class Microsoft.ReportingServices.Modeling.CustomProperty>::GetEnumerator()
0x17b49  stloc.s  5
0x17b4b  br.s     loc_17B7C
0x17b4d  ldloca.s 5
0x17b4f  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Modeling.CustomProperty>::get_Current()
0x17b54  stloc.s  6
0x17b56  ldarg.1
0x17b57  callvirt instance class Microsoft.ReportingServices.Modeling.CustomPropertyCollection Microsoft.ReportingServices.Modeling.ExtensibleModelingObject::get_CustomProperties()
0x17b5c  ldloc.s  6
0x17b5e  callvirt instance valuetype Microsoft.ReportingServices.Modeling.QName Microsoft.ReportingServices.Modeling.CustomProperty::get_Name()
0x17b63  callvirt instance bool Microsoft.ReportingServices.Modeling.CustomPropertyCollection::Contains(valuetype Microsoft.ReportingServices.Modeling.QName name)
0x17b68  brtrue.s loc_17B7C
0x17b6a  ldarg.1
0x17b6b  callvirt instance class Microsoft.ReportingServices.Modeling.CustomPropertyCollection Microsoft.ReportingServices.Modeling.ExtensibleModelingObject::get_CustomProperties()
0x17b70  ldloc.s  6
0x17b72  callvirt instance class Microsoft.ReportingServices.Modeling.CustomProperty Microsoft.ReportingServices.Modeling.CustomProperty::Clone()
0x17b77  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.CustomProperty>::Add(var<u1>)
0x17b7c  ldloca.s 5
0x17b7e  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Modeling.CustomProperty>::MoveNext()
0x17b83  brtrue.s loc_17B4D
0x17b85  leave.s  loc_17B95
0x17b87  ldloca.s 5
0x17b89  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Modeling.CustomProperty>
0x17b8f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x17b94  endfinally
0x17b95  ret
```
