# Microsoft.ManagementConsole.Internal.DataFormatConfiguration::Equals

- ea: `0xd30`
- end: `0xd4e`
- name: `Microsoft.ManagementConsole.Internal.DataFormatConfiguration::Equals`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0xd00`
- `0xd30`

## pseudocode

```c

```

## disassembly

```asm
0xd30  ldc.i4.0
0xd31  stloc.0
0xd32  ldarg.1
0xd33  isinst   Microsoft.ManagementConsole.Internal.DataFormatConfiguration
0xd38  brfalse.s loc_D4C
0xd3a  ldarg.1
0xd3b  unbox.any Microsoft.ManagementConsole.Internal.DataFormatConfiguration
0xd40  ldarg.0
0xd41  ldobj    Microsoft.ManagementConsole.Internal.DataFormatConfiguration
0xd46  call     bool Microsoft.ManagementConsole.Internal.DataFormatConfiguration::op_Equality(valuetype Microsoft.ManagementConsole.Internal.DataFormatConfiguration a, valuetype Microsoft.ManagementConsole.Internal.DataFormatConfiguration b)
0xd4b  stloc.0
0xd4c  ldloc.0
0xd4d  ret
```
