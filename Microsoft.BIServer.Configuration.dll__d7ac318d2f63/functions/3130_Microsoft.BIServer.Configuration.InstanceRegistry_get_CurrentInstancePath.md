# Microsoft.BIServer.Configuration.InstanceRegistry::get_CurrentInstancePath

- ea: `0x3130`
- end: `0x3140`
- name: `Microsoft.BIServer.Configuration.InstanceRegistry::get_CurrentInstancePath`
- size: `16`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x30b0`
- `0x3110`

## callees

- `0xe40`
- `0xf10`

## pseudocode

```c

```

## disassembly

```asm
0x3130  call     class Microsoft.BIServer.Configuration.ConfigReader Microsoft.BIServer.Configuration.ConfigReader::get_Current()
0x3135  callvirt instance string Microsoft.BIServer.Configuration.ConfigReader::get_InstanceId()
0x313a  newobj   instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath::.ctor(string)
0x313f  ret
```
