# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::.ctor

- ea: `0x2870`
- end: `0x28a1`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::.ctor`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x550`
- `0xb70`
- `0xd90`

## pseudocode

```c

```

## disassembly

```asm
0x2870  ldarg.0
0x2871  call     instance void [mscorlib]System.Object::.ctor()
0x2876  ldarg.0
0x2877  ldarg.1
0x2878  stfld    int32 Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::_maxAllowedNodeCount
0x287d  ldarg.0
0x287e  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VisualBasicConstantIdentifier::.ctor()
0x2883  stfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VisualBasicConstantIdentifier Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::_vbConstantIdentifier
0x2888  ldarg.0
0x2889  ldnull
0x288a  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ReportCollectionAccessor::.ctor(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ISafeExpressionsReportContext safeExpressionsReportContext)
0x288f  stfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ReportCollectionAccessor Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::_reportCollectionAccessor
0x2894  ldarg.0
0x2895  ldnull
0x2896  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::.ctor(class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ISafeExpressionsReportContext safeExpressionsReportContext)
0x289b  stfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::_functionFactory
0x28a0  ret
```
