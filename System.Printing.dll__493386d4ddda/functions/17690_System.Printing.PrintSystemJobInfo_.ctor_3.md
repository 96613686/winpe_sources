# System.Printing.PrintSystemJobInfo::.ctor_3

- ea: `0x17690`
- end: `0x1772d`
- name: `System.Printing.PrintSystemJobInfo::.ctor_3`
- size: `157`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0xa7c0`
- `0xa980`
- `0x17690`
- `0x17960`
- `0x183d0`
- `0x18550`
- `0x18970`
- `0x18c60`
- `0x18d90`

## string_xrefs

- `0x176c2`: `PrintSystemException.PrintSystemJobInfo.Create`
- `0x17714`: `PrintSystemException.PrintSystemJobInfo.Create`

## pseudocode

```c

```

## disassembly

```asm
0x17690  ldnull
0x17691  stloc.1
0x17692  ldarg.0
0x17693  ldnull
0x17694  stfld    class System.Printing.PrintQueueStream System.Printing.PrintSystemJobInfo::printStream
0x17699  ldarg.0
0x1769a  ldsfld   string System.Printing.PrintSystemJobInfo::defaultJobName
0x1769f  stfld    string System.Printing.PrintSystemJobInfo::jobName
0x176a4  ldarg.0
0x176a5  ldarg.1
0x176a6  stfld    class System.Printing.PrintQueue System.Printing.PrintSystemJobInfo::hostingPrintQueue
0x176ab  ldarg.0
0x176ac  ldnull
0x176ad  stfld    class System.Printing.PrintSystemDispatcherObject System.Printing.PrintSystemJobInfo::accessVerifier
0x176b2  ldarg.0
0x176b3  call     instance void System.Printing.PrintSystemObject::.ctor()
0x176b8  ldarg.0
0x176b9  ldfld    class System.Printing.PrintQueue System.Printing.PrintSystemJobInfo::hostingPrintQueue
0x176be  brfalse.s loc_176C2
0x176c0  leave.s  loc_176D7
0x176c2  ldstr    aPrintsystemexc_21// "PrintSystemException.PrintSystemJobInfo"...
0x176c7  ldstr    aPrintqueue_0// "printQueue"
0x176cc  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x176d1  call     class [mscorlib]System.Exception System.Printing.PrintSystemJobInfo::CreatePrintJobException(string messageId, class [mscorlib]System.Exception innerException)
0x176d6  throw
0x176d7  nop
0x176d8  ldarg.0
0x176d9  call     instance void System.Printing.PrintSystemJobInfo::Initialize()
0x176de  ldarg.0
0x176df  ldfld    class System.Printing.PrintQueue System.Printing.PrintSystemJobInfo::hostingPrintQueue
0x176e4  ldarg.0
0x176e5  ldfld    string System.Printing.PrintSystemJobInfo::jobName
0x176ea  ldc.i4.0
0x176eb  ldarg.2
0x176ec  newobj   instance void System.Printing.PrintQueueStream::.ctor(class System.Printing.PrintQueue printQueue, string printJobName, [hasfieldmarshal] bool commitDataOnClose, class [ReachFramework]System.Printing.PrintTicket printTicket)
0x176f1  stloc.0
0x176f2  ldarg.0
0x176f3  ldloc.0
0x176f4  stfld    class System.Printing.PrintQueueStream System.Printing.PrintSystemJobInfo::printStream
0x176f9  ldarg.0
0x176fa  ldloc.0
0x176fb  call     instance int32 System.Printing.PrintQueueStream::get_JobIdentifier()
0x17700  call     instance void System.Printing.PrintSystemJobInfo::set_JobIdentifier(int32 newJobIdentifier)
0x17705  ldarg.0
0x17706  dup
0x17707  ldfld    string[] System.Printing.PrintSystemJobInfo::refreshPropertiesFilter
0x1770c  call     instance void System.Printing.PrintSystemJobInfo::PopulateJobProperties(string[] propertiesAsStrings)
0x17711  leave.s  loc_17722
0x17713  stloc.1
0x17714  ldstr    aPrintsystemexc_21// "PrintSystemException.PrintSystemJobInfo"...
0x17719  ldloc.1
0x1771a  call     class [mscorlib]System.Exception System.Printing.PrintSystemJobInfo::CreatePrintJobException(string messageId, class [mscorlib]System.Exception innerException)
0x1771f  throw
0x17720  leave.s  loc_17722
0x17722  leave.s  loc_1772C
0x17724  ldarg.0
0x17725  ldc.i4.1
0x17726  call     instance void System.Printing.PrintSystemObject::Dispose([hasfieldmarshal] bool A_0)
0x1772b  endfinally
0x1772c  ret
```
