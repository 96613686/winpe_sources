# Microsoft.BIServer.HostingEnvironment.StaticConfig::GetOrDefault

- ea: `0x800`
- end: `0x818`
- name: `Microsoft.BIServer.HostingEnvironment.StaticConfig::GetOrDefault`
- size: `24`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4fa0`

## callees

- `0x7a0`
- `0x800`

## pseudocode

```c

```

## disassembly

```asm
0x800  ldarg.2
0x801  stloc.0
0x802  ldarg.0
0x803  ldarg.1
0x804  ldloca.s 1
0x806  call     instance bool Microsoft.BIServer.HostingEnvironment.StaticConfig::TryGet(string key, [out] string& value)
0x80b  brfalse.s loc_816
0x80d  ldloc.1
0x80e  ldloca.s 0
0x810  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x815  pop
0x816  ldloc.0
0x817  ret
```
