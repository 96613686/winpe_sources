# Microsoft.BIServer.Configuration.ConfigReader::GetReportServerUrl

- ea: `0x1b40`
- end: `0x1b51`
- name: `Microsoft.BIServer.Configuration.ConfigReader::GetReportServerUrl`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1c00`

## callees

- `0x15e0`

## pseudocode

```c

```

## disassembly

```asm
0x1b40  ldarg.0
0x1b41  ldstr    aUiReportserver// "/UI/ReportServerUrl"
0x1b46  ldsfld   string [mscorlib]System.String::Empty
0x1b4b  call     instance string Microsoft.BIServer.Configuration.ConfigReader::ReadStringAtPath(string path, string defaultValue)
0x1b50  ret
```
