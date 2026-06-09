# System.Printing.PrintSystemJobInfo::CreatePropertiesDelegates

- ea: `0x182e0`
- end: `0x183c1`
- name: `System.Printing.PrintSystemJobInfo::CreatePropertiesDelegates`
- size: `225`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18420`

## callees

- `0x13ea0`
- `0x13ef0`
- `0x14440`

## pseudocode

```c

```

## disassembly

```asm
0x182e0  ldsfld   string[] System.Printing.PrintSystemJobInfo::secondaryAttributeNames
0x182e5  ldlen
0x182e6  stloc.1
0x182e7  ldsfld   string[] System.Printing.PrintSystemJobInfo::primaryAttributeNames
0x182ec  ldlen
0x182ed  ldloc.1
0x182ee  add
0x182ef  newarr   [mscorlib]System.MulticastDelegate
0x182f4  stloc.0
0x182f5  ldloc.0
0x182f6  ldc.i4.0
0x182f7  ldarg.0
0x182f8  ldftn    instance void System.Printing.PrintSystemJobInfo::set_JobIdentifier(int32 newJobIdentifier)
0x182fe  newobj   instance void Int32ValueChanged::.ctor(object A_0, native int A_1)
0x18303  stelem.ref
0x18304  ldloc.0
0x18305  ldc.i4.1
0x18306  ldarg.0
0x18307  ldftn    instance void System.Printing.PrintSystemJobInfo::set_Submitter(string newSubmitter)
0x1830d  newobj   instance void StringValueChanged::.ctor(object A_0, native int A_1)
0x18312  stelem.ref
0x18313  ldloc.0
0x18314  ldc.i4.2
0x18315  ldnull
0x18316  stelem.ref
0x18317  ldloc.0
0x18318  ldc.i4.3
0x18319  ldarg.0
0x1831a  ldftn    instance void System.Printing.PrintSystemJobInfo::set_PositionInPrintQueue(int32 positionInQueue)
0x18320  newobj   instance void Int32ValueChanged::.ctor(object A_0, native int A_1)
0x18325  stelem.ref
0x18326  ldloc.0
0x18327  ldc.i4.4
0x18328  ldarg.0
0x18329  ldftn    instance void System.Printing.PrintSystemJobInfo::set_StartTimeOfDay(int32 newStartTime)
0x1832f  newobj   instance void Int32ValueChanged::.ctor(object A_0, native int A_1)
0x18334  stelem.ref
0x18335  ldloc.0
0x18336  ldc.i4.5
0x18337  ldarg.0
0x18338  ldftn    instance void System.Printing.PrintSystemJobInfo::set_UntilTimeOfDay(int32 newUntilTime)
0x1833e  newobj   instance void Int32ValueChanged::.ctor(object A_0, native int A_1)
0x18343  stelem.ref
0x18344  ldloc.0
0x18345  ldc.i4.6
0x18346  ldarg.0
0x18347  ldftn    instance void System.Printing.PrintSystemJobInfo::set_NumberOfPages(int32 newNumberOfPages)
0x1834d  newobj   instance void Int32ValueChanged::.ctor(object A_0, native int A_1)
0x18352  stelem.ref
0x18353  ldloc.0
0x18354  ldc.i4.7
0x18355  ldarg.0
0x18356  ldftn    instance void System.Printing.PrintSystemJobInfo::set_NumberOfPagesPrinted(int32 newNumberOfPagesPrinted)
0x1835c  newobj   instance void Int32ValueChanged::.ctor(object A_0, native int A_1)
0x18361  stelem.ref
0x18362  ldloc.0
0x18363  ldc.i4.8
0x18364  ldarg.0
0x18365  ldftn    instance void System.Printing.PrintSystemJobInfo::set_JobSize(int32 newJobSize)
0x1836b  newobj   instance void Int32ValueChanged::.ctor(object A_0, native int A_1)
0x18370  stelem.ref
0x18371  ldloc.0
0x18372  ldc.i4.s 9
0x18374  ldarg.0
0x18375  ldftn    instance void System.Printing.PrintSystemJobInfo::set_TimeJobSubmitted(valuetype [mscorlib]System.DateTime newTimeJobSubmitted)
0x1837b  newobj   instance void SystemDateTimeValueChanged::.ctor(object A_0, native int A_1)
0x18380  stelem.ref
0x18381  ldloc.0
0x18382  ldc.i4.s 0xA
0x18384  ldnull
0x18385  stelem.ref
0x18386  ldloc.0
0x18387  ldc.i4.s 0xB
0x18389  ldnull
0x1838a  stelem.ref
0x1838b  ldloc.0
0x1838c  ldc.i4.s 0xC
0x1838e  ldnull
0x1838f  stelem.ref
0x18390  ldloc.0
0x18391  ldc.i4.s 0xD
0x18393  ldnull
0x18394  stelem.ref
0x18395  ldloc.0
0x18396  ldc.i4.s 0xE
0x18398  ldarg.0
0x18399  ldftn    instance void System.Printing.PrintSystemJobInfo::set_PrioritySecondary(int32 newPrioritySecondary)
0x1839f  newobj   instance void Int32ValueChanged::.ctor(object A_0, native int A_1)
0x183a4  stelem.ref
0x183a5  ldloc.0
0x183a6  ldc.i4.s 0xF
0x183a8  ldarg.0
0x183a9  ldftn    instance void System.Printing.PrintSystemJobInfo::set_JobStatusSecondary(int32 status)
0x183af  newobj   instance void Int32ValueChanged::.ctor(object A_0, native int A_1)
0x183b4  stelem.ref
0x183b5  ldloc.0
0x183b6  ldc.i4.s 0x10
0x183b8  ldnull
0x183b9  stelem.ref
0x183ba  ldloc.0
0x183bb  ldc.i4.s 0x11
0x183bd  ldnull
0x183be  stelem.ref
0x183bf  ldloc.0
0x183c0  ret
```
