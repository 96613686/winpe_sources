# Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfig::IsClassicChannel

- ea: `0x4f920`
- end: `0x4f983`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfig::IsClassicChannel`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x500e0`

## callees

- `0x13510`
- `0x394a0`
- `0x4d110`
- `0x4d270`
- `0x4f920`
- `0x4f9f0`

## string_xrefs

- `0x4f93e`: `Unable to open channel config for the channel `
- `0x4f970`: `Unable to close channel config for the channel `

## pseudocode

```c

```

## disassembly

```asm
0x4f920  ldc.i4.0
0x4f921  stloc.0
0x4f922  ldarg.1
0x4f923  ldarg.0
0x4f924  ldc.i4.0
0x4f925  call     native int Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::OpenChannelConfig(native int Session, [hasfieldmarshal] string channelPath, int32 flags)
0x4f92a  stloc.1
0x4f92b  ldloc.1
0x4f92c  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x4f931  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x4f936  brfalse.s loc_4F95B
0x4f938  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x4f93d  stloc.2
0x4f93e  ldstr    aUnableToOpenCh// "Unable to open channel config for the c"...
0x4f943  ldarg.0
0x4f944  call     string [mscorlib]System.String::Concat(string, string)
0x4f949  ldloc.2
0x4f94a  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x4f94f  ldarg.0
0x4f950  call     bool Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::IsSecurityChannel(string channelPath)
0x4f955  brfalse.s loc_4F981
0x4f957  ldc.i4.0
0x4f958  stloc.0
0x4f959  br.s     loc_4F981
0x4f95b  ldloc.1
0x4f95c  call     bool Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfig::IsClassicChannel(native int channelPtr)
0x4f961  stloc.0
0x4f962  ldloc.1
0x4f963  call     bool Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::CloseHandle(native int eventHandle)
0x4f968  brtrue.s loc_4F981
0x4f96a  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x4f96f  stloc.3
0x4f970  ldstr    aUnableToCloseC// "Unable to close channel config for the "...
0x4f975  ldarg.0
0x4f976  call     string [mscorlib]System.String::Concat(string, string)
0x4f97b  ldloc.3
0x4f97c  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x4f981  ldloc.0
0x4f982  ret
```
