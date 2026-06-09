# PathNode::MergePath

- ea: `0x37940`
- end: `0x379d2`
- name: `PathNode::MergePath`
- size: `146`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x22080`
- `0x37900`
- `0x37940`

## callees

- `0x97d0`
- `0x1de50`
- `0x37900`
- `0x37940`

## string_xrefs

- `0x3796c`: `path is out of range.`

## pseudocode

```c

```

## disassembly

```asm
0x37940  ldarg.2
0x37941  ldc.i4.0
0x37942  blt.s    loc_3794D
0x37944  ldarg.2
0x37945  ldarg.1
0x37946  callvirt instance int32 Microsoft.ReportingServices.Modeling.ExpressionPath::get_Length()
0x3794b  blt.s    loc_37958
0x3794d  ldstr    aItemindexIsOut// "itemIndex is out of range."
0x37952  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x37957  throw
0x37958  ldarg.0
0x37959  ldfld    class Microsoft.ReportingServices.Modeling.PathItem PathNode::m_pathItem
0x3795e  ldarg.1
0x3795f  ldarg.2
0x37960  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.PathItem>::get_Item(!!T0)
0x37965  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x3796a  brtrue.s loc_37977
0x3796c  ldstr    aPathIsOutOfRan// "path is out of range."
0x37971  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x37976  throw
0x37977  ldarg.2
0x37978  ldc.i4.1
0x37979  add
0x3797a  starg.s  2
0x3797c  ldarg.2
0x3797d  ldarg.1
0x3797e  callvirt instance int32 Microsoft.ReportingServices.Modeling.ExpressionPath::get_Length()
0x37983  bge.s    loc_379D1
0x37985  ldarg.0
0x37986  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.ReportingServices.Modeling.PathItem, class PathNode> PathNode::m_children
0x3798b  brtrue.s loc_37998
0x3798d  ldarg.0
0x3798e  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.ReportingServices.Modeling.PathItem, class PathNode>::.ctor()
0x37993  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.ReportingServices.Modeling.PathItem, class PathNode> PathNode::m_children
0x37998  ldarg.0
0x37999  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.ReportingServices.Modeling.PathItem, class PathNode> PathNode::m_children
0x3799e  ldarg.1
0x3799f  ldarg.2
0x379a0  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.ReportingServices.Modeling.PathItem>::get_Item(!!T0)
0x379a5  ldloca.s 0
0x379a7  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.ReportingServices.Modeling.PathItem, class PathNode>::TryGetValue(var<u1>, !!T0)
0x379ac  brfalse.s loc_379B7
0x379ae  ldloc.0
0x379af  ldarg.1
0x379b0  ldarg.2
0x379b1  callvirt instance void PathNode::MergePath(class Microsoft.ReportingServices.Modeling.ExpressionPath path, int32 itemIndex)
0x379b6  ret
0x379b7  ldarg.1
0x379b8  ldarg.2
0x379b9  newobj   instance void PathNode::.ctor(class Microsoft.ReportingServices.Modeling.ExpressionPath path, int32 itemIndex)
0x379be  stloc.0
0x379bf  ldarg.0
0x379c0  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.ReportingServices.Modeling.PathItem, class PathNode> PathNode::m_children
0x379c5  ldloc.0
0x379c6  ldfld    class Microsoft.ReportingServices.Modeling.PathItem PathNode::m_pathItem
0x379cb  ldloc.0
0x379cc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.ReportingServices.Modeling.PathItem, class PathNode>::Add(var<u1>, !!T0)
0x379d1  ret
```
