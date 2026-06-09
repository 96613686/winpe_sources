# Microsoft.BIServer.HostingEnvironment.AccountCredentials::GetSecurityIdentifierWithoutCheck

- ea: `0x180`
- end: `0x19b`
- name: `Microsoft.BIServer.HostingEnvironment.AccountCredentials::GetSecurityIdentifierWithoutCheck`
- size: `27`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x100`
- `0x120`

## callees

- `0xe0`

## pseudocode

```c

```

## disassembly

```asm
0x180  ldarg.0
0x181  call     instance class [mscorlib]System.Security.Principal.NTAccount Microsoft.BIServer.HostingEnvironment.AccountCredentials::GetNtAccount()
0x186  ldtoken  [mscorlib]System.Security.Principal.SecurityIdentifier
0x18b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x190  callvirt instance class [mscorlib]System.Security.Principal.IdentityReference [mscorlib]System.Security.Principal.IdentityReference::Translate(class [mscorlib]System.Type)
0x195  castclass [mscorlib]System.Security.Principal.SecurityIdentifier
0x19a  ret
```
