# System.Deployment.Internal.CodeSigning.SignedCmiManifest2::.ctor_0

- ea: `0x7a40`
- end: `0x7a63`
- name: `System.Deployment.Internal.CodeSigning.SignedCmiManifest2::.ctor_0`
- size: `35`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x26a90`

## callees

- `0x7a40`

## string_xrefs

- `0x7a49`: `manifestDom`

## pseudocode

```c

```

## disassembly

```asm
0x7a40  ldarg.0
0x7a41  call     instance void [mscorlib]System.Object::.ctor()
0x7a46  ldarg.1
0x7a47  brtrue.s loc_7A54
0x7a49  ldstr    aManifestdom// "manifestDom"
0x7a4e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x7a53  throw
0x7a54  ldarg.0
0x7a55  ldarg.1
0x7a56  stfld    class [System.Xml]System.Xml.XmlDocument System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_manifestDom
0x7a5b  ldarg.0
0x7a5c  ldarg.2
0x7a5d  stfld    bool System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_useSha256OrHigher
0x7a62  ret
```
