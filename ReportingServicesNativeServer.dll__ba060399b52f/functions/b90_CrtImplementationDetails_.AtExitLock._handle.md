# ::<CrtImplementationDetails>.AtExitLock._handle

- ea: `0xb90`
- end: `0xbb1`
- name: `::<CrtImplementationDetails>.AtExitLock._handle`
- size: `33`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0xbd0`
- `0xc20`
- `0xc40`

## callees

- `0xb90`

## pseudocode

```c

```

## disassembly

```asm
0xb90  ldsfld   void* ?_lock@AtExitLock@<CrtImplementationDetails>@@$$Q0PEAXEA
0xb95  brfalse.s loc_BAF
0xb97  ldloca.s 0
0xb99  ldsfld   void* ?_lock@AtExitLock@<CrtImplementationDetails>@@$$Q0PEAXEA
0xb9e  call     instance void [mscorlib]System.IntPtr::.ctor(void*)
0xba3  ldloc.0
0xba4  call     valuetype [mscorlib]System.Runtime.InteropServices.GCHandle [mscorlib]System.Runtime.InteropServices.GCHandle::FromIntPtr(native int)
0xba9  box      [mscorlib]System.Runtime.InteropServices.GCHandle
0xbae  ret
0xbaf  ldnull
0xbb0  ret
```
