# System.Deployment.Internal.CodeSigning.SignedCmiManifest::.ctor_0

- ea: `0x6080`
- end: `0x609c`
- name: `System.Deployment.Internal.CodeSigning.SignedCmiManifest::.ctor_0`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x25a00`

## callees

- `0x6080`

## string_xrefs

- `0x6089`: `manifestDom`

## pseudocode

```c

```

## disassembly

```asm
0x6080  ldarg.0
0x6081  call     instance void [mscorlib]System.Object::.ctor()
0x6086  ldarg.1
0x6087  brtrue.s loc_6094
0x6089  ldstr    aManifestdom// "manifestDom"
0x608e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x6093  throw
0x6094  ldarg.0
0x6095  ldarg.1
0x6096  stfld    class [System.Xml]System.Xml.XmlDocument System.Deployment.Internal.CodeSigning.SignedCmiManifest::m_manifestDom
0x609b  ret
```
