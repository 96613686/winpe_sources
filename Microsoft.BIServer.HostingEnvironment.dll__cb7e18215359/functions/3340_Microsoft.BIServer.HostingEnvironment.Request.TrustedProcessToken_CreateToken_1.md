# Microsoft.BIServer.HostingEnvironment.Request.TrustedProcessToken::CreateToken_1

- ea: `0x3340`
- end: `0x336d`
- name: `Microsoft.BIServer.HostingEnvironment.Request.TrustedProcessToken::CreateToken_1`
- size: `45`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x3320`
- `0x3330`

## callees

- `0x3b20`
- `0x4f00`
- `0x4fe0`

## pseudocode

```c

```

## disassembly

```asm
0x3340  ldstr    a01_1// "{0}|{1}"
0x3345  ldarg.0
0x3346  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Principal.IPrincipal::get_Identity()
0x334b  callvirt instance string [mscorlib]System.Security.Principal.IIdentity::get_Name()
0x3350  ldarg.1
0x3351  box      [mscorlib]System.Int64
0x3356  call     string [mscorlib]System.String::Format(string, object, object)
0x335b  stloc.0
0x335c  call     class Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::get_Current()
0x3361  callvirt instance class Microsoft.BIServer.HostingEnvironment.Cryptography.ICrypto Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::get_CatalogCrypto()
0x3366  ldloc.0
0x3367  callvirt instance string Microsoft.BIServer.HostingEnvironment.Cryptography.ICrypto::EncryptToString(string unprotectedData)
0x336c  ret
```
