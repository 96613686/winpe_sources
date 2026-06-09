# Microsoft.BIServer.HostingEnvironment.Request.TrustedProcessToken::.cctor

- ea: `0x34b0`
- end: `0x34cd`
- name: `Microsoft.BIServer.HostingEnvironment.Request.TrustedProcessToken::.cctor`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x870`

## pseudocode

```c

```

## disassembly

```asm
0x34b0  ldsfld   class Microsoft.BIServer.HostingEnvironment.StaticConfig Microsoft.BIServer.HostingEnvironment.StaticConfig::Current
0x34b5  ldstr    aTrustedprocess// "TrustedProcessTimeoutSeconds"
0x34ba  ldc.i4.s 0xA
0x34bc  callvirt instance int32 Microsoft.BIServer.HostingEnvironment.StaticConfig::GetIntOrDefault(string key, int32 defaultValue)
0x34c1  conv.r8
0x34c2  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromSeconds(float64)
0x34c7  stsfld   valuetype [mscorlib]System.TimeSpan Microsoft.BIServer.HostingEnvironment.Request.TrustedProcessToken::RequestTimeout
0x34cc  ret
```
