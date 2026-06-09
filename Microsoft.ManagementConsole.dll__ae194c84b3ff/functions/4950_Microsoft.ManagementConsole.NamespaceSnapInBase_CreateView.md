# Microsoft.ManagementConsole.NamespaceSnapInBase::CreateView

- ea: `0x4950`
- end: `0x4961`
- name: `Microsoft.ManagementConsole.NamespaceSnapInBase::CreateView`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xd60`

## pseudocode

```c

```

## disassembly

```asm
0x4950  ldarg.0
0x4951  ldfld    class Microsoft.ManagementConsole.NodeSyncManager Microsoft.ManagementConsole.NamespaceSnapInBase::_nodeSyncManager
0x4956  ldarg.1
0x4957  ldarg.2
0x4958  ldarg.3
0x4959  ldarg.s  4
0x495b  callvirt instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.IMessageClient Microsoft.ManagementConsole.NodeSyncManager::CreateView(int32 nodeId, int32 componentId, int32 viewDescriptionId, int32 viewInstanceId)
0x4960  ret
```
