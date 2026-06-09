# Microsoft.BIServer.Configuration.WMI.WmiProvider::get_WmiGetOptions

- ea: `0x5de0`
- end: `0x5e06`
- name: `Microsoft.BIServer.Configuration.WMI.WmiProvider::get_WmiGetOptions`
- size: `38`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x5820`
- `0x58d0`

## callees

- `0x5de0`

## pseudocode

```c

```

## disassembly

```asm
0x5de0  ldsfld   class [System.Management]System.Management.ObjectGetOptions Microsoft.BIServer.Configuration.WMI.WmiProvider::GetOptions
0x5de5  brtrue.s loc_5E00
0x5de7  newobj   instance void [System.Management]System.Management.ObjectGetOptions::.ctor()
0x5dec  stsfld   class [System.Management]System.Management.ObjectGetOptions Microsoft.BIServer.Configuration.WMI.WmiProvider::GetOptions
0x5df1  ldsfld   class [System.Management]System.Management.ObjectGetOptions Microsoft.BIServer.Configuration.WMI.WmiProvider::GetOptions
0x5df6  ldsfld   valuetype [mscorlib]System.TimeSpan Microsoft.BIServer.Configuration.WMI.WmiProvider::WmiTimeout
0x5dfb  callvirt instance void [System.Management]System.Management.ManagementOptions::set_Timeout(valuetype [mscorlib]System.TimeSpan)
0x5e00  ldsfld   class [System.Management]System.Management.ObjectGetOptions Microsoft.BIServer.Configuration.WMI.WmiProvider::GetOptions
0x5e05  ret
```
