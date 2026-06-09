# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::SerializeSyntaxTree

- ea: `0x28b0`
- end: `0x28f5`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::SerializeSyntaxTree`
- size: `69`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x28b0`
- `0x2900`

## pseudocode

```c

```

## disassembly

```asm
0x28b0  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor()
0x28b5  stloc.0
0x28b6  ldc.i4.0
0x28b7  stloc.1
0x28b8  ldloc.0
0x28b9  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.JsonTextWriter::.ctor(class [mscorlib]System.IO.TextWriter)
0x28be  stloc.2
0x28bf  ldloc.2
0x28c0  ldc.i4.0
0x28c1  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::set_Formatting(valuetype [Newtonsoft.Json]Newtonsoft.Json.Formatting)
0x28c6  ldarg.0
0x28c7  ldloc.2
0x28c8  ldarg.1
0x28c9  ldloca.s 3
0x28cb  initobj  [mscorlib]System.Threading.CancellationToken
0x28d1  ldloc.3
0x28d2  callvirt instance class [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxNode [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxTree::GetRoot(valuetype [mscorlib]System.Threading.CancellationToken)
0x28d7  ldloca.s 1
0x28d9  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::TraverseSyntaxGraph(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, class [Microsoft.CodeAnalysis]Microsoft.CodeAnalysis.SyntaxNode syntaxNode, int32& nodeCount)
0x28de  ldloc.0
0x28df  callvirt instance string [mscorlib]System.Object::ToString()
0x28e4  stloc.s  4
0x28e6  leave.s  loc_28F2
0x28e8  ldloc.2
0x28e9  brfalse.s loc_28F1
0x28eb  ldloc.2
0x28ec  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x28f1  endfinally
0x28f2  ldloc.s  4
0x28f4  ret
```
