# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::IsKnownIdentifierName

- ea: `0x2da0`
- end: `0x2dcb`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::IsKnownIdentifierName`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x2ad0`

## callees

- `0x590`
- `0xb80`
- `0xd70`
- `0x2da0`

## pseudocode

```c

```

## disassembly

```asm
0x2da0  ldarg.0
0x2da1  ldfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VisualBasicConstantIdentifier Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::_vbConstantIdentifier
0x2da6  ldarg.1
0x2da7  callvirt instance bool Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VisualBasicConstantIdentifier::IsIdentifierVisualBasicConstant(string identifierName)
0x2dac  brtrue.s loc_2DC9
0x2dae  ldarg.0
0x2daf  ldfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::_functionFactory
0x2db4  ldarg.1
0x2db5  callvirt instance bool Microsoft.ReportingServices.RdlExpressions.SafeExpressions.FunctionFactory::Supports(string functionName)
0x2dba  brtrue.s loc_2DC9
0x2dbc  ldarg.0
0x2dbd  ldfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ReportCollectionAccessor Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SyntaxTreeSerializer::_reportCollectionAccessor
0x2dc2  ldarg.1
0x2dc3  callvirt instance bool Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ReportCollectionAccessor::IsValidCollectionName(string collectionName)
0x2dc8  ret
0x2dc9  ldc.i4.1
0x2dca  ret
```
