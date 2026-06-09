# Microsoft.BIServer.HostingEnvironment.StaticConfig::GetIntOrDefault

- ea: `0x870`
- end: `0x893`
- name: `Microsoft.BIServer.HostingEnvironment.StaticConfig::GetIntOrDefault`
- size: `35`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0xf10`
- `0xf80`
- `0x2c90`
- `0x34b0`

## callees

- `0x340`
- `0x870`

## pseudocode

```c

```

## disassembly

```asm
0x870  ldarg.0
0x871  ldfld    class Microsoft.BIServer.HostingEnvironment.Args Microsoft.BIServer.HostingEnvironment.StaticConfig::_args
0x876  ldarg.1
0x877  ldloca.s 0
0x879  callvirt instance bool Microsoft.BIServer.HostingEnvironment.Args::TryGetSwitch(string key, [out] string& value)
0x87e  brtrue.s loc_88C
0x880  ldarg.1
0x881  call     string [mscorlib]System.Environment::GetEnvironmentVariable(string)
0x886  stloc.0
0x887  ldloc.0
0x888  brtrue.s loc_88C
0x88a  ldarg.2
0x88b  ret
0x88c  ldloc.0
0x88d  call     int32 [mscorlib]System.Int32::Parse(string)
0x892  ret
```
