# Microsoft.BIServer.Configuration.ScopedFileDelete::.cctor

- ea: `0x850`
- end: `0x876`
- name: `Microsoft.BIServer.Configuration.ScopedFileDelete::.cctor`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x855`: `TempFileDeleteRetryMinutes`

## pseudocode

```c

```

## disassembly

```asm
0x850  ldsfld   class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::Current
0x855  ldstr    aTempfiledelete// "TempFileDeleteRetryMinutes"
0x85a  ldc.i4.2
0x85b  callvirt instance int32 [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::GetIntOrDefault(string, int32)
0x860  stsfld   int32 Microsoft.BIServer.Configuration.ScopedFileDelete::deleteRetryMintues
0x865  ldsfld   int32 Microsoft.BIServer.Configuration.ScopedFileDelete::deleteRetryMintues
0x86a  conv.r8
0x86b  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMinutes(float64)
0x870  stsfld   valuetype [mscorlib]System.TimeSpan Microsoft.BIServer.Configuration.ScopedFileDelete::DeleteRetrySpan
0x875  ret
```
