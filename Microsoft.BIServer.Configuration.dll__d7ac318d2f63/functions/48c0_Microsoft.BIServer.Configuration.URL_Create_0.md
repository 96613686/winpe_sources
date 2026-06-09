# Microsoft.BIServer.Configuration.URL::Create_0

- ea: `0x48c0`
- end: `0x48e8`
- name: `Microsoft.BIServer.Configuration.URL::Create_0`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x3b00`

## callees

- `0x4860`
- `0x48b0`
- `0x48c0`

## pseudocode

```c

```

## disassembly

```asm
0x48c0  ldarg.1
0x48c1  brfalse.s loc_48E1
0x48c3  ldarg.0
0x48c4  ldarg.1
0x48c5  callvirt instance string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.AccountCredentials::get_DomainUser()
0x48ca  ldarg.1
0x48cb  callvirt instance class [mscorlib]System.Security.Principal.SecurityIdentifier [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.AccountCredentials::GetSecurityIdentifier()
0x48d0  callvirt instance string [mscorlib]System.Object::ToString()
0x48d5  ldarg.1
0x48d6  callvirt instance string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.AccountCredentials::GetSecurityDescriptor()
0x48db  newobj   instance void Microsoft.BIServer.Configuration.URL::.ctor(string urlString, string accountName, string accountSecurityIdentifier, string accountSecurityDescriptor)
0x48e0  ret
0x48e1  ldarg.0
0x48e2  call     class Microsoft.BIServer.Configuration.URL Microsoft.BIServer.Configuration.URL::Create(string urlString)
0x48e7  ret
```
