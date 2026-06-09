# System.Printing.PrintQueueStream::Write

- ea: `0x18e90`
- end: `0x18f39`
- name: `System.Printing.PrintQueueStream::Write`
- size: `169`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x200`
- `0x5af0`
- `0x5b50`
- `0xe530`
- `0xe540`
- `0xf600`
- `0x18e90`
- `0x19380`

## pseudocode

```c

```

## disassembly

```asm
0x18e90  ldarg.0
0x18e91  ldfld    class MS.Internal.PrintWin32Thunk.PrinterThunkHandlerBase System.Printing.PrintQueueStream::printerThunkHandler
0x18e96  brfalse  loc_18F32
0x18e9b  ldarg.0
0x18e9c  ldfld    class System.Printing.PrintQueue System.Printing.PrintQueueStream::printQueue
0x18ea1  call     instance bool System.Printing.PrintQueue::get_PrintingIsCancelled()
0x18ea6  brfalse.s loc_18F00
0x18ea8  ldarg.0
0x18ea9  ldfld    class System.Printing.PrintQueue System.Printing.PrintQueueStream::printQueue
0x18eae  call     instance bool System.Printing.PrintQueue::get_InPartialTrust()
0x18eb3  brfalse.s loc_18EC0
0x18eb5  ldc.i4.2
0x18eb6  newobj   instance void [System.Drawing]System.Drawing.Printing.PrintingPermission::.ctor(valuetype [System.Drawing]System.Drawing.Printing.PrintingPermissionLevel)
0x18ebb  callvirt instance void [mscorlib]System.Security.CodeAccessPermission::Assert()
0x18ec0  nop
0x18ec1  ldarg.0
0x18ec2  ldfld    class MS.Internal.PrintWin32Thunk.PrinterThunkHandlerBase System.Printing.PrintQueueStream::printerThunkHandler
0x18ec7  callvirt instance bool MS.Internal.PrintWin32Thunk.PrinterThunkHandlerBase::ThunkAbortPrinter()
0x18ecc  pop
0x18ecd  leave.s  loc_18EE2
0x18ecf  ldarg.0
0x18ed0  ldfld    class System.Printing.PrintQueue System.Printing.PrintQueueStream::printQueue
0x18ed5  call     instance bool System.Printing.PrintQueue::get_InPartialTrust()
0x18eda  brfalse.s loc_18EE1
0x18edc  call     void [mscorlib]System.Security.CodeAccessPermission::RevertAssert()
0x18ee1  endfinally
0x18ee2  ldarg.0
0x18ee3  ldfld    class System.Printing.PrintQueue System.Printing.PrintQueueStream::printQueue
0x18ee8  ldc.i4.0
0x18ee9  call     instance void System.Printing.PrintQueue::set_PrintingIsCancelled([hasfieldmarshal] bool isCancelled)
0x18eee  ldc.i4.s 0x3F
0x18ef0  call     modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 HRESULT_FROM_WIN32(modopt([mscorlib]System.Runtime.CompilerServices.IsLong) unsigned int32 x)
0x18ef5  ldstr    aPrintsystemexc_25// "PrintSystemException.PrintingCancelled."...
0x18efa  call     class [mscorlib]System.Exception System.Printing.PrintQueueStream::CreatePrintingCanceledException(int32 hresult, string messageId)
0x18eff  throw
0x18f00  ldarg.0
0x18f01  ldfld    bool System.Printing.PrintQueueStream::streamAborted
0x18f06  brtrue.s loc_18F32
0x18f08  ldarg.0
0x18f09  ldfld    class MS.Internal.PrintWin32Thunk.PrinterThunkHandlerBase System.Printing.PrintQueueStream::printerThunkHandler
0x18f0e  callvirt instance class [mscorlib]System.IO.Stream MS.Internal.PrintWin32Thunk.PrinterThunkHandlerBase::get_SpoolStream()
0x18f13  ldarg.1
0x18f14  ldarg.2
0x18f15  ldarg.3
0x18f16  callvirt instance void [mscorlib]System.IO.Stream::Write(unsigned int8[], int32, int32)
0x18f1b  ldarg.0
0x18f1c  ldfld    bool System.Printing.PrintQueueStream::commitStreamDataOnClose
0x18f21  brtrue.s loc_18F32
0x18f23  ldarg.0
0x18f24  ldarg.3
0x18f25  conv.i8
0x18f26  ldarg.0
0x18f27  ldfld    int64 System.Printing.PrintQueueStream::bytesToCommit
0x18f2c  add
0x18f2d  stfld    int64 System.Printing.PrintQueueStream::bytesToCommit
0x18f32  ldarg.0
0x18f33  call     void [mscorlib]System.GC::KeepAlive(object)
0x18f38  ret
```
