# System.Printing.PrintJobSettings::VerifyAccess

- ea: `0xb160`
- end: `0xb17f`
- name: `System.Printing.PrintJobSettings::VerifyAccess`
- size: `31`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0xb100`
- `0xb110`
- `0xb130`
- `0xb140`

## callees

- `0xac10`
- `0xac20`
- `0xb160`

## pseudocode

```c

```

## disassembly

```asm
0xb160  ldarg.0
0xb161  ldfld    class System.Printing.PrintSystemDispatcherObject System.Printing.PrintJobSettings::_accessVerifier
0xb166  brtrue.s loc_B173
0xb168  ldarg.0
0xb169  newobj   instance void System.Printing.PrintSystemDispatcherObject::.ctor()
0xb16e  stfld    class System.Printing.PrintSystemDispatcherObject System.Printing.PrintJobSettings::_accessVerifier
0xb173  ldarg.0
0xb174  ldfld    class System.Printing.PrintSystemDispatcherObject System.Printing.PrintJobSettings::_accessVerifier
0xb179  call     instance void System.Printing.PrintSystemDispatcherObject::VerifyThreadLocality()
0xb17e  ret
```
