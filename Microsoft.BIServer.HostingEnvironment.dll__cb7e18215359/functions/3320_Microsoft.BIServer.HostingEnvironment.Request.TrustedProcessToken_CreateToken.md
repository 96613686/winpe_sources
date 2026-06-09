# Microsoft.BIServer.HostingEnvironment.Request.TrustedProcessToken::CreateToken

- ea: `0x3320`
- end: `0x3330`
- name: `Microsoft.BIServer.HostingEnvironment.Request.TrustedProcessToken::CreateToken`
- size: `16`
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
0x3320  call     class [mscorlib]System.Security.Principal.IPrincipal [mscorlib]System.Threading.Thread::get_CurrentPrincipal()
0x3325  call     int64 Microsoft.BIServer.HostingEnvironment.Request.TrustedProcessToken::NowFileTime()
0x332a  call     string Microsoft.BIServer.HostingEnvironment.Request.TrustedProcessToken::CreateToken(class [mscorlib]System.Security.Principal.IPrincipal principal, int64 fileTime)
0x332f  ret
```
