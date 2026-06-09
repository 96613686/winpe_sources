# System.Printing.PrintPort::VerifyAccess

- ea: `0xaf50`
- end: `0xaf6f`
- name: `System.Printing.PrintPort::VerifyAccess`
- size: `31`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0xae20`
- `0xae30`

## callees

- `0xac10`
- `0xac20`
- `0xaf50`

## pseudocode

```c

```

## disassembly

```asm
0xaf50  ldarg.0
0xaf51  ldfld    class System.Printing.PrintSystemDispatcherObject System.Printing.PrintPort::accessVerifier
0xaf56  brtrue.s loc_AF63
0xaf58  ldarg.0
0xaf59  newobj   instance void System.Printing.PrintSystemDispatcherObject::.ctor()
0xaf5e  stfld    class System.Printing.PrintSystemDispatcherObject System.Printing.PrintPort::accessVerifier
0xaf63  ldarg.0
0xaf64  ldfld    class System.Printing.PrintSystemDispatcherObject System.Printing.PrintPort::accessVerifier
0xaf69  call     instance void System.Printing.PrintSystemDispatcherObject::VerifyThreadLocality()
0xaf6e  ret
```
