# <get_AllSupportedTypes>d__22::.ctor

- ea: `0x20a0`
- end: `0x20b9`
- name: `<get_AllSupportedTypes>d__22::.ctor`
- size: `25`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0xa60`
- `0x2200`

## pseudocode

```c

```

## disassembly

```asm
0x20a0  ldarg.0
0x20a1  call     instance void [mscorlib]System.Object::.ctor()
0x20a6  ldarg.0
0x20a7  ldarg.1
0x20a8  stfld    int32 <get_AllSupportedTypes>d__22::<>1__state
0x20ad  ldarg.0
0x20ae  call     int32 [mscorlib]System.Environment::get_CurrentManagedThreadId()
0x20b3  stfld    int32 <get_AllSupportedTypes>d__22::<>l__initialThreadId
0x20b8  ret
```
