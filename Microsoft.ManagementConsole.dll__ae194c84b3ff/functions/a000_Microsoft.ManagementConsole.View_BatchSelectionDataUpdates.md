# Microsoft.ManagementConsole.View::BatchSelectionDataUpdates

- ea: `0xa000`
- end: `0xa041`
- name: `Microsoft.ManagementConsole.View::BatchSelectionDataUpdates`
- size: `65`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0xd510`
- `0xd550`
- `0xd6b0`

## callees

- `0x42f0`
- `0x8490`
- `0xa000`
- `0xb300`
- `0xb320`

## string_xrefs

- `0xa014`: `BatchSelectionDataUpdates`

## pseudocode

```c

```

## disassembly

```asm
0xa000  ldarg.0
0xa001  call     instance class Microsoft.ManagementConsole.NamespaceSnapInBase Microsoft.ManagementConsole.View::get_SnapIn()
0xa006  callvirt instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ISnapInPlatform Microsoft.ManagementConsole.SnapInBase::get_SnapInPlatform()
0xa00b  stloc.0
0xa00c  ldloc.0
0xa00d  brtrue.s loc_A01F
0xa00f  ldstr    aSnapin// "SnapIn"
0xa014  ldstr    aBatchselection// "BatchSelectionDataUpdates"
0xa019  call     class [mscorlib]System.InvalidOperationException Microsoft.ManagementConsole.Internal.Utility::CreateClassNotInitializedException(string className, string operation)
0xa01e  throw
0xa01f  newobj   instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.BatchSelectionDataUpdatesCommand::.ctor()
0xa024  stloc.1
0xa025  ldloc.1
0xa026  ldarg.0
0xa027  call     instance int32 Microsoft.ManagementConsole.View::get_ViewInstanceId()
0xa02c  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.ViewCommand::set_ViewInstanceId(int32)
0xa031  ldloc.1
0xa032  ldarg.1
0xa033  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.BatchSelectionDataUpdatesCommand::set_Begin(bool)
0xa038  ldloc.0
0xa039  ldloc.1
0xa03a  callvirt instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.CommandResult [MMCFxCommon]Microsoft.ManagementConsole.Internal.ISnapInPlatform::ProcessCommand(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.Command)
0xa03f  pop
0xa040  ret
```
