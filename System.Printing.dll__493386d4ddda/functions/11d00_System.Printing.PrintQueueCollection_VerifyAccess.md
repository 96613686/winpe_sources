# System.Printing.PrintQueueCollection::VerifyAccess

- ea: `0x11d00`
- end: `0x11d1f`
- name: `System.Printing.PrintQueueCollection::VerifyAccess`
- size: `31`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x11c30`
- `0x11c40`
- `0x11c60`
- `0x11c90`
- `0x11d20`

## callees

- `0xac10`
- `0xac20`
- `0x11d00`

## pseudocode

```c

```

## disassembly

```asm
0x11d00  ldarg.0
0x11d01  ldfld    class System.Printing.PrintSystemDispatcherObject System.Printing.PrintQueueCollection::accessVerifier
0x11d06  brtrue.s loc_11D13
0x11d08  ldarg.0
0x11d09  newobj   instance void System.Printing.PrintSystemDispatcherObject::.ctor()
0x11d0e  stfld    class System.Printing.PrintSystemDispatcherObject System.Printing.PrintQueueCollection::accessVerifier
0x11d13  ldarg.0
0x11d14  ldfld    class System.Printing.PrintSystemDispatcherObject System.Printing.PrintQueueCollection::accessVerifier
0x11d19  call     instance void System.Printing.PrintSystemDispatcherObject::VerifyThreadLocality()
0x11d1e  ret
```
