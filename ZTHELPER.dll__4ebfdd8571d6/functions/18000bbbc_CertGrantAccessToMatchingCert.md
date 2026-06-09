# CertGrantAccessToMatchingCert

- ea: `0x18000bbbc`
- end: `0x18000bc49`
- name: `CertGrantAccessToMatchingCert`
- size: `141`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000c788`

## callees

- `0x18000bb18`
- `0x18000bbbc`
- `0x18000c8a8`
- `0x180015008`

## import_xrefs

- `CRYPT32!CertFreeCertificateContext` at `0x18000bc3b`
- `CRYPT32!CertFreeCertificateContext` at `0x18000bc3b`

## pseudocode

```c
__int64 __fastcall CertGrantAccessToMatchingCert(__int64 a1, __int64 a2)
{
  unsigned int v2; // ebx
  unsigned int MatchingCert; // eax
  __int64 v4; // rdx
  PCCERT_CONTEXT pCertContext; // [rsp+30h] [rbp+8h] BYREF

  pCertContext = 0;
  if ( !a1 || !a2 )
    return 87;
  MatchingCert = CertGetMatchingCert(a1, a2, &pCertContext);
  v2 = MatchingCert;
  if ( MatchingCert )
  {
    if ( (BYTE1(xmmword_18001F260) & 8) == 0 )
      goto LABEL_11;
    v4 = 51;
    goto LABEL_10;
  }
  MatchingCert = DnsGrantZtAccessToPrivateKey(pCertContext);
  v2 = MatchingCert;
  if ( MatchingCert && (BYTE1(xmmword_18001F260) & 8) != 0 )
  {
    v4 = 52;
LABEL_10:
    WPP_SF_d(1035, v4, WPP_1219e5a01a7b35ba4ff18a9e20aca908_Traceguids, MatchingCert);
  }
LABEL_11:
  if ( pCertContext )
    CertFreeCertificateContext(pCertContext);
  return v2;
}

```

## disassembly

```asm
0x18000bbbc  push    rbx
0x18000bbbe  sub     rsp, 20h
0x18000bbc2  mov     [rsp+28h+pCertContext], 0
0x18000bbcb  test    rcx, rcx
0x18000bbce  jnz     short loc_18000BBD7
0x18000bbd0  mov     ebx, 57h ; 'W'
0x18000bbd5  jmp     short loc_18000BC41
0x18000bbd7  test    rdx, rdx
0x18000bbda  jz      short loc_18000BBD0
0x18000bbdc  lea     r8, [rsp+28h+pCertContext]
0x18000bbe1  call    CertGetMatchingCert
0x18000bbe6  mov     ebx, eax
0x18000bbe8  test    eax, eax
0x18000bbea  jnz     short loc_18000BC0C
0x18000bbec  mov     rcx, [rsp+28h+pCertContext]
0x18000bbf1  call    DnsGrantZtAccessToPrivateKey
0x18000bbf6  mov     ebx, eax
0x18000bbf8  test    eax, eax
0x18000bbfa  jz      short loc_18000BC2E
0x18000bbfc  test    byte ptr cs:xmmword_18001F260+1, 8
0x18000bc03  jz      short loc_18000BC2E
0x18000bc05  mov     edx, 34h ; '4'
0x18000bc0a  jmp     short loc_18000BC1A
0x18000bc0c  test    byte ptr cs:xmmword_18001F260+1, 8
0x18000bc13  jz      short loc_18000BC2E
0x18000bc15  mov     edx, 33h ; '3'
0x18000bc1a  mov     r9d, eax
0x18000bc1d  lea     r8, WPP_1219e5a01a7b35ba4ff18a9e20aca908_Traceguids
0x18000bc24  mov     ecx, 40Bh
0x18000bc29  call    WPP_SF_d
0x18000bc2e  cmp     [rsp+28h+pCertContext], 0
0x18000bc34  jz      short loc_18000BC41
0x18000bc36  mov     rcx, [rsp+28h+pCertContext]; pCertContext
0x18000bc3b  call    cs:__imp_CertFreeCertificateContext
0x18000bc41  mov     eax, ebx
0x18000bc43  add     rsp, 20h
0x18000bc47  pop     rbx
0x18000bc48  retn
```
