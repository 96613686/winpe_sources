# System.Windows.Xps.VisualsToXpsDocument::VerifyAccess

- ea: `0xd680`
- end: `0xd69f`
- name: `System.Windows.Xps.VisualsToXpsDocument::VerifyAccess`
- size: `31`
- prototype: ``
- caller_count: `10`
- callee_count: `3`
- tags: ``

## callers

- `0xccd0`
- `0xcce0`
- `0xce70`
- `0xce90`
- `0xceb0`
- `0xced0`
- `0xcef0`
- `0xcf10`
- `0xcf30`
- `0xd010`

## callees

- `0xac10`
- `0xac20`
- `0xd680`

## pseudocode

```c

```

## disassembly

```asm
0xd680  ldarg.0
0xd681  ldfld    class System.Printing.PrintSystemDispatcherObject System.Windows.Xps.VisualsToXpsDocument::accessVerifier
0xd686  brtrue.s loc_D693
0xd688  ldarg.0
0xd689  newobj   instance void System.Printing.PrintSystemDispatcherObject::.ctor()
0xd68e  stfld    class System.Printing.PrintSystemDispatcherObject System.Windows.Xps.VisualsToXpsDocument::accessVerifier
0xd693  ldarg.0
0xd694  ldfld    class System.Printing.PrintSystemDispatcherObject System.Windows.Xps.VisualsToXpsDocument::accessVerifier
0xd699  call     instance void System.Printing.PrintSystemDispatcherObject::VerifyThreadLocality()
0xd69e  ret
```
