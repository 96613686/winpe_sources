# Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::GetForwardedEventsDestinationChannelThreadProc

- ea: `0x47110`
- end: `0x4713a`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::GetForwardedEventsDestinationChannelThreadProc`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1cd50`
- `0x1ce20`
- `0x35010`
- `0x47080`
- `0x47110`

## string_xrefs

- `0x47111`: `GetForwardedEventsDestinationChannelThreadProc`
- `0x4712f`: `GetForwardedEventsDestinationChannelThreadProc`

## pseudocode

```c

```

## disassembly

```asm
0x47110  ldarg.0
0x47111  ldstr    aGetforwardedev// "GetForwardedEventsDestinationChannelThr"...
0x47116  call     void Microsoft.Windows.ManagementUI.CombinedControls.TimeTrace::StartMethod(object thisObject, string methodName)
0x4711b  ldarg.0
0x4711c  ldfld    string[] Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::channelsForForwardedEventsDestination
0x47121  brtrue.s loc_4712E
0x47123  call     void Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::EnableSecurityPrilige()
0x47128  ldarg.0
0x47129  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::GetAllChannelsList()
0x4712e  ldarg.0
0x4712f  ldstr    aGetforwardedev// "GetForwardedEventsDestinationChannelThr"...
0x47134  call     void Microsoft.Windows.ManagementUI.CombinedControls.TimeTrace::EndMethod(object thisObject, string methodName)
0x47139  ret
```
