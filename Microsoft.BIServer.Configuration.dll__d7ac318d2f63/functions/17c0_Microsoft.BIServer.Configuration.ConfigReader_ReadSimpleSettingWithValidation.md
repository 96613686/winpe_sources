# Microsoft.BIServer.Configuration.ConfigReader::ReadSimpleSettingWithValidation

- ea: `0x17c0`
- end: `0x17de`
- name: `Microsoft.BIServer.Configuration.ConfigReader::ReadSimpleSettingWithValidation`
- size: `30`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1b80`
- `0x1c00`

## callees

- `0x16f0`
- `0x17c0`
- `0x17e0`

## pseudocode

```c

```

## disassembly

```asm
0x17c0  ldarg.0
0x17c1  ldarg.1
0x17c2  call     instance string Microsoft.BIServer.Configuration.ConfigReader::ReadSimpleSetting(string key)
0x17c7  stloc.0
0x17c8  ldloc.0
0x17c9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x17ce  brfalse.s loc_17D2
0x17d0  ldarg.2
0x17d1  ret
0x17d2  ldarg.0
0x17d3  ldarg.1
0x17d4  ldarg.3
0x17d5  ldarg.s  4
0x17d7  ldloc.0
0x17d8  call     instance int32 Microsoft.BIServer.Configuration.ConfigReader::TryGetInt(string key, int32 minValue, int32 maxValue, string settingValue)
0x17dd  ret
```
