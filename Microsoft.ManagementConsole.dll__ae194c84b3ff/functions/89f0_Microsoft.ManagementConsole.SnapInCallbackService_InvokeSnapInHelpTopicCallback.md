# Microsoft.ManagementConsole.SnapInCallbackService::InvokeSnapInHelpTopicCallback

- ea: `0x89f0`
- end: `0x8a11`
- name: `Microsoft.ManagementConsole.SnapInCallbackService::InvokeSnapInHelpTopicCallback`
- size: `33`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x4a10`
- `0x9d90`
- `0xe670`

## callees

- `0x89f0`
- `0x8a20`
- `0x8a60`

## pseudocode

```c

```

## disassembly

```asm
0x89f0  call     class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.ManagementConsole.SnapInBase, class SnapInHelpTopicCallback> Microsoft.ManagementConsole.SnapInCallbackService::get_Callbacks()
0x89f5  ldarg.0
0x89f6  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.ManagementConsole.SnapInBase, class SnapInHelpTopicCallback>::ContainsKey(var<u1>)
0x89fb  brfalse.s loc_8A10
0x89fd  call     class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.ManagementConsole.SnapInBase, class SnapInHelpTopicCallback> Microsoft.ManagementConsole.SnapInCallbackService::get_Callbacks()
0x8a02  ldarg.0
0x8a03  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.ManagementConsole.SnapInBase, class SnapInHelpTopicCallback>::get_Item(void)
0x8a08  stloc.0
0x8a09  ldloc.0
0x8a0a  ldarg.1
0x8a0b  callvirt instance void SnapInHelpTopicCallback::Invoke(object target)
0x8a10  ret
```
