# Microsoft.BIServer.Configuration.XmlConfigFile::GetFileFromDirectory

- ea: `0x3e60`
- end: `0x3e71`
- name: `Microsoft.BIServer.Configuration.XmlConfigFile::GetFileFromDirectory`
- size: `17`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x3e10`
- `0x3e80`

## string_xrefs

- `0x3e61`: `ReportServer\rsreportserver.config`

## pseudocode

```c

```

## disassembly

```asm
0x3e60  ldarg.0
0x3e61  ldstr    aReportserverRs// "ReportServer\\rsreportserver.config"
0x3e66  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x3e6b  call     string [mscorlib]System.IO.Path::GetFullPath(string)
0x3e70  ret
```
