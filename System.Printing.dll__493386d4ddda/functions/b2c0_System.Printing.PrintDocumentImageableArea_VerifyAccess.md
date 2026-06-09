# System.Printing.PrintDocumentImageableArea::VerifyAccess

- ea: `0xb2c0`
- end: `0xb2df`
- name: `System.Printing.PrintDocumentImageableArea::VerifyAccess`
- size: `31`
- prototype: ``
- caller_count: `12`
- callee_count: `3`
- tags: ``

## callers

- `0xb200`
- `0xb210`
- `0xb220`
- `0xb230`
- `0xb240`
- `0xb250`
- `0xb260`
- `0xb270`
- `0xb280`
- `0xb290`
- `0xb2a0`
- `0xb2b0`

## callees

- `0xac10`
- `0xac20`
- `0xb2c0`

## pseudocode

```c

```

## disassembly

```asm
0xb2c0  ldarg.0
0xb2c1  ldfld    class System.Printing.PrintSystemDispatcherObject System.Printing.PrintDocumentImageableArea::_accessVerifier
0xb2c6  brtrue.s loc_B2D3
0xb2c8  ldarg.0
0xb2c9  newobj   instance void System.Printing.PrintSystemDispatcherObject::.ctor()
0xb2ce  stfld    class System.Printing.PrintSystemDispatcherObject System.Printing.PrintDocumentImageableArea::_accessVerifier
0xb2d3  ldarg.0
0xb2d4  ldfld    class System.Printing.PrintSystemDispatcherObject System.Printing.PrintDocumentImageableArea::_accessVerifier
0xb2d9  call     instance void System.Printing.PrintSystemDispatcherObject::VerifyThreadLocality()
0xb2de  ret
```
