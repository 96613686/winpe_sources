# Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::get_ChannelReferences

- ea: `0x52010`
- end: `0x523cb`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::get_ChannelReferences`
- size: `955`
- prototype: ``
- caller_count: `9`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x25c10`
- `0x4fa90`
- `0x4fcb0`
- `0x50220`
- `0x507c0`
- `0x50870`
- `0x50b80`
- `0x53050`
- `0x574c0`

## callees

- `0x12670`
- `0x126b0`
- `0x13430`
- `0x13510`
- `0x4d110`
- `0x4d300`
- `0x4d320`
- `0x4d330`
- `0x4d340`
- `0x512e0`
- `0x51500`
- `0x51790`
- `0x51920`
- `0x52010`

## string_xrefs

- `0x52196`: `PublisherMetadataChannelReferencePath failed for not providing enough memory.Allocating correct memory size `
- `0x521f8`: `Getting an item for PublisherMetadataChannelReferencePath failed `
- `0x52214`: `Getting an item for PublisherMetadataChannelReferencePath failed `

## pseudocode

```c

```

## disassembly

```asm
0x52010  ldc.i4.0
0x52011  stloc.0
0x52012  ldarg.0
0x52013  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::Initialize()
0x52018  pop
0x52019  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::PrepareConstrainedRegions()
0x5201e  leave    loc_523C4
0x52023  ldarg.0
0x52024  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::channelReference
0x52029  brtrue   loc_523C3
0x5202e  ldarg.0
0x5202f  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x52034  stfld    class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::channelReference
0x52039  ldarg.0
0x5203a  call     instance native int Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::get_PublisherHandle()
0x5203f  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x52044  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x52049  brfalse  loc_523C3
0x5204e  ldarg.0
0x5204f  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::isArchivedPublisher
0x52054  brtrue   loc_523C3
0x52059  ldloca.s 1
0x5205b  initobj  Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x52061  sizeof   Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x52067  stloc.2
0x52068  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x5206d  stloc.3
0x5206e  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.SafeGlobalHandle::.ctor()
0x52073  stloc.s  4
0x52075  ldarg.0
0x52076  call     instance native int Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::get_PublisherHandle()
0x5207b  ldc.i4.6
0x5207c  ldc.i4.0
0x5207d  sizeof   Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x52083  ldloca.s 1
0x52085  ldloca.s 2
0x52087  call     bool Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::GetPublisherMetadataProperty(native int publisherMetadata, [hasfieldmarshal] valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventPublisherMetadataPropertyID propertyId, int32 flags, int32 bufferSize, valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventVariant& publisherMetadataPropertyBuffer, int32& publisherMetadataPropertyBufferUsed)
0x5208c  stloc.s  5
0x5208e  ldloc.s  5
0x52090  brtrue.s loc_520B3
0x52092  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x52097  stloc.0
0x52098  ldstr    aFailedToGetPub_0// "Failed to get publisher meta data prope"...
0x5209d  ldarg.0
0x5209e  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::identifier
0x520a3  call     string [mscorlib]System.String::Concat(string, string)
0x520a8  ldloc.0
0x520a9  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x520ae  br       loc_523C3
0x520b3  ldloc.1
0x520b4  ldfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::type
0x520b9  ldc.i4.s 0x20
0x520bb  beq.s    loc_520D7
0x520bd  ldstr    aWrongTypeRecei_3// "Wrong type received from crimson for Pu"...
0x520c2  ldarg.0
0x520c3  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::identifier
0x520c8  call     string [mscorlib]System.String::Concat(string, string)
0x520cd  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string errorString)
0x520d2  br       loc_523C3
0x520d7  ldc.i4.0
0x520d8  stloc.s  6
0x520da  ldloc.1
0x520db  ldfld    native int Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::EvtHandle
0x520e0  ldloca.s 6
0x520e2  call     bool Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::GetObjectArraySize(native int objectArray, int32& objectArraySize)
0x520e7  brtrue.s loc_5210A
0x520e9  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x520ee  stloc.0
0x520ef  ldstr    aGettingArraySi// "Getting array size for PublisherMetadat"...
0x520f4  ldarg.0
0x520f5  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::identifier
0x520fa  call     string [mscorlib]System.String::Concat(string, string)
0x520ff  ldloc.0
0x52100  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x52105  br       loc_52393
0x5210a  ldloc.s  6
0x5210c  ldc.i4.0
0x5210d  ble      loc_52393
0x52112  ldloca.s 7
0x52114  initobj  Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x5211a  ldsfld   string [mscorlib]System.String::Empty
0x5211f  stloc.s  0xA
0x52121  ldc.i4.0
0x52122  stloc.s  0xB
0x52124  sizeof   Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x5212a  ldc.i4   0x200
0x5212f  add
0x52130  stloc.s  0xC
0x52132  ldloc.s  0xC
0x52134  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::AllocHGlobal(int32)
0x52139  stloc.3
0x5213a  ldloc.3
0x5213b  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x52140  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x52145  brfalse.s loc_5214F
0x52147  ldloc.s  4
0x52149  ldloc.3
0x5214a  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.SafeGlobalHandle::InitHandle(native int inHandle)
0x5214f  ldc.i4.0
0x52150  stloc.s  0xD
0x52152  br       loc_5237F
0x52157  ldsfld   string [mscorlib]System.String::Empty
0x5215c  stloc.s  8
0x5215e  ldloc.s  0xC
0x52160  stloc.2
0x52161  ldc.i4.0
0x52162  stloc.s  9
0x52164  ldc.i4.0
0x52165  stloc.s  0xB
0x52167  ldsfld   string [mscorlib]System.String::Empty
0x5216c  stloc.s  0xA
0x5216e  ldloc.1
0x5216f  ldfld    native int Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::EvtHandle
0x52174  ldc.i4.7
0x52175  ldloc.s  0xD
0x52177  ldc.i4.0
0x52178  ldloc.2
0x52179  ldloc.3
0x5217a  ldloca.s 2
0x5217c  call     bool Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::GetObjectArrayPropertyBuffer(native int objectArray, int32 propertyId, int32 arrayIndex, int32 flags, int32 propertyValueBufferSize, native int propertyValueBuffer, int32& propertyValueBufferUsed)
0x52181  stloc.s  5
0x52183  ldloc.s  5
0x52185  brtrue.s loc_5218D
0x52187  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x5218c  stloc.0
0x5218d  ldloc.s  5
0x5218f  brtrue.s loc_52210
0x52191  ldloc.0
0x52192  ldc.i4.s 0x7A
0x52194  bne.un.s loc_52210
0x52196  ldstr    aPublishermetad_3// "PublisherMetadataChannelReferencePath f"...
0x5219b  ldarg.0
0x5219c  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::identifier
0x521a1  call     string [mscorlib]System.String::Concat(string, string)
0x521a6  ldloc.0
0x521a7  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x521ac  ldloc.s  0xC
0x521ae  brfalse.s loc_521B7
0x521b0  ldloc.s  4
0x521b2  callvirt instance void [mscorlib]System.Runtime.InteropServices.SafeHandle::Close()
0x521b7  ldloc.2
0x521b8  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::AllocHGlobal(int32)
0x521bd  stloc.3
0x521be  ldloc.3
0x521bf  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x521c4  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x521c9  brfalse  loc_52388
0x521ce  ldloc.s  4
0x521d0  ldloc.3
0x521d1  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.SafeGlobalHandle::InitHandle(native int inHandle)
0x521d6  ldloc.2
0x521d7  stloc.s  0xC
0x521d9  ldloc.1
0x521da  ldfld    native int Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::EvtHandle
0x521df  ldc.i4.7
0x521e0  ldloc.s  0xD
0x521e2  ldc.i4.0
0x521e3  ldloc.2
0x521e4  ldloc.3
0x521e5  ldloca.s 2
0x521e7  call     bool Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::GetObjectArrayPropertyBuffer(native int objectArray, int32 propertyId, int32 arrayIndex, int32 flags, int32 propertyValueBufferSize, native int propertyValueBuffer, int32& propertyValueBufferUsed)
0x521ec  stloc.s  5
0x521ee  ldloc.s  5
0x521f0  brtrue.s loc_5222A
0x521f2  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x521f7  stloc.0
0x521f8  ldstr    aGettingAnItemF// "Getting an item for PublisherMetadataCh"...
0x521fd  ldarg.0
0x521fe  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::identifier
0x52203  call     string [mscorlib]System.String::Concat(string, string)
0x52208  ldloc.0
0x52209  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x5220e  br.s     loc_5222A
0x52210  ldloc.s  5
0x52212  brtrue.s loc_5222A
0x52214  ldstr    aGettingAnItemF// "Getting an item for PublisherMetadataCh"...
0x52219  ldarg.0
0x5221a  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::identifier
0x5221f  call     string [mscorlib]System.String::Concat(string, string)
0x52224  ldloc.0
0x52225  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x5222a  ldloc.s  5
0x5222c  brfalse  loc_52379
0x52231  ldloc.3
0x52232  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x52237  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5223c  call     object [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStructure(native int, class [mscorlib]System.Type)
0x52241  unbox.any Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x52246  stloc.s  7
0x52248  ldloc.s  7
0x5224a  ldfld    native int Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::StringVal
0x5224f  call     string [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStringAuto(native int)
0x52254  stloc.s  8
0x52256  ldloc.s  8
0x52258  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5225d  brtrue   loc_52379
0x52262  ldloc.1
0x52263  ldfld    native int Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::EvtHandle
0x52268  ldc.i4.s 0xB
0x5226a  ldloc.s  0xD
0x5226c  ldc.i4.0
0x5226d  ldloc.s  7
0x5226f  box      Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x52274  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::SizeOf(object)
0x52279  ldloca.s 7
0x5227b  ldloca.s 2
0x5227d  call     bool Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::GetObjectArrayProperty(native int objectArray, int32 propertyId, int32 arrayIndex, int32 flags, int32 propertyValueBufferSize, valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventVariant& propertyValueBuffer, int32& propertyValueBufferUsed)
0x52282  stloc.s  5
0x52284  ldloc.s  5
0x52286  brtrue.s loc_522A6
0x52288  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x5228d  stloc.0
0x5228e  ldstr    aGettingAnItemF_0// "Getting an item for PublisherMetadataCh"...
0x52293  ldarg.0
0x52294  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::identifier
0x52299  call     string [mscorlib]System.String::Concat(string, string)
0x5229e  ldloc.0
0x5229f  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x522a4  br.s     loc_522C6
0x522a6  ldloc.s  7
0x522a8  ldfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::type
0x522ad  ldc.i4.8
0x522ae  bne.un.s loc_522C6
0x522b0  ldloc.s  7
0x522b2  ldfld    unsigned int32 Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::UInt32Val
0x522b7  ldc.i4.m1
0x522b8  beq.s    loc_522C3
0x522ba  ldloc.s  7
0x522bc  ldfld    unsigned int32 Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::UInt32Val
0x522c1  br.s     loc_522C4
0x522c3  ldc.i4.0
0x522c4  stloc.s  0xB
0x522c6  ldloc.s  0xB
0x522c8  ldc.i4.0
0x522c9  ble.un.s loc_522E4
0x522cb  ldarg.0
0x522cc  ldloc.s  0xB
0x522ce  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::RenderPublisherString(unsigned int32 messageId)
0x522d3  stloc.s  0xA
0x522d5  ldloc.s  0xA
0x522d7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x522dc  brfalse.s loc_522E8
0x522de  ldloc.s  8
0x522e0  stloc.s  0xA
0x522e2  br.s     loc_522E8
0x522e4  ldloc.s  8
0x522e6  stloc.s  0xA
0x522e8  ldc.i4.0
0x522e9  stloc.s  9
0x522eb  ldloc.1
0x522ec  ldfld    native int Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::EvtHandle
0x522f1  ldc.i4.s 0xA
0x522f3  ldloc.s  0xD
0x522f5  ldc.i4.0
0x522f6  sizeof   Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x522fc  ldloca.s 7
0x522fe  ldloca.s 2
0x52300  call     bool Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::GetObjectArrayProperty(native int objectArray, int32 propertyId, int32 arrayIndex, int32 flags, int32 propertyValueBufferSize, valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventVariant& propertyValueBuffer, int32& propertyValueBufferUsed)
0x52305  brtrue.s loc_5231A
0x52307  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x5230c  stloc.0
0x5230d  ldstr    aGettingItemFro_1// "Getting Item from array failed Publishe"...
0x52312  ldloc.0
0x52313  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x52318  br.s     loc_52362
0x5231a  ldloc.s  7
0x5231c  ldfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::type
0x52321  ldc.i4.7
0x52322  beq.s    loc_52342
0x52324  ldloc.s  7
0x52326  ldfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::type
0x5232b  ldc.i4.8
0x5232c  beq.s    loc_52342
0x5232e  ldloc.s  7
0x52330  ldfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::type
0x52335  ldc.i4.5
0x52336  beq.s    loc_52342
0x52338  ldloc.s  7
0x5233a  ldfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::type
0x5233f  ldc.i4.6
0x52340  bne.un.s loc_5234D
0x52342  ldloc.s  7
0x52344  ldfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::Int32Val
0x52349  stloc.s  9
0x5234b  br.s     loc_52362
0x5234d  ldstr    aWrongTypeRecei_4// "Wrong type received from crimson for Pu"...
0x52352  ldarg.0
0x52353  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::identifier
0x52358  call     string [mscorlib]System.String::Concat(string, string)
0x5235d  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string errorString)
0x52362  ldarg.0
0x52363  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::channelReference
0x52368  ldloc.s  0xA
0x5236a  ldloc.s  8
0x5236c  ldloc.s  9
0x5236e  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.PublisherChannelBase::.ctor(string channelName, string channelPath, int32 channelflag)
0x52373  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x52378  pop
0x52379  ldloc.s  0xD
0x5237b  ldc.i4.1
  ... truncated ...
```
