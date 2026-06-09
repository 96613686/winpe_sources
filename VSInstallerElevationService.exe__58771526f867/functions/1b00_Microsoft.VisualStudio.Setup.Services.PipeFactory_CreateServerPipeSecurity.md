# Microsoft.VisualStudio.Setup.Services.PipeFactory::CreateServerPipeSecurity

- ea: `0x1b00`
- end: `0x1b46`
- name: `Microsoft.VisualStudio.Setup.Services.PipeFactory::CreateServerPipeSecurity`
- size: `70`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1ae0`

## pseudocode

```c

```

## disassembly

```asm
0x1b00  newobj   instance void [System.Core]System.IO.Pipes.PipeSecurity::.ctor()
0x1b05  ldc.i4.s 0x16
0x1b07  ldnull
0x1b08  newobj   instance void [mscorlib]System.Security.Principal.SecurityIdentifier::.ctor(valuetype [mscorlib]System.Security.Principal.WellKnownSidType, class [mscorlib]System.Security.Principal.SecurityIdentifier)
0x1b0d  stloc.0
0x1b0e  ldloc.0
0x1b0f  ldc.i4   0x1F019F
0x1b14  ldc.i4.0
0x1b15  newobj   instance void [System.Core]System.IO.Pipes.PipeAccessRule::.ctor(class [mscorlib]System.Security.Principal.IdentityReference, valuetype [System.Core]System.IO.Pipes.PipeAccessRights, valuetype [mscorlib]System.Security.AccessControl.AccessControlType)
0x1b1a  stloc.1
0x1b1b  dup
0x1b1c  ldloc.1
0x1b1d  callvirt instance void [System.Core]System.IO.Pipes.PipeSecurity::AddAccessRule(class [System.Core]System.IO.Pipes.PipeAccessRule)
0x1b22  dup
0x1b23  ldloc.0
0x1b24  callvirt instance void [mscorlib]System.Security.AccessControl.ObjectSecurity::SetOwner(class [mscorlib]System.Security.Principal.IdentityReference)
0x1b29  ldc.i4.1
0x1b2a  ldnull
0x1b2b  newobj   instance void [mscorlib]System.Security.Principal.SecurityIdentifier::.ctor(valuetype [mscorlib]System.Security.Principal.WellKnownSidType, class [mscorlib]System.Security.Principal.SecurityIdentifier)
0x1b30  stloc.0
0x1b31  ldloc.0
0x1b32  ldc.i4   0x12019B
0x1b37  ldc.i4.0
0x1b38  newobj   instance void [System.Core]System.IO.Pipes.PipeAccessRule::.ctor(class [mscorlib]System.Security.Principal.IdentityReference, valuetype [System.Core]System.IO.Pipes.PipeAccessRights, valuetype [mscorlib]System.Security.AccessControl.AccessControlType)
0x1b3d  stloc.1
0x1b3e  dup
0x1b3f  ldloc.1
0x1b40  callvirt instance void [System.Core]System.IO.Pipes.PipeSecurity::AddAccessRule(class [System.Core]System.IO.Pipes.PipeAccessRule)
0x1b45  ret
```
