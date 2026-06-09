# System.Printing.PrintJobInfoCollection::VerifyAccess

- ea: `0x18ab0`
- end: `0x18acf`
- name: `System.Printing.PrintJobInfoCollection::VerifyAccess`
- size: `31`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18a40`
- `0x18a50`
- `0x18a70`
- `0x18a90`

## callees

- `0xac10`
- `0xac20`
- `0x18ab0`

## pseudocode

```c

```

## disassembly

```asm
0x18ab0  ldarg.0
0x18ab1  ldfld    class System.Printing.PrintSystemDispatcherObject System.Printing.PrintJobInfoCollection::accessVerifier
0x18ab6  brtrue.s loc_18AC3
0x18ab8  ldarg.0
0x18ab9  newobj   instance void System.Printing.PrintSystemDispatcherObject::.ctor()
0x18abe  stfld    class System.Printing.PrintSystemDispatcherObject System.Printing.PrintJobInfoCollection::accessVerifier
0x18ac3  ldarg.0
0x18ac4  ldfld    class System.Printing.PrintSystemDispatcherObject System.Printing.PrintJobInfoCollection::accessVerifier
0x18ac9  call     instance void System.Printing.PrintSystemDispatcherObject::VerifyThreadLocality()
0x18ace  ret
```
