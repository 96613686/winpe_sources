# System.Printing.PrintQueue::Install_0

- ea: `0xe0b0`
- end: `0xe117`
- name: `System.Printing.PrintQueue::Install_0`
- size: `103`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x12000`

## callees

- `0x6ba0`
- `0xdd70`
- `0xe0b0`
- `0x10220`
- `0x12800`
- `0x12a40`
- `0x172a0`

## pseudocode

```c

```

## disassembly

```asm
0xe0b0  ldnull
0xe0b1  stloc.0
0xe0b2  ldarg.1
0xe0b3  brfalse.s loc_E0DF
0xe0b5  ldarg.2
0xe0b6  brfalse.s loc_E0DF
0xe0b8  ldarg.3
0xe0b9  brfalse.s loc_E0DF
0xe0bb  ldarg.0
0xe0bc  callvirt instance string System.Printing.PrintServer::get_Name()
0xe0c1  ldarg.1
0xe0c2  ldarg.2
0xe0c3  ldarg.3
0xe0c4  call     string System.Printing.PrintQueue::BuildPortNamesString(string[] portNames)
0xe0c9  ldarg.s  4
0xe0cb  ldarg.s  7
0xe0cd  ldarg.s  8
0xe0cf  ldarg.s  6
0xe0d1  ldarg.s  9
0xe0d3  ldarg.s  5
0xe0d5  ldarg.s  0xA
0xe0d7  ldarg.s  0xB
0xe0d9  call     class MS.Internal.PrintWin32Thunk.PrinterThunkHandler MS.Internal.PrintWin32Thunk.PrinterThunkHandler::ThunkAddPrinter(string serverName, string printerName, string driverName, string portName, string printProcessorName, string comment, string location, string shareName, string separatorFile, int32 attributes, int32 priority, int32 defaultPriority)
0xe0de  stloc.0
0xe0df  leave.s  loc_E103
0xe0e1  stloc.1
0xe0e2  ldloc.0
0xe0e3  brfalse.s loc_E0ED
0xe0e5  ldloc.0
0xe0e6  stloc.2
0xe0e7  ldloc.0
0xe0e8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe0ed  ldarg.0
0xe0ee  ldloc.1
0xe0ef  call     instance int32 System.Printing.InternalPrintSystemException::get_HResult()
0xe0f4  ldstr    aPrintsystemexc_1// "PrintSystemException.PrintServer.AddPri"...
0xe0f9  call     instance class [mscorlib]System.Exception System.Printing.PrintServer::CreatePrintServerException(int32 hresult, string messageId)
0xe0fe  throw
0xe0ff  leave.s  loc_E103
0xe101  leave.s  loc_E10F
0xe103  leave.s  loc_E10F
0xe105  ldloc.0
0xe106  brfalse.s loc_E10E
0xe108  ldloc.0
0xe109  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe10e  endfinally
0xe10f  ldarg.0
0xe110  ldarg.1
0xe111  newobj   instance void System.Printing.PrintQueue::.ctor(class System.Printing.PrintServer printServer, string printQueueName)
0xe116  ret
```
