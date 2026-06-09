# Microsoft.BIServer.HostingEnvironment.Request.TrustedProcessToken::ValididateTokenOrException

- ea: `0x3370`
- end: `0x337c`
- name: `Microsoft.BIServer.HostingEnvironment.Request.TrustedProcessToken::ValididateTokenOrException`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x3380`

## pseudocode

```c

```

## disassembly

```asm
0x3370  ldarg.0
0x3371  call     class [mscorlib]System.Security.Principal.IPrincipal [mscorlib]System.Threading.Thread::get_CurrentPrincipal()
0x3376  call     void Microsoft.BIServer.HostingEnvironment.Request.TrustedProcessToken::ValidateTokenOrException(string token, class [mscorlib]System.Security.Principal.IPrincipal userPrincipal)
0x337b  ret
```
