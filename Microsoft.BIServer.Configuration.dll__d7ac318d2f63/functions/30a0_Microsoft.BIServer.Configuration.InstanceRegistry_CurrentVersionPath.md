# Microsoft.BIServer.Configuration.InstanceRegistry::CurrentVersionPath

- ea: `0x30a0`
- end: `0x30ac`
- name: `Microsoft.BIServer.Configuration.InstanceRegistry::CurrentVersionPath`
- size: `12`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x3040`
- `0x3070`

## pseudocode

```c

```

## disassembly

```asm
0x30a0  ldarg.1
0x30a1  ldstr    aMssqlserverCur// "MSSQLServer\\CurrentVersion"
0x30a6  call     class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath::op_Addition(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath, string)
0x30ab  ret
```
