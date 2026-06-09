# Microsoft.Windows.ManagementUI.CombinedControls.CrimsonEvent::GetEventMessage

- ea: `0x3b8e0`
- end: `0x3c8d9`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.CrimsonEvent::GetEventMessage`
- size: `4089`
- prototype: ``
- caller_count: `2`
- callee_count: `39`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x3db00`
- `0x3e000`

## callees

- `0x12840`
- `0x12860`
- `0x12ed0`
- `0x13510`
- `0x1cd50`
- `0x1ce20`
- `0x32e90`
- `0x33c10`
- `0x33e70`
- `0x340c0`
- `0x34110`
- `0x344d0`
- `0x34fe0`
- `0x35250`
- `0x38840`
- `0x390b0`
- `0x395e0`
- `0x399c0`
- `0x39df0`
- `0x39f20`
- `0x39f70`
- `0x39ff0`
- `0x3a4c0`
- `0x3a4e0`
- `0x3a500`
- `0x3a520`
- `0x3a530`
- `0x3ae30`
- `0x3b090`
- `0x3b8e0`
- `0x3c8e0`
- `0x3c9a0`
- `0x3d5b0`
- `0x3d620`
- `0x3d9d0`
- `0x3dde0`
- `0x4d1c0`
- `0x4d1d0`
- `0x4d1e0`

## string_xrefs

- `0x3b970`: `DeletedEventMessage`
- `0x3c02a`: `GetEventMessage-AdjustingSIDVales`
- `0x3c1d3`: `GetEventMessage-AdjustingSIdVales`

## pseudocode

```c

```

## disassembly

