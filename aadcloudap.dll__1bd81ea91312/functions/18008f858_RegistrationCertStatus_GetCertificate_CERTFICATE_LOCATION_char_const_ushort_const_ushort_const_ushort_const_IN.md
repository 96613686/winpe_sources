# RegistrationCertStatus::GetCertificate(_CERTFICATE_LOCATION,char const *,ushort const *,ushort const *,ushort const *,INFO_KIND,_CERT_CONTEXT const * *)

- ea: `0x18008f858`
- end: `0x18008fa79`
- name: `?GetCertificate@RegistrationCertStatus@@CAJW4_CERTFICATE_LOCATION@@PEBDPEBG22W4INFO_KIND@@PEAPEBU_CERT_CONTEXT@@@Z`
- size: `545`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800903f0`

## callees

- `0x180003c20`
- `0x18008a300`
- `0x18008a340`
- `0x18008aa28`
- `0x18008aa9c`
- `0x18008aecc`
- `0x18008f858`
- `0x18008fa80`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008fa11`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008fa31`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008fa11`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008fa31`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18008f968`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18008f968`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18008f990`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18008f990`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18008fa1a`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18008fa1a`

## pseudocode

```c
__int64 __fastcall RegistrationCertStatus::GetCertificate(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        PCCERT_CONTEXT *a7)
{
  const struct _CERT_CONTEXT **v7; // r15
  unsigned int v8; // r12d
  unsigned int v9; // r13d
  int Certificates; // eax
  __int64 v11; // rbx
  const struct _CERT_CONTEXT *v12; // rax
  const struct _CERT_CONTEXT *v13; // rcx
  const wchar_t *v14; // rdi
  const struct _CERT_CONTEXT ***v16; // [rsp+28h] [rbp-58h]
  void **p_Block; // [rsp+30h] [rbp-50h]
  void *Block; // [rsp+50h] [rbp-30h] BYREF
  const struct _CERT_CONTEXT **v19; // [rsp+58h] [rbp-28h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+60h] [rbp-20h] BYREF

  v7 = 0;
  v8 = 0;
  v19 = 0;
  LODWORD(Block) = 0;
  SystemTime = 0;
  if ( !a7 )
  {
    v9 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"RegistrationCertStatus::GetCertificate", L"ppCertContext");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"RegistrationCertStatus::GetCertificate", L"ppCertContext");
    goto LABEL_18;
  }
  *a7 = 0;
  p_Block = &Block;
  v16 = &v19;
  Certificates = RegistrationCertStatus::GetCertificates(a1, a2, a3);
  v9 = Certificates;
  if ( Certificates < 0 )
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"RegistrationCertStatus::GetCertificate",
      L"RegistrationCertStatus::GetCertificates",
      (unsigned int)Certificates,
      0,
      &v19,
      &Block);
    v7 = v19;
    v8 = (unsigned int)Block;
    goto LABEL_18;
  }
  v8 = (unsigned int)Block;
  v7 = v19;
  if ( (_DWORD)Block != 1 )
  {
    v11 = 0;
    if ( !(_DWORD)Block )
      goto LABEL_13;
    while ( 1 )
    {
      v12 = v7[v11];
      if ( !*a7 )
        goto LABEL_11;
      if ( CompareFileTime(&v12->pCertInfo->NotBefore, &(*a7)->pCertInfo->NotBefore) == -1 )
        break;
LABEL_12:
      v11 = (unsigned int)(v11 + 1);
      if ( (unsigned int)v11 >= v8 )
        goto LABEL_13;
    }
    v12 = v7[v11];
LABEL_11:
    *a7 = v12;
    goto LABEL_12;
  }
  v9 = 0;
  *a7 = *v19;
LABEL_13:
  if ( FileTimeToSystemTime(&(*a7)->pCertInfo->NotBefore, &SystemTime) )
  {
    v13 = *a7;
    Block = 0;
    CertificateUtil::GetCertificateThumbprint(v13, (unsigned __int16 **)&Block);
    v14 = L"N/A";
    if ( Block )
      v14 = (const wchar_t *)Block;
    LODWORD(p_Block) = SystemTime.wMinute;
    LODWORD(v16) = SystemTime.wHour;
    Logger::TraceVerbose(
      L"%s: Returning certificate with UTC timestamp (YYYY-MM-DD HH:MM:SS.sss) %04u-%02u-%02u %02u:%02u:%02u.%03u and thumbprint %s",
      L"RegistrationCertStatus::GetCertificate",
      SystemTime.wYear,
      SystemTime.wMonth,
      SystemTime.wDay,
      v16,
      p_Block,
      SystemTime.wSecond,
      SystemTime.wMilliseconds,
      v14);
    free(Block);
  }
  *a7 = CertDuplicateCertificateContext(*a7);
