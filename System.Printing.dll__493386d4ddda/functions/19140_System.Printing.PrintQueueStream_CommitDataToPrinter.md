# System.Printing.PrintQueueStream::CommitDataToPrinter

- ea: `0x19140`
- end: `0x19263`
- name: `System.Printing.PrintQueueStream::CommitDataToPrinter`
- size: `291`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18fa0`
- `0x19270`

## callees

- `0x200`
- `0x5af0`
- `0x5b10`
- `0x5b50`
- `0xf600`
- `0x172a0`
- `0x18980`
- `0x19140`
- `0x19380`

## pseudocode

```c

```

## disassembly

```asm
0x19140  ldarg.0
0x19141  ldfld    class System.Printing.PrintQueue System.Printing.PrintQueueStream::printQueue
0x19146  call     instance bool System.Printing.PrintQueue::get_InPartialTrust()
0x1914b  brfalse.s loc_19158
0x1914d  ldc.i4.2
0x1914e  newobj   instance void [System.Drawing]System.Drawing.Printing.PrintingPermission::.ctor(valuetype [System.Drawing]System.Drawing.Printing.PrintingPermissionLevel)
0x19153  callvirt instance void [mscorlib]System.Security.CodeAccessPermission::Assert()
0x19158  nop
0x19159  ldc.i4.0
0x1915a  conv.i8
0x1915b  stloc.3
0x1915c  ldarg.0
0x1915d  ldfld    class MS.Internal.PrintWin32Thunk.PrinterThunkHandlerBase System.Printing.PrintQueueStream::printerThunkHandler
0x19162  callvirt instance class [mscorlib]System.IO.Stream MS.Internal.PrintWin32Thunk.PrinterThunkHandlerBase::get_SpoolStream()
0x19167  callvirt instance bool [mscorlib]System.IO.Stream::get_CanSeek()
0x1916c  brfalse.s loc_19195
0x1916e  ldarg.0
0x1916f  ldfld    class MS.Internal.PrintWin32Thunk.PrinterThunkHandlerBase System.Printing.PrintQueueStream::printerThunkHandler
0x19174  callvirt instance class [mscorlib]System.IO.Stream MS.Internal.PrintWin32Thunk.PrinterThunkHandlerBase::get_SpoolStream()
0x19179  callvirt instance int64 [mscorlib]System.IO.Stream::get_Position()
0x1917e  stloc.3
0x1917f  ldarg.0
0x19180  ldfld    class MS.Internal.PrintWin32Thunk.PrinterThunkHandlerBase System.Printing.PrintQueueStream::printerThunkHandler
0x19185  callvirt instance class [mscorlib]System.IO.Stream MS.Internal.PrintWin32Thunk.PrinterThunkHandlerBase::get_SpoolStream()
0x1918a  ldarg.0
0x1918b  ldfld    int64 System.Printing.PrintQueueStream::bytesPreviouslyCommited
0x19190  callvirt instance void [mscorlib]System.IO.Stream::set_Position(int64)
0x19195  ldarg.0
0x19196  ldfld    int64 System.Printing.PrintQueueStream::bytesToCommit
0x1919b  stloc.2
0x1919c  ldloc.2
0x1919d  ldc.i4.0
0x1919e  conv.i8
0x1919f  ble.s    loc_191CE
0x191a1  ldloc.2
0x191a2  stloc.1
0x191a3  ldarg.0
0x191a4  ldfld    class MS.Internal.PrintWin32Thunk.PrinterThunkHandlerBase System.Printing.PrintQueueStream::printerThunkHandler
0x191a9  ldloc.1
0x191aa  conv.i4
0x191ab  callvirt instance void MS.Internal.PrintWin32Thunk.PrinterThunkHandlerBase::ThunkCommitSpoolData(int32 bytes)
0x191b0  ldarg.0
0x191b1  dup
0x191b2  ldfld    int64 System.Printing.PrintQueueStream::bytesPreviouslyCommited
0x191b7  ldloc.1
0x191b8  add
0x191b9  stfld    int64 System.Printing.PrintQueueStream::bytesPreviouslyCommited
0x191be  ldarg.0
0x191bf  dup
0x191c0  ldfld    int64 System.Printing.PrintQueueStream::bytesToCommit
0x191c5  ldloc.1
0x191c6  sub
0x191c7  stfld    int64 System.Printing.PrintQueueStream::bytesToCommit
0x191cc  br.s     loc_19195
0x191ce  ldarg.0
0x191cf  ldfld    class MS.Internal.PrintWin32Thunk.PrinterThunkHandlerBase System.Printing.PrintQueueStream::printerThunkHandler
0x191d4  callvirt instance class [mscorlib]System.IO.Stream MS.Internal.PrintWin32Thunk.PrinterThunkHandlerBase::get_SpoolStream()
0x191d9  callvirt instance bool [mscorlib]System.IO.Stream::get_CanSeek()
0x191de  brfalse.s loc_191F1
0x191e0  ldarg.0
0x191e1  ldfld    class MS.Internal.PrintWin32Thunk.PrinterThunkHandlerBase System.Printing.PrintQueueStream::printerThunkHandler
0x191e6  callvirt instance class [mscorlib]System.IO.Stream MS.Internal.PrintWin32Thunk.PrinterThunkHandlerBase::get_SpoolStream()
0x191eb  ldloc.3
0x191ec  callvirt instance void [mscorlib]System.IO.Stream::set_Position(int64)
0x191f1  leave.s  loc_19247
0x191f3  stloc.0
0x191f4  ldarg.0
0x191f5  ldfld    class MS.Internal.PrintWin32Thunk.PrinterThunkHandlerBase System.Printing.PrintQueueStream::printerThunkHandler
0x191fa  callvirt instance bool MS.Internal.PrintWin32Thunk.PrinterThunkHandlerBase::ThunkAbortPrinter()
0x191ff  pop
0x19200  ldloc.0
0x19201  call     instance int32 System.Printing.InternalPrintSystemException::get_HResult()
0x19206  ldc.i4   0x4C7
0x1920b  call     modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 HRESULT_FROM_WIN32(modopt([mscorlib]System.Runtime.CompilerServices.IsLong) unsigned int32 x)
0x19210  beq.s    loc_19232
0x19212  ldloc.0
0x19213  call     instance int32 System.Printing.InternalPrintSystemException::get_HResult()
0x19218  ldc.i4.s 0x3F
0x1921a  call     modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 HRESULT_FROM_WIN32(modopt([mscorlib]System.Runtime.CompilerServices.IsLong) unsigned int32 x)
0x1921f  beq.s    loc_19232
0x19221  ldloc.0
0x19222  call     instance int32 System.Printing.InternalPrintSystemException::get_HResult()
0x19227  ldstr    aPrintsystemexc_22// "PrintSystemException.PrintSystemJobInfo"...
0x1922c  call     class [mscorlib]System.Exception System.Printing.PrintSystemJobInfo::CreatePrintJobException(int32 hresult, string messageId)
0x19231  throw
0x19232  ldloc.0
0x19233  call     instance int32 System.Printing.InternalPrintSystemException::get_HResult()
0x19238  ldstr    aPrintsystemexc_25// "PrintSystemException.PrintingCancelled."...
0x1923d  call     class [mscorlib]System.Exception System.Printing.PrintQueueStream::CreatePrintingCanceledException(int32 hresult, string messageId)
0x19242  throw
0x19243  leave.s  loc_19247
0x19245  leave.s  loc_1925C
0x19247  leave.s  loc_1925C
0x19249  ldarg.0
0x1924a  ldfld    class System.Printing.PrintQueue System.Printing.PrintQueueStream::printQueue
0x1924f  call     instance bool System.Printing.PrintQueue::get_InPartialTrust()
0x19254  brfalse.s loc_1925B
0x19256  call     void [mscorlib]System.Security.CodeAccessPermission::RevertAssert()
0x1925b  endfinally
0x1925c  ldarg.0
0x1925d  call     void [mscorlib]System.GC::KeepAlive(object)
0x19262  ret
```
