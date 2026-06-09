# <GetAdvertisedPackageInfo>d__4::.ctor

- ea: `0x6310`
- end: `0x6329`
- name: `<GetAdvertisedPackageInfo>d__4::.ctor`
- size: `25`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x34e0`
- `0x6510`

## pseudocode

```c

```

## disassembly

```asm
0x6310  ldarg.0
0x6311  call     instance void [mscorlib]System.Object::.ctor()
0x6316  ldarg.0
0x6317  ldarg.1
0x6318  stfld    int32 <GetAdvertisedPackageInfo>d__4::<>1__state
0x631d  ldarg.0
0x631e  call     int32 [mscorlib]System.Environment::get_CurrentManagedThreadId()
0x6323  stfld    int32 <GetAdvertisedPackageInfo>d__4::<>l__initialThreadId
0x6328  ret
```
