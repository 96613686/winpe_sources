# ::<CrtImplementationDetails>.AtExitLock.RemoveRef

- ea: `0xca0`
- end: `0xcb9`
- name: `::<CrtImplementationDetails>.AtExitLock.RemoveRef`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0xd30`

## callees

- `0xc40`
- `0xca0`

## pseudocode

```c

```

## disassembly

```asm
0xca0  ldsfld   int32 ?_ref_count@AtExitLock@<CrtImplementationDetails>@@$$Q0HA
0xca5  ldc.i4.m1
0xca6  add
0xca7  stsfld   int32 ?_ref_count@AtExitLock@<CrtImplementationDetails>@@$$Q0HA
0xcac  ldsfld   int32 ?_ref_count@AtExitLock@<CrtImplementationDetails>@@$$Q0HA
0xcb1  brtrue.s loc_CB8
0xcb3  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void <CrtImplementationDetails>.AtExitLock._lock_Destruct()
0xcb8  ret
```
