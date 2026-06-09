# Microsoft.BIServer.Configuration.UrlEndpoints::GetApplicationsForUsage

- ea: `0x3930`
- end: `0x3953`
- name: `Microsoft.BIServer.Configuration.UrlEndpoints::GetApplicationsForUsage`
- size: `35`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x3990`
- `0x3aa0`
- `0x3ac0`
- `0x3ae0`

## callees

- `0x3660`
- `0x3850`

## pseudocode

```c

```

## disassembly

```asm
0x3930  ldarg.0
0x3931  ldarg.1
0x3932  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.BIServer.Configuration.UrlEndpointDefinition> Microsoft.BIServer.Configuration.UrlEndpoints::GetEndpointsForUsage(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.AccountCredentials accountCredentials, valuetype Microsoft.BIServer.Configuration.UrlEndpointUsage targetUsage)
0x3937  ldnull
0x3938  ldftn    class Microsoft.BIServer.Configuration.Application Microsoft.BIServer.Configuration.UrlEndpoints::CreateApplication(class Microsoft.BIServer.Configuration.UrlEndpointDefinition urlEndpointDefinition)
0x393e  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.BIServer.Configuration.UrlEndpointDefinition, class Microsoft.BIServer.Configuration.Application>::.ctor(object, native int)
0x3943  call     T0x2B00002E
0x3948  call     T0x2B00002F
0x394d  newobj   instance void Microsoft.BIServer.Configuration.UrlApplications::.ctor(class [mscorlib]System.Collections.Generic.List`1<class Microsoft.BIServer.Configuration.Application> urlApplications)
0x3952  ret
```
