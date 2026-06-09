# Microsoft.ManagementConsole.SnapInCallbackService::get_Callbacks

- ea: `0x8a20`
- end: `0x8a37`
- name: `Microsoft.ManagementConsole.SnapInCallbackService::get_Callbacks`
- size: `23`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x89d0`
- `0x89f0`

## callees

- `0x8a20`

## pseudocode

```c

```

## disassembly

```asm
0x8a20  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.ManagementConsole.SnapInBase, class SnapInHelpTopicCallback> Microsoft.ManagementConsole.SnapInCallbackService::_callbacks
0x8a25  brtrue.s loc_8A31
0x8a27  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.ManagementConsole.SnapInBase, class SnapInHelpTopicCallback>::.ctor()
0x8a2c  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.ManagementConsole.SnapInBase, class SnapInHelpTopicCallback> Microsoft.ManagementConsole.SnapInCallbackService::_callbacks
0x8a31  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.ManagementConsole.SnapInBase, class SnapInHelpTopicCallback> Microsoft.ManagementConsole.SnapInCallbackService::_callbacks
0x8a36  ret
```
