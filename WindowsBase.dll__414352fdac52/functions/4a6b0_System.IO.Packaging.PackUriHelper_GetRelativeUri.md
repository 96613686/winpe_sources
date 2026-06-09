# System.IO.Packaging.PackUriHelper::GetRelativeUri

- ea: `0x4a6b0`
- end: `0x4a704`
- name: `System.IO.Packaging.PackUriHelper::GetRelativeUri`
- size: `84`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x4a6b0`
- `0x4aa10`

## string_xrefs

- `0x4a6b9`: `sourcePartUri`
- `0x4a6cd`: `targetPartUri`

## pseudocode

```c

```

## disassembly

```asm
0x4a6b0  ldarg.0
0x4a6b1  ldnull
0x4a6b2  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x4a6b7  brfalse.s loc_4A6C4
0x4a6b9  ldstr    aSourceparturi// "sourcePartUri"
0x4a6be  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4a6c3  throw
0x4a6c4  ldarg.1
0x4a6c5  ldnull
0x4a6c6  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x4a6cb  brfalse.s loc_4A6D8
0x4a6cd  ldstr    aTargetparturi// "targetPartUri"
0x4a6d2  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4a6d7  throw
0x4a6d8  ldsfld   class [System]System.Uri System.IO.Packaging.PackUriHelper::_defaultUri
0x4a6dd  ldarg.0
0x4a6de  call     class ValidatedPartUri System.IO.Packaging.PackUriHelper::ValidatePartUri(class [System]System.Uri partUri)
0x4a6e3  newobj   instance void [System]System.Uri::.ctor(class [System]System.Uri, class [System]System.Uri)
0x4a6e8  starg.s  0
0x4a6ea  ldsfld   class [System]System.Uri System.IO.Packaging.PackUriHelper::_defaultUri
0x4a6ef  ldarg.1
0x4a6f0  call     class ValidatedPartUri System.IO.Packaging.PackUriHelper::ValidatePartUri(class [System]System.Uri partUri)
0x4a6f5  newobj   instance void [System]System.Uri::.ctor(class [System]System.Uri, class [System]System.Uri)
0x4a6fa  starg.s  1
0x4a6fc  ldarg.0
0x4a6fd  ldarg.1
0x4a6fe  callvirt instance class [System]System.Uri [System]System.Uri::MakeRelativeUri(class [System]System.Uri)
0x4a703  ret
```
