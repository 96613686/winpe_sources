# Microsoft.BIServer.RSHostingService.RsTraceConfig::get_LogFolderPath

- ea: `0x8a0`
- end: `0x8ce`
- name: `Microsoft.BIServer.RSHostingService.RsTraceConfig::get_LogFolderPath`
- size: `46`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1010`
- `0x12b0`
- `0x2430`

## callees

- `0x700`
- `0x8a0`

## pseudocode

```c

```

## disassembly

```asm
0x8a0  ldarg.0
0x8a1  call     instance string Microsoft.BIServer.RSHostingService.RsTraceConfig::get_Directory()
0x8a6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8ab  brtrue.s loc_8B4
0x8ad  ldarg.0
0x8ae  call     instance string Microsoft.BIServer.RSHostingService.RsTraceConfig::get_Directory()
0x8b3  ret
0x8b4  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x8b9  callvirt instance string [mscorlib]System.AppDomain::get_BaseDirectory()
0x8be  ldstr    aLogfiles// "..\\LogFiles"
0x8c3  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x8c8  call     string [mscorlib]System.IO.Path::GetFullPath(string)
0x8cd  ret
```
