# Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo::GetRegistryStringValue

- ea: `0x53d0`
- end: `0x53dd`
- name: `Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo::GetRegistryStringValue`
- size: `13`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4b30`
- `0x4cc0`

## pseudocode

```c

```

## disassembly

```asm
0x53d0  ldarg.0
0x53d1  ldarg.1
0x53d2  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0x53d7  isinst   [mscorlib]System.String
0x53dc  ret
```
