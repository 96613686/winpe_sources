# Microsoft.BIServer.Configuration.ConfigReader::GetSecureConnectionLevel

- ea: `0x1b80`
- end: `0x1b8f`
- name: `Microsoft.BIServer.Configuration.ConfigReader::GetSecureConnectionLevel`
- size: `15`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1c00`

## callees

- `0x17c0`

## pseudocode

```c

```

## disassembly

```asm
0x1b80  ldarg.0
0x1b81  ldstr    aSecureconnecti// "SecureConnectionLevel"
0x1b86  ldc.i4.0
0x1b87  ldc.i4.0
0x1b88  ldc.i4.3
0x1b89  call     instance int32 Microsoft.BIServer.Configuration.ConfigReader::ReadSimpleSettingWithValidation(string key, int32 defaultValue, int32 minValue, [opt] int32 maxValue)
0x1b8e  ret
```
