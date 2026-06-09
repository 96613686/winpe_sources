# System.Printing.PrintProcessor::VerifyAccess

- ea: `0xb0b0`
- end: `0xb0cf`
- name: `System.Printing.PrintProcessor::VerifyAccess`
- size: `31`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0xaf80`
- `0xaf90`

## callees

- `0xac10`
- `0xac20`
- `0xb0b0`

## pseudocode

```c

```

## disassembly

```asm
0xb0b0  ldarg.0
0xb0b1  ldfld    class System.Printing.PrintSystemDispatcherObject System.Printing.PrintProcessor::accessVerifier
0xb0b6  brtrue.s loc_B0C3
0xb0b8  ldarg.0
0xb0b9  newobj   instance void System.Printing.PrintSystemDispatcherObject::.ctor()
0xb0be  stfld    class System.Printing.PrintSystemDispatcherObject System.Printing.PrintProcessor::accessVerifier
0xb0c3  ldarg.0
0xb0c4  ldfld    class System.Printing.PrintSystemDispatcherObject System.Printing.PrintProcessor::accessVerifier
0xb0c9  call     instance void System.Printing.PrintSystemDispatcherObject::VerifyThreadLocality()
0xb0ce  ret
```
