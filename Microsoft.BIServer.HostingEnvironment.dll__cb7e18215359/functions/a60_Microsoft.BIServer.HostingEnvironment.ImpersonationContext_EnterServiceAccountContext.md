# Microsoft.BIServer.HostingEnvironment.ImpersonationContext::EnterServiceAccountContext

- ea: `0xa60`
- end: `0xa7f`
- name: `Microsoft.BIServer.HostingEnvironment.ImpersonationContext::EnterServiceAccountContext`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x5a70`

## callees

- `0xb20`

## pseudocode

```c

```

## disassembly

```asm
0xa60  ldc.i4   0x202
0xa65  newobj   instance void [mscorlib]System.Security.Permissions.SecurityPermission::.ctor(valuetype [mscorlib]System.Security.Permissions.SecurityPermissionFlag)
0xa6a  call     instance void [mscorlib]System.Security.CodeAccessPermission::Assert()
0xa6f  call     void [mscorlib]System.Security.CodeAccessPermission::RevertAssert()
0xa74  ldsfld   native int [mscorlib]System.IntPtr::Zero
0xa79  newobj   instance void Microsoft.BIServer.HostingEnvironment.ImpersonationContext::.ctor(native int userToken)
0xa7e  ret
```
