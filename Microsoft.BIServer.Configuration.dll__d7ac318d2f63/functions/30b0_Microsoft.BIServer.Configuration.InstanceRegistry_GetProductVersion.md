# Microsoft.BIServer.Configuration.InstanceRegistry::GetProductVersion

- ea: `0x30b0`
- end: `0x30bc`
- name: `Microsoft.BIServer.Configuration.InstanceRegistry::GetProductVersion`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x30c0`
- `0x3130`

## pseudocode

```c

```

## disassembly

```asm
0x30b0  ldarg.0
0x30b1  call     class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath Microsoft.BIServer.Configuration.InstanceRegistry::get_CurrentInstancePath()
0x30b6  call     instance string Microsoft.BIServer.Configuration.InstanceRegistry::GetProductVersion(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath instancePath)
0x30bb  ret
```
