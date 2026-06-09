# System.IO.Packaging.PackUriHelper::IsRelationshipPartUri

- ea: `0x4a810`
- end: `0x4a840`
- name: `System.IO.Packaging.PackUriHelper::IsRelationshipPartUri`
- size: `48`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x21640`
- `0x48cd0`
- `0x49780`
- `0x49990`
- `0x4a840`
- `0x4a8f0`

## callees

- `0x4a810`
- `0x4aa10`
- `0x5a930`

## string_xrefs

- `0x4a819`: `partUri`

## pseudocode

```c

```

## disassembly

```asm
0x4a810  ldarg.0
0x4a811  ldnull
0x4a812  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x4a817  brfalse.s loc_4A824
0x4a819  ldstr    aParturi// "partUri"
0x4a81e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4a823  throw
0x4a824  ldarg.0
0x4a825  isinst   ValidatedPartUri
0x4a82a  brtrue.s loc_4A834
0x4a82c  ldarg.0
0x4a82d  call     class ValidatedPartUri System.IO.Packaging.PackUriHelper::ValidatePartUri(class [System]System.Uri partUri)
0x4a832  starg.s  0
0x4a834  ldarg.0
0x4a835  castclass ValidatedPartUri
0x4a83a  callvirt instance bool ValidatedPartUri::get_IsRelationshipPartUri()
0x4a83f  ret
```
