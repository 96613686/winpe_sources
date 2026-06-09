# Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::.cctor

- ea: `0x39b30`
- end: `0x39c08`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::.cctor`
- size: `216`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x39b61`: `Security`
- `0x39bcb`: `Security`

## pseudocode

```c

```

## disassembly

```asm
0x39b30  ldstr    aForwardedevent// "ForwardedEvents"
0x39b35  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::ForwardedEventsChannel
0x39b3a  ldc.i4.0
0x39b3b  stsfld   bool Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::hasWritePermissionToAllUsers
0x39b40  ldc.i4.0
0x39b41  stsfld   bool Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::hasWritePermissionToAllUsersInitialized
0x39b46  ldc.i4.5
0x39b47  call     string [mscorlib]System.Environment::GetFolderPath(valuetype [mscorlib]System.Environment/SpecialFolder)
0x39b4c  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::currentDirectory
0x39b51  ldc.i4.5
0x39b52  newarr   [mscorlib]System.String
0x39b57  dup
0x39b58  ldc.i4.0
0x39b59  ldstr    aApplication// "Application"
0x39b5e  stelem.ref
0x39b5f  dup
0x39b60  ldc.i4.1
0x39b61  ldstr    aSecurity// "Security"
0x39b66  stelem.ref
0x39b67  dup
0x39b68  ldc.i4.2
0x39b69  ldstr    aSetup// "Setup"
0x39b6e  stelem.ref
0x39b6f  dup
0x39b70  ldc.i4.3
0x39b71  ldstr    aSystem// "System"
0x39b76  stelem.ref
0x39b77  dup
0x39b78  ldc.i4.4
0x39b79  ldstr    aForwardedevent// "ForwardedEvents"
0x39b7e  stelem.ref
0x39b7f  stsfld   string[] Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::GlobalChannels
0x39b84  ldc.i4.5
0x39b85  newarr   [mscorlib]System.String
0x39b8a  dup
0x39b8b  ldc.i4.0
0x39b8c  ldstr    aApplication// "Application"
0x39b91  stelem.ref
0x39b92  dup
0x39b93  ldc.i4.1
0x39b94  ldstr    aHardwareevents// "HardwareEvents"
0x39b99  stelem.ref
0x39b9a  dup
0x39b9b  ldc.i4.2
0x39b9c  ldstr    aSetup// "Setup"
0x39ba1  stelem.ref
0x39ba2  dup
0x39ba3  ldc.i4.3
0x39ba4  ldstr    aSystem// "System"
0x39ba9  stelem.ref
0x39baa  dup
0x39bab  ldc.i4.4
0x39bac  ldstr    aForwardedevent// "ForwardedEvents"
0x39bb1  stelem.ref
0x39bb2  stsfld   string[] Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::StandardForwardingDestinationLogs
0x39bb7  ldstr    aApplication// "Application"
0x39bbc  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::ApplicationChannel
0x39bc1  ldstr    aSystem// "System"
0x39bc6  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::SystemChannel
0x39bcb  ldstr    aSecurity// "Security"
0x39bd0  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::SecurityChannel
0x39bd5  ldc.i4   0xFF
0x39bda  stsfld   int32 Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::batchSizeForDirectChannels
0x39bdf  ldstr    aXml_0// ".xml"
0x39be4  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::ViewerConfigExtension
0x39be9  ldstr    aXml// "xml"
0x39bee  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::ViewerConfigExtension1
0x39bf3  ldc.i4   0x7D0
0x39bf8  stsfld   int32 Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::MinimumTimeOutForNotification
0x39bfd  ldc.i4   0x800
0x39c02  stsfld   int32 Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::MAX_CHANNELPATH_LENGTH
0x39c07  ret
```
