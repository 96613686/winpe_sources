# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Function::Evaluate

- ea: `0x520`
- end: `0x538`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Function::Evaluate`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x930`

## pseudocode

```c

```

## disassembly

```asm
0x520  ldarg.0
0x521  ldfld    class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IFunctionEvaluator Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Function::_evaluator
0x526  ldarg.0
0x527  ldfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IArgumentValidator Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Function::_argumentValidator
0x52c  callvirt instance string Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IArgumentValidator::get_FunctionName()
0x531  ldarg.1
0x532  callvirt instance object [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IFunctionEvaluator::Evaluate(string, class [mscorlib]System.Collections.Generic.List`1<object>)
0x537  ret
```
