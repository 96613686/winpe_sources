# CertificateUtil::FindExtensionByOid(char const *,_CERT_CONTEXT const *)

- ea: `0x18000af7c`
- end: `0x18000afc9`
- name: `?FindExtensionByOid@CertificateUtil@@SAPEAU_CERT_EXTENSION@@PEBDPEBU_CERT_CONTEXT@@@Z`
- size: `77`
- prototype: `PCERT_EXTENSION __fastcall(const char *, const struct _CERT_CONTEXT *)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180007ef0`
- `0x180008950`
- `0x18001943c`

## callees

- `0x18000af7c`
- `0x18000b3c4`

## import_xrefs

- `CRYPT32!CertFindExtension` at `0x18000afc2`

## string_xrefs

- `0x18000af85`: `%s: FindExtensionByOid: pcszOid is NULL.`
- `0x18000af8c`: `CertificateUtil::FindExtensionByOid`
- `0x18000afa4`: `%s: FindExtensionByOid: pCertContext is NULL.`

## pseudocode

```c
PCERT_EXTENSION __fastcall CertificateUtil::FindExtensionByOid(const char *a1, const struct _CERT_CONTEXT *a2)
{
  if ( !a1 )
  {
    Logger::TraceError(L"%s: FindExtensionByOid: pcszOid is NULL.", L"CertificateUtil::FindExtensionByOid");
    return 0;
  }
  if ( !a2 )
  {
    Logger::TraceError(L"%s: FindExtensionByOid: pCertContext is NULL.", L"CertificateUtil::FindExtensionByOid");
    return 0;
  }
  return CertFindExtension(a1, a2->pCertInfo->cExtension, a2->pCertInfo->rgExtension);
}

```

## disassembly

```asm
0x18000af7c  sub     rsp, 28h
0x18000af80  test    rcx, rcx
0x18000af83  jnz     short loc_18000AF9F
0x18000af85  lea     rcx, aSFindextension; "%s: FindExtensionByOid: pcszOid is NULL"...
0x18000af8c  lea     rdx, aCertificateuti_1; "CertificateUtil::FindExtensionByOid"
0x18000af93  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000af98  xor     eax, eax
0x18000af9a  add     rsp, 28h
0x18000af9e  retn
0x18000af9f  test    rdx, rdx
0x18000afa2  jnz     short loc_18000AFAD
0x18000afa4  lea     rcx, aSFindextension_0; "%s: FindExtensionByOid: pCertContext is"...
0x18000afab  jmp     short loc_18000AF8C
0x18000afad  mov     rdx, [rdx+18h]
0x18000afb1  mov     r8, [rdx+0C8h]
0x18000afb8  mov     edx, [rdx+0C0h]
0x18000afbe  add     rsp, 28h
0x18000afc2  jmp     cs:__imp_CertFindExtension
```
