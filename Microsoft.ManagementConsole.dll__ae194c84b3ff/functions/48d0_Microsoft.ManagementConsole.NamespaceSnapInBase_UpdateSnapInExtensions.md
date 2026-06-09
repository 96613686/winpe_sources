# Microsoft.ManagementConsole.NamespaceSnapInBase::UpdateSnapInExtensions

- ea: `0x48d0`
- end: `0x48f9`
- name: `Microsoft.ManagementConsole.NamespaceSnapInBase::UpdateSnapInExtensions`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x170`
- `0x42f0`
- `0x48d0`
- `0x8440`

## pseudocode

```c

```

## disassembly

```asm
0x48d0  ldarg.0
0x48d1  call     instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ISnapInPlatform Microsoft.ManagementConsole.SnapInBase::get_SnapInPlatform()
0x48d6  stloc.0
0x48d7  ldloc.0
0x48d8  brtrue.s loc_48EA
0x48da  call     string Microsoft.ManagementConsole.Internal.Strings::get_ExceptionCommonSnapInPlatformIsNull()
0x48df  call     string Microsoft.ManagementConsole.Internal.Utility::LoadResourceString(string resourceName)
0x48e4  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x48e9  throw
0x48ea  newobj   instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.UpdateSnapInExtensionsCommand::.ctor()
0x48ef  stloc.1
0x48f0  ldloc.0
0x48f1  ldloc.1
0x48f2  callvirt instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.CommandResult [MMCFxCommon]Microsoft.ManagementConsole.Internal.ISnapInPlatform::ProcessCommand(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.Command)
0x48f7  pop
0x48f8  ret
```
