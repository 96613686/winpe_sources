# Microsoft.ManagementConsole.Internal.SnapInUIThreadTable::RegisterThreadWithExecutive

- ea: `0x6900`
- end: `0x6922`
- name: `Microsoft.ManagementConsole.Internal.SnapInUIThreadTable::RegisterThreadWithExecutive`
- size: `34`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x6810`
- `0x6880`

## pseudocode

```c

```

## disassembly

```asm
0x6900  newobj   instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.RegisterUIThreadCommand::.ctor()
0x6905  stloc.0
0x6906  ldloc.0
0x6907  ldarg.1
0x6908  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.RegisterUIThreadCommand::set_UnmanagedThreadId(unsigned int32)
0x690d  ldloc.0
0x690e  ldarg.2
0x690f  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.RegisterUIThreadCommand::set_Register(bool)
0x6914  ldarg.0
0x6915  ldfld    class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ISnapInPlatform Microsoft.ManagementConsole.Internal.SnapInUIThreadTable::_snapInPlatform
0x691a  ldloc.0
0x691b  callvirt instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.CommandResult [MMCFxCommon]Microsoft.ManagementConsole.Internal.ISnapInPlatform::ProcessCommand(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.Command)
0x6920  pop
0x6921  ret
```