```asm
0x3b8e0  ldarg.0
0x3b8e1  ldstr    aGeteventmessag// "GetEventMessage"
0x3b8e6  call     void Microsoft.Windows.ManagementUI.CombinedControls.TimeTrace::StartMethod(object thisObject, string methodName)
0x3b8eb  ldc.i4.0
0x3b8ec  stloc.0
0x3b8ed  ldc.i4.0
0x3b8ee  stloc.1
0x3b8ef  ldsfld   class Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::safeUserContext
0x3b8f4  callvirt instance native int Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle::get_Handle()
0x3b8f9  stloc.2
0x3b8fa  ldc.i4.0
0x3b8fb  stloc.3
0x3b8fc  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x3b901  stloc.s  4
0x3b903  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x3b908  stloc.s  5
0x3b90a  ldsfld   string [mscorlib]System.String::Empty
0x3b90f  stloc.s  6
0x3b911  ldc.i4.0
0x3b912  stloc.s  7
0x3b914  ldnull
0x3b915  stloc.s  8
0x3b917  ldarg.0
0x3b918  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.CrimsonEvent::context
0x3b91d  ldarg.0
0x3b91e  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.CrimsonEvent::get_Source()
0x3b923  callvirt instance native int Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::GetPublisherHandle(string publisherIdentifier)
0x3b928  stloc.s  9
0x3b92a  ldloca.s 0xA
0x3b92c  initobj  Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x3b932  ldc.i4.0
0x3b933  stloc.s  0xB
0x3b935  ldc.i4.0
0x3b936  stloc.s  0xC
0x3b938  ldloc.s  4
0x3b93a  stloc.s  0xD
0x3b93c  ldstr    aEvRenderedvalu// "EV_RenderedValue_"
0x3b941  stloc.s  0xE
0x3b943  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x3b948  stloc.s  0xF
0x3b94a  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x3b94f  stloc.s  0x10
0x3b951  ldc.i4.0
0x3b952  stloc.s  0x11
0x3b954  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x3b959  stloc.s  0x13
0x3b95b  ldc.i4.0
0x3b95c  stloc.s  0x14
0x3b95e  ldarg.0
0x3b95f  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.LiteEventRecord Microsoft.Windows.ManagementUI.CombinedControls.CrimsonEvent::_liteRec
0x3b964  ldfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.LiteEventRecord::LevelValue
0x3b969  ldsfld   int32 Microsoft.Windows.ManagementUI.CombinedControls.CrimsonEvent::EventAlreadyDeletedLevel
0x3b96e  bne.un.s loc_3B97C
0x3b970  ldstr    aDeletedeventme// "DeletedEventMessage"
0x3b975  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x3b97a  stloc.s  6
0x3b97c  ldarg.0
0x3b97d  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.LiteEventRecord Microsoft.Windows.ManagementUI.CombinedControls.CrimsonEvent::_liteRec
0x3b982  ldfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.LiteEventRecord::LevelValue
0x3b987  ldsfld   int32 Microsoft.Windows.ManagementUI.CombinedControls.CrimsonEvent::EventLogCorruptLevel
0x3b98c  bne.un.s loc_3B99A
0x3b98e  call     string Microsoft.Windows.ManagementUI.CombinedControls.CrimsonEvent::get_CorruptEventMessage()
0x3b993  stloc.s  6
0x3b995  leave    loc_3C8B2
0x3b99a  ldarg.0
0x3b99b  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.LiteEventRecord Microsoft.Windows.ManagementUI.CombinedControls.CrimsonEvent::_liteRec
0x3b9a0  ldfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.LiteEventRecord::LevelValue
0x3b9a5  ldsfld   int32 Microsoft.Windows.ManagementUI.CombinedControls.CrimsonEvent::GenericErrorLevel
0x3b9aa  bne.un.s loc_3B9BE
0x3b9ac  ldarg.0
0x3b9ad  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.LiteEventRecord Microsoft.Windows.ManagementUI.CombinedControls.CrimsonEvent::_liteRec
0x3b9b2  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.LiteEventRecord::Level
0x3b9b7  stloc.s  6
0x3b9b9  leave    loc_3C8B2
0x3b9be  ldloc.2
0x3b9bf  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x3b9c4  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x3b9c9  brfalse.s loc_3B9F2
0x3b9cb  ldc.i4.0
0x3b9cc  ldnull
0x3b9cd  ldc.i4.2
0x3b9ce  call     native int Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::CreateRenderContext(int32 countOfValues, string[] valuePaths, int32 flags)
0x3b9d3  stloc.2
0x3b9d4  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x3b9d9  stloc.0
0x3b9da  ldloc.2
0x3b9db  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x3b9e0  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x3b9e5  brfalse.s loc_3B9F2
0x3b9e7  ldsfld   class Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::safeUserContext
0x3b9ec  ldloc.2
0x3b9ed  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle::InitHandle(native int crimsonHandle)
0x3b9f2  ldloc.2
0x3b9f3  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x3b9f8  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x3b9fd  brfalse  loc_3C61E
0x3ba02  ldarg.0
0x3ba03  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.CrimsonEvent::get_Computer()
0x3ba08  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3ba0d  brtrue.s loc_3BA17
0x3ba0f  ldarg.0
0x3ba10  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.CrimsonEvent::get_Computer()
0x3ba15  br.s     loc_3BA22
0x3ba17  ldarg.0
0x3ba18  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.CrimsonEvent::context
0x3ba1d  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::get_RemoteComputer()
0x3ba22  stloc.s  0x15
0x3ba24  ldarg.s  4
0x3ba26  ldc.i4.m1
0x3ba27  bne.un.s loc_3BA36
0x3ba29  ldarg.0
0x3ba2a  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.LiteEventRecord Microsoft.Windows.ManagementUI.CombinedControls.CrimsonEvent::get_LiteRecord()
0x3ba2f  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x3ba34  starg.s  4
0x3ba36  ldarg.3
0x3ba37  ldc.i4.m1
0x3ba38  bne.un.s loc_3BA4C
0x3ba3a  ldarg.0
0x3ba3b  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.CrimsonEvent::context
0x3ba40  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.AsyncRendering Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::get_AsynchronousRendering()
0x3ba45  callvirt instance int32 Microsoft.Windows.ManagementUI.CombinedControls.AsyncRendering::BeginBatchRendering()
0x3ba4a  starg.s  3
0x3ba4c  sizeof   Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x3ba52  ldc.i4   0xC8
0x3ba57  add
0x3ba58  ldc.i4.5
0x3ba59  mul
0x3ba5a  stloc.s  0x16
0x3ba5c  ldloc.s  0x16
0x3ba5e  stloc.s  0x17
0x3ba60  ldarg.0
0x3ba61  ldstr    aGeteventmessag_0// "GetEventMessage-GettingValues"
0x3ba66  call     void Microsoft.Windows.ManagementUI.CombinedControls.TimeTrace::StartMethod(object thisObject, string methodName)
0x3ba6b  ldloc.s  0x16
0x3ba6d  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::AllocHGlobal(int32)
0x3ba72  stloc.s  4
0x3ba74  ldloc.2
0x3ba75  ldarg.0
0x3ba76  ldfld    native int Microsoft.Windows.ManagementUI.CombinedControls.CrimsonEvent::_evtHandle
0x3ba7b  ldc.i4.0
0x3ba7c  ldloc.s  0x17
0x3ba7e  ldloc.s  4
0x3ba80  ldloca.s 0x17
0x3ba82  ldloca.s 0xC
0x3ba84  call     bool Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::RenderEventToBuffer(native int context, native int eventHandle, int32 flags, int32 buffSize, native int buff, int32& buffUsed, int32& propCount)
0x3ba89  stloc.3
0x3ba8a  ldloc.3
0x3ba8b  brtrue.s loc_3BA93
0x3ba8d  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x3ba92  stloc.0
0x3ba93  ldloc.s  0x17
0x3ba95  ldloc.s  0x16
0x3ba97  ble.s    loc_3BAE4
0x3ba99  ldloc.0
0x3ba9a  call     bool Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::IsInsufficientBuffer(int32 error)
0x3ba9f  brfalse.s loc_3BAE4
0x3baa1  ldstr    aBufferInsuffic// "Buffer insufficient for RenderEvent for"...
0x3baa6  ldloc.0
0x3baa7  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x3baac  ldloc.s  4
0x3baae  call     void [mscorlib]System.Runtime.InteropServices.Marshal::FreeHGlobal(native int)
0x3bab3  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x3bab8  stloc.s  4
0x3baba  ldloc.s  0x17
0x3babc  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::AllocHGlobal(int32)
0x3bac1  stloc.s  4
0x3bac3  ldloc.2
0x3bac4  ldarg.0
0x3bac5  ldfld    native int Microsoft.Windows.ManagementUI.CombinedControls.CrimsonEvent::_evtHandle
0x3baca  ldc.i4.0
0x3bacb  ldloc.s  0x17
0x3bacd  ldloc.s  4
0x3bacf  ldloca.s 0x17
0x3bad1  ldloca.s 0xC
0x3bad3  call     bool Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::RenderEventToBuffer(native int context, native int eventHandle, int32 flags, int32 buffSize, native int buff, int32& buffUsed, int32& propCount)
0x3bad8  stloc.3
0x3bad9  ldc.i4.0
0x3bada  stloc.0
0x3badb  ldloc.3
0x3badc  brtrue.s loc_3BAE4
0x3bade  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x3bae3  stloc.0
0x3bae4  ldarg.0
0x3bae5  ldstr    aGeteventmessag_0// "GetEventMessage-GettingValues"
0x3baea  call     void Microsoft.Windows.ManagementUI.CombinedControls.TimeTrace::EndMethod(object thisObject, string methodName)
0x3baef  ldloc.s  0x17
0x3baf1  ldc.i4.0
0x3baf2  ble.s    loc_3BB23
0x3baf4  ldloc.0
0x3baf5  brtrue.s loc_3BB23
0x3baf7  ldloc.s  0x17
0x3baf9  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::AllocHGlobal(int32)
0x3bafe  stloc.s  0x10
0x3bb00  ldc.i4.0
0x3bb01  stloc.s  0x18
0x3bb03  br.s     loc_3BB1D
0x3bb05  ldloc.s  0x10
0x3bb07  ldloc.s  0x18
0x3bb09  ldloc.s  4
0x3bb0b  ldloc.s  0x18
0x3bb0d  call     unsigned int8 [mscorlib]System.Runtime.InteropServices.Marshal::ReadByte(native int, int32)
0x3bb12  call     void [mscorlib]System.Runtime.InteropServices.Marshal::WriteByte(native int, int32, unsigned int8)
0x3bb17  ldloc.s  0x18
0x3bb19  ldc.i4.1
0x3bb1a  add
0x3bb1b  stloc.s  0x18
0x3bb1d  ldloc.s  0x18
0x3bb1f  ldloc.s  0x17
0x3bb21  blt.s    loc_3BB05
0x3bb23  ldarg.0
0x3bb24  ldstr    aGeteventmessag_1// "GetEventMessage-AdjustingValuesWithDumm"...
0x3bb29  call     void Microsoft.Windows.ManagementUI.CombinedControls.TimeTrace::StartMethod(object thisObject, string methodName)
0x3bb2e  ldloc.s  0xC
0x3bb30  ldc.i4.0
0x3bb31  ble      loc_3BDDB
0x3bb36  ldloc.s  4
0x3bb38  stloc.s  0xD
0x3bb3a  ldc.i4.0
0x3bb3b  stloc.s  0xB
0x3bb3d  br       loc_3BDD2
0x3bb42  ldloc.s  0xE
0x3bb44  ldloca.s 0xB
0x3bb46  ldstr    aN// "N"
0x3bb4b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3bb50  ldtoken  [mscorlib]System.UInt32
0x3bb55  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3bb5a  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x3bb5f  castclass [mscorlib]System.IFormatProvider
0x3bb64  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x3bb69  call     string [mscorlib]System.String::Concat(string, string)
0x3bb6e  stloc.s  0x12
0x3bb70  ldc.i4.0
0x3bb71  stloc.s  0x11
0x3bb73  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x3bb78  stloc.s  0x13
0x3bb7a  ldloc.s  0xD
0x3bb7c  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x3bb81  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3bb86  call     object [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStructure(native int, class [mscorlib]System.Type)
0x3bb8b  unbox.any Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x3bb90  stloc.s  0xA
0x3bb92  ldloc.s  0xA
0x3bb94  ldfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::type
0x3bb99  ldc.i4.s 0x13
0x3bb9b  beq.s    loc_3BBA8
0x3bb9d  ldloc.s  0xA
0x3bb9f  ldfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::type
0x3bba4  ldc.i4.s 0xF
0x3bba6  bne.un.s loc_3BBC0
0x3bba8  ldloc.s  0xF
0x3bbaa  ldloc.s  0xB
0x3bbac  box      [mscorlib]System.Int32
0x3bbb1  ldloc.s  0x12
0x3bbb3  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x3bbb8  ldc.i4.1
0x3bbb9  stloc.s  0x11
0x3bbbb  br       loc_3BD44
0x3bbc0  ldloc.s  0xA
0x3bbc2  ldfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::type
0x3bbc7  ldc.i4.s 0x11
0x3bbc9  beq.s    loc_3BBD6
0x3bbcb  ldloc.s  0xA
0x3bbcd  ldfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::type
0x3bbd2  ldc.i4.s 0x12
0x3bbd4  bne.un.s loc_3BBEB
0x3bbd6  ldloc.s  0xF
0x3bbd8  ldloc.s  0xB
0x3bbda  box      [mscorlib]System.Int32
0x3bbdf  ldloc.s  0x12
0x3bbe1  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x3bbe6  br       loc_3BD44
0x3bbeb  ldloc.s  0xA
0x3bbed  ldfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::type
0x3bbf2  ldc.i4.2
0x3bbf3  beq.s    loc_3BC02
0x3bbf5  ldloc.s  0xA
0x3bbf7  ldfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::type
0x3bbfc  ldc.i4.1
0x3bbfd  bne.un   loc_3BD44
0x3bc02  ldloc.s  0xA
0x3bc04  call     object Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::VariantToObject(valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventVariant var)
0x3bc09  castclass [mscorlib]System.String
0x3bc0e  stloc.s  0x12
0x3bc10  ldloc.s  0x12
0x3bc12  callvirt instance string [mscorlib]System.String::Trim()
0x3bc17  stloc.s  0x12
0x3bc19  ldloc.s  0x12
0x3bc1b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3bc20  brtrue   loc_3BD44
0x3bc25  ldloc.s  0x12
0x3bc27  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.CrimsonEvent::SidRendering
0x3bc2c  ldc.i4.4
0x3bc2d  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x3bc32  ldc.i4.0
0x3bc33  ble.s    loc_3BC4D
0x3bc35  ldloc.s  0x12
0x3bc37  ldloc.s  0x12
0x3bc39  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.CrimsonEvent::SidRendering
0x3bc3e  ldc.i4.4
0x3bc3f  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
  ... truncated ...
```
