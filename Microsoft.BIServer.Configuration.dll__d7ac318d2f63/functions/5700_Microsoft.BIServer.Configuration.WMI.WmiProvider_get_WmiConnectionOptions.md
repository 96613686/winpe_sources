# Microsoft.BIServer.Configuration.WMI.WmiProvider::get_WmiConnectionOptions

- ea: `0x5700`
- end: `0x5731`
- name: `Microsoft.BIServer.Configuration.WMI.WmiProvider::get_WmiConnectionOptions`
- size: `49`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x57c0`
- `0x5820`
- `0x58d0`

## callees

- `0x5700`

## pseudocode

```c

```

## disassembly

```asm
0x5700  ldsfld   class [System.Management]System.Management.ConnectionOptions Microsoft.BIServer.Configuration.WMI.WmiProvider::ConnOptions
0x5705  brtrue.s loc_572B
0x5707  newobj   instance void [System.Management]System.Management.ConnectionOptions::.ctor()
0x570c  stsfld   class [System.Management]System.Management.ConnectionOptions Microsoft.BIServer.Configuration.WMI.WmiProvider::ConnOptions
0x5711  ldsfld   class [System.Management]System.Management.ConnectionOptions Microsoft.BIServer.Configuration.WMI.WmiProvider::ConnOptions
0x5716  ldc.i4.6
0x5717  callvirt instance void [System.Management]System.Management.ConnectionOptions::set_Authentication(valuetype [System.Management]System.Management.AuthenticationLevel)
0x571c  ldsfld   class [System.Management]System.Management.ConnectionOptions Microsoft.BIServer.Configuration.WMI.WmiProvider::ConnOptions
0x5721  ldsfld   valuetype [mscorlib]System.TimeSpan Microsoft.BIServer.Configuration.WMI.WmiProvider::WmiTimeout
0x5726  callvirt instance void [System.Management]System.Management.ManagementOptions::set_Timeout(valuetype [mscorlib]System.TimeSpan)
0x572b  ldsfld   class [System.Management]System.Management.ConnectionOptions Microsoft.BIServer.Configuration.WMI.WmiProvider::ConnOptions
0x5730  ret
```
