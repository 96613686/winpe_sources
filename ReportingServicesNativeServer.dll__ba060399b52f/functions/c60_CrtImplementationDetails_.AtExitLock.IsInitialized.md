# ::<CrtImplementationDetails>.AtExitLock.IsInitialized

- ea: `0xc60`
- end: `0xc6e`
- name: `::<CrtImplementationDetails>.AtExitLock.IsInitialized`
- size: `14`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0xc70`
- `0xce0`
- `0xd00`
- `0xd20`

## callees

- `0xc20`
- `0xc60`

## pseudocode

```c

```

## disassembly

```asm
0xc60  call     object <CrtImplementationDetails>.AtExitLock._lock_Get()
0xc65  ldnull
0xc66  bne.un.s loc_C6B
0xc68  ldc.i4.0
0xc69  br.s     loc_C6C
0xc6b  ldc.i4.1
0xc6c  conv.u1
0xc6d  ret
```
