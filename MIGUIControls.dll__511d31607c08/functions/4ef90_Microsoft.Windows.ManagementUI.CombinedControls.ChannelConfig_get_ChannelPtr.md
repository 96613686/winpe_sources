# Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfig::get_ChannelPtr

- ea: `0x4ef90`
- end: `0x4f02e`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfig::get_ChannelPtr`
- size: `158`
- prototype: ``
- caller_count: `24`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x20cc0`
- `0x21120`
- `0x21270`
- `0x29c50`
- `0x4ecd0`
- `0x4eda0`
- `0x4edf0`
- `0x4eec0`
- `0x4f040`
- `0x4f080`
- `0x4f0c0`
- `0x4f150`
- `0x4f1a0`
- `0x4f250`
- `0x4f2a0`
- `0x4f330`
- `0x4f380`
- `0x4f410`
- `0x4f460`
- `0x4f4f0`
- `0x4f530`
- `0x4f600`
- `0x4fa90`
- `0x4fcb0`

## callees

- `0x12840`
- `0x12860`
- `0x12880`
- `0x13510`
- `0x4d270`
- `0x4e960`
- `0x4ea50`
- `0x4ea60`
- `0x4ef90`
- `0x4f480`

## string_xrefs

- `0x4f008`: `Unable to open channel config for the channel `

## pseudocode

```c

```

## disassembly

```asm
0x4ef90  ldarg.0
0x4ef91  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.ConfigInstance::get_NeedsRefresh()
0x4ef96  brfalse.s loc_4EFB7
0x4ef98  ldarg.0
0x4ef99  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfig::channel
0x4ef9e  callvirt instance bool [mscorlib]System.Runtime.InteropServices.SafeHandle::get_IsInvalid()
0x4efa3  brtrue.s loc_4EFB0
0x4efa5  ldarg.0
0x4efa6  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfig::channel
0x4efab  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle::Reset()
0x4efb0  ldarg.0
0x4efb1  ldc.i4.0
0x4efb2  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.ConfigInstance::set_NeedsRefresh(bool value)
0x4efb7  ldarg.0
0x4efb8  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfig::channel
0x4efbd  callvirt instance native int Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle::get_Handle()
0x4efc2  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x4efc7  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x4efcc  brtrue.s loc_4EFDB
0x4efce  ldarg.0
0x4efcf  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfig::channel
0x4efd4  callvirt instance bool [mscorlib]System.Runtime.InteropServices.SafeHandle::get_IsInvalid()
0x4efd9  brfalse.s loc_4F022
0x4efdb  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::PrepareConstrainedRegions()
0x4efe0  leave.s  loc_4F022
0x4efe2  ldarg.0
0x4efe3  call     instance native int Microsoft.Windows.ManagementUI.CombinedControls.ConfigInstance::get_Session()
0x4efe8  ldarg.0
0x4efe9  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfig::get_ChannelPath()
0x4efee  ldc.i4.0
0x4efef  call     native int Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::OpenChannelConfig(native int Session, [hasfieldmarshal] string channelPath, int32 flags)
0x4eff4  stloc.0
0x4eff5  ldloc.0
0x4eff6  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x4effb  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x4f000  brfalse.s loc_4F015
0x4f002  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x4f007  stloc.1
0x4f008  ldstr    aUnableToOpenCh// "Unable to open channel config for the c"...
0x4f00d  ldloc.1
0x4f00e  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x4f013  br.s     loc_4F021
0x4f015  ldarg.0
0x4f016  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfig::channel
0x4f01b  ldloc.0
0x4f01c  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle::InitHandle(native int crimsonHandle)
0x4f021  endfinally
0x4f022  ldarg.0
0x4f023  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfig::channel
0x4f028  callvirt instance native int Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle::get_Handle()
0x4f02d  ret
```
