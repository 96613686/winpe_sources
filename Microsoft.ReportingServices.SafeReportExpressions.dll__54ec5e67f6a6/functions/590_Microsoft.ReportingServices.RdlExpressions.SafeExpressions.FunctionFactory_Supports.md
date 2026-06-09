# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::Supports

- ea: `0x590`
- end: `0x59d`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::Supports`
- size: `13`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x11b0`
- `0x2da0`

## pseudocode

```c

```

## disassembly

```asm
0x590  ldarg.0
0x591  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IFunction> Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::_functions
0x596  ldarg.1
0x597  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IFunction>::ContainsKey(var<u1>)
0x59c  ret
```
