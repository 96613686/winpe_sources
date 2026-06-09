# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::.ctor

- ea: `0x550`
- end: `0x580`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::.ctor`
- size: `48`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1030`
- `0x2870`

## callees

- `0x5d0`
- `0x770`
- `0x7b0`
- `0x810`

## pseudocode

```c

```

## disassembly

```asm
0x550  ldarg.0
0x551  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x556  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IFunction>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x55b  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IFunction> Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::_functions
0x560  ldarg.0
0x561  call     instance void [mscorlib]System.Object::.ctor()
0x566  ldarg.0
0x567  ldarg.1
0x568  call     void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.BuiltInFunctions::Add(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory factory, class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ISafeExpressionsReportContext safeExpressionsReportContext)
0x56d  ldarg.0
0x56e  call     void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExecutionFlowFunctions::Add(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory factory)
0x573  ldarg.0
0x574  call     void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.StringFunctions::Add(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory factory)
0x579  ldarg.0
0x57a  call     void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.InspectionFunctions::Add(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory factory)
0x57f  ret
```
