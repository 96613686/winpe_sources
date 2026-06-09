# Microsoft.BIServer.HostingEnvironment.StaticConfig::Get

- ea: `0x7c0`
- end: `0x7d9`
- name: `Microsoft.BIServer.HostingEnvironment.StaticConfig::Get`
- size: `25`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x7e0`
- `0xf10`
- `0xf80`

## callees

- `0x340`
- `0x7c0`

## pseudocode

```c

```

## disassembly

```asm
0x7c0  ldarg.0
0x7c1  ldfld    class Microsoft.BIServer.HostingEnvironment.Args Microsoft.BIServer.HostingEnvironment.StaticConfig::_args
0x7c6  ldarg.1
0x7c7  ldloca.s 0
0x7c9  callvirt instance bool Microsoft.BIServer.HostingEnvironment.Args::TryGetSwitch(string key, [out] string& value)
0x7ce  brtrue.s loc_7D7
0x7d0  ldarg.1
0x7d1  call     string [mscorlib]System.Environment::GetEnvironmentVariable(string)
0x7d6  stloc.0
0x7d7  ldloc.0
0x7d8  ret
```
