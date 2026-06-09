# <WalkLogDirectories>d__5::.ctor

- ea: `0x4100`
- end: `0x4119`
- name: `<WalkLogDirectories>d__5::.ctor`
- size: `25`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x3f20`
- `0x41c0`

## pseudocode

```c

```

## disassembly

```asm
0x4100  ldarg.0
0x4101  call     instance void [mscorlib]System.Object::.ctor()
0x4106  ldarg.0
0x4107  ldarg.1
0x4108  stfld    int32 <WalkLogDirectories>d__5::<>1__state
0x410d  ldarg.0
0x410e  call     int32 [mscorlib]System.Environment::get_CurrentManagedThreadId()
0x4113  stfld    int32 <WalkLogDirectories>d__5::<>l__initialThreadId
0x4118  ret
```
