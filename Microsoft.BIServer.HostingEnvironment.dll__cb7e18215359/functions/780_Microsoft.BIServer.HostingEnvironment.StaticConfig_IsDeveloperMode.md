# Microsoft.BIServer.HostingEnvironment.StaticConfig::IsDeveloperMode

- ea: `0x780`
- end: `0x791`
- name: `Microsoft.BIServer.HostingEnvironment.StaticConfig::IsDeveloperMode`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3b0`

## pseudocode

```c

```

## disassembly

```asm
0x780  ldarg.0
0x781  ldfld    class Microsoft.BIServer.HostingEnvironment.Args Microsoft.BIServer.HostingEnvironment.StaticConfig::_args
0x786  ldstr    aDev// "dev"
0x78b  callvirt instance bool Microsoft.BIServer.HostingEnvironment.Args::ContainsSwitch(string key)
0x790  ret
```
