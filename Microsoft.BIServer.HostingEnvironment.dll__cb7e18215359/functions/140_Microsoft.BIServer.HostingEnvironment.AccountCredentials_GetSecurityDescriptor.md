# Microsoft.BIServer.HostingEnvironment.AccountCredentials::GetSecurityDescriptor

- ea: `0x140`
- end: `0x17b`
- name: `Microsoft.BIServer.HostingEnvironment.AccountCredentials::GetSecurityDescriptor`
- size: `59`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x100`

## pseudocode

```c

```

## disassembly

```asm
0x140  ldc.i4.0
0x141  ldc.i4.1
0x142  newobj   instance void [mscorlib]System.Security.AccessControl.RawAcl::.ctor(unsigned int8, int32)
0x147  stloc.0
0x148  ldarg.0
0x149  callvirt instance class [mscorlib]System.Security.Principal.SecurityIdentifier Microsoft.BIServer.HostingEnvironment.AccountCredentials::GetSecurityIdentifier()
0x14e  stloc.1
0x14f  ldloc.0
0x150  ldc.i4.0
0x151  ldc.i4.0
0x152  ldc.i4.0
0x153  ldc.i4   0x20000000
0x158  ldloc.1
0x159  ldc.i4.0
0x15a  ldnull
0x15b  newobj   instance void [mscorlib]System.Security.AccessControl.CommonAce::.ctor(valuetype [mscorlib]System.Security.AccessControl.AceFlags, valuetype [mscorlib]System.Security.AccessControl.AceQualifier, int32, class [mscorlib]System.Security.Principal.SecurityIdentifier, bool, unsigned int8[])
0x160  callvirt instance void [mscorlib]System.Security.AccessControl.RawAcl::InsertAce(int32, class [mscorlib]System.Security.AccessControl.GenericAce)
0x165  ldc.i4   0x8004
0x16a  ldnull
0x16b  ldnull
0x16c  ldnull
0x16d  ldloc.0
0x16e  newobj   instance void [mscorlib]System.Security.AccessControl.RawSecurityDescriptor::.ctor(valuetype [mscorlib]System.Security.AccessControl.ControlFlags, class [mscorlib]System.Security.Principal.SecurityIdentifier, class [mscorlib]System.Security.Principal.SecurityIdentifier, class [mscorlib]System.Security.AccessControl.RawAcl, class [mscorlib]System.Security.AccessControl.RawAcl)
0x173  ldc.i4.s 0xF
0x175  callvirt instance string [mscorlib]System.Security.AccessControl.GenericSecurityDescriptor::GetSddlForm(valuetype [mscorlib]System.Security.AccessControl.AccessControlSections)
0x17a  ret
```
