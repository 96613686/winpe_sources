# Microsoft.Windows.Diagnosis.Network.AssociationInfo::GetAssociation

- ea: `0xe0`
- end: `0x10c`
- name: `Microsoft.Windows.Diagnosis.Network.AssociationInfo::GetAssociation`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xb0`

## pseudocode

```c

```

## disassembly

```asm
0xe0  ldc.i4.0
0xe1  stloc.0
0xe2  ldc.i4.s 0x40
0xe4  ldc.i4.2
0xe5  ldarg.0
0xe6  ldarg.1
0xe7  ldnull
0xe8  ldloca.s 0
0xea  call     unsigned int32 Microsoft.Windows.Diagnosis.Network.NativeShellMethods::AssocQueryString(unsigned int32 flags, unsigned int32 assocStr, string pszAssoc, string pszExtra, [out] class [mscorlib]System.Text.StringBuilder pszOut, [in] [out] unsigned int32& pcchOut)
0xef  pop
0xf0  ldloc.0
0xf1  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0xf6  stloc.1
0xf7  ldc.i4.s 0x40
0xf9  ldc.i4.2
0xfa  ldarg.0
0xfb  ldarg.1
0xfc  ldloc.1
0xfd  ldloca.s 0
0xff  call     unsigned int32 Microsoft.Windows.Diagnosis.Network.NativeShellMethods::AssocQueryString(unsigned int32 flags, unsigned int32 assocStr, string pszAssoc, string pszExtra, [out] class [mscorlib]System.Text.StringBuilder pszOut, [in] [out] unsigned int32& pcchOut)
0x104  pop
0x105  ldloc.1
0x106  callvirt instance string [mscorlib]System.Object::ToString()
0x10b  ret
```
