# Microsoft.ReportingServices.Modeling.FunctionInfo::CreateSwitch

- ea: `0x20e20`
- end: `0x20e67`
- name: `Microsoft.ReportingServices.Modeling.FunctionInfo::CreateSwitch`
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
- `0x20e20`
- `0x21020`

## string_xrefs

- `0x20e25`: `Unexpected FunctionName passed to CreateSwitch`

## pseudocode

```c

```

## disassembly

```asm
0x20e20  ldarg.1
0x20e21  ldc.i4.s 0x3C
0x20e23  beq.s    loc_20E30
0x20e25  ldstr    aUnexpectedFunc// "Unexpected FunctionName passed to Creat"...
0x20e2a  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x20e2f  throw
0x20e30  ldarg.0
0x20e31  ldarg.1
0x20e32  ldc.i4.0
0x20e33  ldc.i4.0
0x20e34  ldarg.2
0x20e35  ldc.i4.0
0x20e36  ldc.i4.1
0x20e37  newobj   instance void Microsoft.ReportingServices.Modeling.ResultType::.ctor(valuetype Microsoft.ReportingServices.Modeling.DataType dataType, valuetype Microsoft.ReportingServices.Modeling.Cardinality cardinality, bool nullable)
0x20e3c  ldc.i4.2
0x20e3d  newarr   Microsoft.ReportingServices.Modeling.ResultType
0x20e42  dup
0x20e43  ldc.i4.0
0x20e44  ldc.i4.4
0x20e45  ldc.i4.0
0x20e46  ldc.i4.1
0x20e47  newobj   instance void Microsoft.ReportingServices.Modeling.ResultType::.ctor(valuetype Microsoft.ReportingServices.Modeling.DataType dataType, valuetype Microsoft.ReportingServices.Modeling.Cardinality cardinality, bool nullable)
0x20e4c  stelem   Microsoft.ReportingServices.Modeling.ResultType
0x20e51  dup
0x20e52  ldc.i4.1
0x20e53  ldarg.2
0x20e54  ldc.i4.0
0x20e55  ldc.i4.1
0x20e56  newobj   instance void Microsoft.ReportingServices.Modeling.ResultType::.ctor(valuetype Microsoft.ReportingServices.Modeling.DataType dataType, valuetype Microsoft.ReportingServices.Modeling.Cardinality cardinality, bool nullable)
0x20e5b  stelem   Microsoft.ReportingServices.Modeling.ResultType
0x20e60  ldc.i4.1
0x20e61  newobj   instance void Microsoft.ReportingServices.Modeling.FunctionInfo::.ctor(int32 id, valuetype Microsoft.ReportingServices.Modeling.FunctionName functionName, bool transitive, bool _static, valuetype Microsoft.ReportingServices.Modeling.ResultType returnType, valuetype Microsoft.ReportingServices.Modeling.ResultType[] arguments, bool repeatingArguments)
0x20e66  ret
```
