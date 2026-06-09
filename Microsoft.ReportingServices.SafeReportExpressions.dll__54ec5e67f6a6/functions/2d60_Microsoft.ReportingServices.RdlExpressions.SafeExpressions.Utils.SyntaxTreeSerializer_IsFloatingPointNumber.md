# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::IsFloatingPointNumber

- ea: `0x2d60`
- end: `0x2d97`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::IsFloatingPointNumber`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2b30`

## callees

- `0x2d60`

## pseudocode

```c

```

## disassembly

```asm
0x2d60  ldarg.1
0x2d61  ldtoken  [mscorlib]System.Single
0x2d66  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2d6b  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2d70  brtrue.s loc_2D95
0x2d72  ldarg.1
0x2d73  ldtoken  [mscorlib]System.Double
0x2d78  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2d7d  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2d82  brtrue.s loc_2D95
0x2d84  ldarg.1
0x2d85  ldtoken  [mscorlib]System.Decimal
0x2d8a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2d8f  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2d94  ret
0x2d95  ldc.i4.1
0x2d96  ret
```
