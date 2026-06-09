# Microsoft.ManagementConsole.Internal.SnapInClient::CreateSnapIn

- ea: `0x8020`
- end: `0x8049`
- name: `Microsoft.ManagementConsole.Internal.SnapInClient::CreateSnapIn`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x7df0`

## callees

- `0x4240`
- `0x81e0`

## pseudocode

```c

```

## disassembly

```asm
0x8020  call     void Microsoft.ManagementConsole.Internal.SynchronizationContextCache::RestoreOriginalContext()
0x8025  ldarg.0
0x8026  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x802b  ldarg.1
0x802c  ldarg.2
0x802d  callvirt instance object [mscorlib]System.AppDomain::CreateInstanceAndUnwrap(string, string)
0x8032  castclass Microsoft.ManagementConsole.SnapInBase
0x8037  stfld    class Microsoft.ManagementConsole.SnapInBase Microsoft.ManagementConsole.Internal.SnapInClient::_snapInInstance
0x803c  ldarg.0
0x803d  ldfld    class Microsoft.ManagementConsole.SnapInBase Microsoft.ManagementConsole.Internal.SnapInClient::_snapInInstance
0x8042  ldarg.0
0x8043  callvirt instance void Microsoft.ManagementConsole.SnapInBase::set_SnapInClient(class Microsoft.ManagementConsole.Internal.SnapInClient value)
0x8048  ret
```
