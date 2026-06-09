# <WalkNIFiles>d__8::.ctor

- ea: `0x4940`
- end: `0x4959`
- name: `<WalkNIFiles>d__8::.ctor`
- size: `25`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x3fd0`
- `0x4d20`

## pseudocode

```c

```

## disassembly

```asm
0x4940  ldarg.0
0x4941  call     instance void [mscorlib]System.Object::.ctor()
0x4946  ldarg.0
0x4947  ldarg.1
0x4948  stfld    int32 <WalkNIFiles>d__8::<>1__state
0x494d  ldarg.0
0x494e  call     int32 [mscorlib]System.Environment::get_CurrentManagedThreadId()
0x4953  stfld    int32 <WalkNIFiles>d__8::<>l__initialThreadId
0x4958  ret
```
