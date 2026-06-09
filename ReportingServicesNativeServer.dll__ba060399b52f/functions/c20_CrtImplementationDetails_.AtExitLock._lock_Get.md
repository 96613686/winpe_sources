# ::<CrtImplementationDetails>.AtExitLock._lock_Get

- ea: `0xc20`
- end: `0xc37`
- name: `::<CrtImplementationDetails>.AtExitLock._lock_Get`
- size: `23`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0xc60`
- `0xcc0`
- `0xcd0`

## callees

- `0xb90`
- `0xc20`

## pseudocode

```c

```

## disassembly

```asm
0xc20  call     modopt([mscorlib]System.Runtime.CompilerServices.IsBoxed) modopt([mscorlib]System.Runtime.InteropServices.GCHandle) class [mscorlib]System.ValueType <CrtImplementationDetails>.AtExitLock._handle()
0xc25  stloc.0
0xc26  ldloc.0
0xc27  brfalse.s loc_C35
0xc29  ldloc.0
0xc2a  unbox    [mscorlib]System.Runtime.InteropServices.GCHandle
0xc2f  call     instance object [mscorlib]System.Runtime.InteropServices.GCHandle::get_Target()
0xc34  ret
0xc35  ldnull
0xc36  ret
```
