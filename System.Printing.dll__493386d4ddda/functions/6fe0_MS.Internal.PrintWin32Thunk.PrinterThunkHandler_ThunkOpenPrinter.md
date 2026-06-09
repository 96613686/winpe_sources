# MS.Internal.PrintWin32Thunk.PrinterThunkHandler::ThunkOpenPrinter

- ea: `0x6fe0`
- end: `0x7013`
- name: `MS.Internal.PrintWin32Thunk.PrinterThunkHandler::ThunkOpenPrinter`
- size: `51`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x6130`
- `0x6170`

## callees

- `0x30e0`
- `0x6fe0`
- `0x7400`
- `0x8110`
- `0x172e0`

## pseudocode

```c

```

## disassembly

```asm
0x6fe0  ldloca.s 1
0x6fe2  initobj  [mscorlib]System.IntPtr
0x6fe8  ldarg.2
0x6fe9  brfalse.s loc_6FF6
0x6feb  ldarg.2
0x6fec  call     instance valuetype System.Printing.PrintSystemDesiredAccess MS.Internal.PrintWin32Thunk.PrinterDefaults::get_DesiredAccess()
0x6ff1  call     void MS.Internal.PrintWin32Thunk.SecurityHelper::DemandPrintingPermissions(valuetype System.Printing.PrintSystemDesiredAccess desiredAccess)
0x6ff6  ldarg.1
0x6ff7  ldloca.s 1
0x6ff9  ldarg.2
0x6ffa  call     bool MS.Internal.PrintWin32Thunk.Win32ApiThunk.UnsafeNativeMethods::InvokeOpenPrinter(string A_0, native int* A_1, class MS.Internal.PrintWin32Thunk.PrinterDefaults A_2)
0x6fff  stloc.0
0x7000  ldloc.0
0x7001  brfalse.s loc_700C
0x7003  ldarg.0
0x7004  ldloc.1
0x7005  call     instance void [mscorlib]System.Runtime.InteropServices.SafeHandle::SetHandle(native int)
0x700a  br.s     loc_7011
0x700c  call     void System.Printing.InternalPrintSystemException::ThrowLastError()
0x7011  ldloc.0
0x7012  ret
```
