# Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::InitalizeKeywords

- ea: `0x51c60`
- end: `0x52008`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::InitalizeKeywords`
- size: `936`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x52410`

## callees

- `0x12670`
- `0x126b0`
- `0x13430`
- `0x13510`
- `0x32e90`
- `0x38b60`
- `0x3b710`
- `0x4d110`
- `0x4d300`
- `0x4d320`
- `0x4d330`
- `0x4d340`
- `0x51500`
- `0x51790`
- `0x51c60`
- `0x53720`

## string_xrefs

- `0x51e80`: `Wrong type received from crimson for PublisherMetadataTaskValue property in getting an item from array`

## pseudocode

```c

```

## disassembly

```asm
0x51c60  ldarg.0
0x51c61  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::isArchivedPublisher
0x51c66  brfalse.s loc_51C7C
0x51c68  ldarg.0
0x51c69  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Windows.ManagementUI.CombinedControls.RenderValueExLong> Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::keywords
0x51c6e  brtrue.s loc_51C7B
0x51c70  ldarg.0
0x51c71  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Windows.ManagementUI.CombinedControls.RenderValueExLong>::.ctor()
0x51c76  stfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Windows.ManagementUI.CombinedControls.RenderValueExLong> Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::keywords
0x51c7b  ret
0x51c7c  ldc.i4.0
0x51c7d  stloc.0
0x51c7e  ldarg.0
0x51c7f  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::Initialize()
0x51c84  pop
0x51c85  ldarg.0
0x51c86  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Windows.ManagementUI.CombinedControls.RenderValueExLong> Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::keywords
0x51c8b  brtrue   loc_52007
0x51c90  ldarg.0
0x51c91  call     instance native int Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::get_PublisherHandle()
0x51c96  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x51c9b  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x51ca0  brfalse  loc_52007
0x51ca5  ldloca.s 1
0x51ca7  initobj  Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x51cad  sizeof   Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x51cb3  stloc.2
0x51cb4  ldarg.0
0x51cb5  call     instance native int Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::get_PublisherHandle()
0x51cba  ldc.i4.s 0x19
0x51cbc  ldc.i4.0
0x51cbd  sizeof   Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x51cc3  ldloca.s 1
0x51cc5  ldloca.s 2
0x51cc7  call     bool Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::GetPublisherMetadataProperty(native int publisherMetadata, [hasfieldmarshal] valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventPublisherMetadataPropertyID propertyId, int32 flags, int32 bufferSize, valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventVariant& publisherMetadataPropertyBuffer, int32& publisherMetadataPropertyBufferUsed)
0x51ccc  stloc.3
0x51ccd  ldloc.3
0x51cce  brtrue.s loc_51CED
0x51cd0  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x51cd5  stloc.0
0x51cd6  ldstr    aGettingPublish// "Getting Publisher metadata property Pub"...
0x51cdb  ldarg.0
0x51cdc  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::identifier
0x51ce1  call     string [mscorlib]System.String::Concat(string, string)
0x51ce6  ldloc.0
0x51ce7  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x51cec  ret
0x51ced  ldloc.1
0x51cee  ldfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::type
0x51cf3  ldc.i4.s 0x20
0x51cf5  beq.s    loc_51D0D
0x51cf7  ldstr    aWrongTypeRecei_0// "Wrong type received from crimson for Pu"...
0x51cfc  ldarg.0
0x51cfd  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::identifier
0x51d02  call     string [mscorlib]System.String::Concat(string, string)
0x51d07  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string errorString)
0x51d0c  ret
0x51d0d  ldc.i4.0
0x51d0e  stloc.s  4
0x51d10  ldarg.0
0x51d11  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Windows.ManagementUI.CombinedControls.RenderValueExLong>::.ctor()
0x51d16  stfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Windows.ManagementUI.CombinedControls.RenderValueExLong> Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::keywords
0x51d1b  ldloc.1
0x51d1c  ldfld    native int Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::EvtHandle
0x51d21  ldloca.s 4
0x51d23  call     bool Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::GetObjectArraySize(native int objectArray, int32& objectArraySize)
0x51d28  brtrue.s loc_51D4B
0x51d2a  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x51d2f  stloc.0
0x51d30  ldstr    aGetobjectarray// "GetObjectArraySize on crimson for Publi"...
0x51d35  ldarg.0
0x51d36  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::identifier
0x51d3b  call     string [mscorlib]System.String::Concat(string, string)
0x51d40  ldloc.0
0x51d41  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x51d46  br       loc_51FDE
0x51d4b  ldloc.s  4
0x51d4d  ldc.i4.0
0x51d4e  ble      loc_51FDE
0x51d53  ldloca.s 5
0x51d55  initobj  Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x51d5b  ldsfld   string [mscorlib]System.String::Empty
0x51d60  stloc.s  8
0x51d62  ldc.i4.m1
0x51d63  stloc.s  9
0x51d65  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::PrepareConstrainedRegions()
0x51d6a  leave    loc_51FDE
0x51d6f  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.SafeGlobalHandle::.ctor()
0x51d74  stloc.s  0xA
0x51d76  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x51d7b  stloc.s  0xB
0x51d7d  ldc.i4.0
0x51d7e  stloc.s  0xC
0x51d80  ldc.i4.0
0x51d81  stloc.s  0xD
0x51d83  br       loc_51FCD
0x51d88  ldc.i4.0
0x51d89  conv.i8
0x51d8a  stloc.s  6
0x51d8c  ldsfld   string [mscorlib]System.String::Empty
0x51d91  stloc.s  7
0x51d93  ldsfld   string [mscorlib]System.String::Empty
0x51d98  stloc.s  8
0x51d9a  ldc.i4.0
0x51d9b  stloc.s  9
0x51d9d  ldloc.1
0x51d9e  ldfld    native int Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::EvtHandle
0x51da3  ldc.i4.s 0x1B
0x51da5  ldloc.s  0xD
0x51da7  ldc.i4.0
0x51da8  sizeof   Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x51dae  ldloca.s 5
0x51db0  ldloca.s 2
0x51db2  call     bool Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::GetObjectArrayProperty(native int objectArray, int32 propertyId, int32 arrayIndex, int32 flags, int32 propertyValueBufferSize, valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventVariant& propertyValueBuffer, int32& propertyValueBufferUsed)
0x51db7  brtrue.s loc_51DD7
0x51db9  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x51dbe  stloc.0
0x51dbf  ldstr    aGettingItemFro// "Getting Item from array failed Publishe"...
0x51dc4  ldarg.0
0x51dc5  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::identifier
0x51dca  call     string [mscorlib]System.String::Concat(string, string)
0x51dcf  ldloc.0
0x51dd0  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x51dd5  br.s     loc_51E0D
0x51dd7  ldloc.s  5
0x51dd9  ldfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::type
0x51dde  ldc.i4.s 9
0x51de0  beq.s    loc_51DED
0x51de2  ldloc.s  5
0x51de4  ldfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::type
0x51de9  ldc.i4.s 0xA
0x51deb  bne.un.s loc_51DF8
0x51ded  ldloc.s  5
0x51def  ldfld    unsigned int64 Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::UInt64Val
0x51df4  stloc.s  6
0x51df6  br.s     loc_51E0D
0x51df8  ldstr    aWrongTypeRecei_1// "Wrong type received from crimson for Pu"...
0x51dfd  ldarg.0
0x51dfe  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::identifier
0x51e03  call     string [mscorlib]System.String::Concat(string, string)
0x51e08  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string errorString)
0x51e0d  ldarg.0
0x51e0e  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::context
0x51e13  brfalse.s loc_51E27
0x51e15  ldarg.0
0x51e16  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::context
0x51e1b  ldloc.s  6
0x51e1d  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::IsStandardKeyword(unsigned int64 keyword)
0x51e22  brtrue   loc_51FC7
0x51e27  ldloc.1
0x51e28  ldfld    native int Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::EvtHandle
0x51e2d  ldc.i4.s 0x1C
0x51e2f  ldloc.s  0xD
0x51e31  ldc.i4.0
0x51e32  sizeof   Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x51e38  ldloca.s 5
0x51e3a  ldloca.s 2
0x51e3c  call     bool Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::GetObjectArrayProperty(native int objectArray, int32 propertyId, int32 arrayIndex, int32 flags, int32 propertyValueBufferSize, valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventVariant& propertyValueBuffer, int32& propertyValueBufferUsed)
0x51e41  brtrue.s loc_51E61
0x51e43  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x51e48  stloc.0
0x51e49  ldstr    aGettingItemFro_0// "Getting Item from array failed Publishe"...
0x51e4e  ldarg.0
0x51e4f  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::identifier
0x51e54  call     string [mscorlib]System.String::Concat(string, string)
0x51e59  ldloc.0
0x51e5a  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x51e5f  br.s     loc_51E95
0x51e61  ldloc.s  5
0x51e63  ldfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::type
0x51e68  ldc.i4.7
0x51e69  beq.s    loc_51E75
0x51e6b  ldloc.s  5
0x51e6d  ldfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::type
0x51e72  ldc.i4.8
0x51e73  bne.un.s loc_51E80
0x51e75  ldloc.s  5
0x51e77  ldfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::Int32Val
0x51e7c  stloc.s  9
0x51e7e  br.s     loc_51E95
0x51e80  ldstr    aWrongTypeRecei_2// "Wrong type received from crimson for Pu"...
0x51e85  ldarg.0
0x51e86  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::identifier
0x51e8b  call     string [mscorlib]System.String::Concat(string, string)
0x51e90  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string errorString)
0x51e95  ldloc.s  0xC
0x51e97  stloc.2
0x51e98  ldloc.1
0x51e99  ldfld    native int Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::EvtHandle
0x51e9e  ldc.i4.s 0x1A
0x51ea0  ldloc.s  0xD
0x51ea2  ldc.i4.0
0x51ea3  ldloc.s  0xC
0x51ea5  ldloc.s  0xB
0x51ea7  ldloca.s 2
0x51ea9  call     bool Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::GetObjectArrayPropertyBuffer(native int objectArray, int32 propertyId, int32 arrayIndex, int32 flags, int32 propertyValueBufferSize, native int propertyValueBuffer, int32& propertyValueBufferUsed)
0x51eae  stloc.3
0x51eaf  ldloc.3
0x51eb0  brtrue.s loc_51EB8
0x51eb2  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x51eb7  stloc.0
0x51eb8  ldloc.3
0x51eb9  brtrue   loc_51F40
0x51ebe  ldloc.0
0x51ebf  call     bool Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::IsInsufficientBuffer(int32 error)
0x51ec4  brfalse.s loc_51F40
0x51ec6  ldstr    aPublishermetad_1// "PublisherMetadataKeywordName failed for"...
0x51ecb  ldarg.0
0x51ecc  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::identifier
0x51ed1  call     string [mscorlib]System.String::Concat(string, string)
0x51ed6  ldloc.0
0x51ed7  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x51edc  ldloc.s  0xC
0x51ede  brfalse.s loc_51EE7
0x51ee0  ldloc.s  0xA
0x51ee2  callvirt instance void [mscorlib]System.Runtime.InteropServices.SafeHandle::Close()
0x51ee7  ldloc.2
0x51ee8  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::AllocHGlobal(int32)
0x51eed  stloc.s  0xB
0x51eef  ldloc.s  0xB
0x51ef1  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x51ef6  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x51efb  brfalse.s loc_51F59
0x51efd  ldloc.s  0xA
0x51eff  ldloc.s  0xB
0x51f01  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.SafeGlobalHandle::InitHandle(native int inHandle)
0x51f06  ldloc.2
0x51f07  stloc.s  0xC
0x51f09  ldloc.1
0x51f0a  ldfld    native int Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::EvtHandle
0x51f0f  ldc.i4.s 0x1A
0x51f11  ldloc.s  0xD
0x51f13  ldc.i4.0
0x51f14  ldloc.2
0x51f15  ldloc.s  0xB
0x51f17  ldloca.s 2
0x51f19  call     bool Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::GetObjectArrayPropertyBuffer(native int objectArray, int32 propertyId, int32 arrayIndex, int32 flags, int32 propertyValueBufferSize, native int propertyValueBuffer, int32& propertyValueBufferUsed)
0x51f1e  stloc.3
0x51f1f  ldloc.3
0x51f20  brtrue.s loc_51F59
0x51f22  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x51f27  stloc.0
0x51f28  ldstr    aPublishermetad_2// "PublisherMetadataKeywordName failed in "...
0x51f2d  ldarg.0
0x51f2e  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::identifier
0x51f33  call     string [mscorlib]System.String::Concat(string, string)
0x51f38  ldloc.0
0x51f39  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x51f3e  br.s     loc_51F59
0x51f40  ldloc.3
0x51f41  brtrue.s loc_51F59
0x51f43  ldstr    aPublishermetad_2// "PublisherMetadataKeywordName failed in "...
0x51f48  ldarg.0
0x51f49  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::identifier
0x51f4e  call     string [mscorlib]System.String::Concat(string, string)
0x51f53  ldloc.0
0x51f54  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x51f59  ldloc.3
0x51f5a  brfalse.s loc_51FC7
0x51f5c  ldarg.0
0x51f5d  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::identifier
0x51f62  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x51f67  brfalse.s loc_51F6E
0x51f69  ldloc.s  9
0x51f6b  ldc.i4.m1
0x51f6c  beq.s    loc_51FC7
0x51f6e  ldloc.s  0xB
0x51f70  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x51f75  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x51f7a  call     object [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStructure(native int, class [mscorlib]System.Type)
0x51f7f  unbox.any Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x51f84  stloc.s  5
0x51f86  ldloc.s  5
0x51f88  ldfld    native int Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::StringVal
0x51f8d  call     string [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStringAuto(native int)
0x51f92  stloc.s  7
0x51f94  ldarg.0
0x51f95  call     instance native int Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::get_PublisherHandle()
0x51f9a  ldloc.s  6
0x51f9c  ldloc.s  9
0x51f9e  ldc.i4.8
0x51f9f  call     string Microsoft.Windows.ManagementUI.CombinedControls.CrimsonEvent::GetSingleRenderedString(native int pubHandle, unsigned int64 value, int32 messageId, valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventFormatMessageFlags flag)
0x51fa4  stloc.s  8
0x51fa6  ldloc.s  8
0x51fa8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x51fad  brtrue.s loc_51FC7
0x51faf  ldarg.0
0x51fb0  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Windows.ManagementUI.CombinedControls.RenderValueExLong> Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::keywords
0x51fb5  ldloc.s  9
0x51fb7  ldloc.s  7
0x51fb9  ldloc.s  6
0x51fbb  ldloc.s  8
0x51fbd  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.RenderValueExLong::.ctor(int32 id, string name, unsigned int64 renderValue, string renderedString)
0x51fc2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Windows.ManagementUI.CombinedControls.RenderValueExLong>::Add(var<u1>)
0x51fc7  ldloc.s  0xD
0x51fc9  ldc.i4.1
0x51fca  add
0x51fcb  stloc.s  0xD
0x51fcd  ldloc.s  0xD
0x51fcf  ldloc.s  4
  ... truncated ...
```
