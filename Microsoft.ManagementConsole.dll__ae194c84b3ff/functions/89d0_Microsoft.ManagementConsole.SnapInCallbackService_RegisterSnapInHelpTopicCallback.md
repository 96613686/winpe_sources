# Microsoft.ManagementConsole.SnapInCallbackService::RegisterSnapInHelpTopicCallback

- ea: `0x89d0`
- end: `0x89ee`
- name: `Microsoft.ManagementConsole.SnapInCallbackService::RegisterSnapInHelpTopicCallback`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x89d0`
- `0x8a20`

## pseudocode

```c

```

## disassembly

```asm
0x89d0  ldarg.0
0x89d1  brfalse.s loc_89D6
0x89d3  ldarg.1
0x89d4  brtrue.s loc_89E1
0x89d6  ldstr    aCallback// "callback"
0x89db  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x89e0  throw
0x89e1  call     class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.ManagementConsole.SnapInBase, class SnapInHelpTopicCallback> Microsoft.ManagementConsole.SnapInCallbackService::get_Callbacks()
0x89e6  ldarg.0
0x89e7  ldarg.1
0x89e8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.ManagementConsole.SnapInBase, class SnapInHelpTopicCallback>::set_Item(var<u1>, !!T0)
0x89ed  ret
```
