# System.Printing.LocalPrintServer::DisconnectFromPrintQueue

- ea: `0x13900`
- end: `0x1392e`
- name: `System.Printing.LocalPrintServer::DisconnectFromPrintQueue`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x6d00`
- `0x12a40`
- `0x13900`
- `0x13db0`
- `0x13e10`
- `0x172a0`

## string_xrefs

- `0x1391f`: `PrintSystemException.PrintServer.DeleteConnection`

## pseudocode

```c

```

## disassembly

```asm
0x13900  ldarg.0
0x13901  call     instance void System.Printing.LocalPrintServer::VerifyAccess()
0x13906  ldc.i4.0
0x13907  stloc.0
0x13908  ldarg.0
0x13909  ldarg.1
0x1390a  call     instance string System.Printing.LocalPrintServer::GetFullPrintQueueName(class System.Printing.PrintQueue queue)
0x1390f  call     bool MS.Internal.PrintWin32Thunk.PrinterThunkHandler::ThunkDeletePrinterConnection([hasfieldmarshal] string value)
0x13914  stloc.0
0x13915  leave.s  loc_1392C
0x13917  stloc.1
0x13918  ldarg.0
0x13919  ldloc.1
0x1391a  call     instance int32 System.Printing.InternalPrintSystemException::get_HResult()
0x1391f  ldstr    aPrintsystemexc_18// "PrintSystemException.PrintServer.Delete"...
0x13924  call     instance class [mscorlib]System.Exception System.Printing.PrintServer::CreatePrintServerException(int32 hresult, string messageId)
0x13929  throw
0x1392a  leave.s  loc_1392C
0x1392c  ldloc.0
0x1392d  ret
```
