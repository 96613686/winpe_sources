# System.Printing.PrintQueue::Install_2

- ea: `0xe1d0`
- end: `0xe231`
- name: `System.Printing.PrintQueue::Install_2`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x12040`

## callees

- `0x6ba0`
- `0xdd70`
- `0xe1d0`
- `0x10220`
- `0x12800`
- `0x12a40`
- `0x172a0`

## pseudocode

```c

```

## disassembly

```asm
0xe1d0  ldnull
0xe1d1  stloc.0
0xe1d2  ldarg.1
0xe1d3  brfalse.s loc_E1F9
0xe1d5  ldarg.2
0xe1d6  brfalse.s loc_E1F9
0xe1d8  ldarg.3
0xe1d9  brfalse.s loc_E1F9
0xe1db  ldarg.0
0xe1dc  callvirt instance string System.Printing.PrintServer::get_Name()
0xe1e1  ldarg.1
0xe1e2  ldarg.2
0xe1e3  ldarg.3
0xe1e4  call     string System.Printing.PrintQueue::BuildPortNamesString(string[] portNames)
0xe1e9  ldarg.s  4
0xe1eb  ldnull
0xe1ec  ldnull
0xe1ed  ldnull
0xe1ee  ldnull
0xe1ef  ldarg.s  5
0xe1f1  ldc.i4.0
0xe1f2  ldc.i4.0
0xe1f3  call     class MS.Internal.PrintWin32Thunk.PrinterThunkHandler MS.Internal.PrintWin32Thunk.PrinterThunkHandler::ThunkAddPrinter(string serverName, string printerName, string driverName, string portName, string printProcessorName, string comment, string location, string shareName, string separatorFile, int32 attributes, int32 priority, int32 defaultPriority)
0xe1f8  stloc.0
0xe1f9  leave.s  loc_E21D
0xe1fb  stloc.1
0xe1fc  ldloc.0
0xe1fd  brfalse.s loc_E207
0xe1ff  ldloc.0
0xe200  stloc.2
0xe201  ldloc.0
0xe202  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe207  ldarg.0
0xe208  ldloc.1
0xe209  call     instance int32 System.Printing.InternalPrintSystemException::get_HResult()
0xe20e  ldstr    aPrintsystemexc_1// "PrintSystemException.PrintServer.AddPri"...
0xe213  call     instance class [mscorlib]System.Exception System.Printing.PrintServer::CreatePrintServerException(int32 hresult, string messageId)
0xe218  throw
0xe219  leave.s  loc_E21D
0xe21b  leave.s  loc_E229
0xe21d  leave.s  loc_E229
0xe21f  ldloc.0
0xe220  brfalse.s loc_E228
0xe222  ldloc.0
0xe223  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe228  endfinally
0xe229  ldarg.0
0xe22a  ldarg.1
0xe22b  newobj   instance void System.Printing.PrintQueue::.ctor(class System.Printing.PrintServer printServer, string printQueueName)
0xe230  ret
```
