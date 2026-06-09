# SecureBootGetCertHash(uchar *,ulong,uchar * *,ulong *)

- ea: `0x18003969c`
- end: `0x18003970c`
- name: `?SecureBootGetCertHash@@YAJPEAEKPEAPEAEPEAK@Z`
- size: `112`
- prototype: `__int64 __fastcall(BYTE *pbCertEncoded, DWORD cbCertEncoded, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800397d0`

## callees

- `0x18003969c`
- `0x180039714`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800396ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800396ca`
- `CRYPT32!CertFreeCertificateContext` at `0x1800396f4`
- `CRYPT32!CertFreeCertificateContext` at `0x1800396f4`
- `CRYPT32!CertCreateCertificateContext` at `0x1800396bc`
- `CRYPT32!CertCreateCertificateContext` at `0x1800396bc`

## pseudocode

```c
__int64 __fastcall SecureBootGetCertHash(
        BYTE *pbCertEncoded,
        DWORD cbCertEncoded,
        unsigned __int8 **a3,
        unsigned int *a4)
{
  const CERT_CONTEXT *CertificateContext; // rax
  const CERT_CONTEXT *v7; // rdi
  signed int LastError; // eax
  unsigned int CertHashFromCertContext; // ebx

  CertificateContext = CertCreateCertificateContext(1u, pbCertEncoded, cbCertEncoded);
  v7 = CertificateContext;
  if ( CertificateContext )
  {
    CertHashFromCertContext = SecureBootGetCertHashFromCertContext(CertificateContext, a3, a4);
    CertFreeCertificateContext(v7);
  }
  else
  {
    LastError = GetLastError();
    CertHashFromCertContext = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return CertHashFromCertContext;
}

```

## disassembly

```asm
0x18003969c  mov     [rsp+arg_0], rbx
0x1800396a1  mov     [rsp+arg_8], rsi
0x1800396a6  push    rdi
0x1800396a7  sub     rsp, 20h
0x1800396ab  mov     rsi, r8
0x1800396ae  mov     rbx, r9
0x1800396b1  mov     r8d, edx; cbCertEncoded
0x1800396b4  mov     rdx, rcx; pbCertEncoded
0x1800396b7  mov     ecx, 1; dwCertEncodingType
0x1800396bc  call    cs:__imp_CertCreateCertificateContext
0x1800396c2  mov     rdi, rax
0x1800396c5  test    rax, rax
0x1800396c8  jnz     short loc_1800396E1
0x1800396ca  call    cs:__imp_GetLastError
0x1800396d0  mov     ebx, eax
0x1800396d2  test    eax, eax
0x1800396d4  jle     short loc_1800396FA
0x1800396d6  movzx   ebx, ax
0x1800396d9  or      ebx, 80070000h
0x1800396df  jmp     short loc_1800396FA
0x1800396e1  mov     r8, rbx; unsigned int *
0x1800396e4  mov     rdx, rsi; unsigned __int8 **
0x1800396e7  mov     rcx, rdi; pCertContext
0x1800396ea  call    ?SecureBootGetCertHashFromCertContext@@YAJPEBU_CERT_CONTEXT@@PEAPEAEPEAK@Z; SecureBootGetCertHashFromCertContext(_CERT_CONTEXT const *,uchar * *,ulong *)
0x1800396ef  mov     ebx, eax
0x1800396f1  mov     rcx, rdi; pCertContext
0x1800396f4  call    cs:__imp_CertFreeCertificateContext
0x1800396fa  mov     rsi, [rsp+28h+arg_8]
0x1800396ff  mov     eax, ebx
0x180039701  mov     rbx, [rsp+28h+arg_0]
0x180039706  add     rsp, 20h
0x18003970a  pop     rdi
0x18003970b  retn
```
