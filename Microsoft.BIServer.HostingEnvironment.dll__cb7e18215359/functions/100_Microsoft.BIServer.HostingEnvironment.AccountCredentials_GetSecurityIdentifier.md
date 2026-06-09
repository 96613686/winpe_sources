# Microsoft.BIServer.HostingEnvironment.AccountCredentials::GetSecurityIdentifier

- ea: `0x100`
- end: `0x113`
- name: `Microsoft.BIServer.HostingEnvironment.AccountCredentials::GetSecurityIdentifier`
- size: `19`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140`

## callees

- `0x100`
- `0x180`
- `0x36c0`

## pseudocode

```c

```

## disassembly

```asm
0x100  ldarg.0
0x101  call     instance class [mscorlib]System.Security.Principal.SecurityIdentifier Microsoft.BIServer.HostingEnvironment.AccountCredentials::GetSecurityIdentifierWithoutCheck()
0x106  stloc.0
0x107  leave.s  loc_111
0x109  pop
0x10a  ldarg.0
0x10b  newobj   instance void Microsoft.BIServer.HostingEnvironment.Exceptions.AccountDoesNotExistException::.ctor(class Microsoft.BIServer.HostingEnvironment.AccountCredentials credentials)
0x110  throw
0x111  ldloc.0
0x112  ret
```
