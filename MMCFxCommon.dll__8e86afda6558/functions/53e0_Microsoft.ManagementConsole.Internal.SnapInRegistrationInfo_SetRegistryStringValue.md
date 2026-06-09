# Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo::SetRegistryStringValue

- ea: `0x53e0`
- end: `0x5409`
- name: `Microsoft.ManagementConsole.Internal.SnapInRegistrationInfo::SetRegistryStringValue`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x5060`

## callees

- `0x53e0`

## pseudocode

```c

```

## disassembly

```asm
0x53e0  ldarg.2
0x53e1  brfalse.s loc_53F0
0x53e3  ldarg.2
0x53e4  ldsfld   string [mscorlib]System.String::Empty
0x53e9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x53ee  brfalse.s loc_5400
0x53f0  ldarg.3
0x53f1  brtrue.s loc_5408
0x53f3  ldarg.0
0x53f4  ldarg.1
0x53f5  ldsfld   string [mscorlib]System.String::Empty
0x53fa  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::SetValue(string, object)
0x53ff  ret
0x5400  ldarg.0
0x5401  ldarg.1
0x5402  ldarg.2
0x5403  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::SetValue(string, object)
0x5408  ret
```
