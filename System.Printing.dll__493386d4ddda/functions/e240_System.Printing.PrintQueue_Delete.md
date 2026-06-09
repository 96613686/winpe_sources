# System.Printing.PrintQueue::Delete

- ea: `0xe240`
- end: `0xe279`
- name: `System.Printing.PrintQueue::Delete`
- size: `57`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x12060`
- `0x12070`

## callees

- `0x3070`
- `0x6130`
- `0x6220`
- `0x6a10`
- `0xe240`

## pseudocode

```c

```

## disassembly

```asm
0xe240  ldc.i4.0
0xe241  stloc.1
0xe242  ldnull
0xe243  stloc.0
0xe244  ldnull
0xe245  ldnull
0xe246  ldc.i4   0xF000C
0xe24b  newobj   instance void MS.Internal.PrintWin32Thunk.PrinterDefaults::.ctor(string dataType, class MS.Internal.PrintWin32Thunk.DeviceMode devMode, valuetype System.Printing.PrintSystemDesiredAccess desiredAccess)
0xe250  stloc.2
0xe251  ldarg.0
0xe252  ldloc.2
0xe253  newobj   instance void MS.Internal.PrintWin32Thunk.PrinterThunkHandler::.ctor(string printName, class MS.Internal.PrintWin32Thunk.PrinterDefaults printerDefaults)
0xe258  stloc.0
0xe259  ldloc.0
0xe25a  brfalse.s loc_E26B
0xe25c  ldloc.0
0xe25d  callvirt instance bool MS.Internal.PrintWin32Thunk.PrinterThunkHandler::get_IsInvalid()
0xe262  brtrue.s loc_E26B
0xe264  ldloc.0
0xe265  call     instance bool MS.Internal.PrintWin32Thunk.PrinterThunkHandler::ThunkDeletePrinter()
0xe26a  stloc.1
0xe26b  leave.s  loc_E277
0xe26d  ldloc.0
0xe26e  brfalse.s loc_E276
0xe270  ldloc.0
0xe271  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe276  endfinally
0xe277  ldloc.1
0xe278  ret
```
