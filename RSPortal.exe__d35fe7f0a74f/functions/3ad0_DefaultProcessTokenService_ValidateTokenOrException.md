# DefaultProcessTokenService::ValidateTokenOrException

- ea: `0x3ad0`
- end: `0x3ad8`
- name: `DefaultProcessTokenService::ValidateTokenOrException`
- size: `8`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## pseudocode

```c

```

## disassembly

```asm
0x3ad0  ldarg.1
0x3ad1  ldarg.2
0x3ad2  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Request.TrustedProcessToken::ValidateTokenOrException(string, class [mscorlib]System.Security.Principal.IPrincipal)
0x3ad7  ret
```
