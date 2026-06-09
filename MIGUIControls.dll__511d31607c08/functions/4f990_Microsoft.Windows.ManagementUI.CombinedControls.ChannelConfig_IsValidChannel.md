# Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfig::IsValidChannel

- ea: `0x4f990`
- end: `0x4f9f0`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfig::IsValidChannel`
- size: `96`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x13510`
- `0x394a0`
- `0x4d110`
- `0x4d270`
- `0x4f990`

## string_xrefs

- `0x4f9b0`: `Unable to open channel config for the channel `
- `0x4f9dd`: `Unable to close channel config for the channel `

## pseudocode

```c

```

## disassembly

```asm
0x4f990  ldc.i4.0
0x4f991  stloc.0
0x4f992  ldarg.1
0x4f993  ldarg.0
0x4f994  ldc.i4.0
0x4f995  call     native int Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::OpenChannelConfig(native int Session, [hasfieldmarshal] string channelPath, int32 flags)
0x4f99a  stloc.1
0x4f99b  ldc.i4.0
0x4f99c  stloc.2
0x4f99d  ldloc.1
0x4f99e  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x4f9a3  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x4f9a8  brfalse.s loc_4F9CD
0x4f9aa  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x4f9af  stloc.2
0x4f9b0  ldstr    aUnableToOpenCh// "Unable to open channel config for the c"...
0x4f9b5  ldarg.0
0x4f9b6  call     string [mscorlib]System.String::Concat(string, string)
0x4f9bb  ldloc.2
0x4f9bc  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x4f9c1  ldarg.0
0x4f9c2  call     bool Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::IsSecurityChannel(string channelPath)
0x4f9c7  brfalse.s loc_4F9EE
0x4f9c9  ldc.i4.1
0x4f9ca  stloc.0
0x4f9cb  br.s     loc_4F9EE
0x4f9cd  ldc.i4.1
0x4f9ce  stloc.0
0x4f9cf  ldloc.1
0x4f9d0  call     bool Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::CloseHandle(native int eventHandle)
0x4f9d5  brtrue.s loc_4F9EE
0x4f9d7  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x4f9dc  stloc.2
0x4f9dd  ldstr    aUnableToCloseC// "Unable to close channel config for the "...
0x4f9e2  ldarg.0
0x4f9e3  call     string [mscorlib]System.String::Concat(string, string)
0x4f9e8  ldloc.2
0x4f9e9  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x4f9ee  ldloc.0
0x4f9ef  ret
```
