# Microsoft.BIServer.HostingEnvironment.StaticConfig::GetOrDefault_0

- ea: `0x820`
- end: `0x83e`
- name: `Microsoft.BIServer.HostingEnvironment.StaticConfig::GetOrDefault_0`
- size: `30`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0xf10`
- `0xf80`
- `0x4dc0`
- `0x4e30`

## callees

- `0x340`
- `0x820`

## pseudocode

```c

```

## disassembly

```asm
0x820  ldarg.0
0x821  ldfld    class Microsoft.BIServer.HostingEnvironment.Args Microsoft.BIServer.HostingEnvironment.StaticConfig::_args
0x826  ldarg.1
0x827  ldloca.s 0
0x829  callvirt instance bool Microsoft.BIServer.HostingEnvironment.Args::TryGetSwitch(string key, [out] string& value)
0x82e  brtrue.s loc_83C
0x830  ldarg.1
0x831  call     string [mscorlib]System.Environment::GetEnvironmentVariable(string)
0x836  stloc.0
0x837  ldloc.0
0x838  brtrue.s loc_83C
0x83a  ldarg.2
0x83b  stloc.0
0x83c  ldloc.0
0x83d  ret
```
