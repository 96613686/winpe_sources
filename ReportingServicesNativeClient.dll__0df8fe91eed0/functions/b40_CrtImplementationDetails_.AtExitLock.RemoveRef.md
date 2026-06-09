# ::<CrtImplementationDetails>.AtExitLock.RemoveRef

- ea: `0xb40`
- end: `0xb59`
- name: `::<CrtImplementationDetails>.AtExitLock.RemoveRef`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0xb70`

## callees

- `0xae0`
- `0xb40`

## pseudocode

```c

```

## disassembly

```asm
0xb40  ldsfld   int32 ?_ref_count@AtExitLock@<CrtImplementationDetails>@@$$Q0HA
0xb45  ldc.i4.m1
0xb46  add
0xb47  stsfld   int32 ?_ref_count@AtExitLock@<CrtImplementationDetails>@@$$Q0HA
0xb4c  ldsfld   int32 ?_ref_count@AtExitLock@<CrtImplementationDetails>@@$$Q0HA
0xb51  brtrue.s loc_B58
0xb53  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void <CrtImplementationDetails>.AtExitLock._lock_Destruct()
0xb58  ret
```
