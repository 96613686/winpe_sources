# ::<CrtImplementationDetails>.AtExitLock.AddRef

- ea: `0xc70`
- end: `0xc94`
- name: `::<CrtImplementationDetails>.AtExitLock.AddRef`
- size: `36`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0xd20`

## callees

- `0xbc0`
- `0xc60`
- `0xc70`

## pseudocode

```c

```

## disassembly

```asm
0xc70  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) bool <CrtImplementationDetails>.AtExitLock.IsInitialized()
0xc75  brtrue.s loc_C87
0xc77  newobj   instance void [mscorlib]System.Object::.ctor()
0xc7c  call     void <CrtImplementationDetails>.AtExitLock._lock_Construct(object value)
0xc81  ldc.i4.0
0xc82  stsfld   int32 ?_ref_count@AtExitLock@<CrtImplementationDetails>@@$$Q0HA
0xc87  ldsfld   int32 ?_ref_count@AtExitLock@<CrtImplementationDetails>@@$$Q0HA
0xc8c  ldc.i4.1
0xc8d  add
0xc8e  stsfld   int32 ?_ref_count@AtExitLock@<CrtImplementationDetails>@@$$Q0HA
0xc93  ret
```
