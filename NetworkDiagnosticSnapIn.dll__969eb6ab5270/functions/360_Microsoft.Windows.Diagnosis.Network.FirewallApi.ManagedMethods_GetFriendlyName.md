# Microsoft.Windows.Diagnosis.Network.FirewallApi.ManagedMethods::GetFriendlyName

- ea: `0x360`
- end: `0x39d`
- name: `Microsoft.Windows.Diagnosis.Network.FirewallApi.ManagedMethods::GetFriendlyName`
- size: `61`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x3a0`

## callees

- `0x190`
- `0x360`

## pseudocode

```c

```

## disassembly

```asm
0x360  ldc.i4.0
0x361  stloc.0
0x362  ldc.i4.0
0x363  stloc.1
0x364  ldnull
0x365  stloc.2
0x366  ldc.i4.2
0x367  ldc.i4.4
0x368  ldarg.0
0x369  ldnull
0x36a  ldnull
0x36b  ldloca.s 0
0x36d  call     unsigned int32 Microsoft.Windows.Diagnosis.Network.FirewallApi.NativeMethods::AssocQueryString(valuetype Microsoft.Windows.Diagnosis.Network.FirewallApi.AssocF flags, valuetype Microsoft.Windows.Diagnosis.Network.FirewallApi.AssocStr str, string pszAssoc, string pszExtra, [out] class [mscorlib]System.Text.StringBuilder pszOut, [in] [out] unsigned int32& pcchOut)
0x372  stloc.1
0x373  ldloc.0
0x374  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0x379  stloc.3
0x37a  ldc.i4.2
0x37b  ldc.i4.4
0x37c  ldarg.0
0x37d  ldnull
0x37e  ldloc.3
0x37f  ldloca.s 0
0x381  call     unsigned int32 Microsoft.Windows.Diagnosis.Network.FirewallApi.NativeMethods::AssocQueryString(valuetype Microsoft.Windows.Diagnosis.Network.FirewallApi.AssocF flags, valuetype Microsoft.Windows.Diagnosis.Network.FirewallApi.AssocStr str, string pszAssoc, string pszExtra, [out] class [mscorlib]System.Text.StringBuilder pszOut, [in] [out] unsigned int32& pcchOut)
0x386  stloc.1
0x387  ldloc.1
0x388  brtrue.s loc_391
0x38a  ldloc.3
0x38b  callvirt instance string [mscorlib]System.Object::ToString()
0x390  stloc.2
0x391  ldloc.2
0x392  brtrue.s loc_39B
0x394  ldarg.0
0x395  call     string [mscorlib]System.IO.Path::GetFileNameWithoutExtension(string)
0x39a  stloc.2
0x39b  ldloc.2
0x39c  ret
```
