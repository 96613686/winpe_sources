# System.Printing.PrintDriver::VerifyAccess

- ea: `0xadf0`
- end: `0xae0f`
- name: `System.Printing.PrintDriver::VerifyAccess`
- size: `31`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0xacc0`
- `0xacd0`

## callees

- `0xac10`
- `0xac20`
- `0xadf0`

## pseudocode

```c

```

## disassembly

```asm
0xadf0  ldarg.0
0xadf1  ldfld    class System.Printing.PrintSystemDispatcherObject System.Printing.PrintDriver::accessVerifier
0xadf6  brtrue.s loc_AE03
0xadf8  ldarg.0
0xadf9  newobj   instance void System.Printing.PrintSystemDispatcherObject::.ctor()
0xadfe  stfld    class System.Printing.PrintSystemDispatcherObject System.Printing.PrintDriver::accessVerifier
0xae03  ldarg.0
0xae04  ldfld    class System.Printing.PrintSystemDispatcherObject System.Printing.PrintDriver::accessVerifier
0xae09  call     instance void System.Printing.PrintSystemDispatcherObject::VerifyThreadLocality()
0xae0e  ret
```
