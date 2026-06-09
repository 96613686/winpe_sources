# Microsoft.BIServer.HostingEnvironment.ImpersonationContext::Dispose

- ea: `0xb40`
- end: `0xb81`
- name: `Microsoft.BIServer.HostingEnvironment.ImpersonationContext::Dispose`
- size: `65`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xb40`

## pseudocode

```c

```

## disassembly

```asm
0xb40  ldarg.0
0xb41  ldfld    bool Microsoft.BIServer.HostingEnvironment.ImpersonationContext::_disposed
0xb46  brtrue.s loc_B80
0xb48  ldarg.0
0xb49  ldc.i4.1
0xb4a  stfld    bool Microsoft.BIServer.HostingEnvironment.ImpersonationContext::_disposed
0xb4f  ldarg.0
0xb50  ldfld    class [mscorlib]System.Security.Principal.WindowsImpersonationContext Microsoft.BIServer.HostingEnvironment.ImpersonationContext::_context
0xb55  brfalse.s loc_B6D
0xb57  ldarg.0
0xb58  ldfld    class [mscorlib]System.Security.Principal.WindowsImpersonationContext Microsoft.BIServer.HostingEnvironment.ImpersonationContext::_context
0xb5d  callvirt instance void [mscorlib]System.Security.Principal.WindowsImpersonationContext::Undo()
0xb62  ldarg.0
0xb63  ldfld    class [mscorlib]System.Security.Principal.WindowsImpersonationContext Microsoft.BIServer.HostingEnvironment.ImpersonationContext::_context
0xb68  callvirt instance void [mscorlib]System.Security.Principal.WindowsImpersonationContext::Dispose()
0xb6d  ldarg.0
0xb6e  ldfld    class Microsoft.BIServer.HostingEnvironment.SafeTokenHandle Microsoft.BIServer.HostingEnvironment.ImpersonationContext::_handle
0xb73  brfalse.s loc_B80
0xb75  ldarg.0
0xb76  ldfld    class Microsoft.BIServer.HostingEnvironment.SafeTokenHandle Microsoft.BIServer.HostingEnvironment.ImpersonationContext::_handle
0xb7b  callvirt instance void [mscorlib]System.Runtime.InteropServices.SafeHandle::Dispose()
0xb80  ret
```
