# Microsoft.BIServer.HostingEnvironment.Request.TrustedProcessToken::CreateToken_0

- ea: `0x3330`
- end: `0x333c`
- name: `Microsoft.BIServer.HostingEnvironment.Request.TrustedProcessToken::CreateToken_0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x3300`
- `0x3340`

## pseudocode

```c

```

## disassembly

```asm
0x3330  ldarg.0
0x3331  call     int64 Microsoft.BIServer.HostingEnvironment.Request.TrustedProcessToken::NowFileTime()
0x3336  call     string Microsoft.BIServer.HostingEnvironment.Request.TrustedProcessToken::CreateToken(class [mscorlib]System.Security.Principal.IPrincipal principal, int64 fileTime)
0x333b  ret
```