LABEL_18:
  CertificateUtil::FreeCertificates(v7, v8);
  free(v7);
  Logger::TraceVerbose(L"%s - hr: 0x%08x", L"RegistrationCertStatus::GetCertificate", v9);
  return v9;
}

```

## disassembly

```asm
0x18008f858  mov     [rsp-28h+arg_8], rbx
0x18008f85d  mov     [rsp-28h+arg_18], rdi
0x18008f862  push    rbp
0x18008f863  push    r12
0x18008f865  push    r13
0x18008f867  push    r14
0x18008f869  push    r15
0x18008f86b  mov     rbp, rsp
0x18008f86e  sub     rsp, 80h
0x18008f875  mov     rax, cs:__security_cookie
0x18008f87c  xor     rax, rsp
0x18008f87f  mov     [rbp+var_10], rax
0x18008f883  mov     r14, [rbp+arg_30]
0x18008f887  xor     r15d, r15d
0x18008f88a  xor     r12d, r12d
0x18008f88d  mov     [rbp+var_28], r15
0x18008f891  mov     dword ptr [rbp+Block], r12d
0x18008f895  xorps   xmm0, xmm0
0x18008f898  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x18008f89c  test    r14, r14
0x18008f89f  jnz     short loc_18008F8D9
0x18008f8a1  lea     r8, aPpcertcontext; "ppCertContext"
0x18008f8a8  mov     r13d, 80070057h
0x18008f8ae  lea     rdx, aRegistrationce_5; "RegistrationCertStatus::GetCertificate"
0x18008f8b5  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18008f8bc  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008f8c1  lea     rdx, aPpcertcontext; "ppCertContext"
0x18008f8c8  lea     rcx, aRegistrationce_5; "RegistrationCertStatus::GetCertificate"
0x18008f8cf  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18008f8d4  jmp     loc_18008FA23
0x18008f8d9  lea     rax, [rbp+Block]
0x18008f8dd  mov     [r14], r12
0x18008f8e0  mov     [rsp+80h+var_50], rax
0x18008f8e5  xor     r9d, r9d
0x18008f8e8  lea     rax, [rbp+var_28]
0x18008f8ec  mov     [rsp+80h+var_58], rax
0x18008f8f1  mov     [rsp+80h+var_60], r12
0x18008f8f6  call    ?GetCertificates@RegistrationCertStatus@@CAJW4_CERTFICATE_LOCATION@@PEBDPEBG22PEAPEAPEBU_CERT_CONTEXT@@PEAK@Z; RegistrationCertStatus::GetCertificates(_CERTFICATE_LOCATION,char const *,ushort const *,ushort const *,ushort const *,_CERT_CONTEXT const * * *,ulong *)
0x18008f8fb  mov     r13d, eax
0x18008f8fe  test    eax, eax
0x18008f900  jns     short loc_18008F92C
0x18008f902  mov     r9d, eax
0x18008f905  lea     r8, aRegistrationce_6; "RegistrationCertStatus::GetCertificates"
0x18008f90c  lea     rdx, aRegistrationce_5; "RegistrationCertStatus::GetCertificate"
0x18008f913  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18008f91a  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008f91f  mov     r15, [rbp+var_28]
0x18008f923  mov     r12d, dword ptr [rbp+Block]
0x18008f927  jmp     loc_18008FA23
0x18008f92c  mov     r12d, dword ptr [rbp+Block]
0x18008f930  mov     r15, [rbp+var_28]
0x18008f934  cmp     r12d, 1
0x18008f938  jnz     short loc_18008F945
0x18008f93a  mov     rax, [r15]
0x18008f93d  xor     r13d, r13d
0x18008f940  mov     [r14], rax
0x18008f943  jmp     short loc_18008F981
0x18008f945  xor     ebx, ebx
0x18008f947  test    r12d, r12d
0x18008f94a  jz      short loc_18008F981
0x18008f94c  mov     rdx, [r14]
0x18008f94f  mov     rax, [r15+rbx*8]
0x18008f953  test    rdx, rdx
0x18008f956  jz      short loc_18008F977
0x18008f958  mov     rdx, [rdx+18h]
0x18008f95c  mov     rcx, [rax+18h]
0x18008f960  add     rdx, 40h ; '@'; lpFileTime2
0x18008f964  add     rcx, 40h ; '@'; lpFileTime1
0x18008f968  call    cs:__imp_CompareFileTime
0x18008f96e  cmp     eax, 0FFFFFFFFh
0x18008f971  jnz     short loc_18008F97A
0x18008f973  mov     rax, [r15+rbx*8]
0x18008f977  mov     [r14], rax
0x18008f97a  inc     ebx
0x18008f97c  cmp     ebx, r12d
0x18008f97f  jb      short loc_18008F94C
0x18008f981  mov     rax, [r14]
0x18008f984  lea     rdx, [rbp+SystemTime]; lpSystemTime
0x18008f988  mov     rcx, [rax+18h]
0x18008f98c  add     rcx, 40h ; '@'; lpFileTime
0x18008f990  call    cs:__imp_FileTimeToSystemTime
0x18008f996  test    eax, eax
0x18008f998  jz      short loc_18008FA17
0x18008f99a  mov     rcx, [r14]; struct _CERT_CONTEXT *
0x18008f99d  lea     rdx, [rbp+Block]; unsigned __int16 **
0x18008f9a1  mov     [rbp+Block], 0
0x18008f9a9  call    ?GetCertificateThumbprint@CertificateUtil@@SAJPEBU_CERT_CONTEXT@@PEAPEAG@Z; CertificateUtil::GetCertificateThumbprint(_CERT_CONTEXT const *,ushort * *)
0x18008f9ae  movzx   edx, [rbp+SystemTime.wSecond]
0x18008f9b2  lea     rdi, aNA; "N/A"
0x18008f9b9  movzx   eax, [rbp+SystemTime.wMilliseconds]
0x18008f9bd  lea     rcx, aSReturningCert; "%s: Returning certificate with UTC time"...
0x18008f9c4  movzx   r10d, [rbp+SystemTime.wMinute]
0x18008f9c9  movzx   r11d, [rbp+SystemTime.wHour]
0x18008f9ce  movzx   ebx, [rbp+SystemTime.wDay]
0x18008f9d2  cmp     [rbp+Block], 0
0x18008f9d7  movzx   r9d, [rbp+SystemTime.wMonth]
0x18008f9dc  cmovnz  rdi, [rbp+Block]
0x18008f9e1  movzx   r8d, [rbp+SystemTime.wYear]
0x18008f9e6  mov     [rsp+80h+var_38], rdi
0x18008f9eb  mov     [rsp+80h+var_40], eax
0x18008f9ef  mov     [rsp+80h+var_48], edx
0x18008f9f3  lea     rdx, aRegistrationce_5; "RegistrationCertStatus::GetCertificate"
0x18008f9fa  mov     dword ptr [rsp+80h+var_50], r10d
0x18008f9ff  mov     dword ptr [rsp+80h+var_58], r11d
0x18008fa04  mov     dword ptr [rsp+80h+var_60], ebx
0x18008fa08  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18008fa0d  mov     rcx, [rbp+Block]; Block
0x18008fa11  call    cs:__imp_free
0x18008fa17  mov     rcx, [r14]; pCertContext
0x18008fa1a  call    cs:__imp_CertDuplicateCertificateContext
0x18008fa20  mov     [r14], rax
0x18008fa23  mov     edx, r12d; unsigned int
0x18008fa26  mov     rcx, r15; struct _CERT_CONTEXT **
0x18008fa29  call    ?FreeCertificates@CertificateUtil@@SAXQEAPEBU_CERT_CONTEXT@@K@Z; CertificateUtil::FreeCertificates(_CERT_CONTEXT const * * const,ulong)
0x18008fa2e  mov     rcx, r15; Block
0x18008fa31  call    cs:__imp_free
0x18008fa37  mov     r8d, r13d
0x18008fa3a  lea     rdx, aRegistrationce_5; "RegistrationCertStatus::GetCertificate"
0x18008fa41  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x18008fa48  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18008fa4d  mov     eax, r13d
0x18008fa50  mov     rcx, [rbp+var_10]
0x18008fa54  xor     rcx, rsp; StackCookie
0x18008fa57  call    __security_check_cookie
0x18008fa5c  lea     r11, [rsp+80h+var_s0]
0x18008fa64  mov     rbx, [r11+38h]
0x18008fa68  mov     rdi, [r11+48h]
0x18008fa6c  mov     rsp, r11
0x18008fa6f  pop     r15
0x18008fa71  pop     r14
0x18008fa73  pop     r13
0x18008fa75  pop     r12
0x18008fa77  pop     rbp
0x18008fa78  retn
```
