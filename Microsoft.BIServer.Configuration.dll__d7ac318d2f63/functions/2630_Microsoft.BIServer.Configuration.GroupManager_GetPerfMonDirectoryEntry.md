# Microsoft.BIServer.Configuration.GroupManager::GetPerfMonDirectoryEntry

- ea: `0x2630`
- end: `0x267f`
- name: `Microsoft.BIServer.Configuration.GroupManager::GetPerfMonDirectoryEntry`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2610`

## callees

- `0x2630`

## pseudocode

```c

```

## disassembly

```asm
0x2630  ldc.i4.s 0x39
0x2632  ldnull
0x2633  newobj   instance void [mscorlib]System.Security.Principal.SecurityIdentifier::.ctor(valuetype [mscorlib]System.Security.Principal.WellKnownSidType, class [mscorlib]System.Security.Principal.SecurityIdentifier)
0x2638  ldtoken  [mscorlib]System.Security.Principal.NTAccount
0x263d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2642  callvirt instance class [mscorlib]System.Security.Principal.IdentityReference [mscorlib]System.Security.Principal.IdentityReference::Translate(class [mscorlib]System.Type)
0x2647  castclass [mscorlib]System.Security.Principal.NTAccount
0x264c  callvirt instance string [mscorlib]System.Security.Principal.IdentityReference::get_Value()
0x2651  stloc.0
0x2652  ldloc.0
0x2653  ldc.i4.s 0x5C
0x2655  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x265a  stloc.1
0x265b  ldloc.1
0x265c  ldc.i4.m1
0x265d  ble.s    loc_2669
0x265f  ldloc.0
0x2660  ldloc.1
0x2661  ldc.i4.1
0x2662  add
0x2663  callvirt instance string [mscorlib]System.String::Substring(int32)
0x2668  stloc.0
0x2669  ldstr    aWinnt01// "WinNT://{0}/{1}"
0x266e  call     string [mscorlib]System.Environment::get_MachineName()
0x2673  ldloc.0
0x2674  call     string [mscorlib]System.String::Format(string, object, object)
0x2679  newobj   instance void [System.DirectoryServices]System.DirectoryServices.DirectoryEntry::.ctor(string)
0x267e  ret
```
