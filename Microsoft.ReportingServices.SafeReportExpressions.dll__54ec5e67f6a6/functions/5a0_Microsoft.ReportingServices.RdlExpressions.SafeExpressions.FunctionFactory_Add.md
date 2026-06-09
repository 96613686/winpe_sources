# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::Add

- ea: `0x5a0`
- end: `0x5bb`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::Add`
- size: `27`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x5d0`
- `0x770`
- `0x7b0`
- `0x810`

## callees

- `0x4f0`
- `0x930`

## pseudocode

```c

```

## disassembly

```asm
0x5a0  ldarg.1
0x5a1  ldarg.2
0x5a2  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Function::.ctor(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IArgumentValidator argumentValidator, class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IFunctionEvaluator evaluator)
0x5a7  stloc.0
0x5a8  ldarg.0
0x5a9  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IFunction> Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::_functions
0x5ae  ldarg.1
0x5af  callvirt instance string Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IArgumentValidator::get_FunctionName()
0x5b4  ldloc.0
0x5b5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IFunction>::Add(var<u1>, !!T0)
0x5ba  ret
```
