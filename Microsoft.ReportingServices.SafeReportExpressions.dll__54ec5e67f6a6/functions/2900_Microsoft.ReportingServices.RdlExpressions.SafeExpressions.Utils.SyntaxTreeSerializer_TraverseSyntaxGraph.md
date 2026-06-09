# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::TraverseSyntaxGraph

- ea: `0x2900`
- end: `0x2a02`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::TraverseSyntaxGraph`
- size: `258`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x28b0`
- `0x2900`

## callees

- `0x2900`
- `0x2a10`

## pseudocode

```c

```

## disassembly

```asm
0x2900  ldarg.3
0x2901  ldarg.3
0x2902  ldind.i4
0x2903  ldc.i4.1
0x2904  add
0x2905  stind.i4
0x2906  ldarg.3
0x2907  ldind.i4
0x2908  ldarg.0
0x2909  ldfld    int32 Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::_maxAllowedNodeCount
0x290e  ble.s    loc_292B
0x2910  ldstr    aSyntaxTreeNode// "Syntax tree node count has crossed the "...
0x2915  ldarg.0
0x2916  ldfld    int32 Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::_maxAllowedNodeCount
0x291b  box      [mscorlib]System.Int32
0x2920  call     string [mscorlib]System.String::Format(string, object)
0x2925  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x292a  throw
0x292b  ldarg.1
0x292c  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WriteStartObject()
0x2931  ldarg.2
0x2932  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2937  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x293c  stloc.0
0x293d  ldarg.2
0x293e  call     valuetype [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.SyntaxKind [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.VisualBasicExtensions::Kind(class [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxNode)
0x2943  stloc.3
0x2944  ldloca.s 3
0x2946  constrained. [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.SyntaxKind
0x294c  callvirt instance string [mscorlib]System.Object::ToString()
0x2951  stloc.1
0x2952  ldarg.1
0x2953  ldstr    aSyntax// "Syntax"
0x2958  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WritePropertyName(string)
0x295d  ldarg.1
0x295e  ldloc.0
0x295f  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WriteValue(string)
0x2964  ldloc.0
0x2965  ldloc.1
0x2966  callvirt instance bool [mscorlib]System.String::StartsWith(string)
0x296b  brtrue.s loc_297F
0x296d  ldarg.1
0x296e  ldstr    aKind// "Kind"
0x2973  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WritePropertyName(string)
0x2978  ldarg.1
0x2979  ldloc.1
0x297a  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WriteValue(string)
0x297f  ldarg.2
0x2980  callvirt instance bool [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxNode::get_ContainsDiagnostics()
0x2985  brfalse.s loc_2999
0x2987  ldarg.1
0x2988  ldstr    aContainsdiagno// "ContainsDiagnostics"
0x298d  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WritePropertyName(string)
0x2992  ldarg.1
0x2993  ldc.i4.1
0x2994  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WriteValue(bool)
0x2999  ldarg.0
0x299a  ldarg.1
0x299b  ldarg.2
0x299c  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::WriteNodeSpecificProperties(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, class [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxNode syntaxNode)
0x29a1  ldarg.2
0x29a2  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxNode> [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxNode::ChildNodes()
0x29a7  stloc.2
0x29a8  ldloc.2
0x29a9  call     T0x2B00001E
0x29ae  brfalse.s loc_29FB
0x29b0  ldarg.1
0x29b1  ldstr    aChildren// "Children"
0x29b6  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WritePropertyName(string)
0x29bb  ldarg.1
0x29bc  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WriteStartArray()
0x29c1  ldloc.2
0x29c2  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxNode>::GetEnumerator()
0x29c7  stloc.s  4
0x29c9  br.s     loc_29DE
0x29cb  ldloc.s  4
0x29cd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxNode>::get_Current()
0x29d2  stloc.s  5
0x29d4  ldarg.0
0x29d5  ldarg.1
0x29d6  ldloc.s  5
0x29d8  ldarg.3
0x29d9  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::TraverseSyntaxGraph(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, class [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxNode syntaxNode, int32& nodeCount)
0x29de  ldloc.s  4
0x29e0  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x29e5  brtrue.s loc_29CB
0x29e7  leave.s  loc_29F5
0x29e9  ldloc.s  4
0x29eb  brfalse.s loc_29F4
0x29ed  ldloc.s  4
0x29ef  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x29f4  endfinally
0x29f5  ldarg.1
0x29f6  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WriteEndArray()
0x29fb  ldarg.1
0x29fc  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WriteEndObject()
0x2a01  ret
```
