# Microsoft.BIServer.HostingEnvironment.StaticConfig::TryGet

- ea: `0x7a0`
- end: `0x7bf`
- name: `Microsoft.BIServer.HostingEnvironment.StaticConfig::TryGet`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x800`

## callees

- `0x340`
- `0x7a0`

## pseudocode

```c

```

## disassembly

```asm
0x7a0  ldarg.0
0x7a1  ldfld    class Microsoft.BIServer.HostingEnvironment.Args Microsoft.BIServer.HostingEnvironment.StaticConfig::_args
0x7a6  ldarg.1
0x7a7  ldarg.2
0x7a8  callvirt instance bool Microsoft.BIServer.HostingEnvironment.Args::TryGetSwitch(string key, [out] string& value)
0x7ad  brtrue.s loc_7BD
0x7af  ldarg.2
0x7b0  ldarg.1
0x7b1  call     string [mscorlib]System.Environment::GetEnvironmentVariable(string)
0x7b6  stind.ref
0x7b7  ldarg.2
0x7b8  ldind.ref
0x7b9  brtrue.s loc_7BD
0x7bb  ldc.i4.0
0x7bc  ret
0x7bd  ldc.i4.1
0x7be  ret
```
