# System.Printing.PrintSystemJobInfo::.ctor_1

- ea: `0x17460`
- end: `0x175d2`
- name: `System.Printing.PrintSystemJobInfo::.ctor_1`
- size: `370`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: ``

## callers

- `0x17730`

## callees

- `0x200`
- `0xa7c0`
- `0xa980`
- `0xb140`
- `0xb400`
- `0xb470`
- `0xb4d0`
- `0xe550`
- `0xf540`
- `0x172a0`
- `0x17460`
- `0x17960`
- `0x183d0`
- `0x18550`
- `0x18910`
- `0x18970`
- `0x18980`
- `0x18b10`
- `0x18d90`

## string_xrefs

- `0x174ad`: `PrintSystemException.PrintSystemJobInfo.Create`
- `0x17595`: `PrintSystemException.PrintSystemJobInfo.Create`
- `0x175b2`: `PrintSystemException.PrintSystemJobInfo.Create`

## pseudocode

```c

```

## disassembly

```asm
0x17460  ldnull
0x17461  stloc.0
0x17462  ldnull
0x17463  stloc.3
0x17464  ldnull
0x17465  stloc.2
0x17466  ldnull
0x17467  stloc.s  6
0x17469  ldnull
0x1746a  stloc.1
0x1746b  ldnull
0x1746c  stloc.s  5
0x1746e  ldarg.0
0x1746f  ldnull
0x17470  stfld    class System.Printing.PrintQueueStream System.Printing.PrintSystemJobInfo::printStream
0x17475  ldarg.2
0x17476  brfalse.s loc_1747D
0x17478  ldarg.2
0x17479  stloc.s  4
0x1747b  br.s     loc_17484
0x1747d  ldsfld   string System.Printing.PrintSystemJobInfo::defaultJobName
0x17482  stloc.s  4
0x17484  ldarg.0
0x17485  ldloc.s  4
0x17487  stfld    string System.Printing.PrintSystemJobInfo::jobName
0x1748c  ldarg.0
0x1748d  ldarg.1
0x1748e  stfld    class System.Printing.PrintQueue System.Printing.PrintSystemJobInfo::hostingPrintQueue
0x17493  ldarg.0
0x17494  ldnull
0x17495  stfld    class System.Printing.PrintSystemDispatcherObject System.Printing.PrintSystemJobInfo::accessVerifier
0x1749a  ldarg.0
0x1749b  call     instance void System.Printing.PrintSystemObject::.ctor()
0x174a0  ldc.i4.0
0x174a1  stloc.s  7
0x174a3  ldarg.0
0x174a4  ldfld    class System.Printing.PrintQueue System.Printing.PrintSystemJobInfo::hostingPrintQueue
0x174a9  brfalse.s loc_174AD
0x174ab  leave.s  loc_174C2
0x174ad  ldstr    aPrintsystemexc_21// "PrintSystemException.PrintSystemJobInfo"...
0x174b2  ldstr    aPrintqueue_0// "printQueue"
0x174b7  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x174bc  call     class [mscorlib]System.Exception System.Printing.PrintSystemJobInfo::CreatePrintJobException(string messageId, class [mscorlib]System.Exception innerException)
0x174c1  throw
0x174c2  nop
0x174c3  ldarg.0
0x174c4  call     instance void System.Printing.PrintSystemJobInfo::Initialize()
0x174c9  ldarg.s  4
0x174cb  brfalse.s loc_1752B
0x174cd  ldarg.0
0x174ce  ldfld    class System.Printing.PrintQueue System.Printing.PrintSystemJobInfo::hostingPrintQueue
0x174d3  call     instance bool System.Printing.PrintQueue::get_IsXpsDevice()
0x174d8  brfalse.s loc_17525
0x174da  ldarg.0
0x174db  ldfld    class System.Printing.PrintQueue System.Printing.PrintSystemJobInfo::hostingPrintQueue
0x174e0  ldarg.0
0x174e1  ldfld    string System.Printing.PrintSystemJobInfo::jobName
0x174e6  ldc.i4.0
0x174e7  ldarg.s  5
0x174e9  ldarg.s  4
0x174eb  newobj   instance void System.Printing.PrintQueueStream::.ctor(class System.Printing.PrintQueue printQueue, string printJobName, [hasfieldmarshal] bool commitDataOnClose, class [ReachFramework]System.Printing.PrintTicket printTicket, [hasfieldmarshal] bool fastCopy)
0x174f0  stloc.0
0x174f1  ldarg.0
0x174f2  ldarg.3
0x174f3  ldloc.0
0x174f4  call     instance void System.Printing.PrintSystemJobInfo::CopyFileStreamToPrinter(string xpsFileName, class [mscorlib]System.IO.Stream printStream)
0x174f9  ldarg.0
0x174fa  ldloc.0
0x174fb  call     instance int32 System.Printing.PrintQueueStream::get_JobIdentifier()
0x17500  call     instance void System.Printing.PrintSystemJobInfo::set_JobIdentifier(int32 newJobIdentifier)
0x17505  ldarg.0
0x17506  dup
0x17507  ldfld    string[] System.Printing.PrintSystemJobInfo::refreshPropertiesFilter
0x1750c  call     instance void System.Printing.PrintSystemJobInfo::PopulateJobProperties(string[] propertiesAsStrings)
0x17511  ldloc.0
0x17512  stloc.s  8
0x17514  ldloc.0
0x17515  brfalse  loc_175AE
0x1751a  ldloc.0
0x1751b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x17520  br       loc_175AE
0x17525  newobj   instance void [mscorlib]System.NotSupportedException::.ctor()
0x1752a  throw
0x1752b  ldarg.0
0x1752c  ldfld    class System.Printing.PrintQueue System.Printing.PrintSystemJobInfo::hostingPrintQueue
0x17531  call     instance class System.Printing.PrintJobSettings System.Printing.PrintQueue::get_CurrentJobSettings()
0x17536  ldarg.0
0x17537  ldfld    string System.Printing.PrintSystemJobInfo::jobName
0x1753c  call     instance void System.Printing.PrintJobSettings::set_Description(string description)
0x17541  ldarg.3
0x17542  ldc.i4.1
0x17543  newobj   instance void [ReachFramework]System.Windows.Xps.Packaging.XpsDocument::.ctor(string, valuetype [mscorlib]System.IO.FileAccess)
0x17548  stloc.3
0x17549  ldarg.0
0x1754a  ldfld    class System.Printing.PrintQueue System.Printing.PrintSystemJobInfo::hostingPrintQueue
0x1754f  newobj   instance void System.Windows.Xps.XpsDocumentWriter::.ctor(class System.Printing.PrintQueue printQueue)
0x17554  stloc.2
0x17555  ldloc.3
0x17556  call     instance class [PresentationFramework]System.Windows.Documents.FixedDocumentSequence [ReachFramework]System.Windows.Xps.Packaging.XpsDocument::GetFixedDocumentSequence()
0x1755b  stloc.s  6
0x1755d  ldloc.2
0x1755e  ldloc.s  6
0x17560  ldarg.s  5
0x17562  ldloca.s 7
0x17564  call     instance void System.Windows.Xps.XpsDocumentWriter::BeginPrintFixedDocumentSequence(class [PresentationFramework]System.Windows.Documents.FixedDocumentSequence fixedDocumentSequence, class [ReachFramework]System.Printing.PrintTicket printTicket, modopt([mscorlib]System.Runtime.CompilerServices.IsImplicitlyDereferenced) int32* printJobIdentifier)
0x17569  ldarg.0
0x1756a  ldloc.s  7
0x1756c  call     instance void System.Printing.PrintSystemJobInfo::set_JobIdentifier(int32 newJobIdentifier)
0x17571  ldarg.0
0x17572  dup
0x17573  ldfld    string[] System.Printing.PrintSystemJobInfo::refreshPropertiesFilter
0x17578  call     instance void System.Printing.PrintSystemJobInfo::PopulateJobProperties(string[] propertiesAsStrings)
0x1757d  leave.s  loc_175A2
0x1757f  stloc.1
0x17580  ldloc.1
0x17581  call     instance int32 System.Printing.InternalPrintSystemException::get_HResult()
0x17586  ldc.i4.s 0x57
0x17588  call     modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 HRESULT_FROM_WIN32(modopt([mscorlib]System.Runtime.CompilerServices.IsLong) unsigned int32 x)
0x1758d  beq.s    loc_175A0
0x1758f  ldloc.1
0x17590  call     instance int32 System.Printing.InternalPrintSystemException::get_HResult()
0x17595  ldstr    aPrintsystemexc_21// "PrintSystemException.PrintSystemJobInfo"...
0x1759a  call     class [mscorlib]System.Exception System.Printing.PrintSystemJobInfo::CreatePrintJobException(int32 hresult, string messageId)
0x1759f  throw
0x175a0  leave.s  loc_175A2
0x175a2  ldloc.2
0x175a3  call     instance void System.Windows.Xps.XpsDocumentWriter::EndPrintFixedDocumentSequence()
0x175a8  ldloc.3
0x175a9  call     instance void [ReachFramework]System.Windows.Xps.Packaging.XpsDocument::Close()
0x175ae  leave.s  loc_175C1
0x175b0  stloc.s  5
0x175b2  ldstr    aPrintsystemexc_21// "PrintSystemException.PrintSystemJobInfo"...
0x175b7  ldloc.s  5
0x175b9  call     class [mscorlib]System.Exception System.Printing.PrintSystemJobInfo::CreatePrintJobException(string messageId, class [mscorlib]System.Exception innerException)
0x175be  throw
0x175bf  leave.s  loc_175C1
0x175c1  ldarg.0
0x175c2  call     void [mscorlib]System.GC::KeepAlive(object)
0x175c7  leave.s  loc_175D1
0x175c9  ldarg.0
0x175ca  ldc.i4.1
0x175cb  call     instance void System.Printing.PrintSystemObject::Dispose([hasfieldmarshal] bool A_0)
0x175d0  endfinally
0x175d1  ret
```
