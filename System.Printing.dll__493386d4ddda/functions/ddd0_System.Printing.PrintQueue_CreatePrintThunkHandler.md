# System.Printing.PrintQueue::CreatePrintThunkHandler

- ea: `0xddd0`
- end: `0xddf0`
- name: `System.Printing.PrintQueue::CreatePrintThunkHandler`
- size: `32`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x19070`

## callees

- `0x6270`
- `0x7440`
- `0xddd0`
- `0xddf0`
- `0xf080`
- `0xfc70`

## pseudocode

```c

```

## disassembly

```asm
0xddd0  ldarg.0
0xddd1  call     instance bool System.Printing.PrintQueue::IsXpsDeviceSimulationSupported()
0xddd6  brfalse.s loc_DDE4
0xddd8  ldarg.0
0xddd9  call     instance string System.Printing.PrintQueue::get_FullName()
0xddde  newobj   instance void MS.Internal.PrintWin32Thunk.XpsDeviceSimulatingPrintThunkHandler::.ctor(string printerName)
0xdde3  ret
0xdde4  ldarg.0
0xdde5  call     instance class MS.Internal.PrintWin32Thunk.PrinterThunkHandler System.Printing.PrintQueue::get_PrinterThunkHandler()
0xddea  call     instance class MS.Internal.PrintWin32Thunk.PrinterThunkHandler MS.Internal.PrintWin32Thunk.PrinterThunkHandler::DuplicateHandler()
0xddef  ret
```
