# Microsoft.ManagementConsole.View::ExpandScopeNode

- ea: `0xb190`
- end: `0xb21d`
- name: `Microsoft.ManagementConsole.View::ExpandScopeNode`
- size: `141`
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
- `0xb190`
- `0xb2c0`
- `0xb2d0`
- `0xb300`
- `0xb320`

## string_xrefs

- `0xb191`: `ExpandScopeNode`

## pseudocode

```c

```

## disassembly

```asm
0xb190  ldarg.0
0xb191  ldstr    aExpandscopenod// "ExpandScopeNode"
0xb196  call     instance void Microsoft.ManagementConsole.View::ThrowIfShutdown(string viewOperation)
0xb19b  ldarg.1
0xb19c  brtrue.s loc_B1B4
0xb19e  ldstr    aTargetnode// "targetNode"
0xb1a3  call     string Microsoft.ManagementConsole.Internal.Strings::get_ArgumentExceptionNullValue()
0xb1a8  ldc.i4.0
0xb1a9  newarr   [mscorlib]System.Object
0xb1ae  call     class [mscorlib]System.ArgumentException Microsoft.ManagementConsole.Internal.Utility::CreateArgumentException(string name, string resourceName, object[] parms)
0xb1b3  throw
0xb1b4  ldarg.0
0xb1b5  call     instance bool Microsoft.ManagementConsole.View::get_Initialized()
0xb1ba  brfalse.s loc_B1C4
0xb1bc  ldarg.0
0xb1bd  call     instance bool Microsoft.ManagementConsole.View::get_Visible()
0xb1c2  brtrue.s loc_B1D7
0xb1c4  call     class [System]System.Diagnostics.TraceSource [MMCFxCommon]Microsoft.ManagementConsole.TraceSources::get_ExecutiveSource()
0xb1c9  ldc.i4.4
0xb1ca  ldc.i4.s 0xC
0xb1cc  ldstr    aIgnoringExpand// "Ignoring expand scope node request sinc"...
0xb1d1  callvirt instance void [System]System.Diagnostics.TraceSource::TraceEvent(valuetype [System]System.Diagnostics.TraceEventType, int32, string)
0xb1d6  ret
0xb1d7  ldarg.0
0xb1d8  call     instance class Microsoft.ManagementConsole.NamespaceSnapInBase Microsoft.ManagementConsole.View::get_SnapIn()
0xb1dd  callvirt instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ISnapInPlatform Microsoft.ManagementConsole.SnapInBase::get_SnapInPlatform()
0xb1e2  stloc.0
0xb1e3  ldloc.0
0xb1e4  brtrue.s loc_B1F6
0xb1e6  call     string Microsoft.ManagementConsole.Internal.Strings::get_ExceptionCommonSnapInPlatformIsNull()
0xb1eb  call     string Microsoft.ManagementConsole.Internal.Utility::LoadResourceString(string resourceName)
0xb1f0  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xb1f5  throw
0xb1f6  newobj   instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.ExpandConsoleScopeNodeCommand::.ctor()
0xb1fb  stloc.1
0xb1fc  ldloc.1
0xb1fd  ldarg.0
0xb1fe  call     instance int32 Microsoft.ManagementConsole.View::get_ViewInstanceId()
0xb203  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.ViewCommand::set_ViewInstanceId(int32)
0xb208  ldloc.1
0xb209  ldarg.1
0xb20a  callvirt instance int32 Microsoft.ManagementConsole.Node::get_Id()
0xb20f  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.ExpandConsoleScopeNodeCommand::set_ScopeNodeId(int32)
0xb214  ldloc.0
0xb215  ldloc.1
0xb216  callvirt instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.CommandResult [MMCFxCommon]Microsoft.ManagementConsole.Internal.ISnapInPlatform::ProcessCommand(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.Command)
0xb21b  pop
0xb21c  ret
```
