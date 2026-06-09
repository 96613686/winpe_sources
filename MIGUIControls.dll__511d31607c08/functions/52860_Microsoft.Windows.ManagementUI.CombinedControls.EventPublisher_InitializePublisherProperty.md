# Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::InitializePublisherProperty

- ea: `0x52860`
- end: `0x52c89`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::InitializePublisherProperty`
- size: `1065`
- prototype: ``
- caller_count: `3`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callers

- `0x51b40`
- `0x51ba0`
- `0x51c00`

## callees

- `0x12670`
- `0x126b0`
- `0x13430`
- `0x13510`
- `0x32e90`
- `0x38b70`
- `0x38ce0`
- `0x38db0`
- `0x3b750`
- `0x4d110`
- `0x4d300`
- `0x4d320`
- `0x4d330`
- `0x4d340`
- `0x51790`
- `0x52860`
- `0x536b0`

## string_xrefs

- `0x52aec`: `Wrong type received from crimson for PublisherMetadataTaskValue property in getting an item from array`
- `0x52937`: `GetObjectArraySize on crimson for PublisherMetadataTasks failed `
- `0x52ab4`: `Getting Item from array failed PublisherMetadataTaskMessageID `
- `0x52b3b`: `PublisherMetadataTaskName failed for not providing enough memory. Trying with the correct memory `
- `0x52c71`: `Unable to close handle on PublisherMetadataTasks `

## pseudocode

```c

