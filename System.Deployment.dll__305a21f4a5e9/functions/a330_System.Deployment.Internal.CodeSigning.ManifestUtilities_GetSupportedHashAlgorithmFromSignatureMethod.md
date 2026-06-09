# System.Deployment.Internal.CodeSigning.ManifestUtilities::GetSupportedHashAlgorithmFromSignatureMethod

- ea: `0xa330`
- end: `0xa37b`
- name: `System.Deployment.Internal.CodeSigning.ManifestUtilities::GetSupportedHashAlgorithmFromSignatureMethod`
- size: `75`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x7b40`

## callees

- `0xa330`

## string_xrefs

- `0xa334`: `http://www.w3.org/2000/09/xmldsig#rsa-sha512`
- `0xa344`: `http://www.w3.org/2000/09/xmldsig#rsa-sha384`
- `0xa354`: `http://www.w3.org/2000/09/xmldsig#rsa-sha256`
- `0xa364`: `http://www.w3.org/2000/09/xmldsig#rsa-sha1`

## pseudocode

```c

```

## disassembly

```asm
0xa330  ldarg.1
0xa331  brfalse.s loc_A363
0xa333  ldarg.0
0xa334  ldstr    aHttpWwwW3Org20_2// "http://www.w3.org/2000/09/xmldsig#rsa-s"...
0xa339  ldc.i4.5
0xa33a  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0xa33f  brfalse.s loc_A343
0xa341  ldc.i4.3
0xa342  ret
0xa343  ldarg.0
0xa344  ldstr    aHttpWwwW3Org20_4// "http://www.w3.org/2000/09/xmldsig#rsa-s"...
0xa349  ldc.i4.5
0xa34a  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0xa34f  brfalse.s loc_A353
0xa351  ldc.i4.2
0xa352  ret
0xa353  ldarg.0
0xa354  ldstr    aHttpWwwW3Org20_6// "http://www.w3.org/2000/09/xmldsig#rsa-s"...
0xa359  ldc.i4.5
0xa35a  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0xa35f  brfalse.s loc_A373
0xa361  ldc.i4.1
0xa362  ret
0xa363  ldarg.0
0xa364  ldstr    aHttpWwwW3Org20_8// "http://www.w3.org/2000/09/xmldsig#rsa-s"...
0xa369  ldc.i4.5
0xa36a  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0xa36f  brfalse.s loc_A373
0xa371  ldc.i4.0
0xa372  ret
0xa373  ldarg.2
0xa374  callvirt instance void [mscorlib]System.Action::Invoke()
0xa379  ldc.i4.4
0xa37a  ret
```
