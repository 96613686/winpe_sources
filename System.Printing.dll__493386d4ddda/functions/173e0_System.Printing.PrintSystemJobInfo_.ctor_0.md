# System.Printing.PrintSystemJobInfo::.ctor_0

- ea: `0x173e0`
- end: `0x17458`
- name: `System.Printing.PrintSystemJobInfo::.ctor_0`
- size: `120`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x17760`

## callees

- `0xa7c0`
- `0xa980`
- `0x172a0`
- `0x173e0`
- `0x183d0`
- `0x18550`
- `0x18970`
- `0x18980`

## string_xrefs

- `0x17410`: `PrintSystemException.PrintSystemJobInfo.Create`
- `0x17440`: `PrintSystemException.PrintSystemJobInfo.Create`

## pseudocode

```c

```

## disassembly

```asm
0x173e0  ldnull
0x173e1  stloc.0
0x173e2  ldarg.0
0x173e3  ldarg.2
0x173e4  stfld    int32 System.Printing.PrintSystemJobInfo::jobIdentifier
0x173e9  ldarg.0
0x173ea  ldsfld   string System.Printing.PrintSystemJobInfo::defaultJobName
0x173ef  stfld    string System.Printing.PrintSystemJobInfo::jobName
0x173f4  ldarg.0
0x173f5  ldarg.1
0x173f6  stfld    class System.Printing.PrintQueue System.Printing.PrintSystemJobInfo::hostingPrintQueue
0x173fb  ldarg.0
0x173fc  ldnull
0x173fd  stfld    class System.Printing.PrintSystemDispatcherObject System.Printing.PrintSystemJobInfo::accessVerifier
0x17402  ldarg.0
0x17403  call     instance void System.Printing.PrintSystemObject::.ctor()
0x17408  ldarg.0
0x17409  ldfld    class System.Printing.PrintQueue System.Printing.PrintSystemJobInfo::hostingPrintQueue
0x1740e  brtrue.s loc_17425
0x17410  ldstr    aPrintsystemexc_21// "PrintSystemException.PrintSystemJobInfo"...
0x17415  ldstr    aPrintqueue_0// "printQueue"
0x1741a  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1741f  call     class [mscorlib]System.Exception System.Printing.PrintSystemJobInfo::CreatePrintJobException(string messageId, class [mscorlib]System.Exception innerException)
0x17424  throw
0x17425  ldarg.0
0x17426  call     instance void System.Printing.PrintSystemJobInfo::Initialize()
0x1742b  ldarg.0
0x1742c  dup
0x1742d  ldfld    string[] System.Printing.PrintSystemJobInfo::refreshPropertiesFilter
0x17432  call     instance void System.Printing.PrintSystemJobInfo::PopulateJobProperties(string[] propertiesAsStrings)
0x17437  leave.s  loc_1744D
0x17439  stloc.0
0x1743a  ldloc.0
0x1743b  call     instance int32 System.Printing.InternalPrintSystemException::get_HResult()
0x17440  ldstr    aPrintsystemexc_21// "PrintSystemException.PrintSystemJobInfo"...
0x17445  call     class [mscorlib]System.Exception System.Printing.PrintSystemJobInfo::CreatePrintJobException(int32 hresult, string messageId)
0x1744a  throw
0x1744b  leave.s  loc_1744D
0x1744d  leave.s  loc_17457
0x1744f  ldarg.0
0x17450  ldc.i4.1
0x17451  call     instance void System.Printing.PrintSystemObject::Dispose([hasfieldmarshal] bool A_0)
0x17456  endfinally
0x17457  ret
```
