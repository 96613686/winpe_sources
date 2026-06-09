# System.IO.Packaging.PackUriHelper::GetNormalizedPartUri

- ea: `0x4a710`
- end: `0x4a740`
- name: `System.IO.Packaging.PackUriHelper::GetNormalizedPartUri`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x4a710`
- `0x4aa10`
- `0x5a8f0`

## string_xrefs

- `0x4a719`: `partUri`

## pseudocode

```c

```

## disassembly

```asm
0x4a710  ldarg.0
0x4a711  ldnull
0x4a712  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x4a717  brfalse.s loc_4A724
0x4a719  ldstr    aParturi// "partUri"
0x4a71e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4a723  throw
0x4a724  ldarg.0
0x4a725  isinst   ValidatedPartUri
0x4a72a  brtrue.s loc_4A734
0x4a72c  ldarg.0
0x4a72d  call     class ValidatedPartUri System.IO.Packaging.PackUriHelper::ValidatePartUri(class [System]System.Uri partUri)
0x4a732  starg.s  0
0x4a734  ldarg.0
0x4a735  castclass ValidatedPartUri
0x4a73a  callvirt instance class ValidatedPartUri ValidatedPartUri::get_NormalizedPartUri()
0x4a73f  ret
```
