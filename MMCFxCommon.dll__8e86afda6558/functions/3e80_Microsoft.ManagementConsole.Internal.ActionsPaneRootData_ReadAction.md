# Microsoft.ManagementConsole.Internal.ActionsPaneRootData::ReadAction

- ea: `0x3e80`
- end: `0x3ea5`
- name: `Microsoft.ManagementConsole.Internal.ActionsPaneRootData::ReadAction`
- size: `37`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x3d50`

## callees

- `0x39f0`
- `0x3a10`

## pseudocode

```c

```

## disassembly

```asm
0x3e80  ldarg.1
0x3e81  ldarg.0
0x3e82  ldfld    bool[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::_executeSync
0x3e87  ldarg.2
0x3e88  ldind.i4
0x3e89  ldelem.i1
0x3e8a  callvirt instance void Microsoft.ManagementConsole.Internal.ActionData::set_ExecuteSync(bool value)
0x3e8f  ldarg.1
0x3e90  ldarg.0
0x3e91  ldfld    valuetype Microsoft.ManagementConsole.Internal.ActionStates[] Microsoft.ManagementConsole.Internal.ActionsPaneRootData::_state
0x3e96  ldarg.2
0x3e97  ldind.i4
0x3e98  ldelem.i4
0x3e99  callvirt instance void Microsoft.ManagementConsole.Internal.ActionData::set_State(valuetype Microsoft.ManagementConsole.Internal.ActionStates value)
0x3e9e  ldarg.2
0x3e9f  dup
0x3ea0  ldind.i4
0x3ea1  ldc.i4.1
0x3ea2  add
0x3ea3  stind.i4
0x3ea4  ret
```
