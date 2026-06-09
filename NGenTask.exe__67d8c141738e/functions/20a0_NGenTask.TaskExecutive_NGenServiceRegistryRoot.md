# NGenTask.TaskExecutive::NGenServiceRegistryRoot

- ea: `0x20a0`
- end: `0x20c4`
- name: `NGenTask.TaskExecutive::NGenServiceRegistryRoot`
- size: `36`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1d30`
- `0x1d80`
- `0x2150`
- `0x2170`
- `0x2190`
- `0x21b0`
- `0x21e0`
- `0x2220`
- `0x2240`
- `0x2290`

## callees

- `0x2050`
- `0x20a0`

## string_xrefs

- `0x20b3`: `\NGenService\`
- `0x20be`: `Software\Microsoft\.NETFramework\v2.0.50727\NGenService\`

## pseudocode

```c

```

## disassembly

```asm
0x20a0  ldarg.0
0x20a1  call     instance bool NGenTask.TaskExecutive::IsUsingPrivateStore()
0x20a6  brfalse.s loc_20BE
0x20a8  ldstr    aSoftwareMicros_1// "Software\\Microsoft\\.NETFramework\\"
0x20ad  ldarg.0
0x20ae  ldfld    string NGenTask.TaskExecutive::m_version
0x20b3  ldstr    aNgenservice// "\\NGenService\\"
0x20b8  call     string [mscorlib]System.String::Concat(string, string, string)
0x20bd  ret
0x20be  ldstr    aSoftwareMicros_2// "Software\\Microsoft\\.NETFramework\\v2."...
0x20c3  ret
```
