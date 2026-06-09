# Microsoft.BIServer.HostingEnvironment.StaticConfig::GetOrException

- ea: `0x7e0`
- end: `0x7fc`
- name: `Microsoft.BIServer.HostingEnvironment.StaticConfig::GetOrException`
- size: `28`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x840`
- `0x4e30`

## callees

- `0x7c0`
- `0x7e0`

## string_xrefs

- `0x7ea`: `Missing Configuration [{0}]`

## pseudocode

```c

```

## disassembly

```asm
0x7e0  ldarg.0
0x7e1  ldarg.1
0x7e2  call     instance string Microsoft.BIServer.HostingEnvironment.StaticConfig::Get(string key)
0x7e7  dup
0x7e8  brtrue.s loc_7FB
0x7ea  ldstr    aMissingConfigu// "Missing Configuration [{0}]"
0x7ef  ldarg.1
0x7f0  call     string [mscorlib]System.String::Format(string, object)
0x7f5  newobj   instance void [mscorlib]System.Collections.Generic.KeyNotFoundException::.ctor(string)
0x7fa  throw
0x7fb  ret
```
