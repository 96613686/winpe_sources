# System.IO.Packaging.PackageDigitalSignatureManager::RemoveSignature

- ea: `0x4c510`
- end: `0x4c588`
- name: `System.IO.Packaging.PackageDigitalSignatureManager::RemoveSignature`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x2c100`
- `0x4bc90`
- `0x4bef0`
- `0x4c510`
- `0x4c980`
- `0x4cb70`
- `0x4ce10`

## string_xrefs

- `0x4c518`: `CannotRemoveSignatureFromReadOnlyFile`
- `0x4c531`: `signatureUri`

## pseudocode

```c

```

## disassembly

```asm
0x4c510  ldarg.0
0x4c511  call     instance bool System.IO.Packaging.PackageDigitalSignatureManager::get_ReadOnly()
0x4c516  brfalse.s loc_4C528
0x4c518  ldstr    aCannotremovesi// "CannotRemoveSignatureFromReadOnlyFile"
0x4c51d  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x4c522  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x4c527  throw
0x4c528  ldarg.1
0x4c529  ldnull
0x4c52a  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x4c52f  brfalse.s loc_4C53C
0x4c531  ldstr    aSignatureuri// "signatureUri"
0x4c536  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4c53b  throw
0x4c53c  ldarg.0
0x4c53d  call     instance bool System.IO.Packaging.PackageDigitalSignatureManager::get_IsSigned()
0x4c542  brtrue.s loc_4C545
0x4c544  ret
0x4c545  ldarg.0
0x4c546  ldarg.1
0x4c547  call     instance int32 System.IO.Packaging.PackageDigitalSignatureManager::GetSignatureIndex(class [System]System.Uri uri)
0x4c54c  stloc.0
0x4c54d  ldloc.0
0x4c54e  ldc.i4.0
0x4c54f  bge.s    loc_4C552
0x4c551  ret
0x4c552  nop
0x4c553  ldarg.0
0x4c554  ldarg.1
0x4c555  ldarg.0
0x4c556  ldfld    class [mscorlib]System.Collections.Generic.List`1<class System.IO.Packaging.PackageDigitalSignature> System.IO.Packaging.PackageDigitalSignatureManager::_signatures
0x4c55b  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class System.IO.Packaging.PackageDigitalSignature>::get_Count()
0x4c560  ldc.i4.1
0x4c561  sub
0x4c562  call     instance void System.IO.Packaging.PackageDigitalSignatureManager::InternalRemoveSignature(class [System]System.Uri signatureUri, int32 countOfSignaturesRemaining)
0x4c567  ldarg.0
0x4c568  ldfld    class [mscorlib]System.Collections.Generic.List`1<class System.IO.Packaging.PackageDigitalSignature> System.IO.Packaging.PackageDigitalSignatureManager::_signatures
0x4c56d  ldloc.0
0x4c56e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class System.IO.Packaging.PackageDigitalSignature>::get_Item(!!T0)
0x4c573  callvirt instance void System.IO.Packaging.PackageDigitalSignature::Invalidate()
0x4c578  leave.s  loc_4C587
0x4c57a  ldarg.0
0x4c57b  ldfld    class [mscorlib]System.Collections.Generic.List`1<class System.IO.Packaging.PackageDigitalSignature> System.IO.Packaging.PackageDigitalSignatureManager::_signatures
0x4c580  ldloc.0
0x4c581  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.IO.Packaging.PackageDigitalSignature>::RemoveAt(int32)
0x4c586  endfinally
0x4c587  ret
```
