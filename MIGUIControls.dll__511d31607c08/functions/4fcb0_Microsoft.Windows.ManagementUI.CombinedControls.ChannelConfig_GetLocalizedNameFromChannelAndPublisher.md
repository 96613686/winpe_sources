# Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfig::GetLocalizedNameFromChannelAndPublisher

- ea: `0x4fcb0`
- end: `0x4fe47`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfig::GetLocalizedNameFromChannelAndPublisher`
- size: `407`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4fc10`

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
- `0x4fcb0`
- `0x512a0`
- `0x512b0`
- `0x513c0`
- `0x519f0`
- `0x52010`

## string_xrefs

- `0x4fd07`: `Failed to get ChannelConfigOwningPublisher `
- `0x4fd47`: `Failed to get ChannelConfigOwningPublisher `

## pseudocode

```c

```

## disassembly

```asm
0x4fcb0  ldarg.0
0x4fcb1  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfig::get_ChannelPath()
0x4fcb6  stloc.0
0x4fcb7  ldarg.1
0x4fcb8  ldsfld   string [mscorlib]System.String::Empty
0x4fcbd  stind.ref
0x4fcbe  ldarg.2
0x4fcbf  ldsfld   string [mscorlib]System.String::Empty
0x4fcc4  stind.ref
0x4fcc5  ldarg.0
0x4fcc6  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfig::get_IsLegacyLog()
0x4fccb  brtrue   loc_4FE33
0x4fcd0  ldloca.s 1
0x4fcd2  initobj  Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x4fcd8  ldloc.1
0x4fcd9  box      Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x4fcde  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::SizeOf(object)
0x4fce3  stloc.2
0x4fce4  ldc.i4.0
0x4fce5  stloc.3
0x4fce6  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x4fceb  stloc.s  4
0x4fced  ldarg.0
0x4fcee  call     instance native int Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfig::get_ChannelPtr()
0x4fcf3  ldc.i4.3
0x4fcf4  ldc.i4.0
0x4fcf5  ldloc.2
0x4fcf6  ldloca.s 1
0x4fcf8  ldloca.s 2
0x4fcfa  call     int32 Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::GetChannelConfigProperty(native int channelConfig, [hasfieldmarshal] valuetype Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfigPropertyID propertyId, int32 Flags, int32 propertyValueBufferSize, valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventVariant& PropertyValueBuffer, int32& bufLen)
0x4fcff  brtrue.s loc_4FD6D
0x4fd01  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x4fd06  stloc.3
0x4fd07  ldstr    aFailedToGetCha// "Failed to get ChannelConfigOwningPublis"...
0x4fd0c  ldloc.3
0x4fd0d  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x4fd12  ldloc.3
0x4fd13  ldc.i4.s 0x7A
0x4fd15  bne.un.s loc_4FD6D
0x4fd17  ldloc.2
0x4fd18  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::AllocHGlobal(int32)
0x4fd1d  stloc.s  4
0x4fd1f  ldloc.s  4
0x4fd21  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x4fd26  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x4fd2b  brfalse.s loc_4FD6D
0x4fd2d  ldarg.0
0x4fd2e  call     instance native int Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfig::get_ChannelPtr()
0x4fd33  ldc.i4.3
0x4fd34  ldc.i4.0
0x4fd35  ldloc.2
0x4fd36  ldloc.s  4
0x4fd38  ldloca.s 2
0x4fd3a  call     int32 Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::GetChannelConfigPropertyB(native int channelConfig, [hasfieldmarshal] valuetype Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfigPropertyID PropertyId, int32 Flags, int32 propertyValueBufferSize, native int PropertyValueBuffer, int32& bufLen)
0x4fd3f  brtrue.s loc_4FD54
0x4fd41  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x4fd46  stloc.3
0x4fd47  ldstr    aFailedToGetCha// "Failed to get ChannelConfigOwningPublis"...
0x4fd4c  ldloc.3
0x4fd4d  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x4fd52  br.s     loc_4FD6D
0x4fd54  ldloc.s  4
0x4fd56  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x4fd5b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4fd60  call     object [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStructure(native int, class [mscorlib]System.Type)
0x4fd65  unbox.any Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x4fd6a  stloc.1
0x4fd6b  ldc.i4.0
0x4fd6c  stloc.3
0x4fd6d  ldloc.3
0x4fd6e  brtrue.s loc_4FD79
0x4fd70  ldloc.1
0x4fd71  ldfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::type
0x4fd76  ldc.i4.2
0x4fd77  beq.s    loc_4FD85
0x4fd79  ldloc.1
0x4fd7a  ldfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::type
0x4fd7f  ldc.i4.1
0x4fd80  bne.un   loc_4FE2A
0x4fd85  ldarg.2
0x4fd86  ldloc.1
0x4fd87  call     object Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::VariantToObject(valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventVariant var)
0x4fd8c  castclass [mscorlib]System.String
0x4fd91  stind.ref
0x4fd92  ldarg.1
0x4fd93  ldarg.2
0x4fd94  ldind.ref
0x4fd95  stind.ref
0x4fd96  ldarg.1
0x4fd97  ldind.ref
0x4fd98  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4fd9d  brtrue   loc_4FE2A
0x4fda2  ldarg.0
0x4fda3  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.ConfigInstance::context
0x4fda8  ldarg.2
0x4fda9  ldind.ref
0x4fdaa  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::GetPublisher(string publisherId)
0x4fdaf  stloc.s  5
0x4fdb1  ldloc.s  5
0x4fdb3  brtrue.s loc_4FDC6
0x4fdb5  ldarg.2
0x4fdb6  ldind.ref
0x4fdb7  ldarg.2
0x4fdb8  ldind.ref
0x4fdb9  ldarg.0
0x4fdba  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.ConfigInstance::context
0x4fdbf  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::.ctor(string publisherIdentifier, string publisherName, class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext ctx)
0x4fdc4  stloc.s  5
0x4fdc6  ldarg.1
0x4fdc7  ldloc.s  5
0x4fdc9  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::get_LocalizedPublisherName()
0x4fdce  stind.ref
0x4fdcf  ldloc.s  5
0x4fdd1  callvirt instance class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::get_ChannelReferences()
0x4fdd6  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x4fddb  stloc.s  6
0x4fddd  br.s     loc_4FE0A
0x4fddf  ldloc.s  6
0x4fde1  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x4fde6  castclass Microsoft.Windows.ManagementUI.CombinedControls.PublisherChannelBase
0x4fdeb  stloc.s  7
0x4fded  ldarg.0
0x4fdee  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfig::get_ChannelPath()
0x4fdf3  ldloc.s  7
0x4fdf5  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.PublisherChannelBase::get_ChannelPath()
0x4fdfa  ldc.i4.5
0x4fdfb  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x4fe00  brtrue.s loc_4FE0A
0x4fe02  ldloc.s  7
0x4fe04  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.PublisherChannelBase::get_Name()
0x4fe09  stloc.0
0x4fe0a  ldloc.s  6
0x4fe0c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4fe11  brtrue.s loc_4FDDF
0x4fe13  leave.s  loc_4FE2A
0x4fe15  ldloc.s  6
0x4fe17  isinst   [mscorlib]System.IDisposable
0x4fe1c  stloc.s  8
0x4fe1e  ldloc.s  8
0x4fe20  brfalse.s loc_4FE29
0x4fe22  ldloc.s  8
0x4fe24  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4fe29  endfinally
0x4fe2a  ldloc.s  4
0x4fe2c  call     void [mscorlib]System.Runtime.InteropServices.Marshal::FreeHGlobal(native int)
0x4fe31  br.s     loc_4FE45
0x4fe33  ldarg.0
0x4fe34  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.ConfigInstance::context
0x4fe39  ldarg.0
0x4fe3a  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfig::get_ChannelPath()
0x4fe3f  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::GetLocalizedNameForClassicChannel(string classicChannelPath)
0x4fe44  stloc.0
0x4fe45  ldloc.0
0x4fe46  ret
```
