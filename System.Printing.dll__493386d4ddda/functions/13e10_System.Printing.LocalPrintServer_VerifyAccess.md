# System.Printing.LocalPrintServer::VerifyAccess

- ea: `0x13e10`
- end: `0x13e2f`
- name: `System.Printing.LocalPrintServer::VerifyAccess`
- size: `31`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x13800`
- `0x13850`
- `0x138a0`
- `0x138d0`
- `0x13900`
- `0x13930`
- `0x13960`
- `0x13990`

## callees

- `0xac10`
- `0xac20`
- `0x13e10`

## pseudocode

```c

```

## disassembly

```asm
0x13e10  ldarg.0
0x13e11  ldfld    class System.Printing.PrintSystemDispatcherObject System.Printing.LocalPrintServer::accessVerifier
0x13e16  brtrue.s loc_13E23
0x13e18  ldarg.0
0x13e19  newobj   instance void System.Printing.PrintSystemDispatcherObject::.ctor()
0x13e1e  stfld    class System.Printing.PrintSystemDispatcherObject System.Printing.LocalPrintServer::accessVerifier
0x13e23  ldarg.0
0x13e24  ldfld    class System.Printing.PrintSystemDispatcherObject System.Printing.LocalPrintServer::accessVerifier
0x13e29  call     instance void System.Printing.PrintSystemDispatcherObject::VerifyThreadLocality()
0x13e2e  ret
```
