# System.Printing.PrintServer::.cctor

- ea: `0x12a70`
- end: `0x12e93`
- name: `System.Printing.PrintServer::.cctor`
- size: `1059`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0xa900`
- `0x12a70`
- `0x12ea0`
- `0x134f0`
- `0x13540`

## string_xrefs

- `0x12a7c`: `DefaultSpoolDirectory`
- `0x12c26`: `DefaultSpoolDirectory`
- `0x12a8c`: `PortThreadPriority`
- `0x12c36`: `PortThreadPriority`
- `0x12a9c`: `DefaultPortThreadPriority`
- `0x12c46`: `PortThreadPriorityDefault`
- `0x12c56`: `SchedulerThreadPriority`
- `0x12c66`: `SchedulerThreadPriorityDefault`

## pseudocode

```c

```

## disassembly

```asm
0x12a70  ldc.i4.s 0xC
0x12a72  newarr   [mscorlib]System.String
0x12a77  stsfld   string[] System.Printing.PrintServer::primaryAttributeNames
0x12a7c  ldstr    aDefaultspooldi// "DefaultSpoolDirectory"
0x12a81  stloc.s  0x19
0x12a83  ldsfld   string[] System.Printing.PrintServer::primaryAttributeNames
0x12a88  ldc.i4.0
0x12a89  ldloc.s  0x19
0x12a8b  stelem.ref
0x12a8c  ldstr    aPortthreadprio// "PortThreadPriority"
0x12a91  stloc.s  0x18
0x12a93  ldsfld   string[] System.Printing.PrintServer::primaryAttributeNames
0x12a98  ldc.i4.1
0x12a99  ldloc.s  0x18
0x12a9b  stelem.ref
0x12a9c  ldstr    aDefaultportthr// "DefaultPortThreadPriority"
0x12aa1  stloc.s  0x17
0x12aa3  ldsfld   string[] System.Printing.PrintServer::primaryAttributeNames
0x12aa8  ldc.i4.2
0x12aa9  ldloc.s  0x17
0x12aab  stelem.ref
0x12aac  ldstr    aSchedulerprior// "SchedulerPriority"
0x12ab1  stloc.s  0x16
0x12ab3  ldsfld   string[] System.Printing.PrintServer::primaryAttributeNames
0x12ab8  ldc.i4.3
0x12ab9  ldloc.s  0x16
0x12abb  stelem.ref
0x12abc  ldstr    aDefaultschedul// "DefaultSchedulerPriority"
0x12ac1  stloc.s  0x15
0x12ac3  ldsfld   string[] System.Printing.PrintServer::primaryAttributeNames
0x12ac8  ldc.i4.4
0x12ac9  ldloc.s  0x15
0x12acb  stelem.ref
0x12acc  ldstr    aBeepenabled// "BeepEnabled"
0x12ad1  stloc.s  0x14
0x12ad3  ldsfld   string[] System.Printing.PrintServer::primaryAttributeNames
0x12ad8  ldc.i4.5
0x12ad9  ldloc.s  0x14
0x12adb  stelem.ref
0x12adc  ldstr    aNetpopup// "NetPopup"
0x12ae1  stloc.s  0x13
0x12ae3  ldsfld   string[] System.Printing.PrintServer::primaryAttributeNames
0x12ae8  ldc.i4.6
0x12ae9  ldloc.s  0x13
0x12aeb  stelem.ref
0x12aec  ldstr    aEventlog// "EventLog"
0x12af1  stloc.s  0x12
0x12af3  ldsfld   string[] System.Printing.PrintServer::primaryAttributeNames
0x12af8  ldc.i4.7
0x12af9  ldloc.s  0x12
0x12afb  stelem.ref
0x12afc  ldstr    aMajorversion// "MajorVersion"
0x12b01  stloc.s  0x11
0x12b03  ldsfld   string[] System.Printing.PrintServer::primaryAttributeNames
0x12b08  ldc.i4.8
0x12b09  ldloc.s  0x11
0x12b0b  stelem.ref
0x12b0c  ldstr    aMinorversion// "MinorVersion"
0x12b11  stloc.s  0x10
0x12b13  ldsfld   string[] System.Printing.PrintServer::primaryAttributeNames
0x12b18  ldc.i4.s 9
0x12b1a  ldloc.s  0x10
0x12b1c  stelem.ref
0x12b1d  ldstr    aRestartjobonpo// "RestartJobOnPoolTimeout"
0x12b22  stloc.s  0xF
0x12b24  ldsfld   string[] System.Printing.PrintServer::primaryAttributeNames
0x12b29  ldc.i4.s 0xA
0x12b2b  ldloc.s  0xF
0x12b2d  stelem.ref
0x12b2e  ldstr    aRestartjobonpo_0// "RestartJobOnPoolEnabled"
0x12b33  stloc.s  0xE
0x12b35  ldsfld   string[] System.Printing.PrintServer::primaryAttributeNames
0x12b3a  ldc.i4.s 0xB
0x12b3c  ldloc.s  0xE
0x12b3e  stelem.ref
0x12b3f  ldc.i4.s 0xC
0x12b41  newarr   [mscorlib]System.Type
0x12b46  stsfld   class [mscorlib]System.Type[] System.Printing.PrintServer::primaryAttributeTypes
0x12b4b  ldsfld   class [mscorlib]System.Type[] System.Printing.PrintServer::primaryAttributeTypes
0x12b50  ldc.i4.0
0x12b51  ldtoken  [mscorlib]System.String
0x12b56  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12b5b  stelem.ref
0x12b5c  ldsfld   class [mscorlib]System.Type[] System.Printing.PrintServer::primaryAttributeTypes
0x12b61  ldc.i4.1
0x12b62  ldtoken  [mscorlib]System.Threading.ThreadPriority
0x12b67  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12b6c  stelem.ref
0x12b6d  ldsfld   class [mscorlib]System.Type[] System.Printing.PrintServer::primaryAttributeTypes
0x12b72  ldc.i4.2
0x12b73  ldtoken  [mscorlib]System.Threading.ThreadPriority
0x12b78  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12b7d  stelem.ref
0x12b7e  ldsfld   class [mscorlib]System.Type[] System.Printing.PrintServer::primaryAttributeTypes
0x12b83  ldc.i4.3
0x12b84  ldtoken  [mscorlib]System.Threading.ThreadPriority
0x12b89  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12b8e  stelem.ref
0x12b8f  ldsfld   class [mscorlib]System.Type[] System.Printing.PrintServer::primaryAttributeTypes
0x12b94  ldc.i4.4
0x12b95  ldtoken  [mscorlib]System.Threading.ThreadPriority
0x12b9a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12b9f  stelem.ref
0x12ba0  ldsfld   class [mscorlib]System.Type[] System.Printing.PrintServer::primaryAttributeTypes
0x12ba5  ldc.i4.5
0x12ba6  ldtoken  [mscorlib]System.Boolean
0x12bab  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12bb0  stelem.ref
0x12bb1  ldsfld   class [mscorlib]System.Type[] System.Printing.PrintServer::primaryAttributeTypes
0x12bb6  ldc.i4.6
0x12bb7  ldtoken  [mscorlib]System.Boolean
0x12bbc  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12bc1  stelem.ref
0x12bc2  ldsfld   class [mscorlib]System.Type[] System.Printing.PrintServer::primaryAttributeTypes
0x12bc7  ldc.i4.7
0x12bc8  ldtoken  System.Printing.PrintServerEventLoggingTypes
0x12bcd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12bd2  stelem.ref
0x12bd3  ldsfld   class [mscorlib]System.Type[] System.Printing.PrintServer::primaryAttributeTypes
0x12bd8  ldc.i4.8
0x12bd9  ldtoken  [mscorlib]System.Int32
0x12bde  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12be3  stelem.ref
0x12be4  ldsfld   class [mscorlib]System.Type[] System.Printing.PrintServer::primaryAttributeTypes
0x12be9  ldc.i4.s 9
0x12beb  ldtoken  [mscorlib]System.Int32
0x12bf0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12bf5  stelem.ref
0x12bf6  ldsfld   class [mscorlib]System.Type[] System.Printing.PrintServer::primaryAttributeTypes
0x12bfb  ldc.i4.s 0xA
0x12bfd  ldtoken  [mscorlib]System.Int32
0x12c02  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12c07  stelem.ref
0x12c08  ldsfld   class [mscorlib]System.Type[] System.Printing.PrintServer::primaryAttributeTypes
0x12c0d  ldc.i4.s 0xB
0x12c0f  ldtoken  [mscorlib]System.Boolean
0x12c14  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12c19  stelem.ref
0x12c1a  ldc.i4.s 0xC
0x12c1c  newarr   [mscorlib]System.String
0x12c21  stsfld   string[] System.Printing.PrintServer::internalAttributeNames
0x12c26  ldstr    aDefaultspooldi// "DefaultSpoolDirectory"
0x12c2b  stloc.s  0xD
0x12c2d  ldsfld   string[] System.Printing.PrintServer::internalAttributeNames
0x12c32  ldc.i4.0
0x12c33  ldloc.s  0xD
0x12c35  stelem.ref
0x12c36  ldstr    aPortthreadprio// "PortThreadPriority"
0x12c3b  stloc.s  0xC
0x12c3d  ldsfld   string[] System.Printing.PrintServer::internalAttributeNames
0x12c42  ldc.i4.1
0x12c43  ldloc.s  0xC
0x12c45  stelem.ref
0x12c46  ldstr    aPortthreadprio_0// "PortThreadPriorityDefault"
0x12c4b  stloc.s  0xB
0x12c4d  ldsfld   string[] System.Printing.PrintServer::internalAttributeNames
0x12c52  ldc.i4.2
0x12c53  ldloc.s  0xB
0x12c55  stelem.ref
0x12c56  ldstr    aSchedulerthrea// "SchedulerThreadPriority"
0x12c5b  stloc.s  0xA
0x12c5d  ldsfld   string[] System.Printing.PrintServer::internalAttributeNames
0x12c62  ldc.i4.3
0x12c63  ldloc.s  0xA
0x12c65  stelem.ref
0x12c66  ldstr    aSchedulerthrea_0// "SchedulerThreadPriorityDefault"
0x12c6b  stloc.s  9
0x12c6d  ldsfld   string[] System.Printing.PrintServer::internalAttributeNames
0x12c72  ldc.i4.4
0x12c73  ldloc.s  9
0x12c75  stelem.ref
0x12c76  ldstr    aBeepenabled// "BeepEnabled"
0x12c7b  stloc.s  8
0x12c7d  ldsfld   string[] System.Printing.PrintServer::internalAttributeNames
0x12c82  ldc.i4.5
0x12c83  ldloc.s  8
0x12c85  stelem.ref
0x12c86  ldstr    aNetpopup// "NetPopup"
0x12c8b  stloc.s  7
0x12c8d  ldsfld   string[] System.Printing.PrintServer::internalAttributeNames
0x12c92  ldc.i4.6
0x12c93  ldloc.s  7
0x12c95  stelem.ref
0x12c96  ldstr    aEventlog// "EventLog"
0x12c9b  stloc.s  6
0x12c9d  ldsfld   string[] System.Printing.PrintServer::internalAttributeNames
0x12ca2  ldc.i4.7
0x12ca3  ldloc.s  6
0x12ca5  stelem.ref
0x12ca6  ldstr    aMajorversion// "MajorVersion"
0x12cab  stloc.s  5
0x12cad  ldsfld   string[] System.Printing.PrintServer::internalAttributeNames
0x12cb2  ldc.i4.8
0x12cb3  ldloc.s  5
0x12cb5  stelem.ref
0x12cb6  ldstr    aMinorversion// "MinorVersion"
0x12cbb  stloc.s  4
0x12cbd  ldsfld   string[] System.Printing.PrintServer::internalAttributeNames
0x12cc2  ldc.i4.s 9
0x12cc4  ldloc.s  4
0x12cc6  stelem.ref
0x12cc7  ldstr    aRestartjobonpo_1// "RestartJobOnPoolError"
0x12ccc  stloc.3
0x12ccd  ldsfld   string[] System.Printing.PrintServer::internalAttributeNames
0x12cd2  ldc.i4.s 0xA
0x12cd4  ldloc.3
0x12cd5  stelem.ref
0x12cd6  ldstr    aRestartjobonpo_0// "RestartJobOnPoolEnabled"
0x12cdb  stloc.2
0x12cdc  ldsfld   string[] System.Printing.PrintServer::internalAttributeNames
0x12ce1  ldc.i4.s 0xB
0x12ce3  ldloc.2
0x12ce4  stelem.ref
0x12ce5  ldc.i4.5
0x12ce6  newarr   [mscorlib]System.Type
0x12ceb  stsfld   class [mscorlib]System.Type[] System.Printing.PrintServer::attributeInteropTypes
0x12cf0  ldsfld   class [mscorlib]System.Type[] System.Printing.PrintServer::attributeInteropTypes
0x12cf5  ldc.i4.0
0x12cf6  ldtoken  System.Printing.IndexedProperties.PrintStringProperty
0x12cfb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12d00  stelem.ref
0x12d01  ldsfld   class [mscorlib]System.Type[] System.Printing.PrintServer::attributeInteropTypes
0x12d06  ldc.i4.1
0x12d07  ldtoken  System.Printing.IndexedProperties.PrintInt32Property
0x12d0c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12d11  stelem.ref
0x12d12  ldsfld   class [mscorlib]System.Type[] System.Printing.PrintServer::attributeInteropTypes
0x12d17  ldc.i4.2
0x12d18  ldtoken  System.Printing.IndexedProperties.PrintBooleanProperty
0x12d1d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12d22  stelem.ref
0x12d23  ldsfld   class [mscorlib]System.Type[] System.Printing.PrintServer::attributeInteropTypes
0x12d28  ldc.i4.3
0x12d29  ldtoken  System.Printing.IndexedProperties.PrintServerLoggingProperty
0x12d2e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12d33  stelem.ref
0x12d34  ldsfld   class [mscorlib]System.Type[] System.Printing.PrintServer::attributeInteropTypes
0x12d39  ldc.i4.4
0x12d3a  ldtoken  System.Printing.IndexedProperties.PrintThreadPriorityProperty
0x12d3f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12d44  stelem.ref
0x12d45  ldc.i4.5
0x12d46  newarr   ThunkGetPrinterData
0x12d4b  stsfld   class ThunkGetPrinterData[] System.Printing.PrintServer::getAttributeInteropDelegates
0x12d50  ldsfld   class ThunkGetPrinterData[] System.Printing.PrintServer::getAttributeInteropDelegates
0x12d55  ldc.i4.0
0x12d56  ldnull
0x12d57  ldftn    object MS.Internal.PrintWin32Thunk.PrinterThunkHandler::ThunkGetPrinterDataString(class MS.Internal.PrintWin32Thunk.PrinterThunkHandler printerHandle, string valueName)
0x12d5d  newobj   instance void ThunkGetPrinterData::.ctor(object A_0, native int A_1)
0x12d62  stelem.ref
0x12d63  ldsfld   class ThunkGetPrinterData[] System.Printing.PrintServer::getAttributeInteropDelegates
0x12d68  ldc.i4.1
0x12d69  ldnull
0x12d6a  ldftn    object MS.Internal.PrintWin32Thunk.PrinterThunkHandler::ThunkGetPrinterDataInt32(class MS.Internal.PrintWin32Thunk.PrinterThunkHandler printerHandle, string valueName)
0x12d70  newobj   instance void ThunkGetPrinterData::.ctor(object A_0, native int A_1)
0x12d75  stelem.ref
0x12d76  ldsfld   class ThunkGetPrinterData[] System.Printing.PrintServer::getAttributeInteropDelegates
0x12d7b  ldc.i4.2
0x12d7c  ldnull
0x12d7d  ldftn    object MS.Internal.PrintWin32Thunk.PrinterThunkHandler::ThunkGetPrinterDataBoolean(class MS.Internal.PrintWin32Thunk.PrinterThunkHandler printerHandle, string valueName)
0x12d83  newobj   instance void ThunkGetPrinterData::.ctor(object A_0, native int A_1)
0x12d88  stelem.ref
0x12d89  ldsfld   class ThunkGetPrinterData[] System.Printing.PrintServer::getAttributeInteropDelegates
0x12d8e  ldc.i4.3
0x12d8f  ldnull
0x12d90  ldftn    object MS.Internal.PrintWin32Thunk.PrinterThunkHandler::ThunkGetPrinterDataServerEventLogging(class MS.Internal.PrintWin32Thunk.PrinterThunkHandler printerHandle, string valueName)
0x12d96  newobj   instance void ThunkGetPrinterData::.ctor(object A_0, native int A_1)
0x12d9b  stelem.ref
0x12d9c  ldsfld   class ThunkGetPrinterData[] System.Printing.PrintServer::getAttributeInteropDelegates
0x12da1  ldc.i4.4
0x12da2  ldnull
0x12da3  ldftn    object MS.Internal.PrintWin32Thunk.PrinterThunkHandler::ThunkGetPrinterDataThreadPriority(class MS.Internal.PrintWin32Thunk.PrinterThunkHandler printerHandle, string valueName)
0x12da9  newobj   instance void ThunkGetPrinterData::.ctor(object A_0, native int A_1)
0x12dae  stelem.ref
0x12daf  ldc.i4.5
0x12db0  newarr   ThunkSetPrinterData
0x12db5  stsfld   class ThunkSetPrinterData[] System.Printing.PrintServer::setAttributeInteropDelegates
0x12dba  ldsfld   class ThunkSetPrinterData[] System.Printing.PrintServer::setAttributeInteropDelegates
0x12dbf  ldc.i4.0
0x12dc0  ldnull
0x12dc1  ldftn    bool MS.Internal.PrintWin32Thunk.PrinterThunkHandler::ThunkSetPrinterDataString([hasfieldmarshal] class MS.Internal.PrintWin32Thunk.PrinterThunkHandler value, string printerHandle, object valueName)
0x12dc7  newobj   instance void ThunkSetPrinterData::.ctor(object A_0, native int A_1)
0x12dcc  stelem.ref
0x12dcd  ldsfld   class ThunkSetPrinterData[] System.Printing.PrintServer::setAttributeInteropDelegates
0x12dd2  ldc.i4.1
0x12dd3  ldnull
0x12dd4  ldftn    bool MS.Internal.PrintWin32Thunk.PrinterThunkHandler::ThunkSetPrinterDataInt32([hasfieldmarshal] class MS.Internal.PrintWin32Thunk.PrinterThunkHandler value, string printerHandle, object valueName)
0x12dda  newobj   instance void ThunkSetPrinterData::.ctor(object A_0, native int A_1)
0x12ddf  stelem.ref
0x12de0  ldsfld   class ThunkSetPrinterData[] System.Printing.PrintServer::setAttributeInteropDelegates
0x12de5  ldc.i4.2
0x12de6  ldnull
0x12de7  ldftn    bool MS.Internal.PrintWin32Thunk.PrinterThunkHandler::ThunkSetPrinterDataBoolean([hasfieldmarshal] class MS.Internal.PrintWin32Thunk.PrinterThunkHandler value, string printerHandle, object valueName)
0x12ded  newobj   instance void ThunkSetPrinterData::.ctor(object A_0, native int A_1)
0x12df2  stelem.ref
0x12df3  ldsfld   class ThunkSetPrinterData[] System.Printing.PrintServer::setAttributeInteropDelegates
0x12df8  ldc.i4.3
0x12df9  ldnull
0x12dfa  ldftn    bool MS.Internal.PrintWin32Thunk.PrinterThunkHandler::ThunkSetPrinterDataServerEventLogging([hasfieldmarshal] class MS.Internal.PrintWin32Thunk.PrinterThunkHandler value, string printerHandle, object valueName)
0x12e00  newobj   instance void ThunkSetPrinterData::.ctor(object A_0, native int A_1)
  ... truncated ...
```
