# Microsoft.CommonSchema.Services.Logging.CorrelationVector::Set

- ea: `0xb60`
- end: `0xb9c`
- name: `Microsoft.CommonSchema.Services.Logging.CorrelationVector::Set`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0xb60`
- `0xbc0`
- `0xc70`
- `0xd20`

## pseudocode

```c

```

## disassembly

```asm
0xb60  ldarg.0
0xb61  call     valuetype CorrelationVectorVersion Microsoft.CommonSchema.Services.Logging.CorrelationVector::InferVersion(string correlationVector)
0xb66  stloc.0
0xb67  ldsfld   bool Microsoft.CommonSchema.Services.Logging.CorrelationVector::validateCorrelationVectorDuringCreation
0xb6c  brfalse.s loc_B75
0xb6e  ldarg.0
0xb6f  ldloc.0
0xb70  call     void Microsoft.CommonSchema.Services.Logging.CorrelationVector::ValidateCorrelationVector(string correlationVector, valuetype CorrelationVectorVersion version)
0xb75  ldarg.0
0xb76  ldc.i4.s 0x2E
0xb78  callvirt instance int32 [mscorlib]System.String::LastIndexOf(char)
0xb7d  stloc.1
0xb7e  ldarg.0
0xb7f  ldloc.1
0xb80  ldc.i4.1
0xb81  add
0xb82  callvirt instance string [mscorlib]System.String::Substring(int32)
0xb87  call     int32 [mscorlib]System.Int32::Parse(string)
0xb8c  stloc.2
0xb8d  ldarg.0
0xb8e  ldloc.1
0xb8f  callvirt instance string [mscorlib]System.String::Remove(int32)
0xb94  ldloc.2
0xb95  ldloc.0
0xb96  newobj   instance void Microsoft.CommonSchema.Services.Logging.CorrelationVector::.ctor(string vectorBase, int32 lastExtension, valuetype CorrelationVectorVersion version)
0xb9b  ret
```
