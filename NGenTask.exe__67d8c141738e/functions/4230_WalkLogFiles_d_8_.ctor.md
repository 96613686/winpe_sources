# <WalkLogFiles>d__8::.ctor

- ea: `0x4230`
- end: `0x4249`
- name: `<WalkLogFiles>d__8::.ctor`
- size: `25`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x3f50`
- `0x4540`

## pseudocode

```c

```

## disassembly

```asm
0x4230  ldarg.0
0x4231  call     instance void [mscorlib]System.Object::.ctor()
0x4236  ldarg.0
0x4237  ldarg.1
0x4238  stfld    int32 <WalkLogFiles>d__8::<>1__state
0x423d  ldarg.0
0x423e  call     int32 [mscorlib]System.Environment::get_CurrentManagedThreadId()
0x4243  stfld    int32 <WalkLogFiles>d__8::<>l__initialThreadId
0x4248  ret
```
