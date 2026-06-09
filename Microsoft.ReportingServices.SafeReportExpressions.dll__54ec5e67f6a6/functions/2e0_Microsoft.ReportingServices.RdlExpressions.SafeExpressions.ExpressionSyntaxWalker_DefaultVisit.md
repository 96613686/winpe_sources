# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionSyntaxWalker::DefaultVisit

- ea: `0x2e0`
- end: `0x300`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionSyntaxWalker::DefaultVisit`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x2e0  ldstr    aSyntaxnode// "SyntaxNode <"
0x2e5  ldarg.1
0x2e6  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2eb  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x2f0  ldstr    aIsNotSupported// "> is not supported yet."
0x2f5  call     string [mscorlib]System.String::Concat(string, string, string)
0x2fa  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x2ff  throw
```
