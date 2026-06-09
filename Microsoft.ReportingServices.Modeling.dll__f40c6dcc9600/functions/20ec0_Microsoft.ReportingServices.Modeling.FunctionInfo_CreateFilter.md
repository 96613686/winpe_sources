# Microsoft.ReportingServices.Modeling.FunctionInfo::CreateFilter

- ea: `0x20ec0`
- end: `0x20f07`
- name: `Microsoft.ReportingServices.Modeling.FunctionInfo::CreateFilter`
- size: `71`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1f530`

## callees

- `0x97d0`
- `0x19c50`
- `0x20ec0`
- `0x21040`

## string_xrefs

- `0x20ec5`: `Unexpected FunctionName passed to CreateFilter`

## pseudocode

```c

```

## disassembly

```asm
0x20ec0  ldarg.1
0x20ec1  ldc.i4.s 0x3E
0x20ec3  beq.s    loc_20ED0
0x20ec5  ldstr    aUnexpectedFunc_1// "Unexpected FunctionName passed to Creat"...
0x20eca  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x20ecf  throw
0x20ed0  ldarg.0
0x20ed1  ldarg.1
0x20ed2  ldc.i4.0
0x20ed3  ldc.i4.0
0x20ed4  ldarg.2
0x20ed5  ldc.i4.1
0x20ed6  ldc.i4.1
0x20ed7  newobj   instance void Microsoft.ReportingServices.Modeling.ResultType::.ctor(valuetype Microsoft.ReportingServices.Modeling.DataType dataType, valuetype Microsoft.ReportingServices.Modeling.Cardinality cardinality, bool nullable)
0x20edc  ldc.i4.2
0x20edd  newarr   Microsoft.ReportingServices.Modeling.ResultType
0x20ee2  dup
0x20ee3  ldc.i4.0
0x20ee4  ldarg.2
0x20ee5  ldc.i4.1
0x20ee6  ldc.i4.1
0x20ee7  newobj   instance void Microsoft.ReportingServices.Modeling.ResultType::.ctor(valuetype Microsoft.ReportingServices.Modeling.DataType dataType, valuetype Microsoft.ReportingServices.Modeling.Cardinality cardinality, bool nullable)
0x20eec  stelem   Microsoft.ReportingServices.Modeling.ResultType
0x20ef1  dup
0x20ef2  ldc.i4.1
0x20ef3  ldc.i4.4
0x20ef4  ldc.i4.0
0x20ef5  ldc.i4.1
0x20ef6  newobj   instance void Microsoft.ReportingServices.Modeling.ResultType::.ctor(valuetype Microsoft.ReportingServices.Modeling.DataType dataType, valuetype Microsoft.ReportingServices.Modeling.Cardinality cardinality, bool nullable)
0x20efb  stelem   Microsoft.ReportingServices.Modeling.ResultType
0x20f00  ldc.i4.0
0x20f01  newobj   instance void Microsoft.ReportingServices.Modeling.FunctionInfo::.ctor(int32 id, valuetype Microsoft.ReportingServices.Modeling.FunctionName functionName, bool transitive, bool _static, valuetype Microsoft.ReportingServices.Modeling.ResultType returnType, valuetype Microsoft.ReportingServices.Modeling.ResultType[] arguments, int32 passthroughArgIndex)
0x20f06  ret
```
