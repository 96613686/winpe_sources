# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VisualBasic.ObjectAccessEvaluator::EvaluateProperty

- ea: `0xcd0`
- end: `0xd08`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VisualBasic.ObjectAccessEvaluator::EvaluateProperty`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0xcd0`

## string_xrefs

- `0xcf0`: `Object Access Expression Evaluator: Syntax kind <{0}> is not supported yet.`

## pseudocode

```c

```

## disassembly

```asm
0xcd0  ldarg.3
0xcd1  stloc.1
0xcd2  ldloc.1
0xcd3  ldc.i4   0x28A
0xcd8  bne.un.s loc_CF0
0xcda  ldarg.1
0xcdb  call     object [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::GetObjectValue(object)
0xce0  ldarg.2
0xce1  ldc.i4.2
0xce2  ldc.i4.0
0xce3  newarr   [mscorlib]System.Object
0xce8  call     object [Microsoft.VisualBasic]Microsoft.VisualBasic.CompilerServices.Versioned::CallByName(object, string, valuetype [Microsoft.VisualBasic]Microsoft.VisualBasic.CallType, object[])
0xced  stloc.0
0xcee  br.s     loc_D06
0xcf0  ldstr    aObjectAccessEx// "Object Access Expression Evaluator: Syn"...
0xcf5  ldarg.3
0xcf6  box      [Microsoft.CodeAnalysis.VisualBasic]Microsoft.CodeAnalysis.VisualBasic.SyntaxKind
0xcfb  call     string [mscorlib]System.String::Format(string, object)
0xd00  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0xd05  throw
0xd06  ldloc.0
0xd07  ret
```
