# Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfig::GetLocalizedNameFromChannel

- ea: `0x4fa90`
- end: `0x4fc03`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfig::GetLocalizedNameFromChannel`
- size: `371`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x50030`
- `0x50b80`

## callees

- `0x13510`
- `0x33e70`
- `0x38a20`
- `0x38ea0`
- `0x4d2a0`
- `0x4d2b0`
- `0x4ef90`
- `0x4f040`
- `0x4f480`
- `0x4fa90`
- `0x512a0`
- `0x512b0`
- `0x513c0`
- `0x52010`

## string_xrefs

- `0x4fad9`: `Failed to get ChannelConfigOwningPublisher `
- `0x4fb19`: `Failed to get ChannelConfigOwningPublisher `

## pseudocode

```c

```

## disassembly

```asm
0x4fa90  ldarg.0
0x4fa91  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfig::get_ChannelPath()
0x4fa96  stloc.0
0x4fa97  ldarg.0
0x4fa98  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfig::get_IsLegacyLog()
0x4fa9d  brtrue   loc_4FBEF
0x4faa2  ldloca.s 1
0x4faa4  initobj  Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x4faaa  ldloc.1
0x4faab  box      Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x4fab0  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::SizeOf(object)
0x4fab5  stloc.2
0x4fab6  ldc.i4.0
0x4fab7  stloc.3
0x4fab8  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x4fabd  stloc.s  4
0x4fabf  ldarg.0
0x4fac0  call     instance native int Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfig::get_ChannelPtr()
0x4fac5  ldc.i4.3
0x4fac6  ldc.i4.0
0x4fac7  ldloc.2
0x4fac8  ldloca.s 1
0x4faca  ldloca.s 2
0x4facc  call     int32 Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::GetChannelConfigProperty(native int channelConfig, [hasfieldmarshal] valuetype Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfigPropertyID propertyId, int32 Flags, int32 propertyValueBufferSize, valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventVariant& PropertyValueBuffer, int32& bufLen)
0x4fad1  brtrue.s loc_4FB3F
0x4fad3  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x4fad8  stloc.3
0x4fad9  ldstr    aFailedToGetCha// "Failed to get ChannelConfigOwningPublis"...
0x4fade  ldloc.3
0x4fadf  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x4fae4  ldloc.3
0x4fae5  ldc.i4.s 0x7A
0x4fae7  bne.un.s loc_4FB3F
0x4fae9  ldloc.2
0x4faea  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::AllocHGlobal(int32)
0x4faef  stloc.s  4
0x4faf1  ldloc.s  4
0x4faf3  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x4faf8  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x4fafd  brfalse.s loc_4FB3F
0x4faff  ldarg.0
0x4fb00  call     instance native int Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfig::get_ChannelPtr()
0x4fb05  ldc.i4.3
0x4fb06  ldc.i4.0
0x4fb07  ldloc.2
0x4fb08  ldloc.s  4
0x4fb0a  ldloca.s 2
0x4fb0c  call     int32 Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::GetChannelConfigPropertyB(native int channelConfig, [hasfieldmarshal] valuetype Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfigPropertyID PropertyId, int32 Flags, int32 propertyValueBufferSize, native int PropertyValueBuffer, int32& bufLen)
0x4fb11  brtrue.s loc_4FB26
0x4fb13  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x4fb18  stloc.3
0x4fb19  ldstr    aFailedToGetCha// "Failed to get ChannelConfigOwningPublis"...
0x4fb1e  ldloc.3
0x4fb1f  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x4fb24  br.s     loc_4FB3F
0x4fb26  ldloc.s  4
0x4fb28  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x4fb2d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4fb32  call     object [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStructure(native int, class [mscorlib]System.Type)
0x4fb37  unbox.any Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x4fb3c  stloc.1
0x4fb3d  ldc.i4.0
0x4fb3e  stloc.3
0x4fb3f  ldloc.3
0x4fb40  brtrue.s loc_4FB4B
0x4fb42  ldloc.1
0x4fb43  ldfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::type
0x4fb48  ldc.i4.2
0x4fb49  beq.s    loc_4FB57
0x4fb4b  ldloc.1
0x4fb4c  ldfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::type
0x4fb51  ldc.i4.1
0x4fb52  bne.un   loc_4FC01
0x4fb57  ldloc.1
0x4fb58  call     object Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::VariantToObject(valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventVariant var)
0x4fb5d  castclass [mscorlib]System.String
0x4fb62  stloc.s  5
0x4fb64  ldloc.s  5
0x4fb66  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4fb6b  brtrue   loc_4FC01
0x4fb70  ldarg.0
0x4fb71  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.ConfigInstance::context
0x4fb76  ldloc.s  5
0x4fb78  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::GetPublisher(string publisherId)
0x4fb7d  stloc.s  6
0x4fb7f  ldloc.s  6
0x4fb81  brtrue.s loc_4FB94
0x4fb83  ldloc.s  5
0x4fb85  ldloc.s  5
0x4fb87  ldarg.0
0x4fb88  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.ConfigInstance::context
0x4fb8d  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::.ctor(string publisherIdentifier, string publisherName, class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext ctx)
0x4fb92  stloc.s  6
0x4fb94  ldloc.s  6
0x4fb96  callvirt instance class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::get_ChannelReferences()
0x4fb9b  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x4fba0  stloc.s  7
0x4fba2  br.s     loc_4FBCF
0x4fba4  ldloc.s  7
0x4fba6  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x4fbab  castclass Microsoft.Windows.ManagementUI.CombinedControls.PublisherChannelBase
0x4fbb0  stloc.s  8
0x4fbb2  ldarg.0
0x4fbb3  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfig::get_ChannelPath()
0x4fbb8  ldloc.s  8
0x4fbba  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.PublisherChannelBase::get_ChannelPath()
0x4fbbf  ldc.i4.5
0x4fbc0  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x4fbc5  brtrue.s loc_4FBCF
0x4fbc7  ldloc.s  8
0x4fbc9  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.PublisherChannelBase::get_Name()
0x4fbce  stloc.0
0x4fbcf  ldloc.s  7
0x4fbd1  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4fbd6  brtrue.s loc_4FBA4
0x4fbd8  leave.s  loc_4FC01
0x4fbda  ldloc.s  7
0x4fbdc  isinst   [mscorlib]System.IDisposable
0x4fbe1  stloc.s  9
0x4fbe3  ldloc.s  9
0x4fbe5  brfalse.s loc_4FBEE
0x4fbe7  ldloc.s  9
0x4fbe9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4fbee  endfinally
0x4fbef  ldarg.0
0x4fbf0  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.ConfigInstance::context
0x4fbf5  ldarg.0
0x4fbf6  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfig::get_ChannelPath()
0x4fbfb  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::GetLocalizedNameForClassicChannel(string classicChannelPath)
0x4fc00  stloc.0
0x4fc01  ldloc.0
0x4fc02  ret
```
