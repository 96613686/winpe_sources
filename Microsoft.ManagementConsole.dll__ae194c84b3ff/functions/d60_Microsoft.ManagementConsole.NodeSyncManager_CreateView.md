# Microsoft.ManagementConsole.NodeSyncManager::CreateView

- ea: `0xd60`
- end: `0xdb9`
- name: `Microsoft.ManagementConsole.NodeSyncManager::CreateView`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x4950`

## callees

- `0x2c0`
- `0xd60`
- `0xdc0`
- `0x1620`
- `0x8440`
- `0x8be0`

## string_xrefs

- `0xd8b`: `Node id:{0} not found. Cannot create view.`

## pseudocode

```c

```

## disassembly

```asm
0xd60  ldarg.0
0xd61  ldfld    bool Microsoft.ManagementConsole.NodeSyncManager::_initialized
0xd66  brtrue.s loc_D78
0xd68  call     string Microsoft.ManagementConsole.Internal.Strings::get_NodeSyncManagerNotInitialized()
0xd6d  call     string Microsoft.ManagementConsole.Internal.Utility::LoadResourceString(string resourceName)
0xd72  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0xd77  throw
0xd78  ldarg.0
0xd79  ldarg.1
0xd7a  call     instance class Microsoft.ManagementConsole.ScopeNode Microsoft.ManagementConsole.NodeSyncManager::GetNode(int32 id)
0xd7f  stloc.0
0xd80  ldloc.0
0xd81  brtrue.s loc_DA8
0xd83  call     class [System]System.Diagnostics.TraceSource [MMCFxCommon]Microsoft.ManagementConsole.TraceSources::get_ExecutiveSource()
0xd88  ldc.i4.8
0xd89  ldc.i4.s 0xC
0xd8b  ldstr    aNodeId0NotFoun// "Node id:{0} not found. Cannot create vi"...
0xd90  ldc.i4.1
0xd91  newarr   [mscorlib]System.Object
0xd96  stloc.1
0xd97  ldloc.1
0xd98  ldc.i4.0
0xd99  ldarg.1
0xd9a  box      [mscorlib]System.Int32
0xd9f  stelem.ref
0xda0  ldloc.1
0xda1  callvirt instance void [System]System.Diagnostics.TraceSource::TraceEvent(valuetype [System]System.Diagnostics.TraceEventType, int32, string, object[])
0xda6  ldnull
0xda7  ret
0xda8  ldloc.0
0xda9  callvirt instance class Microsoft.ManagementConsole.ViewDescriptionCollection Microsoft.ManagementConsole.ScopeNode::get_ViewDescriptions()
0xdae  ldarg.3
0xdaf  ldloc.0
0xdb0  ldarg.2
0xdb1  ldarg.s  4
0xdb3  callvirt instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.IMessageClient Microsoft.ManagementConsole.ViewDescriptionCollection::CreateView(int32 id, class Microsoft.ManagementConsole.ScopeNode node, int32 componentId, int32 viewInstanceId)
0xdb8  ret
```
