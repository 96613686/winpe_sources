# ::<CrtImplementationDetails>.AtExitLock._handle

- ea: `0xa30`
- end: `0xa51`
- name: `::<CrtImplementationDetails>.AtExitLock._handle`
- size: `33`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0xa70`
- `0xac0`
- `0xae0`

## callees

- `0xa30`

## pseudocode

```c

```

## disassembly

```asm
0xa30  ldsfld   void* ?_lock@AtExitLock@<CrtImplementationDetails>@@$$Q0PEAXEA
0xa35  brfalse.s loc_A4F
0xa37  ldloca.s 0
0xa39  ldsfld   void* ?_lock@AtExitLock@<CrtImplementationDetails>@@$$Q0PEAXEA
0xa3e  call     instance void [mscorlib]System.IntPtr::.ctor(void*)
0xa43  ldloc.0
0xa44  call     valuetype [mscorlib]System.Runtime.InteropServices.GCHandle [mscorlib]System.Runtime.InteropServices.GCHandle::FromIntPtr(native int)
0xa49  box      [mscorlib]System.Runtime.InteropServices.GCHandle
0xa4e  ret
0xa4f  ldnull
0xa50  ret
```
