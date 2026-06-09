# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::TryGet

- ea: `0x580`
- end: `0x58e`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::TryGet`
- size: `14`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x1160`

## pseudocode

```c

```

## disassembly

```asm
0x580  ldarg.0
0x581  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IFunction> Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::_functions
0x586  ldarg.1
0x587  ldarg.2
0x588  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IFunction>::TryGetValue(var<u1>, !!T0)
0x58d  ret
```