```

## disassembly

```asm
0x52860  ldarg.1
0x52861  ldc.i4.1
0x52862  sub
0x52863  switch   loc_52875, loc_52886, loc_52897
0x52874  ret
0x52875  ldc.i4.s 0xC
0x52877  stloc.0
0x52878  ldc.i4.s 0xD
0x5287a  stloc.1
0x5287b  ldc.i4.s 0xE
0x5287d  stloc.2
0x5287e  ldc.i4.s 0xF
0x52880  stloc.3
0x52881  ldc.i4.8
0x52882  stloc.s  4
0x52884  br.s     loc_528A6
0x52886  ldc.i4.s 0x10
0x52888  stloc.0
0x52889  ldc.i4.s 0x11
0x5288b  stloc.1
0x5288c  ldc.i4.s 0x13
0x5288e  stloc.2
0x5288f  ldc.i4.s 0x14
0x52891  stloc.3
0x52892  ldc.i4.8
0x52893  stloc.s  4
0x52895  br.s     loc_528A6
0x52897  ldc.i4.s 0x15
0x52899  stloc.0
0x5289a  ldc.i4.s 0x16
0x5289c  stloc.1
0x5289d  ldc.i4.s 0x17
0x5289f  stloc.2
0x528a0  ldc.i4.s 0x18
0x528a2  stloc.3
0x528a3  ldc.i4.8
0x528a4  stloc.s  4
0x528a6  ldc.i4.0
0x528a7  stloc.s  5
0x528a9  ldloca.s 6
0x528ab  initobj  Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x528b1  sizeof   Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x528b7  stloc.s  7
0x528b9  ldarg.0
0x528ba  call     instance native int Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::get_PublisherHandle()
0x528bf  ldloc.0
0x528c0  ldc.i4.0
0x528c1  sizeof   Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x528c7  ldloca.s 6
0x528c9  ldloca.s 7
0x528cb  call     bool Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::GetPublisherMetadataProperty(native int publisherMetadata, [hasfieldmarshal] valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventPublisherMetadataPropertyID propertyId, int32 flags, int32 bufferSize, valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventVariant& publisherMetadataPropertyBuffer, int32& publisherMetadataPropertyBufferUsed)
0x528d0  stloc.s  8
0x528d2  ldloc.s  8
0x528d4  brtrue.s loc_528F5
0x528d6  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x528db  stloc.s  5
0x528dd  ldstr    aGettingPublish_0// "Getting Publisher metadata property Pub"...
0x528e2  ldarg.0
0x528e3  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::identifier
0x528e8  call     string [mscorlib]System.String::Concat(string, string)
0x528ed  ldloc.s  5
0x528ef  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x528f4  ret
0x528f5  ldloc.s  6
0x528f7  ldfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::type
0x528fc  ldc.i4.s 0x20
0x528fe  beq.s    loc_52916
0x52900  ldstr    aWrongTypeRecei_5// "Wrong type received from crimson for Pu"...
0x52905  ldarg.0
0x52906  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::identifier
0x5290b  call     string [mscorlib]System.String::Concat(string, string)
0x52910  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string errorString)
0x52915  ret
0x52916  ldc.i4.0
0x52917  stloc.s  9
0x52919  ldarg.2
0x5291a  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x5291f  stind.ref
0x52920  ldloc.s  6
0x52922  ldfld    native int Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::EvtHandle
0x52927  ldloca.s 9
0x52929  call     bool Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::GetObjectArraySize(native int objectArray, int32& objectArraySize)
0x5292e  brtrue.s loc_52953
0x52930  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x52935  stloc.s  5
0x52937  ldstr    aGetobjectarray_0// "GetObjectArraySize on crimson for Publi"...
0x5293c  ldarg.0
0x5293d  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::identifier
0x52942  call     string [mscorlib]System.String::Concat(string, string)
0x52947  ldloc.s  5
0x52949  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x5294e  br       loc_52C5C
0x52953  ldloc.s  9
0x52955  ldc.i4.0
0x52956  ble      loc_52C5C
0x5295b  ldloca.s 0xA
0x5295d  initobj  Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x52963  ldc.i4.0
0x52964  stloc.s  0xB
0x52966  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::PrepareConstrainedRegions()
0x5296b  leave    loc_52C5C
0x52970  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.SafeGlobalHandle::.ctor()
0x52975  stloc.s  0xF
0x52977  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x5297c  stloc.s  0x10
0x5297e  ldc.i4   0x200
0x52983  stloc.s  0x11
0x52985  ldc.i4.1
0x52986  stloc.s  0x12
0x52988  ldloc.s  0x11
0x5298a  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::AllocHGlobal(int32)
0x5298f  stloc.s  0x10
0x52991  ldloc.s  0x10
0x52993  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x52998  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x5299d  brfalse.s loc_529A8
0x5299f  ldloc.s  0xF
0x529a1  ldloc.s  0x10
0x529a3  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.SafeGlobalHandle::InitHandle(native int inHandle)
0x529a8  ldc.i4.0
0x529a9  stloc.s  0x13
0x529ab  br       loc_52C4B
0x529b0  ldc.i4.1
0x529b1  stloc.s  0x12
0x529b3  ldc.i4.0
0x529b4  stloc.s  0xB
0x529b6  ldsfld   string [mscorlib]System.String::Empty
0x529bb  stloc.s  0xC
0x529bd  ldsfld   string [mscorlib]System.String::Empty
0x529c2  stloc.s  0xD
0x529c4  ldc.i4.m1
0x529c5  stloc.s  0xE
0x529c7  ldloc.s  6
0x529c9  ldfld    native int Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::EvtHandle
0x529ce  ldloc.2
0x529cf  ldloc.s  0x13
0x529d1  ldc.i4.0
0x529d2  sizeof   Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x529d8  ldloca.s 0xA
0x529da  ldloca.s 7
0x529dc  call     bool Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::GetObjectArrayProperty(native int objectArray, int32 propertyId, int32 arrayIndex, int32 flags, int32 propertyValueBufferSize, valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventVariant& propertyValueBuffer, int32& propertyValueBufferUsed)
0x529e1  brtrue.s loc_52A03
0x529e3  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x529e8  stloc.s  5
0x529ea  ldstr    aGettingItemFro_1// "Getting Item from array failed Publishe"...
0x529ef  ldarg.0
0x529f0  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::identifier
0x529f5  call     string [mscorlib]System.String::Concat(string, string)
0x529fa  ldloc.s  5
0x529fc  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x52a01  br.s     loc_52A37
0x52a03  ldloc.s  0xA
0x52a05  ldfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::type
0x52a0a  ldc.i4.7
0x52a0b  beq.s    loc_52A17
0x52a0d  ldloc.s  0xA
0x52a0f  ldfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::type
0x52a14  ldc.i4.8
0x52a15  bne.un.s loc_52A22
0x52a17  ldloc.s  0xA
0x52a19  ldfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::Int32Val
0x52a1e  stloc.s  0xB
0x52a20  br.s     loc_52A37
0x52a22  ldstr    aWrongTypeRecei_4// "Wrong type received from crimson for Pu"...
0x52a27  ldarg.0
0x52a28  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::identifier
0x52a2d  call     string [mscorlib]System.String::Concat(string, string)
0x52a32  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string errorString)
0x52a37  ldarg.0
0x52a38  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::identifier
0x52a3d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x52a42  brtrue.s loc_52A8A
0x52a44  ldarg.1
0x52a45  ldc.i4.1
0x52a46  bne.un.s loc_52A5C
0x52a48  ldarg.0
0x52a49  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::context
0x52a4e  ldloc.s  0xB
0x52a50  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::IsStandardLevel(int32 level)
0x52a55  ldc.i4.0
0x52a56  ceq
0x52a58  stloc.s  0x12
0x52a5a  br.s     loc_52A8A
0x52a5c  ldarg.1
0x52a5d  ldc.i4.2
0x52a5e  bne.un.s loc_52A74
0x52a60  ldarg.0
0x52a61  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::context
0x52a66  ldloc.s  0xB
0x52a68  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::IsStandardTask(int32 task)
0x52a6d  ldc.i4.0
0x52a6e  ceq
0x52a70  stloc.s  0x12
0x52a72  br.s     loc_52A8A
0x52a74  ldarg.1
0x52a75  ldc.i4.3
0x52a76  bne.un.s loc_52A8A
0x52a78  ldarg.0
0x52a79  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::context
0x52a7e  ldloc.s  0xB
0x52a80  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::IsStandardOpcode(int32 opcode)
0x52a85  ldc.i4.0
0x52a86  ceq
0x52a88  stloc.s  0x12
0x52a8a  ldloc.s  0x12
0x52a8c  brfalse  loc_52C45
0x52a91  ldloc.s  6
0x52a93  ldfld    native int Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::EvtHandle
0x52a98  ldloc.3
0x52a99  ldloc.s  0x13
0x52a9b  ldc.i4.0
0x52a9c  sizeof   Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x52aa2  ldloca.s 0xA
0x52aa4  ldloca.s 7
0x52aa6  call     bool Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::GetObjectArrayProperty(native int objectArray, int32 propertyId, int32 arrayIndex, int32 flags, int32 propertyValueBufferSize, valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventVariant& propertyValueBuffer, int32& propertyValueBufferUsed)
0x52aab  brtrue.s loc_52ACD
0x52aad  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x52ab2  stloc.s  5
0x52ab4  ldstr    aGettingItemFro_2// "Getting Item from array failed Publishe"...
0x52ab9  ldarg.0
0x52aba  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::identifier
0x52abf  call     string [mscorlib]System.String::Concat(string, string)
0x52ac4  ldloc.s  5
0x52ac6  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x52acb  br.s     loc_52B01
0x52acd  ldloc.s  0xA
0x52acf  ldfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::type
0x52ad4  ldc.i4.7
0x52ad5  beq.s    loc_52AE1
0x52ad7  ldloc.s  0xA
0x52ad9  ldfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::type
0x52ade  ldc.i4.8
0x52adf  bne.un.s loc_52AEC
0x52ae1  ldloc.s  0xA
0x52ae3  ldfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::Int32Val
0x52ae8  stloc.s  0xE
0x52aea  br.s     loc_52B01
0x52aec  ldstr    aWrongTypeRecei_2// "Wrong type received from crimson for Pu"...
0x52af1  ldarg.0
0x52af2  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::identifier
0x52af7  call     string [mscorlib]System.String::Concat(string, string)
0x52afc  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string errorString)
0x52b01  ldloc.s  0x11
0x52b03  stloc.s  7
0x52b05  ldloc.s  6
0x52b07  ldfld    native int Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::EvtHandle
0x52b0c  ldloc.1
0x52b0d  ldloc.s  0x13
0x52b0f  ldc.i4.0
0x52b10  ldloc.s  0x11
0x52b12  ldloc.s  0x10
0x52b14  ldloca.s 7
0x52b16  call     bool Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::GetObjectArrayPropertyBuffer(native int objectArray, int32 propertyId, int32 arrayIndex, int32 flags, int32 propertyValueBufferSize, native int propertyValueBuffer, int32& propertyValueBufferUsed)
0x52b1b  stloc.s  8
0x52b1d  ldloc.s  8
0x52b1f  brtrue.s loc_52B28
0x52b21  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x52b26  stloc.s  5
0x52b28  ldloc.s  8
0x52b2a  brtrue   loc_52BBD
0x52b2f  ldloc.s  5
0x52b31  call     bool Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::IsInsufficientBuffer(int32 error)
0x52b36  brfalse  loc_52BBD
0x52b3b  ldstr    aPublishermetad_4// "PublisherMetadataTaskName failed for no"...
0x52b40  ldarg.0
0x52b41  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::identifier
0x52b46  call     string [mscorlib]System.String::Concat(string, string)
0x52b4b  ldloc.s  5
0x52b4d  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x52b52  ldloc.s  0x11
0x52b54  brfalse.s loc_52B5D
0x52b56  ldloc.s  0xF
0x52b58  callvirt instance void [mscorlib]System.Runtime.InteropServices.SafeHandle::Close()
0x52b5d  ldloc.s  7
0x52b5f  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::AllocHGlobal(int32)
0x52b64  stloc.s  0x10
0x52b66  ldloc.s  0x10
0x52b68  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x52b6d  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x52b72  brfalse.s loc_52BD8
0x52b74  ldloc.s  0xF
0x52b76  ldloc.s  0x10
0x52b78  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.SafeGlobalHandle::InitHandle(native int inHandle)
0x52b7d  ldloc.s  7
0x52b7f  stloc.s  0x11
0x52b81  ldloc.s  6
0x52b83  ldfld    native int Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::EvtHandle
0x52b88  ldloc.1
0x52b89  ldloc.s  0x13
0x52b8b  ldc.i4.0
0x52b8c  ldloc.s  7
0x52b8e  ldloc.s  0x10
0x52b90  ldloca.s 7
0x52b92  call     bool Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::GetObjectArrayPropertyBuffer(native int objectArray, int32 propertyId, int32 arrayIndex, int32 flags, int32 propertyValueBufferSize, native int propertyValueBuffer, int32& propertyValueBufferUsed)
0x52b97  stloc.s  8
0x52b99  ldloc.s  8
0x52b9b  brtrue.s loc_52BD8
0x52b9d  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x52ba2  stloc.s  5
0x52ba4  ldstr    aPublishermetad_5// "PublisherMetadataName failed in getting"...
  ... truncated ...
```
