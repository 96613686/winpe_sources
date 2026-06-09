# Microsoft.ManagementConsole.View::SelectScopeNode_0

- ea: `0xb020`
- end: `0xb18e`
- name: `Microsoft.ManagementConsole.View::SelectScopeNode_0`
- size: `366`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0xb010`

## callees

- `0x170`
- `0x180`
- `0x670`
- `0x900`
- `0x960`
- `0x9e0`
- `0x42f0`
- `0x8440`
- `0x8470`
- `0x9d70`
- `0xb020`
- `0xb2c0`
- `0xb2d0`
- `0xb300`
- `0xb320`

## string_xrefs

- `0xb021`: `SelectScopeNode`
- `0xb03c`: `relativePath`
- `0xb136`: `relativePath`

## pseudocode

```c

```

## disassembly

```asm
0xb020  ldarg.0
0xb021  ldstr    aSelectscopenod// "SelectScopeNode"
0xb026  call     instance void Microsoft.ManagementConsole.View::ThrowIfShutdown(string viewOperation)
0xb02b  ldarg.1
0xb02c  brtrue.s loc_B039
0xb02e  ldstr    aStartnode// "startNode"
0xb033  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xb038  throw
0xb039  ldarg.2
0xb03a  brtrue.s loc_B047
0xb03c  ldstr    aRelativepath// "relativePath"
0xb041  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xb046  throw
0xb047  ldarg.0
0xb048  call     instance bool Microsoft.ManagementConsole.View::get_Initialized()
0xb04d  brfalse.s loc_B057
0xb04f  ldarg.0
0xb050  call     instance bool Microsoft.ManagementConsole.View::get_Visible()
0xb055  brtrue.s loc_B06A
0xb057  call     class [System]System.Diagnostics.TraceSource [MMCFxCommon]Microsoft.ManagementConsole.TraceSources::get_ExecutiveSource()
0xb05c  ldc.i4.4
0xb05d  ldc.i4.s 0xC
0xb05f  ldstr    aIgnoringSelect// "Ignoring select scope node request sinc"...
0xb064  callvirt instance void [System]System.Diagnostics.TraceSource::TraceEvent(valuetype [System]System.Diagnostics.TraceEventType, int32, string)
0xb069  ret
0xb06a  ldarg.0
0xb06b  call     instance class Microsoft.ManagementConsole.NamespaceSnapInBase Microsoft.ManagementConsole.View::get_SnapIn()
0xb070  callvirt instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ISnapInPlatform Microsoft.ManagementConsole.SnapInBase::get_SnapInPlatform()
0xb075  stloc.0
0xb076  ldloc.0
0xb077  brtrue.s loc_B089
0xb079  call     string Microsoft.ManagementConsole.Internal.Strings::get_ExceptionCommonSnapInPlatformIsNull()
0xb07e  call     string Microsoft.ManagementConsole.Internal.Utility::LoadResourceString(string resourceName)
0xb083  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xb088  throw
0xb089  ldarg.2
0xb08a  ldlen
0xb08b  conv.i4
0xb08c  newarr   [MMCFxCommon]Microsoft.ManagementConsole.Internal.NodeIdData
0xb091  stloc.1
0xb092  ldc.i4.0
0xb093  stloc.2
0xb094  ldarg.2
0xb095  stloc.s  6
0xb097  ldc.i4.0
0xb098  stloc.s  7
0xb09a  br       loc_B150
0xb09f  ldloc.s  6
0xb0a1  ldloc.s  7
0xb0a3  ldelem.ref
0xb0a4  stloc.3
0xb0a5  newobj   instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.NodeIdData::.ctor()
0xb0aa  stloc.s  4
0xb0ac  ldloc.3
0xb0ad  isinst   Microsoft.ManagementConsole.DisplayNameNodeId
0xb0b2  brfalse.s loc_B0D0
0xb0b4  ldloc.s  4
0xb0b6  ldloc.3
0xb0b7  castclass Microsoft.ManagementConsole.DisplayNameNodeId
0xb0bc  callvirt instance string Microsoft.ManagementConsole.DisplayNameNodeId::get_DisplayName()
0xb0c1  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.NodeIdData::set_NameId(string)
0xb0c6  ldloc.s  4
0xb0c8  ldc.i4.0
0xb0c9  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.NodeIdData::set_Type(valuetype [MMCFxCommon]Microsoft.ManagementConsole.Internal.NodeIdType)
0xb0ce  br.s     loc_B141
0xb0d0  ldloc.3
0xb0d1  isinst   Microsoft.ManagementConsole.LanguageIndependentNameNodeId
0xb0d6  brfalse.s loc_B0F4
0xb0d8  ldloc.s  4
0xb0da  ldloc.3
0xb0db  castclass Microsoft.ManagementConsole.LanguageIndependentNameNodeId
0xb0e0  callvirt instance string Microsoft.ManagementConsole.LanguageIndependentNameNodeId::get_LanguageIndependentName()
0xb0e5  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.NodeIdData::set_NameId(string)
0xb0ea  ldloc.s  4
0xb0ec  ldc.i4.1
0xb0ed  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.NodeIdData::set_Type(valuetype [MMCFxCommon]Microsoft.ManagementConsole.Internal.NodeIdType)
0xb0f2  br.s     loc_B141
0xb0f4  ldloc.3
0xb0f5  isinst   Microsoft.ManagementConsole.CustomNodeId
0xb0fa  brfalse.s loc_B118
0xb0fc  ldloc.s  4
0xb0fe  ldloc.3
0xb0ff  castclass Microsoft.ManagementConsole.CustomNodeId
0xb104  callvirt instance unsigned int8[] Microsoft.ManagementConsole.CustomNodeId::GetCustomId()
0xb109  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.NodeIdData::SetCustomId(unsigned int8[])
0xb10e  ldloc.s  4
0xb110  ldc.i4.2
0xb111  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.NodeIdData::set_Type(valuetype [MMCFxCommon]Microsoft.ManagementConsole.Internal.NodeIdType)
0xb116  br.s     loc_B141
0xb118  call     string Microsoft.ManagementConsole.Internal.Strings::get_ViewSelectScopeNodeNullOrUnrecognizedNodeId()
0xb11d  ldc.i4.1
0xb11e  newarr   [mscorlib]System.Object
0xb123  stloc.s  8
0xb125  ldloc.s  8
0xb127  ldc.i4.0
0xb128  ldloc.2
0xb129  box      [mscorlib]System.Int32
0xb12e  stelem.ref
0xb12f  ldloc.s  8
0xb131  call     string Microsoft.ManagementConsole.Internal.Utility::FormatResourceString(string resourceName, object[] parms)
0xb136  ldstr    aRelativepath// "relativePath"
0xb13b  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0xb140  throw
0xb141  ldloc.1
0xb142  ldloc.2
0xb143  dup
0xb144  ldc.i4.1
0xb145  add
0xb146  stloc.2
0xb147  ldloc.s  4
0xb149  stelem.ref
0xb14a  ldloc.s  7
0xb14c  ldc.i4.1
0xb14d  add
0xb14e  stloc.s  7
0xb150  ldloc.s  7
0xb152  ldloc.s  6
0xb154  ldlen
0xb155  conv.i4
0xb156  blt      loc_B09F
0xb15b  newobj   instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.SelectScopeNodeCommand::.ctor()
0xb160  stloc.s  5
0xb162  ldloc.s  5
0xb164  ldarg.0
0xb165  call     instance int32 Microsoft.ManagementConsole.View::get_ViewInstanceId()
0xb16a  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.ViewCommand::set_ViewInstanceId(int32)
0xb16f  ldloc.s  5
0xb171  ldarg.1
0xb172  callvirt instance int32 Microsoft.ManagementConsole.Node::get_Id()
0xb177  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.SelectScopeNodeCommand::set_ScopeNodeId(int32)
0xb17c  ldloc.s  5
0xb17e  ldloc.1
0xb17f  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.SelectScopeNodeCommand::SetRelativePath(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.NodeIdData[])
0xb184  ldloc.0
0xb185  ldloc.s  5
0xb187  callvirt instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.CommandResult [MMCFxCommon]Microsoft.ManagementConsole.Internal.ISnapInPlatform::ProcessCommand(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.Command)
0xb18c  pop
0xb18d  ret
```
