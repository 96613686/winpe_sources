# Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfig::get_OwningPublisher

- ea: `0x4f530`
- end: `0x4f5fa`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfig::get_OwningPublisher`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x504e0`

## callees

- `0x13510`
- `0x33e70`
- `0x4d2a0`
- `0x4d2b0`
- `0x4ef90`
- `0x4f530`

## string_xrefs

- `0x4f56d`: `Failed to get ChannelConfigOwningPublisher `
- `0x4f5aa`: `Failed to get ChannelConfigOwningPublisher `

## pseudocode

```c

```

## disassembly

```asm
0x4f530  ldloca.s 0
0x4f532  initobj  Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x4f538  ldloc.0
0x4f539  box      Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x4f53e  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::SizeOf(object)
0x4f543  stloc.1
0x4f544  ldc.i4.0
0x4f545  stloc.2
0x4f546  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x4f54b  stloc.3
0x4f54c  ldsfld   string [mscorlib]System.String::Empty
0x4f551  stloc.s  4
0x4f553  ldarg.0
0x4f554  call     instance native int Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfig::get_ChannelPtr()
0x4f559  ldc.i4.3
0x4f55a  ldc.i4.0
0x4f55b  ldloc.1
0x4f55c  ldloca.s 0
0x4f55e  ldloca.s 1
0x4f560  call     int32 Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::GetChannelConfigProperty(native int channelConfig, [hasfieldmarshal] valuetype Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfigPropertyID propertyId, int32 Flags, int32 propertyValueBufferSize, valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventVariant& PropertyValueBuffer, int32& bufLen)
0x4f565  brtrue.s loc_4F5CF
0x4f567  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x4f56c  stloc.2
0x4f56d  ldstr    aFailedToGetCha// "Failed to get ChannelConfigOwningPublis"...
0x4f572  ldloc.2
0x4f573  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x4f578  ldloc.2
0x4f579  ldc.i4.s 0x7A
0x4f57b  bne.un.s loc_4F5CF
0x4f57d  ldloc.1
0x4f57e  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::AllocHGlobal(int32)
0x4f583  stloc.3
0x4f584  ldloc.3
0x4f585  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x4f58a  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x4f58f  brfalse.s loc_4F5CF
0x4f591  ldarg.0
0x4f592  call     instance native int Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfig::get_ChannelPtr()
0x4f597  ldc.i4.3
0x4f598  ldc.i4.0
0x4f599  ldloc.1
0x4f59a  ldloc.3
0x4f59b  ldloca.s 1
0x4f59d  call     int32 Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::GetChannelConfigPropertyB(native int channelConfig, [hasfieldmarshal] valuetype Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfigPropertyID PropertyId, int32 Flags, int32 propertyValueBufferSize, native int PropertyValueBuffer, int32& bufLen)
0x4f5a2  brtrue.s loc_4F5B7
0x4f5a4  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x4f5a9  stloc.2
0x4f5aa  ldstr    aFailedToGetCha// "Failed to get ChannelConfigOwningPublis"...
0x4f5af  ldloc.2
0x4f5b0  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x4f5b5  br.s     loc_4F5CF
0x4f5b7  ldloc.3
0x4f5b8  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x4f5bd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4f5c2  call     object [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStructure(native int, class [mscorlib]System.Type)
0x4f5c7  unbox.any Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x4f5cc  stloc.0
0x4f5cd  ldc.i4.0
0x4f5ce  stloc.2
0x4f5cf  ldloc.2
0x4f5d0  brtrue.s loc_4F5DB
0x4f5d2  ldloc.0
0x4f5d3  ldfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::type
0x4f5d8  ldc.i4.2
0x4f5d9  beq.s    loc_4F5E4
0x4f5db  ldloc.0
0x4f5dc  ldfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::type
0x4f5e1  ldc.i4.1
0x4f5e2  bne.un.s loc_4F5F1
0x4f5e4  ldloc.0
0x4f5e5  call     object Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::VariantToObject(valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventVariant var)
0x4f5ea  castclass [mscorlib]System.String
0x4f5ef  stloc.s  4
0x4f5f1  ldloc.3
0x4f5f2  call     void [mscorlib]System.Runtime.InteropServices.Marshal::FreeHGlobal(native int)
0x4f5f7  ldloc.s  4
0x4f5f9  ret
```
