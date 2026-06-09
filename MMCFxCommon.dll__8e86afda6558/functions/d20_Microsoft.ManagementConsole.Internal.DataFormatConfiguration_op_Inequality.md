# Microsoft.ManagementConsole.Internal.DataFormatConfiguration::op_Inequality

- ea: `0xd20`
- end: `0xd2b`
- name: `Microsoft.ManagementConsole.Internal.DataFormatConfiguration::op_Inequality`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xd00`

## pseudocode

```c

```

## disassembly

```asm
0xd20  ldarg.0
0xd21  ldarg.1
0xd22  call     bool Microsoft.ManagementConsole.Internal.DataFormatConfiguration::op_Equality(valuetype Microsoft.ManagementConsole.Internal.DataFormatConfiguration a, valuetype Microsoft.ManagementConsole.Internal.DataFormatConfiguration b)
0xd27  ldc.i4.0
0xd28  ceq
0xd2a  ret
```
