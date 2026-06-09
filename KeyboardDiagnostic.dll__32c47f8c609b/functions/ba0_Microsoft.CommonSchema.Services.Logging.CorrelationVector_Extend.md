# Microsoft.CommonSchema.Services.Logging.CorrelationVector::Extend

- ea: `0xba0`
- end: `0xbbe`
- name: `Microsoft.CommonSchema.Services.Logging.CorrelationVector::Extend`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0xb40`
- `0xba0`
- `0xbc0`
- `0xc70`
- `0xd20`

## pseudocode

```c

```

## disassembly

```asm
0xba0  ldarg.0
0xba1  call     valuetype CorrelationVectorVersion Microsoft.CommonSchema.Services.Logging.CorrelationVector::InferVersion(string correlationVector)
0xba6  stloc.0
0xba7  call     bool Microsoft.CommonSchema.Services.Logging.CorrelationVector::get_ValidateCorrelationVectorDuringCreation()
0xbac  brfalse.s loc_BB5
0xbae  ldarg.0
0xbaf  ldloc.0
0xbb0  call     void Microsoft.CommonSchema.Services.Logging.CorrelationVector::ValidateCorrelationVector(string correlationVector, valuetype CorrelationVectorVersion version)
0xbb5  ldarg.0
0xbb6  ldc.i4.0
0xbb7  ldloc.0
0xbb8  newobj   instance void Microsoft.CommonSchema.Services.Logging.CorrelationVector::.ctor(string vectorBase, int32 lastExtension, valuetype CorrelationVectorVersion version)
0xbbd  ret
```
