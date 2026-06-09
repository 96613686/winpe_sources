# Microsoft.ReportingServices.Modeling.FunctionInfo::CreateEvaluate

- ea: `0x20f10`
- end: `0x20f48`
- name: `Microsoft.ReportingServices.Modeling.FunctionInfo::CreateEvaluate`
- size: `56`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1f530`

## callees

- `0x97d0`
- `0x19c50`
- `0x20f10`
- `0x21040`

## string_xrefs

- `0x20f15`: `Unexpected FunctionName passed to CreateEvaluate`

## pseudocode

```c

```

## disassembly

```asm
0x20f10  ldarg.1
0x20f11  ldc.i4.s 0x3F
0x20f13  beq.s    loc_20F20
0x20f15  ldstr    aUnexpectedFunc_2// "Unexpected FunctionName passed to Creat"...
0x20f1a  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x20f1f  throw
0x20f20  ldarg.0
0x20f21  ldarg.1
0x20f22  ldc.i4.0
0x20f23  ldc.i4.0
0x20f24  ldarg.2
0x20f25  ldc.i4.1
0x20f26  ldc.i4.1
0x20f27  newobj   instance void Microsoft.ReportingServices.Modeling.ResultType::.ctor(valuetype Microsoft.ReportingServices.Modeling.DataType dataType, valuetype Microsoft.ReportingServices.Modeling.Cardinality cardinality, bool nullable)
0x20f2c  ldc.i4.1
0x20f2d  newarr   Microsoft.ReportingServices.Modeling.ResultType
0x20f32  dup
0x20f33  ldc.i4.0
0x20f34  ldarg.2
0x20f35  ldc.i4.1
0x20f36  ldc.i4.1
0x20f37  newobj   instance void Microsoft.ReportingServices.Modeling.ResultType::.ctor(valuetype Microsoft.ReportingServices.Modeling.DataType dataType, valuetype Microsoft.ReportingServices.Modeling.Cardinality cardinality, bool nullable)
0x20f3c  stelem   Microsoft.ReportingServices.Modeling.ResultType
0x20f41  ldc.i4.0
0x20f42  newobj   instance void Microsoft.ReportingServices.Modeling.FunctionInfo::.ctor(int32 id, valuetype Microsoft.ReportingServices.Modeling.FunctionName functionName, bool transitive, bool _static, valuetype Microsoft.ReportingServices.Modeling.ResultType returnType, valuetype Microsoft.ReportingServices.Modeling.ResultType[] arguments, int32 passthroughArgIndex)
0x20f47  ret
```
