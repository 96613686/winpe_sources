# Microsoft.BIServer.HostingEnvironment.ImpersonationContext::EnterUserContext

- ea: `0xa80`
- end: `0xa95`
- name: `Microsoft.BIServer.HostingEnvironment.ImpersonationContext::EnterUserContext`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0xa80`
- `0xac0`

## pseudocode

```c

```

## disassembly

```asm
0xa80  ldarg.0
0xa81  brtrue.s loc_A8E
0xa83  ldstr    aNullAccountCre// "Null account credentials"
0xa88  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xa8d  throw
0xa8e  ldarg.0
0xa8f  newobj   instance void Microsoft.BIServer.HostingEnvironment.ImpersonationContext::.ctor(class Microsoft.BIServer.HostingEnvironment.AccountCredentials accountCredentials)
0xa94  ret
```
