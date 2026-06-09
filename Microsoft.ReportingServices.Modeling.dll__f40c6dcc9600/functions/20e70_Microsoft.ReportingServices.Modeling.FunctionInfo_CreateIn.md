# Microsoft.ReportingServices.Modeling.FunctionInfo::CreateIn

- ea: `0x20e70`
- end: `0x20eb6`
- name: `Microsoft.ReportingServices.Modeling.FunctionInfo::CreateIn`
- size: `70`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1f530`

## callees

- `0x97d0`
- `0x19c50`
- `0x20e70`
- `0x20f50`

## string_xrefs

- `0x20e75`: `Unexpected FunctionName passed to CreateIn`

## pseudocode

```c

```

## disassembly

```asm
0x20e70  ldarg.1
0x20e71  ldc.i4.s 0x3D
0x20e73  beq.s    loc_20E80
0x20e75  ldstr    aUnexpectedFunc_0// "Unexpected FunctionName passed to Creat"...
0x20e7a  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x20e7f  throw
0x20e80  ldarg.0
0x20e81  ldarg.1
0x20e82  ldc.i4.0
0x20e83  ldc.i4.0
0x20e84  ldc.i4.4
0x20e85  ldc.i4.0
0x20e86  ldc.i4.0
0x20e87  newobj   instance void Microsoft.ReportingServices.Modeling.ResultType::.ctor(valuetype Microsoft.ReportingServices.Modeling.DataType dataType, valuetype Microsoft.ReportingServices.Modeling.Cardinality cardinality, bool nullable)
0x20e8c  ldc.i4.2
0x20e8d  newarr   Microsoft.ReportingServices.Modeling.ResultType
0x20e92  dup
0x20e93  ldc.i4.0
0x20e94  ldarg.2
0x20e95  ldc.i4.0
0x20e96  ldc.i4.1
0x20e97  newobj   instance void Microsoft.ReportingServices.Modeling.ResultType::.ctor(valuetype Microsoft.ReportingServices.Modeling.DataType dataType, valuetype Microsoft.ReportingServices.Modeling.Cardinality cardinality, bool nullable)
0x20e9c  stelem   Microsoft.ReportingServices.Modeling.ResultType
0x20ea1  dup
0x20ea2  ldc.i4.1
0x20ea3  ldarg.2
0x20ea4  ldc.i4.1
0x20ea5  ldc.i4.1
0x20ea6  newobj   instance void Microsoft.ReportingServices.Modeling.ResultType::.ctor(valuetype Microsoft.ReportingServices.Modeling.DataType dataType, valuetype Microsoft.ReportingServices.Modeling.Cardinality cardinality, bool nullable)
0x20eab  stelem   Microsoft.ReportingServices.Modeling.ResultType
0x20eb0  newobj   instance void Microsoft.ReportingServices.Modeling.FunctionInfo::.ctor(int32 id, valuetype Microsoft.ReportingServices.Modeling.FunctionName functionName, bool transitive, bool _static, valuetype Microsoft.ReportingServices.Modeling.ResultType returnType, valuetype Microsoft.ReportingServices.Modeling.ResultType[] arguments)
0x20eb5  ret
```
