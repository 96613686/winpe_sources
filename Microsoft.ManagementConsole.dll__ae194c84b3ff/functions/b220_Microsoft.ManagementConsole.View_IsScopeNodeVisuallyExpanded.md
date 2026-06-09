# Microsoft.ManagementConsole.View::IsScopeNodeVisuallyExpanded

- ea: `0xb220`
- end: `0xb2be`
- name: `Microsoft.ManagementConsole.View::IsScopeNodeVisuallyExpanded`
- size: `158`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0xb0`
- `0x170`
- `0x670`
- `0x42f0`
- `0x8440`
- `0x8530`
- `0x9d70`
- `0xb220`
- `0xb2c0`
- `0xb2d0`
- `0xb300`
- `0xb320`

## string_xrefs

- `0xb221`: `IsScopeNodeVisuallyExpanded`
- `0xb25c`: `Ignoring IsScopeNodeVisuallyExpanded request since view hasn't been initialized or is hidden.`

## pseudocode

```c

```

## disassembly

```asm
0xb220  ldarg.0
0xb221  ldstr    aIsscopenodevis// "IsScopeNodeVisuallyExpanded"
0xb226  call     instance void Microsoft.ManagementConsole.View::ThrowIfShutdown(string viewOperation)
0xb22b  ldarg.1
0xb22c  brtrue.s loc_B244
0xb22e  ldstr    aNode_0// "node"
0xb233  call     string Microsoft.ManagementConsole.Internal.Strings::get_ArgumentExceptionNullValue()
0xb238  ldc.i4.0
0xb239  newarr   [mscorlib]System.Object
0xb23e  call     class [mscorlib]System.ArgumentException Microsoft.ManagementConsole.Internal.Utility::CreateArgumentException(string name, string resourceName, object[] parms)
0xb243  throw
0xb244  ldarg.0
0xb245  call     instance bool Microsoft.ManagementConsole.View::get_Initialized()
0xb24a  brfalse.s loc_B254
0xb24c  ldarg.0
0xb24d  call     instance bool Microsoft.ManagementConsole.View::get_Visible()
0xb252  brtrue.s loc_B268
0xb254  call     class [System]System.Diagnostics.TraceSource [MMCFxCommon]Microsoft.ManagementConsole.TraceSources::get_ExecutiveSource()
0xb259  ldc.i4.4
0xb25a  ldc.i4.s 0xC
0xb25c  ldstr    aIgnoringIsscop// "Ignoring IsScopeNodeVisuallyExpanded re"...
0xb261  callvirt instance void [System]System.Diagnostics.TraceSource::TraceEvent(valuetype [System]System.Diagnostics.TraceEventType, int32, string)
0xb266  br.s     loc_B2BC
0xb268  ldarg.0
0xb269  call     instance class Microsoft.ManagementConsole.NamespaceSnapInBase Microsoft.ManagementConsole.View::get_SnapIn()
0xb26e  callvirt instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ISnapInPlatform Microsoft.ManagementConsole.SnapInBase::get_SnapInPlatform()
0xb273  stloc.0
0xb274  ldloc.0
0xb275  brtrue.s loc_B287
0xb277  call     string Microsoft.ManagementConsole.Internal.Strings::get_ExceptionCommonSnapInPlatformIsNull()
0xb27c  call     string Microsoft.ManagementConsole.Internal.Utility::LoadResourceString(string resourceName)
0xb281  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xb286  throw
0xb287  newobj   instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.IsScopeNodeVisuallyExpandedCommand::.ctor()
0xb28c  stloc.1
0xb28d  ldloc.1
0xb28e  ldarg.0
0xb28f  call     instance int32 Microsoft.ManagementConsole.View::get_ViewInstanceId()
0xb294  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.ViewCommand::set_ViewInstanceId(int32)
0xb299  ldloc.1
0xb29a  ldarg.1
0xb29b  callvirt instance int32 Microsoft.ManagementConsole.Node::get_Id()
0xb2a0  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.IsScopeNodeVisuallyExpandedCommand::set_ScopeNodeId(int32)
0xb2a5  ldloc.0
0xb2a6  ldloc.1
0xb2a7  callvirt instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.CommandResult [MMCFxCommon]Microsoft.ManagementConsole.Internal.ISnapInPlatform::ProcessCommand(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.Command)
0xb2ac  isinst   [MMCFxCommon]Microsoft.ManagementConsole.Internal.IsScopeNodeVisuallyExpandedCommandResult
0xb2b1  stloc.2
0xb2b2  ldloc.2
0xb2b3  brfalse.s loc_B2BC
0xb2b5  ldloc.2
0xb2b6  callvirt instance bool [MMCFxCommon]Microsoft.ManagementConsole.Internal.IsScopeNodeVisuallyExpandedCommandResult::get_IsExpanded()
0xb2bb  ret
0xb2bc  ldc.i4.0
0xb2bd  ret
```
