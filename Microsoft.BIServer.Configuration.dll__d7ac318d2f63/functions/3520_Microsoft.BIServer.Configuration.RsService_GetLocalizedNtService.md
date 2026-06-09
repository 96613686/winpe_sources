# Microsoft.BIServer.Configuration.RsService::GetLocalizedNtService

- ea: `0x3520`
- end: `0x3579`
- name: `Microsoft.BIServer.Configuration.RsService::GetLocalizedNtService`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x3500`

## callees

- `0x3580`

## pseudocode

```c

```

## disassembly

```asm
0x3520  ldstr    aS1580// "S-1-5-80"
0x3525  newobj   instance void [mscorlib]System.Security.Principal.SecurityIdentifier::.ctor(string)
0x352a  dup
0x352b  callvirt instance int32 [mscorlib]System.Security.Principal.SecurityIdentifier::get_BinaryLength()
0x3530  newarr   [mscorlib]System.Byte
0x3535  stloc.0
0x3536  ldloc.0
0x3537  ldc.i4.0
0x3538  callvirt instance void [mscorlib]System.Security.Principal.SecurityIdentifier::GetBinaryForm(unsigned int8[], int32)
0x353d  ldc.i4   0x80
0x3542  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0x3547  stloc.1
0x3548  ldloc.1
0x3549  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Capacity()
0x354e  stloc.2
0x354f  ldc.i4   0x80
0x3554  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0x3559  stloc.3
0x355a  ldloc.3
0x355b  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Capacity()
0x3560  stloc.s  4
0x3562  ldnull
0x3563  ldloc.0
0x3564  ldloc.1
0x3565  ldloca.s 2
0x3567  ldloc.3
0x3568  ldloca.s 4
0x356a  ldloca.s 5
0x356c  call     bool Microsoft.BIServer.Configuration.RsService::LookupAccountSid(string lpSystemName, [hasfieldmarshal] unsigned int8[] sid, class [mscorlib]System.Text.StringBuilder lpName, unsigned int32& cchName, class [mscorlib]System.Text.StringBuilder ReferencedDomainName, unsigned int32& cchReferencedDomainName, [out] valuetype sidNameUsage& peUsage)
0x3571  pop
0x3572  ldloc.1
0x3573  callvirt instance string [mscorlib]System.Object::ToString()
0x3578  ret
```
