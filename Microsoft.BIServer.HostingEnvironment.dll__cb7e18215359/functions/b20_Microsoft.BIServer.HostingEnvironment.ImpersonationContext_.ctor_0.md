# Microsoft.BIServer.HostingEnvironment.ImpersonationContext::.ctor_0

- ea: `0xb20`
- end: `0xb33`
- name: `Microsoft.BIServer.HostingEnvironment.ImpersonationContext::.ctor_0`
- size: `19`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xa60`
- `0xaa0`

## pseudocode

```c

```

## disassembly

```asm
0xb20  ldarg.0
0xb21  call     instance void [mscorlib]System.Object::.ctor()
0xb26  ldarg.0
0xb27  ldarg.1
0xb28  call     class [mscorlib]System.Security.Principal.WindowsImpersonationContext [mscorlib]System.Security.Principal.WindowsIdentity::Impersonate(native int)
0xb2d  stfld    class [mscorlib]System.Security.Principal.WindowsImpersonationContext Microsoft.BIServer.HostingEnvironment.ImpersonationContext::_context
0xb32  ret
```
