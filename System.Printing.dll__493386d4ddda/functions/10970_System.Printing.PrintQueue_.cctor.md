# System.Printing.PrintQueue::.cctor

- ea: `0x10970`
- end: `0x10f0d`
- name: `System.Printing.PrintQueue::.cctor`
- size: `1437`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0xac40`
- `0x10970`

## string_xrefs

- `0x1097c`: `ShareName`
- `0x1098c`: `Comment`

## pseudocode

```c

```

## disassembly

```asm
0x10970  ldc.i4.s 0x14
0x10972  newarr   [mscorlib]System.String
0x10977  stsfld   string[] System.Printing.PrintQueue::primaryAttributeNames
0x1097c  ldstr    aSharename// "ShareName"
0x10981  stloc.s  0x2F
0x10983  ldsfld   string[] System.Printing.PrintQueue::primaryAttributeNames
0x10988  ldc.i4.0
0x10989  ldloc.s  0x2F
0x1098b  stelem.ref
0x1098c  ldstr    aComment// "Comment"
0x10991  stloc.s  0x2E
0x10993  ldsfld   string[] System.Printing.PrintQueue::primaryAttributeNames
0x10998  ldc.i4.1
0x10999  ldloc.s  0x2E
0x1099b  stelem.ref
0x1099c  ldstr    aLocation// "Location"
0x109a1  stloc.s  0x2D
0x109a3  ldsfld   string[] System.Printing.PrintQueue::primaryAttributeNames
0x109a8  ldc.i4.2
0x109a9  ldloc.s  0x2D
0x109ab  stelem.ref
0x109ac  ldstr    aDescription// "Description"
0x109b1  stloc.s  0x2C
0x109b3  ldsfld   string[] System.Printing.PrintQueue::primaryAttributeNames
0x109b8  ldc.i4.3
0x109b9  ldloc.s  0x2C
0x109bb  stelem.ref
0x109bc  ldstr    aPriority// "Priority"
0x109c1  stloc.s  0x2B
0x109c3  ldsfld   string[] System.Printing.PrintQueue::primaryAttributeNames
0x109c8  ldc.i4.4
0x109c9  ldloc.s  0x2B
0x109cb  stelem.ref
0x109cc  ldstr    aDefaultpriorit// "DefaultPriority"
0x109d1  stloc.s  0x2A
0x109d3  ldsfld   string[] System.Printing.PrintQueue::primaryAttributeNames
0x109d8  ldc.i4.5
0x109d9  ldloc.s  0x2A
0x109db  stelem.ref
0x109dc  ldstr    aStarttimeofday// "StartTimeOfDay"
0x109e1  stloc.s  0x29
0x109e3  ldsfld   string[] System.Printing.PrintQueue::primaryAttributeNames
0x109e8  ldc.i4.6
0x109e9  ldloc.s  0x29
0x109eb  stelem.ref
0x109ec  ldstr    aUntiltimeofday// "UntilTimeOfDay"
0x109f1  stloc.s  0x28
0x109f3  ldsfld   string[] System.Printing.PrintQueue::primaryAttributeNames
0x109f8  ldc.i4.7
0x109f9  ldloc.s  0x28
0x109fb  stelem.ref
0x109fc  ldstr    aAveragepagespe// "AveragePagesPerMinute"
0x10a01  stloc.s  0x27
0x10a03  ldsfld   string[] System.Printing.PrintQueue::primaryAttributeNames
0x10a08  ldc.i4.8
0x10a09  ldloc.s  0x27
0x10a0b  stelem.ref
0x10a0c  ldstr    aNumberofjobs// "NumberOfJobs"
0x10a11  stloc.s  0x26
0x10a13  ldsfld   string[] System.Printing.PrintQueue::primaryAttributeNames
0x10a18  ldc.i4.s 9
0x10a1a  ldloc.s  0x26
0x10a1c  stelem.ref
0x10a1d  ldstr    aQueueattribute// "QueueAttributes"
0x10a22  stloc.s  0x25
0x10a24  ldsfld   string[] System.Printing.PrintQueue::primaryAttributeNames
0x10a29  ldc.i4.s 0xA
0x10a2b  ldloc.s  0x25
0x10a2d  stelem.ref
0x10a2e  ldstr    aQueuedriver// "QueueDriver"
0x10a33  stloc.s  0x24
0x10a35  ldsfld   string[] System.Printing.PrintQueue::primaryAttributeNames
0x10a3a  ldc.i4.s 0xB
0x10a3c  ldloc.s  0x24
0x10a3e  stelem.ref
0x10a3f  ldstr    aQueueport// "QueuePort"
0x10a44  stloc.s  0x23
0x10a46  ldsfld   string[] System.Printing.PrintQueue::primaryAttributeNames
0x10a4b  ldc.i4.s 0xC
0x10a4d  ldloc.s  0x23
0x10a4f  stelem.ref
0x10a50  ldstr    aQueueprintproc_0// "QueuePrintProcessor"
0x10a55  stloc.s  0x22
0x10a57  ldsfld   string[] System.Printing.PrintQueue::primaryAttributeNames
0x10a5c  ldc.i4.s 0xD
0x10a5e  ldloc.s  0x22
0x10a60  stelem.ref
0x10a61  ldstr    aHostingprintse_0// "HostingPrintServer"
0x10a66  stloc.s  0x21
0x10a68  ldsfld   string[] System.Printing.PrintQueue::primaryAttributeNames
0x10a6d  ldc.i4.s 0xE
0x10a6f  ldloc.s  0x21
0x10a71  stelem.ref
0x10a72  ldstr    aQueuestatus// "QueueStatus"
0x10a77  stloc.s  0x20
0x10a79  ldsfld   string[] System.Printing.PrintQueue::primaryAttributeNames
0x10a7e  ldc.i4.s 0xF
0x10a80  ldloc.s  0x20
0x10a82  stelem.ref
0x10a83  ldstr    aSeparatorfile// "SeparatorFile"
0x10a88  stloc.s  0x1F
0x10a8a  ldsfld   string[] System.Printing.PrintQueue::primaryAttributeNames
0x10a8f  ldc.i4.s 0x10
0x10a91  ldloc.s  0x1F
0x10a93  stelem.ref
0x10a94  ldstr    aDefaultprintti// "DefaultPrintTicket"
0x10a99  stloc.s  0x1E
0x10a9b  ldsfld   string[] System.Printing.PrintQueue::primaryAttributeNames
0x10aa0  ldc.i4.s 0x11
0x10aa2  ldloc.s  0x1E
0x10aa4  stelem.ref
0x10aa5  ldstr    aUserprintticke// "UserPrintTicket"
0x10aaa  stloc.s  0x1D
0x10aac  ldsfld   string[] System.Printing.PrintQueue::primaryAttributeNames
0x10ab1  ldc.i4.s 0x12
0x10ab3  ldloc.s  0x1D
0x10ab5  stelem.ref
0x10ab6  ldstr    aIsxpsenabled// "IsXpsEnabled"
0x10abb  stloc.s  0x1C
0x10abd  ldsfld   string[] System.Printing.PrintQueue::primaryAttributeNames
0x10ac2  ldc.i4.s 0x13
0x10ac4  ldloc.s  0x1C
0x10ac6  stelem.ref
0x10ac7  ldc.i4.s 0x14
0x10ac9  newarr   [mscorlib]System.Type
0x10ace  stsfld   class [mscorlib]System.Type[] System.Printing.PrintQueue::primaryAttributeTypes
0x10ad3  ldsfld   class [mscorlib]System.Type[] System.Printing.PrintQueue::primaryAttributeTypes
0x10ad8  ldc.i4.0
0x10ad9  ldtoken  [mscorlib]System.String
0x10ade  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10ae3  stelem.ref
0x10ae4  ldsfld   class [mscorlib]System.Type[] System.Printing.PrintQueue::primaryAttributeTypes
0x10ae9  ldc.i4.1
0x10aea  ldtoken  [mscorlib]System.String
0x10aef  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10af4  stelem.ref
0x10af5  ldsfld   class [mscorlib]System.Type[] System.Printing.PrintQueue::primaryAttributeTypes
0x10afa  ldc.i4.2
0x10afb  ldtoken  [mscorlib]System.String
0x10b00  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10b05  stelem.ref
0x10b06  ldsfld   class [mscorlib]System.Type[] System.Printing.PrintQueue::primaryAttributeTypes
0x10b0b  ldc.i4.3
0x10b0c  ldtoken  [mscorlib]System.String
0x10b11  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10b16  stelem.ref
0x10b17  ldsfld   class [mscorlib]System.Type[] System.Printing.PrintQueue::primaryAttributeTypes
0x10b1c  ldc.i4.4
0x10b1d  ldtoken  [mscorlib]System.Int32
0x10b22  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10b27  stelem.ref
0x10b28  ldsfld   class [mscorlib]System.Type[] System.Printing.PrintQueue::primaryAttributeTypes
0x10b2d  ldc.i4.5
0x10b2e  ldtoken  [mscorlib]System.Int32
0x10b33  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10b38  stelem.ref
0x10b39  ldsfld   class [mscorlib]System.Type[] System.Printing.PrintQueue::primaryAttributeTypes
0x10b3e  ldc.i4.6
0x10b3f  ldtoken  [mscorlib]System.Int32
0x10b44  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10b49  stelem.ref
0x10b4a  ldsfld   class [mscorlib]System.Type[] System.Printing.PrintQueue::primaryAttributeTypes
0x10b4f  ldc.i4.7
0x10b50  ldtoken  [mscorlib]System.Int32
0x10b55  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10b5a  stelem.ref
0x10b5b  ldsfld   class [mscorlib]System.Type[] System.Printing.PrintQueue::primaryAttributeTypes
0x10b60  ldc.i4.8
0x10b61  ldtoken  [mscorlib]System.Int32
0x10b66  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10b6b  stelem.ref
0x10b6c  ldsfld   class [mscorlib]System.Type[] System.Printing.PrintQueue::primaryAttributeTypes
0x10b71  ldc.i4.s 9
0x10b73  ldtoken  [mscorlib]System.Int32
0x10b78  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10b7d  stelem.ref
0x10b7e  ldsfld   class [mscorlib]System.Type[] System.Printing.PrintQueue::primaryAttributeTypes
0x10b83  ldc.i4.s 0xA
0x10b85  ldtoken  System.Printing.PrintQueueAttributes
0x10b8a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10b8f  stelem.ref
0x10b90  ldsfld   class [mscorlib]System.Type[] System.Printing.PrintQueue::primaryAttributeTypes
0x10b95  ldc.i4.s 0xB
0x10b97  ldtoken  System.Printing.PrintDriver
0x10b9c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10ba1  stelem.ref
0x10ba2  ldsfld   class [mscorlib]System.Type[] System.Printing.PrintQueue::primaryAttributeTypes
0x10ba7  ldc.i4.s 0xC
0x10ba9  ldtoken  System.Printing.PrintPort
0x10bae  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10bb3  stelem.ref
0x10bb4  ldsfld   class [mscorlib]System.Type[] System.Printing.PrintQueue::primaryAttributeTypes
0x10bb9  ldc.i4.s 0xD
0x10bbb  ldtoken  System.Printing.PrintProcessor
0x10bc0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10bc5  stelem.ref
0x10bc6  ldsfld   class [mscorlib]System.Type[] System.Printing.PrintQueue::primaryAttributeTypes
0x10bcb  ldc.i4.s 0xE
0x10bcd  ldtoken  System.Printing.PrintServer
0x10bd2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10bd7  stelem.ref
0x10bd8  ldsfld   class [mscorlib]System.Type[] System.Printing.PrintQueue::primaryAttributeTypes
0x10bdd  ldc.i4.s 0xF
0x10bdf  ldtoken  System.Printing.PrintQueueStatus
0x10be4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10be9  stelem.ref
0x10bea  ldsfld   class [mscorlib]System.Type[] System.Printing.PrintQueue::primaryAttributeTypes
0x10bef  ldc.i4.s 0x10
0x10bf1  ldtoken  [mscorlib]System.String
0x10bf6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10bfb  stelem.ref
0x10bfc  ldsfld   class [mscorlib]System.Type[] System.Printing.PrintQueue::primaryAttributeTypes
0x10c01  ldc.i4.s 0x11
0x10c03  ldtoken  [ReachFramework]System.Printing.PrintTicket
0x10c08  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10c0d  stelem.ref
0x10c0e  ldsfld   class [mscorlib]System.Type[] System.Printing.PrintQueue::primaryAttributeTypes
0x10c13  ldc.i4.s 0x12
0x10c15  ldtoken  [ReachFramework]System.Printing.PrintTicket
0x10c1a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10c1f  stelem.ref
0x10c20  ldsfld   class [mscorlib]System.Type[] System.Printing.PrintQueue::primaryAttributeTypes
0x10c25  ldc.i4.s 0x13
0x10c27  ldtoken  [mscorlib]System.Boolean
0x10c2c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10c31  stelem.ref
0x10c32  ldc.i4.8
0x10c33  newarr   [mscorlib]System.String
0x10c38  stsfld   string[] System.Printing.PrintQueue::secondaryAttributeNames
0x10c3d  ldstr    aHostingprintse// "HostingPrintServerName"
0x10c42  stloc.s  0x1B
0x10c44  ldsfld   string[] System.Printing.PrintQueue::secondaryAttributeNames
0x10c49  ldc.i4.0
0x10c4a  ldloc.s  0x1B
0x10c4c  stelem.ref
0x10c4d  ldstr    aQueuedrivernam// "QueueDriverName"
0x10c52  stloc.s  0x1A
0x10c54  ldsfld   string[] System.Printing.PrintQueue::secondaryAttributeNames
0x10c59  ldc.i4.1
0x10c5a  ldloc.s  0x1A
0x10c5c  stelem.ref
0x10c5d  ldstr    aQueueprintproc// "QueuePrintProcessorName"
0x10c62  stloc.s  0x19
0x10c64  ldsfld   string[] System.Printing.PrintQueue::secondaryAttributeNames
0x10c69  ldc.i4.2
0x10c6a  ldloc.s  0x19
0x10c6c  stelem.ref
0x10c6d  ldstr    aQueueportname// "QueuePortName"
0x10c72  stloc.s  0x18
0x10c74  ldsfld   string[] System.Printing.PrintQueue::secondaryAttributeNames
0x10c79  ldc.i4.3
0x10c7a  ldloc.s  0x18
0x10c7c  stelem.ref
0x10c7d  ldstr    aDefaultdevmode// "DefaultDevMode"
0x10c82  stloc.s  0x17
0x10c84  ldsfld   string[] System.Printing.PrintQueue::secondaryAttributeNames
0x10c89  ldc.i4.4
0x10c8a  ldloc.s  0x17
0x10c8c  stelem.ref
0x10c8d  ldstr    aUserdevmode// "UserDevMode"
0x10c92  stloc.s  0x16
0x10c94  ldsfld   string[] System.Printing.PrintQueue::secondaryAttributeNames
0x10c99  ldc.i4.5
0x10c9a  ldloc.s  0x16
0x10c9c  stelem.ref
0x10c9d  ldstr    aStatus// "Status"
0x10ca2  stloc.s  0x15
0x10ca4  ldsfld   string[] System.Printing.PrintQueue::secondaryAttributeNames
0x10ca9  ldc.i4.6
0x10caa  ldloc.s  0x15
0x10cac  stelem.ref
0x10cad  ldstr    aAttributes// "Attributes"
0x10cb2  stloc.s  0x14
0x10cb4  ldsfld   string[] System.Printing.PrintQueue::secondaryAttributeNames
0x10cb9  ldc.i4.7
0x10cba  ldloc.s  0x14
0x10cbc  stelem.ref
0x10cbd  ldc.i4.8
0x10cbe  newarr   [mscorlib]System.Type
0x10cc3  stsfld   class [mscorlib]System.Type[] System.Printing.PrintQueue::secondaryAttributeTypes
0x10cc8  ldsfld   class [mscorlib]System.Type[] System.Printing.PrintQueue::secondaryAttributeTypes
0x10ccd  ldc.i4.0
0x10cce  ldtoken  [mscorlib]System.String
0x10cd3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10cd8  stelem.ref
0x10cd9  ldsfld   class [mscorlib]System.Type[] System.Printing.PrintQueue::secondaryAttributeTypes
0x10cde  ldc.i4.1
0x10cdf  ldtoken  [mscorlib]System.String
0x10ce4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10ce9  stelem.ref
0x10cea  ldsfld   class [mscorlib]System.Type[] System.Printing.PrintQueue::secondaryAttributeTypes
0x10cef  ldc.i4.2
0x10cf0  ldtoken  [mscorlib]System.String
0x10cf5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10cfa  stelem.ref
0x10cfb  ldsfld   class [mscorlib]System.Type[] System.Printing.PrintQueue::secondaryAttributeTypes
0x10d00  ldc.i4.3
0x10d01  ldtoken  [mscorlib]System.String
0x10d06  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10d0b  stelem.ref
  ... truncated ...
```
