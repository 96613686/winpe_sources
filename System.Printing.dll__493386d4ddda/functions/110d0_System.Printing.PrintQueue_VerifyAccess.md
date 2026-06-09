# System.Printing.PrintQueue::VerifyAccess

- ea: `0x110d0`
- end: `0x110ef`
- name: `System.Printing.PrintQueue::VerifyAccess`
- size: `31`
- prototype: ``
- caller_count: `97`
- callee_count: `3`
- tags: ``

## callers

- `0xe280`
- `0xe2c0`
- `0xe320`
- `0xe360`
- `0xe3a0`
- `0xe3e0`
- `0xe420`
- `0xe450`
- `0xe480`
- `0xe4a0`
- `0xe4d0`
- `0xe4f0`
- `0xe510`
- `0xe530`
- `0xe540`
- `0xe550`
- `0xe580`
- `0xe590`
- `0xe5b0`
- `0xe5e0`
- `0xe600`
- `0xe760`
- `0xe780`
- `0xe7c0`
- `0xe7e0`
- `0xe820`
- `0xe840`
- `0xe880`
- `0xe8a0`
- `0xe8c0`
- `0xe910`
- `0xe930`
- `0xe9f0`
- `0xea10`
- `0xea60`
- `0xea80`
- `0xead0`
- `0xeaf0`
- `0xeb40`
- `0xeb60`
- `0xeba0`
- `0xec60`
- `0xed00`
- `0xedc0`
- `0xee60`
- `0xee80`
- `0xeef0`
- `0xef10`
- `0xef80`
- `0xefa0`

## callees

- `0xac10`
- `0xac20`
- `0x110d0`

## pseudocode

```c

```

## disassembly

```asm
0x110d0  ldarg.0
0x110d1  ldfld    class System.Printing.PrintSystemDispatcherObject System.Printing.PrintQueue::accessVerifier
0x110d6  brtrue.s loc_110E3
0x110d8  ldarg.0
0x110d9  newobj   instance void System.Printing.PrintSystemDispatcherObject::.ctor()
0x110de  stfld    class System.Printing.PrintSystemDispatcherObject System.Printing.PrintQueue::accessVerifier
0x110e3  ldarg.0
0x110e4  ldfld    class System.Printing.PrintSystemDispatcherObject System.Printing.PrintQueue::accessVerifier
0x110e9  call     instance void System.Printing.PrintSystemDispatcherObject::VerifyThreadLocality()
0x110ee  ret
```
