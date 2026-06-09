# Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfig::GetChannelType

- ea: `0x4f770`
- end: `0x4f7d5`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfig::GetChannelType`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x39020`

## callees

- `0x13510`
- `0x394a0`
- `0x4d110`
- `0x4d270`
- `0x4f770`
- `0x4f7e0`

## string_xrefs

- `0x4f790`: `Unable to open channel config for the channel `
- `0x4f7c2`: `Unable to close channel config for the channel `

## pseudocode

```c

```

## disassembly

```asm
0x4f770  ldc.i4.0
0x4f771  stloc.0
0x4f772  ldarg.1
0x4f773  ldarg.0
0x4f774  ldc.i4.0
0x4f775  call     native int Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::OpenChannelConfig(native int Session, [hasfieldmarshal] string channelPath, int32 flags)
0x4f77a  stloc.1
0x4f77b  ldloc.1
0x4f77c  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x4f781  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x4f786  brfalse.s loc_4F7AD
0x4f788  ldc.i4.4
0x4f789  stloc.0
0x4f78a  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x4f78f  stloc.2
0x4f790  ldstr    aUnableToOpenCh// "Unable to open channel config for the c"...
0x4f795  ldarg.0
0x4f796  call     string [mscorlib]System.String::Concat(string, string)
0x4f79b  ldloc.2
0x4f79c  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x4f7a1  ldarg.0
0x4f7a2  call     bool Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::IsSecurityChannel(string channelPath)
0x4f7a7  brfalse.s loc_4F7D3
0x4f7a9  ldc.i4.0
0x4f7aa  stloc.0
0x4f7ab  br.s     loc_4F7D3
0x4f7ad  ldloc.1
0x4f7ae  call     valuetype Microsoft.Windows.ManagementUI.CombinedControls.CrimsonChannelType Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfig::GetChannelType(native int channelPtr)
0x4f7b3  stloc.0
0x4f7b4  ldloc.1
0x4f7b5  call     bool Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::CloseHandle(native int eventHandle)
0x4f7ba  brtrue.s loc_4F7D3
0x4f7bc  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x4f7c1  stloc.3
0x4f7c2  ldstr    aUnableToCloseC// "Unable to close channel config for the "...
0x4f7c7  ldarg.0
0x4f7c8  call     string [mscorlib]System.String::Concat(string, string)
0x4f7cd  ldloc.3
0x4f7ce  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x4f7d3  ldloc.0
0x4f7d4  ret
```
