# Microsoft.BIServer.Configuration.Application::Equals

- ea: `0x4830`
- end: `0x4848`
- name: `Microsoft.BIServer.Configuration.Application::Equals`
- size: `24`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x37d0`

## callees

- `0x4730`
- `0x4830`

## pseudocode

```c

```

## disassembly

```asm
0x4830  ldarg.1
0x4831  brfalse.s loc_4846
0x4833  ldarg.0
0x4834  call     instance string Microsoft.BIServer.Configuration.Application::get_Name()
0x4839  ldarg.1
0x483a  callvirt instance string Microsoft.BIServer.Configuration.Application::get_Name()
0x483f  ldc.i4.5
0x4840  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x4845  ret
0x4846  ldc.i4.0
0x4847  ret
```
