# ::<CrtImplementationDetails>.AtExitLock.RemoveRef

- ea: `0x1cf0`
- end: `0x1d09`
- name: `::<CrtImplementationDetails>.AtExitLock.RemoveRef`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1d80`

## callees

- `0x1c90`
- `0x1cf0`

## pseudocode

```c

```

## disassembly

```asm
0x1cf0  ldsfld   int32 ?_ref_count@AtExitLock@<CrtImplementationDetails>@@$$Q0HA
0x1cf5  ldc.i4.m1
0x1cf6  add
0x1cf7  stsfld   int32 ?_ref_count@AtExitLock@<CrtImplementationDetails>@@$$Q0HA
0x1cfc  ldsfld   int32 ?_ref_count@AtExitLock@<CrtImplementationDetails>@@$$Q0HA
0x1d01  brtrue.s loc_1D08
0x1d03  call     void <CrtImplementationDetails>.AtExitLock._lock_Destruct()
0x1d08  ret
```
