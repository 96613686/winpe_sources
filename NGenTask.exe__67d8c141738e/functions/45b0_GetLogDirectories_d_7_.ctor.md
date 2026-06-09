# <GetLogDirectories>d__7::.ctor

- ea: `0x45b0`
- end: `0x45c9`
- name: `<GetLogDirectories>d__7::.ctor`
- size: `25`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x3fc0`
- `0x48d0`

## pseudocode

```c

```

## disassembly

```asm
0x45b0  ldarg.0
0x45b1  call     instance void [mscorlib]System.Object::.ctor()
0x45b6  ldarg.0
0x45b7  ldarg.1
0x45b8  stfld    int32 <GetLogDirectories>d__7::<>1__state
0x45bd  ldarg.0
0x45be  call     int32 [mscorlib]System.Environment::get_CurrentManagedThreadId()
0x45c3  stfld    int32 <GetLogDirectories>d__7::<>l__initialThreadId
0x45c8  ret
```
