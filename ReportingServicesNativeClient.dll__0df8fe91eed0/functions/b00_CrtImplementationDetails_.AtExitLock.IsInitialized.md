# ::<CrtImplementationDetails>.AtExitLock.IsInitialized

- ea: `0xb00`
- end: `0xb0e`
- name: `::<CrtImplementationDetails>.AtExitLock.IsInitialized`
- size: `14`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0xb10`
- `0xb60`

## callees

- `0xac0`
- `0xb00`

## pseudocode

```c

```

## disassembly

```asm
0xb00  call     object <CrtImplementationDetails>.AtExitLock._lock_Get()
0xb05  ldnull
0xb06  bne.un.s loc_B0B
0xb08  ldc.i4.0
0xb09  br.s     loc_B0C
0xb0b  ldc.i4.1
0xb0c  conv.u1
0xb0d  ret
```
