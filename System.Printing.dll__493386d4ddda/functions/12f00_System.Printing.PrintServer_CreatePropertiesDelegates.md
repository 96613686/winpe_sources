# System.Printing.PrintServer::CreatePropertiesDelegates

- ea: `0x12f00`
- end: `0x12fc5`
- name: `System.Printing.PrintServer::CreatePropertiesDelegates`
- size: `197`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x12fd0`

## callees

- `0x13ea0`
- `0x13ef0`
- `0x13f90`
- `0x13fe0`
- `0x14030`

## pseudocode

```c

```

## disassembly

```asm
0x12f00  ldsfld   string[] System.Printing.PrintServer::primaryAttributeNames
0x12f05  ldlen
0x12f06  newarr   [mscorlib]System.MulticastDelegate
0x12f0b  stloc.0
0x12f0c  ldloc.0
0x12f0d  ldc.i4.0
0x12f0e  ldarg.0
0x12f0f  ldftn    instance void System.Printing.PrintServer::set_DefaultSpoolDirectory(string value)
0x12f15  newobj   instance void StringValueChanged::.ctor(object A_0, native int A_1)
0x12f1a  stelem.ref
0x12f1b  ldloc.0
0x12f1c  ldc.i4.1
0x12f1d  ldarg.0
0x12f1e  ldftn    instance void System.Printing.PrintServer::set_PortThreadPriority(valuetype [mscorlib]System.Threading.ThreadPriority value)
0x12f24  newobj   instance void ThreadPriorityValueChanged::.ctor(object A_0, native int A_1)
0x12f29  stelem.ref
0x12f2a  ldloc.0
0x12f2b  ldc.i4.2
0x12f2c  ldarg.0
0x12f2d  ldftn    instance void System.Printing.PrintServer::set_DefaultPortThreadPriority(valuetype [mscorlib]System.Threading.ThreadPriority value)
0x12f33  newobj   instance void ThreadPriorityValueChanged::.ctor(object A_0, native int A_1)
0x12f38  stelem.ref
0x12f39  ldloc.0
0x12f3a  ldc.i4.3
0x12f3b  ldarg.0
0x12f3c  ldftn    instance void System.Printing.PrintServer::set_SchedulerPriority(valuetype [mscorlib]System.Threading.ThreadPriority value)
0x12f42  newobj   instance void ThreadPriorityValueChanged::.ctor(object A_0, native int A_1)
0x12f47  stelem.ref
0x12f48  ldloc.0
0x12f49  ldc.i4.4
0x12f4a  ldarg.0
0x12f4b  ldftn    instance void System.Printing.PrintServer::set_DefaultSchedulerPriority(valuetype [mscorlib]System.Threading.ThreadPriority value)
0x12f51  newobj   instance void ThreadPriorityValueChanged::.ctor(object A_0, native int A_1)
0x12f56  stelem.ref
0x12f57  ldloc.0
0x12f58  ldc.i4.5
0x12f59  ldarg.0
0x12f5a  ldftn    instance void System.Printing.PrintServer::set_BeepEnabled([hasfieldmarshal] bool value)
0x12f60  newobj   instance void BooleanValueChanged::.ctor(object A_0, native int A_1)
0x12f65  stelem.ref
0x12f66  ldloc.0
0x12f67  ldc.i4.6
0x12f68  ldarg.0
0x12f69  ldftn    instance void System.Printing.PrintServer::set_NetPopup([hasfieldmarshal] bool value)
0x12f6f  newobj   instance void BooleanValueChanged::.ctor(object A_0, native int A_1)
0x12f74  stelem.ref
0x12f75  ldloc.0
0x12f76  ldc.i4.7
0x12f77  ldarg.0
0x12f78  ldftn    instance void System.Printing.PrintServer::set_EventLog(valuetype System.Printing.PrintServerEventLoggingTypes value)
0x12f7e  newobj   instance void PrintServerEventLoggingValueChanged::.ctor(object A_0, native int A_1)
0x12f83  stelem.ref
0x12f84  ldloc.0
0x12f85  ldc.i4.8
0x12f86  ldarg.0
0x12f87  ldftn    instance void System.Printing.PrintServer::set_MajorVersion(int32 value)
0x12f8d  newobj   instance void Int32ValueChanged::.ctor(object A_0, native int A_1)
0x12f92  stelem.ref
0x12f93  ldloc.0
0x12f94  ldc.i4.s 9
0x12f96  ldarg.0
0x12f97  ldftn    instance void System.Printing.PrintServer::set_MinorVersion(int32 value)
0x12f9d  newobj   instance void Int32ValueChanged::.ctor(object A_0, native int A_1)
0x12fa2  stelem.ref
0x12fa3  ldloc.0
0x12fa4  ldc.i4.s 0xA
0x12fa6  ldarg.0
0x12fa7  ldftn    instance void System.Printing.PrintServer::set_RestartJobOnPoolTimeout(int32 value)
0x12fad  newobj   instance void Int32ValueChanged::.ctor(object A_0, native int A_1)
0x12fb2  stelem.ref
0x12fb3  ldloc.0
0x12fb4  ldc.i4.s 0xB
0x12fb6  ldarg.0
0x12fb7  ldftn    instance void System.Printing.PrintServer::set_RestartJobOnPoolEnabled([hasfieldmarshal] bool value)
0x12fbd  newobj   instance void BooleanValueChanged::.ctor(object A_0, native int A_1)
0x12fc2  stelem.ref
0x12fc3  ldloc.0
0x12fc4  ret
```
