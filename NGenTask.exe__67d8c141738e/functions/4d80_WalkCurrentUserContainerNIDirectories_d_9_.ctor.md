# <WalkCurrentUserContainerNIDirectories>d__9::.ctor

- ea: `0x4d80`
- end: `0x4d99`
- name: `<WalkCurrentUserContainerNIDirectories>d__9::.ctor`
- size: `25`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x3fe0`
- `0x4f40`

## pseudocode

```c

```

## disassembly

```asm
0x4d80  ldarg.0
0x4d81  call     instance void [mscorlib]System.Object::.ctor()
0x4d86  ldarg.0
0x4d87  ldarg.1
0x4d88  stfld    int32 <WalkCurrentUserContainerNIDirectories>d__9::<>1__state
0x4d8d  ldarg.0
0x4d8e  call     int32 [mscorlib]System.Environment::get_CurrentManagedThreadId()
0x4d93  stfld    int32 <WalkCurrentUserContainerNIDirectories>d__9::<>l__initialThreadId
0x4d98  ret
```
