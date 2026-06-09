# System.Printing.PrintSystemJobInfo::.ctor

- ea: `0x17380`
- end: `0x173db`
- name: `System.Printing.PrintSystemJobInfo::.ctor`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x182d0`

## callees

- `0xa7c0`
- `0xa980`
- `0x17380`
- `0x183d0`
- `0x18970`

## string_xrefs

- `0x173ae`: `PrintSystemException.PrintSystemJobInfo.Create`

## pseudocode

```c

```

## disassembly

```asm
0x17380  ldarg.0
0x17381  ldsfld   string System.Printing.PrintSystemJobInfo::defaultJobName
0x17386  stfld    string System.Printing.PrintSystemJobInfo::jobName
0x1738b  ldarg.0
0x1738c  ldarg.1
0x1738d  stfld    class System.Printing.PrintQueue System.Printing.PrintSystemJobInfo::hostingPrintQueue
0x17392  ldarg.0
0x17393  ldnull
0x17394  stfld    class System.Printing.PrintSystemDispatcherObject System.Printing.PrintSystemJobInfo::accessVerifier
0x17399  ldarg.0
0x1739a  ldnull
0x1739b  stfld    string[] System.Printing.PrintSystemJobInfo::refreshPropertiesFilter
0x173a0  ldarg.0
0x173a1  call     instance void System.Printing.PrintSystemObject::.ctor()
0x173a6  ldarg.0
0x173a7  ldfld    class System.Printing.PrintQueue System.Printing.PrintSystemJobInfo::hostingPrintQueue
0x173ac  brtrue.s loc_173C3
0x173ae  ldstr    aPrintsystemexc_21// "PrintSystemException.PrintSystemJobInfo"...
0x173b3  ldstr    aPrintqueue_0// "printQueue"
0x173b8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x173bd  call     class [mscorlib]System.Exception System.Printing.PrintSystemJobInfo::CreatePrintJobException(string messageId, class [mscorlib]System.Exception innerException)
0x173c2  throw
0x173c3  ldarg.0
0x173c4  call     instance void System.Printing.PrintSystemJobInfo::Initialize()
0x173c9  ldarg.0
0x173ca  ldarg.2
0x173cb  stfld    string[] System.Printing.PrintSystemJobInfo::refreshPropertiesFilter
0x173d0  leave.s  loc_173DA
0x173d2  ldarg.0
0x173d3  ldc.i4.1
0x173d4  call     instance void System.Printing.PrintSystemObject::Dispose([hasfieldmarshal] bool A_0)
0x173d9  endfinally
0x173da  ret
```
