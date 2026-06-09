# System.Printing.PrintQueue::Install_1

- ea: `0xe120`
- end: `0xe1c3`
- name: `System.Printing.PrintQueue::Install_1`
- size: `163`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x12020`

## callees

- `0x6ba0`
- `0xd870`
- `0xd890`
- `0xdd70`
- `0xe120`
- `0x10220`
- `0x12800`
- `0x12a30`
- `0x12a40`
- `0x172a0`

## pseudocode

```c

```

## disassembly

```asm
0xe120  ldnull
0xe121  stloc.0
0xe122  ldarg.1
0xe123  brfalse.s loc_E18A
0xe125  ldarg.2
0xe126  brfalse.s loc_E18A
0xe128  ldarg.3
0xe129  brfalse.s loc_E18A
0xe12b  ldc.i4.3
0xe12c  newarr   [mscorlib]System.String
0xe131  stloc.1
0xe132  ldarg.s  6
0xe134  call     instance valuetype System.Printing.PrintQueueStringPropertyType System.Printing.PrintQueueStringProperty::get_Type()
0xe139  stloc.s  4
0xe13b  ldloc.1
0xe13c  ldloc.s  4
0xe13e  ldarg.s  6
0xe140  call     instance string System.Printing.PrintQueueStringProperty::get_Name()
0xe145  stelem.ref
0xe146  leave.s  loc_E164
0xe148  stloc.3
0xe149  ldc.i4   0x80070057
0xe14e  stloc.s  6
0xe150  ldarg.0
0xe151  ldc.i4   0x80070057
0xe156  ldstr    aPrintsystemexc_1// "PrintSystemException.PrintServer.AddPri"...
0xe15b  ldloc.3
0xe15c  call     instance class [mscorlib]System.Exception System.Printing.PrintServer::CreatePrintServerException(int32 hresult, string messageId, class [mscorlib]System.Exception innerException)
0xe161  throw
0xe162  leave.s  loc_E164
0xe164  ldarg.0
0xe165  callvirt instance string System.Printing.PrintServer::get_Name()
0xe16a  ldarg.1
0xe16b  ldarg.2
0xe16c  ldarg.3
0xe16d  call     string System.Printing.PrintQueue::BuildPortNamesString(string[] portNames)
0xe172  ldarg.s  4
0xe174  ldloc.1
0xe175  ldc.i4.1
0xe176  ldelem.ref
0xe177  ldloc.1
0xe178  ldc.i4.0
0xe179  ldelem.ref
0xe17a  ldloc.1
0xe17b  ldc.i4.2
0xe17c  ldelem.ref
0xe17d  ldnull
0xe17e  ldarg.s  5
0xe180  ldarg.s  7
0xe182  ldarg.s  8
0xe184  call     class MS.Internal.PrintWin32Thunk.PrinterThunkHandler MS.Internal.PrintWin32Thunk.PrinterThunkHandler::ThunkAddPrinter(string serverName, string printerName, string driverName, string portName, string printProcessorName, string comment, string location, string shareName, string separatorFile, int32 attributes, int32 priority, int32 defaultPriority)
0xe189  stloc.0
0xe18a  leave.s  loc_E1AF
0xe18c  stloc.2
0xe18d  ldloc.0
0xe18e  brfalse.s loc_E199
0xe190  ldloc.0
0xe191  stloc.s  5
0xe193  ldloc.0
0xe194  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe199  ldarg.0
0xe19a  ldloc.2
0xe19b  call     instance int32 System.Printing.InternalPrintSystemException::get_HResult()
0xe1a0  ldstr    aPrintsystemexc_1// "PrintSystemException.PrintServer.AddPri"...
0xe1a5  call     instance class [mscorlib]System.Exception System.Printing.PrintServer::CreatePrintServerException(int32 hresult, string messageId)
0xe1aa  throw
0xe1ab  leave.s  loc_E1AF
0xe1ad  leave.s  loc_E1BB
0xe1af  leave.s  loc_E1BB
0xe1b1  ldloc.0
0xe1b2  brfalse.s loc_E1BA
0xe1b4  ldloc.0
0xe1b5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe1ba  endfinally
0xe1bb  ldarg.0
0xe1bc  ldarg.1
0xe1bd  newobj   instance void System.Printing.PrintQueue::.ctor(class System.Printing.PrintServer printServer, string printQueueName)
0xe1c2  ret
```
