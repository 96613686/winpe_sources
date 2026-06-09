# System.Printing.PrintQueue::CreatePropertiesDelegates

- ea: `0x10f10`
- end: `0x110c1`
- name: `System.Printing.PrintQueue::CreatePropertiesDelegates`
- size: `433`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x110f0`

## callees

- `0x13ea0`
- `0x13ef0`
- `0x13f90`
- `0x14170`
- `0x141c0`
- `0x14210`
- `0x142b0`
- `0x14300`

## pseudocode

```c

```

## disassembly

```asm
0x10f10  ldsfld   string[] System.Printing.PrintQueue::secondaryAttributeNames
0x10f15  ldlen
0x10f16  stloc.1
0x10f17  ldsfld   string[] System.Printing.PrintQueue::primaryAttributeNames
0x10f1c  ldlen
0x10f1d  ldloc.1
0x10f1e  add
0x10f1f  newarr   [mscorlib]System.MulticastDelegate
0x10f24  stloc.0
0x10f25  ldloc.0
0x10f26  ldc.i4.0
0x10f27  ldarg.0
0x10f28  dup
0x10f29  ldvirtftn instance void System.Printing.PrintQueue::set_ShareName(string inShareName)
0x10f2f  newobj   instance void StringValueChanged::.ctor(object A_0, native int A_1)
0x10f34  stelem.ref
0x10f35  ldloc.0
0x10f36  ldc.i4.1
0x10f37  ldarg.0
0x10f38  dup
0x10f39  ldvirtftn instance void System.Printing.PrintQueue::set_Comment(string inComment)
0x10f3f  newobj   instance void StringValueChanged::.ctor(object A_0, native int A_1)
0x10f44  stelem.ref
0x10f45  ldloc.0
0x10f46  ldc.i4.2
0x10f47  ldarg.0
0x10f48  dup
0x10f49  ldvirtftn instance void System.Printing.PrintQueue::set_Location(string inLocation)
0x10f4f  newobj   instance void StringValueChanged::.ctor(object A_0, native int A_1)
0x10f54  stelem.ref
0x10f55  ldloc.0
0x10f56  ldc.i4.3
0x10f57  ldarg.0
0x10f58  dup
0x10f59  ldvirtftn instance void System.Printing.PrintQueue::set_Description(string inDescription)
0x10f5f  newobj   instance void StringValueChanged::.ctor(object A_0, native int A_1)
0x10f64  stelem.ref
0x10f65  ldloc.0
0x10f66  ldc.i4.4
0x10f67  ldarg.0
0x10f68  dup
0x10f69  ldvirtftn instance void System.Printing.PrintQueue::set_Priority(int32 inPriority)
0x10f6f  newobj   instance void Int32ValueChanged::.ctor(object A_0, native int A_1)
0x10f74  stelem.ref
0x10f75  ldloc.0
0x10f76  ldc.i4.5
0x10f77  ldarg.0
0x10f78  dup
0x10f79  ldvirtftn instance void System.Printing.PrintQueue::set_DefaultPriority(int32 inDefaultPriority)
0x10f7f  newobj   instance void Int32ValueChanged::.ctor(object A_0, native int A_1)
0x10f84  stelem.ref
0x10f85  ldloc.0
0x10f86  ldc.i4.6
0x10f87  ldarg.0
0x10f88  dup
0x10f89  ldvirtftn instance void System.Printing.PrintQueue::set_StartTimeOfDay(int32 inStartTime)
0x10f8f  newobj   instance void Int32ValueChanged::.ctor(object A_0, native int A_1)
0x10f94  stelem.ref
0x10f95  ldloc.0
0x10f96  ldc.i4.7
0x10f97  ldarg.0
0x10f98  dup
0x10f99  ldvirtftn instance void System.Printing.PrintQueue::set_UntilTimeOfDay(int32 inUntilTime)
0x10f9f  newobj   instance void Int32ValueChanged::.ctor(object A_0, native int A_1)
0x10fa4  stelem.ref
0x10fa5  ldloc.0
0x10fa6  ldc.i4.8
0x10fa7  ldnull
0x10fa8  stelem.ref
0x10fa9  ldloc.0
0x10faa  ldc.i4.s 9
0x10fac  ldarg.0
0x10fad  dup
0x10fae  ldvirtftn instance void System.Printing.PrintQueue::set_NumberOfJobs(int32 numOfJobs)
0x10fb4  newobj   instance void Int32ValueChanged::.ctor(object A_0, native int A_1)
0x10fb9  stelem.ref
0x10fba  ldloc.0
0x10fbb  ldc.i4.s 0xA
0x10fbd  ldnull
0x10fbe  stelem.ref
0x10fbf  ldloc.0
0x10fc0  ldc.i4.s 0xB
0x10fc2  ldarg.0
0x10fc3  dup
0x10fc4  ldvirtftn instance void System.Printing.PrintQueue::set_QueueDriver(class System.Printing.PrintDriver driver)
0x10fca  newobj   instance void DriverValueChanged::.ctor(object A_0, native int A_1)
0x10fcf  stelem.ref
0x10fd0  ldloc.0
0x10fd1  ldc.i4.s 0xC
0x10fd3  ldarg.0
0x10fd4  dup
0x10fd5  ldvirtftn instance void System.Printing.PrintQueue::set_QueuePort(class System.Printing.PrintPort port)
0x10fdb  newobj   instance void PortValueChanged::.ctor(object A_0, native int A_1)
0x10fe0  stelem.ref
0x10fe1  ldloc.0
0x10fe2  ldc.i4.s 0xD
0x10fe4  ldarg.0
0x10fe5  dup
0x10fe6  ldvirtftn instance void System.Printing.PrintQueue::set_QueuePrintProcessor(class System.Printing.PrintProcessor printProcessor)
0x10fec  newobj   instance void PrintProcessorValueChanged::.ctor(object A_0, native int A_1)
0x10ff1  stelem.ref
0x10ff2  ldloc.0
0x10ff3  ldc.i4.s 0xE
0x10ff5  ldnull
0x10ff6  stelem.ref
0x10ff7  ldloc.0
0x10ff8  ldc.i4.s 0xF
0x10ffa  ldnull
0x10ffb  stelem.ref
0x10ffc  ldloc.0
0x10ffd  ldc.i4.s 0x10
0x10fff  ldarg.0
0x11000  dup
0x11001  ldvirtftn instance void System.Printing.PrintQueue::set_SeparatorFile(string inSeparatorFile)
0x11007  newobj   instance void StringValueChanged::.ctor(object A_0, native int A_1)
0x1100c  stelem.ref
0x1100d  ldloc.0
0x1100e  ldc.i4.s 0x11
0x11010  ldarg.0
0x11011  dup
0x11012  ldvirtftn instance void System.Printing.PrintQueue::set_DefaultPrintTicket(class [ReachFramework]System.Printing.PrintTicket newDefaultPrintTicket)
0x11018  newobj   instance void PrintTicketValueChanged::.ctor(object A_0, native int A_1)
0x1101d  stelem.ref
0x1101e  ldloc.0
0x1101f  ldc.i4.s 0x12
0x11021  ldarg.0
0x11022  dup
0x11023  ldvirtftn instance void System.Printing.PrintQueue::set_UserPrintTicket(class [ReachFramework]System.Printing.PrintTicket newUserPrintTicket)
0x11029  newobj   instance void PrintTicketValueChanged::.ctor(object A_0, native int A_1)
0x1102e  stelem.ref
0x1102f  ldloc.0
0x11030  ldc.i4.s 0x13
0x11032  ldarg.0
0x11033  ldftn    instance void System.Printing.PrintQueue::set_IsXpsDevice([hasfieldmarshal] bool isMetroEnabled)
0x11039  newobj   instance void BooleanValueChanged::.ctor(object A_0, native int A_1)
0x1103e  stelem.ref
0x1103f  ldloc.0
0x11040  ldc.i4.s 0x14
0x11042  ldarg.0
0x11043  ldftn    instance void System.Printing.PrintQueue::set_HostingPrintServerName(string printServerName)
0x11049  newobj   instance void StringValueChanged::.ctor(object A_0, native int A_1)
0x1104e  stelem.ref
0x1104f  ldloc.0
0x11050  ldc.i4.s 0x15
0x11052  ldarg.0
0x11053  ldftn    instance void System.Printing.PrintQueue::set_QueueDriverName(string driverName)
0x11059  newobj   instance void StringValueChanged::.ctor(object A_0, native int A_1)
0x1105e  stelem.ref
0x1105f  ldloc.0
0x11060  ldc.i4.s 0x16
0x11062  ldarg.0
0x11063  ldftn    instance void System.Printing.PrintQueue::set_QueuePrintProcessorName(string printProcessorName)
0x11069  newobj   instance void StringValueChanged::.ctor(object A_0, native int A_1)
0x1106e  stelem.ref
0x1106f  ldloc.0
0x11070  ldc.i4.s 0x17
0x11072  ldarg.0
0x11073  ldftn    instance void System.Printing.PrintQueue::set_QueuePortName(string portName)
0x11079  newobj   instance void StringValueChanged::.ctor(object A_0, native int A_1)
0x1107e  stelem.ref
0x1107f  ldloc.0
0x11080  ldc.i4.s 0x18
0x11082  ldarg.0
0x11083  ldftn    instance void System.Printing.PrintQueue::set_DefaultDevMode(unsigned int8[] devMode)
0x11089  newobj   instance void ByteArrayValueChanged::.ctor(object A_0, native int A_1)
0x1108e  stelem.ref
0x1108f  ldloc.0
0x11090  ldc.i4.s 0x19
0x11092  ldarg.0
0x11093  ldftn    instance void System.Printing.PrintQueue::set_UserDevMode(unsigned int8[] devMode)
0x11099  newobj   instance void ByteArrayValueChanged::.ctor(object A_0, native int A_1)
0x1109e  stelem.ref
0x1109f  ldloc.0
0x110a0  ldc.i4.s 0x1A
0x110a2  ldarg.0
0x110a3  ldftn    instance void System.Printing.PrintQueue::set_Status(int32 status)
0x110a9  newobj   instance void Int32ValueChanged::.ctor(object A_0, native int A_1)
0x110ae  stelem.ref
0x110af  ldloc.0
0x110b0  ldc.i4.s 0x1B
0x110b2  ldarg.0
0x110b3  ldftn    instance void System.Printing.PrintQueue::set_Attributes(int32 attributes)
0x110b9  newobj   instance void Int32ValueChanged::.ctor(object A_0, native int A_1)
0x110be  stelem.ref
0x110bf  ldloc.0
0x110c0  ret
```
