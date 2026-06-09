# System.Printing.PrintSystemJobInfo::.ctor_2

- ea: `0x175e0`
- end: `0x17684`
- name: `System.Printing.PrintSystemJobInfo::.ctor_2`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x17740`

## callees

- `0xa7c0`
- `0xa980`
- `0x172a0`
- `0x175e0`
- `0x17960`
- `0x183d0`
- `0x18550`
- `0x18970`
- `0x18980`
- `0x18c60`
- `0x18d90`

## string_xrefs

- `0x17614`: `PrintSystemException.PrintSystemJobInfo.Create`
- `0x1766c`: `PrintSystemException.PrintSystemJobInfo.Create`

## pseudocode

```c

```

## disassembly

```asm
0x175e0  ldnull
0x175e1  stloc.2
0x175e2  ldarg.2
0x175e3  brfalse.s loc_175E9
0x175e5  ldarg.2
0x175e6  stloc.1
0x175e7  br.s     loc_175EF
0x175e9  ldsfld   string System.Printing.PrintSystemJobInfo::defaultJobName
0x175ee  stloc.1
0x175ef  ldarg.0
0x175f0  ldloc.1
0x175f1  stfld    string System.Printing.PrintSystemJobInfo::jobName
0x175f6  ldarg.0
0x175f7  ldarg.1
0x175f8  stfld    class System.Printing.PrintQueue System.Printing.PrintSystemJobInfo::hostingPrintQueue
0x175fd  ldarg.0
0x175fe  ldnull
0x175ff  stfld    class System.Printing.PrintSystemDispatcherObject System.Printing.PrintSystemJobInfo::accessVerifier
0x17604  ldarg.0
0x17605  call     instance void System.Printing.PrintSystemObject::.ctor()
0x1760a  ldarg.0
0x1760b  ldfld    class System.Printing.PrintQueue System.Printing.PrintSystemJobInfo::hostingPrintQueue
0x17610  brfalse.s loc_17614
0x17612  leave.s  loc_17629
0x17614  ldstr    aPrintsystemexc_21// "PrintSystemException.PrintSystemJobInfo"...
0x17619  ldstr    aPrintqueue_0// "printQueue"
0x1761e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x17623  call     class [mscorlib]System.Exception System.Printing.PrintSystemJobInfo::CreatePrintJobException(string messageId, class [mscorlib]System.Exception innerException)
0x17628  throw
0x17629  nop
0x1762a  ldarg.0
0x1762b  call     instance void System.Printing.PrintSystemJobInfo::Initialize()
0x17630  ldarg.0
0x17631  ldfld    class System.Printing.PrintQueue System.Printing.PrintSystemJobInfo::hostingPrintQueue
0x17636  ldarg.0
0x17637  ldfld    string System.Printing.PrintSystemJobInfo::jobName
0x1763c  ldc.i4.0
0x1763d  ldarg.3
0x1763e  newobj   instance void System.Printing.PrintQueueStream::.ctor(class System.Printing.PrintQueue printQueue, string printJobName, [hasfieldmarshal] bool commitDataOnClose, class [ReachFramework]System.Printing.PrintTicket printTicket)
0x17643  stloc.0
0x17644  ldarg.0
0x17645  ldloc.0
0x17646  stfld    class System.Printing.PrintQueueStream System.Printing.PrintSystemJobInfo::printStream
0x1764b  ldarg.0
0x1764c  ldloc.0
0x1764d  call     instance int32 System.Printing.PrintQueueStream::get_JobIdentifier()
0x17652  call     instance void System.Printing.PrintSystemJobInfo::set_JobIdentifier(int32 newJobIdentifier)
0x17657  ldarg.0
0x17658  dup
0x17659  ldfld    string[] System.Printing.PrintSystemJobInfo::refreshPropertiesFilter
0x1765e  call     instance void System.Printing.PrintSystemJobInfo::PopulateJobProperties(string[] propertiesAsStrings)
0x17663  leave.s  loc_17679
0x17665  stloc.2
0x17666  ldloc.2
0x17667  call     instance int32 System.Printing.InternalPrintSystemException::get_HResult()
0x1766c  ldstr    aPrintsystemexc_21// "PrintSystemException.PrintSystemJobInfo"...
0x17671  call     class [mscorlib]System.Exception System.Printing.PrintSystemJobInfo::CreatePrintJobException(int32 hresult, string messageId)
0x17676  throw
0x17677  leave.s  loc_17679
0x17679  leave.s  loc_17683
0x1767b  ldarg.0
0x1767c  ldc.i4.1
0x1767d  call     instance void System.Printing.PrintSystemObject::Dispose([hasfieldmarshal] bool A_0)
0x17682  endfinally
0x17683  ret
```
