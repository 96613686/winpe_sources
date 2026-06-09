# System.Deployment.Internal.CodeSigning.ManifestUtilities::GetSignatureMethodUri

- ea: `0xa3b0`
- end: `0xa3eb`
- name: `System.Deployment.Internal.CodeSigning.ManifestUtilities::GetSignatureMethodUri`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x7e60`

## callees

- `0xa3b0`

## string_xrefs

- `0xa3c9`: `http://www.w3.org/2000/09/xmldsig#rsa-sha512`
- `0xa3cf`: `http://www.w3.org/2000/09/xmldsig#rsa-sha384`
- `0xa3d5`: `http://www.w3.org/2000/09/xmldsig#rsa-sha256`
- `0xa3de`: `http://www.w3.org/2000/09/xmldsig#rsa-sha1`

## pseudocode

```c

```

## disassembly

```asm
0xa3b0  ldarg.1
0xa3b1  brfalse.s loc_A3DB
0xa3b3  ldarg.0
0xa3b4  ldc.i4.1
0xa3b5  sub
0xa3b6  switch   loc_A3D5, loc_A3CF, loc_A3C9
0xa3c7  br.s     loc_A3E4
0xa3c9  ldstr    aHttpWwwW3Org20_2// "http://www.w3.org/2000/09/xmldsig#rsa-s"...
0xa3ce  ret
0xa3cf  ldstr    aHttpWwwW3Org20_4// "http://www.w3.org/2000/09/xmldsig#rsa-s"...
0xa3d4  ret
0xa3d5  ldstr    aHttpWwwW3Org20_6// "http://www.w3.org/2000/09/xmldsig#rsa-s"...
0xa3da  ret
0xa3db  ldarg.0
0xa3dc  brtrue.s loc_A3E4
0xa3de  ldstr    aHttpWwwW3Org20_8// "http://www.w3.org/2000/09/xmldsig#rsa-s"...
0xa3e3  ret
0xa3e4  ldarg.2
0xa3e5  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0xa3ea  throw
```
