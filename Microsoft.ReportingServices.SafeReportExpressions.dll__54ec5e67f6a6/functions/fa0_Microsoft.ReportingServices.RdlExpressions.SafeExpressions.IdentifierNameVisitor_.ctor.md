# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IdentifierNameVisitor::.ctor

- ea: `0xfa0`
- end: `0xfbd`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IdentifierNameVisitor::.ctor`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x390`

## callees

- `0x290`
- `0xd90`
- `0x1690`

## pseudocode

```c

```

## disassembly

```asm
0xfa0  ldarg.0
0xfa1  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VisitorBase::.ctor()
0xfa6  ldarg.0
0xfa7  call     class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IVisualBasicConstantEvaluator Microsoft.ReportingServices.RdlExpressions.SafeExpressions.EvaluatorFactory::CreateVbConstantIdentifierEvaluator()
0xfac  stfld    class [Microsoft.ReportingServices.SafeReportExpressions.Interfaces]Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Interfaces.IVisualBasicConstantEvaluator Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IdentifierNameVisitor::_vbConstantIdentifierEvaluator
0xfb1  ldarg.0
0xfb2  newobj   instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VisualBasicConstantIdentifier::.ctor()
0xfb7  stfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VisualBasicConstantIdentifier Microsoft.ReportingServices.RdlExpressions.SafeExpressions.IdentifierNameVisitor::_vbConstantIdentifier
0xfbc  ret
```
