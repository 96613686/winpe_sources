# Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfig::DoesUserHaveAccessToChannel

- ea: `0x4eb20`
- end: `0x4ebcf`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfig::DoesUserHaveAccessToChannel`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4eaf0`

## callees

- `0x12830`
- `0x12840`
- `0x12880`
- `0x13510`
- `0x33120`
- `0x4d1f0`
- `0x4d210`
- `0x4eb20`

## string_xrefs

- `0x4eb58`: `Unable to open the log for channel properties `
- `0x4ebb5`: `Current user does not have read permission to  `

## pseudocode

```c

```

## disassembly

```asm
0x4eb20  ldc.i4.1
0x4eb21  stloc.0
0x4eb22  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::PrepareConstrainedRegions()
0x4eb27  leave    loc_4EBCD
0x4eb2c  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle::.ctor()
0x4eb31  stloc.1
0x4eb32  ldc.i4.0
0x4eb33  stloc.2
0x4eb34  ldarg.1
0x4eb35  call     string Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::GetChannelPathWithoutFilePrefix(string channelPath)
0x4eb3a  starg.s  1
0x4eb3c  ldarg.0
0x4eb3d  ldarg.1
0x4eb3e  ldc.i4.1
0x4eb3f  call     native int Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::OpenLog(native int session, [hasfieldmarshal] string channelPath, [hasfieldmarshal] valuetype Microsoft.Windows.ManagementUI.CombinedControls.LogOpenFlags flags)
0x4eb44  stloc.3
0x4eb45  ldloc.3
0x4eb46  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x4eb4b  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x4eb50  brfalse.s loc_4EB71
0x4eb52  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x4eb57  stloc.2
0x4eb58  ldstr    aUnableToOpenTh// "Unable to open the log for channel prop"...
0x4eb5d  ldarg.1
0x4eb5e  call     string [mscorlib]System.String::Concat(string, string)
0x4eb63  ldloc.2
0x4eb64  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x4eb69  ldloc.2
0x4eb6a  ldc.i4.5
0x4eb6b  bne.un.s loc_4EBCC
0x4eb6d  ldc.i4.0
0x4eb6e  stloc.0
0x4eb6f  br.s     loc_4EBCC
0x4eb71  ldloc.1
0x4eb72  ldloc.3
0x4eb73  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle::InitHandle(native int crimsonHandle)
0x4eb78  ldloc.3
0x4eb79  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x4eb7e  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x4eb83  brfalse.s loc_4EBC6
0x4eb85  ldloca.s 4
0x4eb87  initobj  Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x4eb8d  ldc.i4.0
0x4eb8e  stloc.s  5
0x4eb90  ldloc.3
0x4eb91  ldc.i4.5
0x4eb92  ldloc.s  4
0x4eb94  box      Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x4eb99  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::SizeOf(object)
0x4eb9e  ldloca.s 4
0x4eba0  ldloca.s 5
0x4eba2  call     bool Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::GetLogInfo(native int log, [hasfieldmarshal] valuetype Microsoft.Windows.ManagementUI.CombinedControls.LogPropertyIdentifier propertyId, int32 propertyValueBufferSize, valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventVariant& propertyValueBuffer, int32& propertyValueBufferUsed)
0x4eba7  brtrue.s loc_4EBC6
0x4eba9  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x4ebae  stloc.2
0x4ebaf  ldloc.2
0x4ebb0  ldc.i4.5
0x4ebb1  bne.un.s loc_4EBB5
0x4ebb3  ldc.i4.0
0x4ebb4  stloc.0
0x4ebb5  ldstr    aCurrentUserDoe// "Current user does not have read permiss"...
0x4ebba  ldarg.1
0x4ebbb  call     string [mscorlib]System.String::Concat(string, string)
0x4ebc0  ldloc.2
0x4ebc1  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x4ebc6  ldloc.1
0x4ebc7  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle::Reset()
0x4ebcc  endfinally
0x4ebcd  ldloc.0
0x4ebce  ret
```
