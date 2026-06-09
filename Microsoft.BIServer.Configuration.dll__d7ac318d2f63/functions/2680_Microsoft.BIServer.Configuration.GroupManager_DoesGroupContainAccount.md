# Microsoft.BIServer.Configuration.GroupManager::DoesGroupContainAccount

- ea: `0x2680`
- end: `0x2708`
- name: `Microsoft.BIServer.Configuration.GroupManager::DoesGroupContainAccount`
- size: `136`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x2610`

## callees

- `0x2680`

## string_xrefs

- `0x26b4`: `objectSid`

## pseudocode

```c

```

## disassembly

```asm
0x2680  ldarg.1
0x2681  callvirt instance class [mscorlib]System.Security.Principal.SecurityIdentifier [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.AccountCredentials::GetSecurityIdentifier()
0x2686  stloc.0
0x2687  ldarg.0
0x2688  ldstr    aMembers// "members"
0x268d  call     T0x2B000015
0x2692  callvirt instance object [System.DirectoryServices]System.DirectoryServices.DirectoryEntry::Invoke(string, object[])
0x2697  castclass [mscorlib]System.Collections.IEnumerable
0x269c  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x26a1  stloc.1
0x26a2  br.s     loc_26E6
0x26a4  ldloc.1
0x26a5  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x26aa  newobj   instance void [System.DirectoryServices]System.DirectoryServices.DirectoryEntry::.ctor(object)
0x26af  callvirt instance class [System.DirectoryServices]System.DirectoryServices.PropertyCollection [System.DirectoryServices]System.DirectoryServices.DirectoryEntry::get_Properties()
0x26b4  ldstr    aObjectsid// "objectSid"
0x26b9  callvirt instance class [System.DirectoryServices]System.DirectoryServices.PropertyValueCollection [System.DirectoryServices]System.DirectoryServices.PropertyCollection::get_Item(string)
0x26be  stloc.2
0x26bf  ldloc.2
0x26c0  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x26c5  ldc.i4.0
0x26c6  ble.s    loc_26E6
0x26c8  ldloc.2
0x26c9  ldc.i4.0
0x26ca  callvirt instance object [System.DirectoryServices]System.DirectoryServices.PropertyValueCollection::get_Item(int32)
0x26cf  castclass unsigned int8[]
0x26d4  ldc.i4.0
0x26d5  newobj   instance void [mscorlib]System.Security.Principal.SecurityIdentifier::.ctor(unsigned int8[], int32)
0x26da  ldloc.0
0x26db  callvirt instance bool [mscorlib]System.Security.Principal.SecurityIdentifier::Equals(class [mscorlib]System.Security.Principal.SecurityIdentifier)
0x26e0  brfalse.s loc_26E6
0x26e2  ldc.i4.1
0x26e3  stloc.3
0x26e4  leave.s  loc_2706
0x26e6  ldloc.1
0x26e7  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x26ec  brtrue.s loc_26A4
0x26ee  leave.s  loc_2704
0x26f0  ldloc.1
0x26f1  isinst   [mscorlib]System.IDisposable
0x26f6  stloc.s  4
0x26f8  ldloc.s  4
0x26fa  brfalse.s loc_2703
0x26fc  ldloc.s  4
0x26fe  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2703  endfinally
0x2704  ldc.i4.0
0x2705  ret
0x2706  ldloc.3
0x2707  ret
```
