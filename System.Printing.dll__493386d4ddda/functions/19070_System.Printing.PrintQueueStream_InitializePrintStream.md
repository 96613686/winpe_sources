# System.Printing.PrintQueueStream::InitializePrintStream

- ea: `0x19070`
- end: `0x19124`
- name: `System.Printing.PrintQueueStream::InitializePrintStream`
- size: `180`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x18b10`
- `0x19130`

## callees

- `0x3190`
- `0x5ad0`
- `0x5b00`
- `0xa730`
- `0xac10`
- `0xddd0`
- `0xeef0`
- `0xf600`
- `0x172a0`
- `0x18980`
- `0x19070`

## string_xrefs

- `0x190ff`: `PrintSystemException.PrintSystemJobInfo.Create`

## pseudocode

```c

```

## disassembly

```asm
0x19070  ldnull
0x19071  stloc.1
0x19072  ldnull
0x19073  stloc.0
0x19074  ldarg.0
0x19075  newobj   instance void System.Printing.PrintSystemDispatcherObject::.ctor()
0x1907a  stfld    class System.Printing.PrintSystemDispatcherObject System.Printing.PrintQueueStream::accessVerifier
0x1907f  ldarg.0
0x19080  ldfld    class System.Printing.PrintQueue System.Printing.PrintQueueStream::printQueue
0x19085  call     instance bool System.Printing.PrintQueue::get_InPartialTrust()
0x1908a  brfalse.s loc_19097
0x1908c  ldc.i4.2
0x1908d  newobj   instance void [System.Drawing]System.Drawing.Printing.PrintingPermission::.ctor(valuetype [System.Drawing]System.Drawing.Printing.PrintingPermissionLevel)
0x19092  callvirt instance void [mscorlib]System.Security.CodeAccessPermission::Assert()
0x19097  nop
0x19098  ldarg.2
0x19099  ldc.i4.0
0x1909a  bne.un.s loc_1909F
0x1909c  ldc.i4.1
0x1909d  br.s     loc_190A4
0x1909f  ldc.i4   0x40000001
0x190a4  stloc.2
0x190a5  ldarg.0
0x190a6  dup
0x190a7  ldfld    class System.Printing.PrintQueue System.Printing.PrintQueueStream::printQueue
0x190ac  call     instance class MS.Internal.PrintWin32Thunk.PrinterThunkHandlerBase System.Printing.PrintQueue::CreatePrintThunkHandler()
0x190b1  stfld    class MS.Internal.PrintWin32Thunk.PrinterThunkHandlerBase System.Printing.PrintQueueStream::printerThunkHandler
0x190b6  ldarg.0
0x190b7  ldfld    string System.Printing.PrintQueueStream::printJobName
0x190bc  ldarg.0
0x190bd  ldfld    class System.Printing.PrintQueue System.Printing.PrintQueueStream::printQueue
0x190c2  callvirt instance class System.Printing.PrintPort System.Printing.PrintQueue::get_QueuePort()
0x190c7  callvirt instance string System.Printing.PrintSystemObject::get_Name()
0x190cc  ldsfld   string MS.Internal.PrintWin32Thunk.DocInfoThree::defaultDataType
0x190d1  ldloc.2
0x190d2  newobj   instance void MS.Internal.PrintWin32Thunk.DocInfoThree::.ctor(string name, string outputFile, string dataType, int32 flags)
0x190d7  stloc.1
0x190d8  ldarg.0
0x190d9  dup
0x190da  ldfld    class MS.Internal.PrintWin32Thunk.PrinterThunkHandlerBase System.Printing.PrintQueueStream::printerThunkHandler
0x190df  ldloc.1
0x190e0  ldarg.1
0x190e1  callvirt instance int32 MS.Internal.PrintWin32Thunk.PrinterThunkHandlerBase::ThunkStartDocPrinter(class MS.Internal.PrintWin32Thunk.DocInfoThree docInfo, class [ReachFramework]System.Printing.PrintTicket printTicket)
0x190e6  stfld    int32 System.Printing.PrintQueueStream::jobIdentifier
0x190eb  ldarg.0
0x190ec  ldfld    class MS.Internal.PrintWin32Thunk.PrinterThunkHandlerBase System.Printing.PrintQueueStream::printerThunkHandler
0x190f1  callvirt instance void MS.Internal.PrintWin32Thunk.PrinterThunkHandlerBase::ThunkOpenSpoolStream()
0x190f6  leave.s  loc_1910E
0x190f8  stloc.0
0x190f9  ldloc.0
0x190fa  call     instance int32 System.Printing.InternalPrintSystemException::get_HResult()
0x190ff  ldstr    aPrintsystemexc_21// "PrintSystemException.PrintSystemJobInfo"...
0x19104  call     class [mscorlib]System.Exception System.Printing.PrintSystemJobInfo::CreatePrintJobException(int32 hresult, string messageId)
0x19109  throw
0x1910a  leave.s  loc_1910E
0x1910c  leave.s  loc_19123
0x1910e  leave.s  loc_19123
0x19110  ldarg.0
0x19111  ldfld    class System.Printing.PrintQueue System.Printing.PrintQueueStream::printQueue
0x19116  call     instance bool System.Printing.PrintQueue::get_InPartialTrust()
0x1911b  brfalse.s loc_19122
0x1911d  call     void [mscorlib]System.Security.CodeAccessPermission::RevertAssert()
0x19122  endfinally
0x19123  ret
```
