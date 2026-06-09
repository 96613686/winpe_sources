# System.Printing.LocalPrintServer::DisconnectFromPrintQueue_0

- ea: `0x13930`
- end: `0x13958`
- name: `System.Printing.LocalPrintServer::DisconnectFromPrintQueue_0`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x6d00`
- `0x12a40`
- `0x13930`
- `0x13e10`
- `0x172a0`

## string_xrefs

- `0x13949`: `PrintSystemException.PrintServer.DeleteConnection`

## pseudocode

```c

```

## disassembly

```asm
0x13930  ldarg.0
0x13931  call     instance void System.Printing.LocalPrintServer::VerifyAccess()
0x13936  ldc.i4.0
0x13937  stloc.0
0x13938  ldarg.1
0x13939  call     bool MS.Internal.PrintWin32Thunk.PrinterThunkHandler::ThunkDeletePrinterConnection([hasfieldmarshal] string value)
0x1393e  stloc.0
0x1393f  leave.s  loc_13956
0x13941  stloc.1
0x13942  ldarg.0
0x13943  ldloc.1
0x13944  call     instance int32 System.Printing.InternalPrintSystemException::get_HResult()
0x13949  ldstr    aPrintsystemexc_18// "PrintSystemException.PrintServer.Delete"...
0x1394e  call     instance class [mscorlib]System.Exception System.Printing.PrintServer::CreatePrintServerException(int32 hresult, string messageId)
0x13953  throw
0x13954  leave.s  loc_13956
0x13956  ldloc.0
0x13957  ret
```
