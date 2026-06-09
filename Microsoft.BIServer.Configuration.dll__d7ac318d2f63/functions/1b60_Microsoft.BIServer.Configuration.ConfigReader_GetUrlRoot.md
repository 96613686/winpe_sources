# Microsoft.BIServer.Configuration.ConfigReader::GetUrlRoot

- ea: `0x1b60`
- end: `0x1b71`
- name: `Microsoft.BIServer.Configuration.ConfigReader::GetUrlRoot`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1c00`

## callees

- `0x15e0`

## string_xrefs

- `0x1b61`: `/Service/UrlRoot`

## pseudocode

```c

```

## disassembly

```asm
0x1b60  ldarg.0
0x1b61  ldstr    aServiceUrlroot// "/Service/UrlRoot"
0x1b66  ldsfld   string [mscorlib]System.String::Empty
0x1b6b  call     instance string Microsoft.BIServer.Configuration.ConfigReader::ReadStringAtPath(string path, string defaultValue)
0x1b70  ret
```
