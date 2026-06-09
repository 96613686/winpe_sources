# Microsoft.ManagementConsole.Internal.NamespaceExtensionInitNotification::.ctor

- ea: `0x4320`
- end: `0x4332`
- name: `Microsoft.ManagementConsole.Internal.NamespaceExtensionInitNotification::.ctor`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x390`

## pseudocode

```c

```

## disassembly

```asm
0x4320  ldarg.0
0x4321  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4326  stfld    valuetype [mscorlib]System.Guid Microsoft.ManagementConsole.Internal.NamespaceExtensionInitNotification::_primaryNodeType
0x432b  ldarg.0
0x432c  call     instance void Microsoft.ManagementConsole.Internal.Notification::.ctor()
0x4331  ret
```
