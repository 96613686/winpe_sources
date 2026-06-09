# EkCertificate::EkCertificate(std::vector<uchar,std::allocator<uchar>> const &)

- ea: `0x18005a2c8`
- end: `0x18005a83e`
- name: `??0EkCertificate@@QEAA@AEBV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `1398`
- prototype: `__int64 *__fastcall(__int64 *, __int64)`
- caller_count: `4`
- callee_count: `11`
- tags: `registry_config, loader_planting`

## callers

- `0x1800ad28c`
- `0x1800ad2d8`
- `0x1800ad4c0`
- `0x1800add5c`

## callees

- `0x180028900`
- `0x18002da38`
- `0x180049c40`
- `0x18005a198`
- `0x18005a2c8`
- `0x18005a844`
- `0x18008f398`
- `0x1800ad614`
- `0x1800adfcc`
- `0x1800ae078`
- `0x1800c40e4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005a648`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005a6ec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005a648`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005a6ec`
- `CRYPT32!CertGetNameStringW` at `0x18005a714`
- `CRYPT32!CertGetNameStringW` at `0x18005a767`
- `CRYPT32!CertGetNameStringW` at `0x18005a79e`
- `CRYPT32!CertGetNameStringW` at `0x18005a7d4`
- `CRYPT32!CertGetNameStringW` at `0x18005a714`
- `CRYPT32!CertGetNameStringW` at `0x18005a767`
- `CRYPT32!CertGetNameStringW` at `0x18005a79e`
- `CRYPT32!CertGetNameStringW` at `0x18005a7d4`
- `CRYPT32!CryptDecodeObject` at `0x18005a4fe`
- `CRYPT32!CryptDecodeObject` at `0x18005a608`
- `CRYPT32!CryptDecodeObject` at `0x18005a6ac`
- `CRYPT32!CryptDecodeObject` at `0x18005a4fe`
- `CRYPT32!CryptDecodeObject` at `0x18005a608`
- `CRYPT32!CryptDecodeObject` at `0x18005a6ac`
- `CRYPT32!CertFindExtension` at `0x18005a5c7`
- `CRYPT32!CertFindExtension` at `0x18005a669`
- `CRYPT32!CertFindExtension` at `0x18005a5c7`
- `CRYPT32!CertFindExtension` at `0x18005a669`
- `CRYPT32!CertCreateCertificateContext` at `0x18005a3f9`
- `CRYPT32!CertCreateCertificateContext` at `0x18005a3f9`
- `CRYPT32!CryptDecodeObjectEx` at `0x18005a3c4`
- `CRYPT32!CryptDecodeObjectEx` at `0x18005a3c4`

## pseudocode

```c
__int64 *__fastcall EkCertificate::EkCertificate(__int64 *a1, __int64 a2)
{
  WCHAR *v4; // r15
  WCHAR *v5; // r14
  unsigned int v6; // eax
  const char *v7; // r9
  __int64 v8; // r13
  const char *v9; // rbx
  char *v10; // rbx
  PCERT_EXTENSION Extension; // rax
  const char *v12; // r9
  char *v13; // rbx
  PCERT_EXTENSION v14; // rax
  const char *v15; // r9
  char *v16; // rbx
  DWORD NameStringW; // eax
  DWORD v18; // eax
  __int64 v19; // rbx
  int dwFlags; // [rsp+20h] [rbp-28h]
  int dwFlagsa; // [rsp+20h] [rbp-28h]
  int dwFlagsb; // [rsp+20h] [rbp-28h]
  int dwFlagsc; // [rsp+20h] [rbp-28h]
  const char *pDecodePara; // [rsp+28h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+40h]
  PCCERT_CONTEXT pcbStructInfo; // [rsp+98h] [rbp+50h] BYREF
  char *Str1; // [rsp+A0h] [rbp+58h] BYREF
  char *v29; // [rsp+A8h] [rbp+60h]

  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  a1[3] = 0;
  a1[4] = 0;
  a1[5] = 0;
  a1[6] = 0;
  a1[7] = 0;
  a1[8] = 0;
  a1[9] = 0;
  a1[10] = 0;
  a1[11] = 0;
  a1[12] = 0;
  v4 = (WCHAR *)(a1 + 13);
  *(_OWORD *)(a1 + 13) = 0;
  a1[15] = 0;
  a1[16] = 7;
  *((_WORD *)a1 + 52) = 0;
  v5 = (WCHAR *)(a1 + 17);
  *(_OWORD *)(a1 + 17) = 0;
  a1[19] = 0;
  a1[20] = 7;
  *((_WORD *)a1 + 68) = 0;
  *((_DWORD *)a1 + 42) = 2162688;
  if ( *(_QWORD *)a2 == *(_QWORD *)(a2 + 8) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x11D,
      (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\ekcert.cpp",
      (const char *)0x80070057LL,
      dwFlags);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AMD_P384_EK_Cert>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AMD_P384_EK_Cert>::GetImpl'::`2'::impl) )
  {
    LODWORD(pcbStructInfo) = 0;
    v6 = CryptDecodeObjectEx(
           0x10001u,
           (LPCSTR)1,
           *(const BYTE **)a2,
           *(_DWORD *)(a2 + 8) - *(_DWORD *)a2,
           0,
           0,
           0,
           (DWORD *)&pcbStructInfo);
    wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
      retaddr,
      (void *)0x12C,
      (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\ekcert.cpp",
      (const char *)v6,
      (int)"EK Certificate decoding error.",
      pDecodePara);
  }
  pcbStructInfo = CertCreateCertificateContext(0x10001u, *(const BYTE **)a2, *(_DWORD *)(a2 + 8) - *(_DWORD *)a2);
  wil::unique_any_t<wil::cert_context_t>::operator=(a1, &pcbStructInfo);
  wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&pcbStructInfo);
  if ( !*a1 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x134,
      (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\ekcert.cpp",
      v7);
  if ( !*(_DWORD *)(*(_QWORD *)(*a1 + 24) + 192LL) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x137,
      (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\ekcert.cpp",
      (const char *)0x800B0108LL,
      dwFlags);
  std::vector<unsigned char>::operator=(a1 + 10, a2);
  v8 = *a1;
  v9 = *(const char **)(*(_QWORD *)(*a1 + 24) + 96LL);
  if ( !strncmp_0(v9, "1.2.840.113549", 0xEu) )
  {
    *((_DWORD *)a1 + 42) = 1;
    goto LABEL_22;
  }
  if ( strncmp_0(v9, "1.2.840.10045.2.1", 0x11u) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x170,
      (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\ekcert.cpp",
      (const char *)0x80091002LL,
      dwFlags);
  *((_WORD *)a1 + 84) = 35;
  Str1 = 0;
  LODWORD(pcbStructInfo) = 8;
  if ( !CryptDecodeObject(
          0x10001u,
          *(LPCSTR *)(*(_QWORD *)(v8 + 24) + 96LL),
          *(const BYTE **)(*(_QWORD *)(v8 + 24) + 112LL),
          *(_DWORD *)(*(_QWORD *)(v8 + 24) + 104LL),
          4u,
          &Str1,
          (DWORD *)&pcbStructInfo) )
    goto LABEL_21;
  v10 = Str1;
  if ( !strncmp_0(Str1, "1.2.840.10045.3.1.7", 0x14u) )
  {
    *((_WORD *)a1 + 85) = 3;
    goto LABEL_22;
  }
  if ( !strncmp_0(v10, "1.3.132.0.34", 0xDu) )
  {
    *((_WORD *)a1 + 85) = 4;
    goto LABEL_22;
  }
  if ( !strncmp_0(v10, "1.3.132.0.35", 0xDu) )
  {
    *((_WORD *)a1 + 85) = 5;
    goto LABEL_22;
  }
  if ( !strncmp_0(v10, "1.2.156.10197.1.301", 0x14u) )
    *((_WORD *)a1 + 85) = 32;
  else
LABEL_21:
    *((_WORD *)a1 + 85) = 33;
LABEL_22:
  Extension = CertFindExtension(
                "2.5.29.35",
                *(_DWORD *)(*(_QWORD *)(*a1 + 24) + 192LL),
                *(CERT_EXTENSION **)(*(_QWORD *)(*a1 + 24) + 200LL));
  if ( Extension )
  {
    Str1 = 0;
    v29 = 0;
    LODWORD(pcbStructInfo) = 0;
    if ( !CryptDecodeObject(
            1u,
            (LPCSTR)0x1F,
            Extension->Value.pbData,
            Extension->Value.cbData,
            0x8001u,
            &Str1,
            (DWORD *)&pcbStructInfo) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x189,
        (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\ekcert.cpp",
        v12);
    v13 = Str1;
    v29 = Str1;
    std::vector<unsigned char>::assign<unsigned char *,0>(
      a1 + 1,
      *((_QWORD *)Str1 + 1),
      *((_QWORD *)Str1 + 1) + *(unsigned int *)Str1);
    if ( v13 )
      LocalFree(v13);
  }
  v14 = CertFindExtension(
          "2.5.29.14",
          *(_DWORD *)(*(_QWORD *)(*a1 + 24) + 192LL),
          *(CERT_EXTENSION **)(*(_QWORD *)(*a1 + 24) + 200LL));
  if ( v14 )
  {
    Str1 = 0;
    v29 = 0;
    LODWORD(pcbStructInfo) = 0;
    if ( !CryptDecodeObject(
            1u,
            "2.5.29.14",
            v14->Value.pbData,
            v14->Value.cbData,
            0x8001u,
            &Str1,
            (DWORD *)&pcbStructInfo) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x1A6,
        (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\ekcert.cpp",
        v15);
    v16 = Str1;
    v29 = Str1;
    std::vector<unsigned char>::assign<unsigned char *,0>(
      a1 + 4,
      *((_QWORD *)Str1 + 1),
      *((_QWORD *)Str1 + 1) + *(unsigned int *)Str1);
    if ( v16 )
      LocalFree(v16);
  }
  NameStringW = CertGetNameStringW((PCCERT_CONTEXT)*a1, 4u, 1u, "2.5.4.3", 0, 0);
  if ( NameStringW < 2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1B8,
      (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\ekcert.cpp",
      (const char *)0x800B0108LL,
      dwFlagsa);
  std::wstring::resize(v4, NameStringW);
  if ( *((_QWORD *)v4 + 3) > 7u )
    v4 = *(WCHAR **)v4;
  v18 = CertGetNameStringW((PCCERT_CONTEXT)*a1, 4u, 1u, "2.5.4.3", v4, *((_DWORD *)a1 + 30));
  if ( v18 < 2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\ekcert.cpp",
      (const char *)0x800B0108LL,
      dwFlagsb);
  v19 = CertGetNameStringW((PCCERT_CONTEXT)*a1, 4u, 0, "2.5.4.3", 0, v18);
  std::wstring::resize(v5, v19);
  if ( *((_QWORD *)v5 + 3) > 7u )
    v5 = *(WCHAR **)v5;
  if ( CertGetNameStringW((PCCERT_CONTEXT)*a1, 4u, 0, "2.5.4.3", v5, v19) < 2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1D5,
      (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\ekcert.cpp",
      (const char *)0x800B0108LL,
      dwFlagsc);
  std::vector<unsigned char>::assign<unsigned char *,0>(
    a1 + 7,
    *(_QWORD *)(*(_QWORD *)(*a1 + 24) + 16LL),
    *(_QWORD *)(*(_QWORD *)(*a1 + 24) + 16LL) + *(unsigned int *)(*(_QWORD *)(*a1 + 24) + 8LL));
  return a1;
}

```

## disassembly

```asm
0x18005a2c8  mov     [rsp-40h+arg_0], rcx
0x18005a2cd  push    rbp
0x18005a2ce  push    rbx
0x18005a2cf  push    rsi
0x18005a2d0  push    rdi
0x18005a2d1  push    r12
0x18005a2d3  push    r13
0x18005a2d5  push    r14
0x18005a2d7  push    r15
0x18005a2d9  mov     rbp, rsp
0x18005a2dc  sub     rsp, 48h
0x18005a2e0  mov     rbx, rdx
0x18005a2e3  mov     rdi, rcx
0x18005a2e6  xor     r13d, r13d
0x18005a2e9  mov     [rcx], r13
0x18005a2ec  mov     [rcx+8], r13
0x18005a2f0  mov     [rcx+10h], r13
0x18005a2f4  mov     [rcx+18h], r13
0x18005a2f8  mov     [rcx+20h], r13
0x18005a2fc  mov     [rcx+28h], r13
0x18005a300  mov     [rcx+30h], r13
0x18005a304  mov     [rcx+38h], r13
0x18005a308  mov     [rcx+40h], r13
0x18005a30c  mov     [rcx+48h], r13
0x18005a310  mov     [rcx+50h], r13
0x18005a314  mov     [rcx+58h], r13
0x18005a318  mov     [rcx+60h], r13
0x18005a31c  lea     r15, [rcx+68h]
0x18005a320  xorps   xmm0, xmm0
0x18005a323  movups  xmmword ptr [r15], xmm0
0x18005a327  mov     [r15+10h], r13
0x18005a32b  lea     ecx, [r13+7]
0x18005a32f  mov     [r15+18h], rcx
0x18005a333  mov     [r15], r13w
0x18005a337  lea     r14, [rdi+88h]
0x18005a33e  movups  xmmword ptr [r14], xmm0
0x18005a342  mov     [r14+10h], r13
0x18005a346  mov     [r14+18h], rcx
0x18005a34a  mov     [r14], r13w
0x18005a34e  mov     dword ptr [rdi+0A8h], 210000h
0x18005a358  mov     rcx, [rbp+40h]; this
0x18005a35c  mov     rax, [rdx+8]
0x18005a360  cmp     [rdx], rax
0x18005a363  jnz     short loc_18005A37D
0x18005a365  mov     r9d, 80070057h; char *
0x18005a36b  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\tpmhli\\lib\\ekce"...
0x18005a372  mov     edx, 11Dh; void *
0x18005a377  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005a37d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AMD_P384_EK_Cert@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AMD_P384_EK_Cert@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AMD_P384_EK_Cert> `wil::Feature<__WilFeatureTraits_Feature_AMD_P384_EK_Cert>::GetImpl(void)'::`2'::impl
0x18005a384  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AMD_P384_EK_Cert@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AMD_P384_EK_Cert>::__private_IsEnabled(void)
0x18005a389  lea     rsi, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\tpmhli\\lib\\ekce"...
0x18005a390  test    al, al
0x18005a392  jz      short loc_18005A3EA
0x18005a394  mov     dword ptr [rbp+arg_8], r13d
0x18005a398  mov     r9d, [rbx+8]
0x18005a39c  sub     r9d, [rbx]; cbEncoded
0x18005a39f  lea     rax, [rbp+arg_8]
0x18005a3a3  mov     [rsp+48h+pcbStructInfo], rax; pcbStructInfo
0x18005a3a8  mov     [rsp+48h+pvStructInfo], r13; pvStructInfo
0x18005a3ad  mov     [rsp+48h+pDecodePara], r13; char *
0x18005a3b2  mov     [rsp+48h+dwFlags], r13d; dwFlags
0x18005a3b7  mov     r8, [rbx]; pbEncoded
0x18005a3ba  mov     edx, 1; lpszStructType
0x18005a3bf  mov     ecx, 10001h; dwCertEncodingType
0x18005a3c4  call    cs:__imp_CryptDecodeObjectEx
0x18005a3ca  mov     rcx, [rbp+40h]; this
0x18005a3ce  lea     rdx, aEkCertificateD; "EK Certificate decoding error."
0x18005a3d5  mov     qword ptr [rsp+48h+dwFlags], rdx; int
0x18005a3da  mov     r9d, eax; char *
0x18005a3dd  mov     r8, rsi; unsigned int
0x18005a3e0  mov     edx, 12Ch; void *
0x18005a3e5  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x18005a3ea  mov     r8d, [rbx+8]
0x18005a3ee  sub     r8d, [rbx]; cbCertEncoded
0x18005a3f1  mov     rdx, [rbx]; pbCertEncoded
0x18005a3f4  mov     ecx, 10001h; dwCertEncodingType
0x18005a3f9  call    cs:__imp_CertCreateCertificateContext
0x18005a3ff  mov     [rbp+arg_8], rax
0x18005a403  lea     rdx, [rbp+arg_8]
0x18005a407  mov     rcx, rdi
0x18005a40a  call    ??4?$unique_any_t@Ucert_context_t@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::cert_context_t>::operator=(wil::unique_any_t<wil::cert_context_t> &&)
0x18005a40f  lea     rcx, [rbp+arg_8]
0x18005a413  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x18005a418  mov     rax, [rdi]
0x18005a41b  mov     rcx, [rbp+40h]; this
0x18005a41f  test    rax, rax
0x18005a422  jnz     short loc_18005A432
0x18005a424  mov     r8, rsi; unsigned int
0x18005a427  mov     edx, 134h; void *
0x18005a42c  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18005a432  mov     rcx, [rbp+40h]; this
0x18005a436  mov     rax, [rax+18h]
0x18005a43a  cmp     dword ptr [rax+0C0h], 1
0x18005a441  jnb     short loc_18005A457
0x18005a443  mov     r9d, 800B0108h; char *
0x18005a449  mov     r8, rsi; unsigned int
0x18005a44c  mov     edx, 137h; void *
0x18005a451  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005a457  mov     rdx, rbx
0x18005a45a  lea     rcx, [rdi+50h]
0x18005a45e  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> const &)
0x18005a463  mov     r13, [rdi]
0x18005a466  mov     rax, [r13+18h]
0x18005a46a  mov     rbx, [rax+60h]
0x18005a46e  mov     r8d, 0Eh; MaxCount
0x18005a474  lea     rdx, Str2; "1.2.840.113549"
0x18005a47b  mov     rcx, rbx; Str1
0x18005a47e  call    strncmp_0
0x18005a483  xor     r12d, r12d
0x18005a486  test    eax, eax
0x18005a488  jnz     short loc_18005A49B
0x18005a48a  lea     r13d, [r12+1]
0x18005a48f  mov     [rdi+0A8h], r13d
0x18005a496  jmp     loc_18005A5AC
0x18005a49b  mov     r8d, 11h; MaxCount
0x18005a4a1  lea     rdx, a128401004521; "1.2.840.10045.2.1"
0x18005a4a8  mov     rcx, rbx; Str1
0x18005a4ab  call    strncmp_0
0x18005a4b0  test    eax, eax
0x18005a4b2  jnz     loc_18005A826
0x18005a4b8  mov     word ptr [rdi+0A8h], 23h ; '#'
0x18005a4c1  mov     [rbp+Str1], r12
0x18005a4c5  mov     dword ptr [rbp+arg_8], 8
0x18005a4cc  mov     rdx, [r13+18h]
0x18005a4d0  lea     rax, [rbp+arg_8]
0x18005a4d4  mov     [rsp+48h+pvStructInfo], rax; pcbStructInfo
0x18005a4d9  lea     rax, [rbp+Str1]
0x18005a4dd  mov     [rsp+48h+pDecodePara], rax; pvStructInfo
0x18005a4e2  mov     r13d, 4
0x18005a4e8  mov     [rsp+48h+dwFlags], r13d; dwFlags
0x18005a4ed  mov     r9d, [rdx+68h]; cbEncoded
0x18005a4f1  mov     r8, [rdx+70h]; pbEncoded
0x18005a4f5  mov     rdx, [rdx+60h]; lpszStructType
0x18005a4f9  mov     ecx, 10001h; dwCertEncodingType
0x18005a4fe  call    cs:__imp_CryptDecodeObject
0x18005a504  test    eax, eax
0x18005a506  jz      loc_18005A59D
0x18005a50c  lea     r8d, [r13+10h]; MaxCount
0x18005a510  lea     rdx, a1284010045317; "1.2.840.10045.3.1.7"
0x18005a517  mov     rbx, [rbp+Str1]
0x18005a51b  mov     rcx, rbx; Str1
0x18005a51e  call    strncmp_0
0x18005a523  test    eax, eax
0x18005a525  jnz     short loc_18005A532
0x18005a527  mov     word ptr [rdi+0AAh], 3
0x18005a530  jmp     short loc_18005A5A6
0x18005a532  mov     r8d, 0Dh; MaxCount
0x18005a538  lea     rdx, a13132034; "1.3.132.0.34"
0x18005a53f  mov     rcx, rbx; Str1
0x18005a542  call    strncmp_0
0x18005a547  test    eax, eax
0x18005a549  jnz     short loc_18005A555
0x18005a54b  mov     [rdi+0AAh], r13w
0x18005a553  jmp     short loc_18005A5A6
0x18005a555  mov     r8d, 0Dh; MaxCount
0x18005a55b  lea     rdx, a13132035; "1.3.132.0.35"
0x18005a562  mov     rcx, rbx; Str1
0x18005a565  call    strncmp_0
0x18005a56a  test    eax, eax
0x18005a56c  jnz     short loc_18005A579
0x18005a56e  mov     word ptr [rdi+0AAh], 5
0x18005a577  jmp     short loc_18005A5A6
0x18005a579  mov     r8d, 14h; MaxCount
0x18005a57f  lea     rdx, a12156101971301; "1.2.156.10197.1.301"
0x18005a586  mov     rcx, rbx; Str1
0x18005a589  call    strncmp_0
0x18005a58e  test    eax, eax
0x18005a590  jnz     short loc_18005A59D
0x18005a592  mov     word ptr [rdi+0AAh], 20h ; ' '
0x18005a59b  jmp     short loc_18005A5A6
0x18005a59d  mov     word ptr [rdi+0AAh], 21h ; '!'
0x18005a5a6  mov     r13d, 1
0x18005a5ac  mov     rax, [rdi]
0x18005a5af  mov     rdx, [rax+18h]
0x18005a5b3  mov     r8, [rdx+0C8h]; rgExtensions
0x18005a5ba  mov     edx, [rdx+0C0h]; cExtensions
0x18005a5c0  lea     rcx, pszObjId; "2.5.29.35"
0x18005a5c7  call    cs:__imp_CertFindExtension
0x18005a5cd  test    rax, rax
0x18005a5d0  jz      short loc_18005A64E
0x18005a5d2  mov     [rbp+Str1], r12
0x18005a5d6  mov     [rbp+arg_18], r12
0x18005a5da  mov     dword ptr [rbp+arg_8], r12d
0x18005a5de  lea     rcx, [rbp+arg_8]
0x18005a5e2  mov     [rsp+48h+pvStructInfo], rcx; pcbStructInfo
0x18005a5e7  lea     rcx, [rbp+Str1]
0x18005a5eb  mov     [rsp+48h+pDecodePara], rcx; pvStructInfo
0x18005a5f0  mov     [rsp+48h+dwFlags], 8001h; dwFlags
0x18005a5f8  mov     r9d, [rax+10h]; cbEncoded
0x18005a5fc  mov     r8, [rax+18h]; pbEncoded
0x18005a600  mov     edx, 1Fh; lpszStructType
0x18005a605  mov     ecx, r13d; dwCertEncodingType
0x18005a608  call    cs:__imp_CryptDecodeObject
0x18005a60e  mov     rcx, [rbp+40h]; this
0x18005a612  test    eax, eax
0x18005a614  jnz     short loc_18005A624
0x18005a616  mov     r8, rsi; unsigned int
0x18005a619  mov     edx, 189h; void *
0x18005a61e  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18005a624  mov     rbx, [rbp+Str1]
0x18005a628  mov     [rbp+arg_18], rbx
0x18005a62c  mov     rdx, [rbx+8]
0x18005a630  mov     r8d, [rbx]
0x18005a633  add     r8, rdx
0x18005a636  lea     rcx, [rdi+8]
0x18005a63a  call    ??$assign@PEAE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAAXPEAE0@Z; std::vector<uchar>::assign<uchar *,0>(uchar *,uchar *)
0x18005a63f  nop
0x18005a640  test    rbx, rbx
0x18005a643  jz      short loc_18005A64E
0x18005a645  mov     rcx, rbx; hMem
0x18005a648  call    cs:__imp_LocalFree
0x18005a64e  mov     rax, [rdi]
0x18005a651  mov     rdx, [rax+18h]
0x18005a655  mov     r8, [rdx+0C8h]; rgExtensions
0x18005a65c  mov     edx, [rdx+0C0h]; cExtensions
0x18005a662  lea     rcx, szStructType; "2.5.29.14"
0x18005a669  call    cs:__imp_CertFindExtension
0x18005a66f  test    rax, rax
0x18005a672  jz      short loc_18005A6F2
0x18005a674  mov     [rbp+Str1], r12
0x18005a678  mov     [rbp+arg_18], r12
0x18005a67c  mov     dword ptr [rbp+arg_8], r12d
0x18005a680  lea     rcx, [rbp+arg_8]
0x18005a684  mov     [rsp+48h+pvStructInfo], rcx; pcbStructInfo
0x18005a689  lea     rcx, [rbp+Str1]
0x18005a68d  mov     [rsp+48h+pDecodePara], rcx; pvStructInfo
0x18005a692  mov     [rsp+48h+dwFlags], 8001h; dwFlags
0x18005a69a  mov     r9d, [rax+10h]; cbEncoded
0x18005a69e  mov     r8, [rax+18h]; pbEncoded
0x18005a6a2  lea     rdx, szStructType; "2.5.29.14"
0x18005a6a9  mov     ecx, r13d; dwCertEncodingType
0x18005a6ac  call    cs:__imp_CryptDecodeObject
0x18005a6b2  mov     rcx, [rbp+40h]; this
0x18005a6b6  test    eax, eax
0x18005a6b8  jnz     short loc_18005A6C8
0x18005a6ba  mov     r8, rsi; unsigned int
0x18005a6bd  mov     edx, 1A6h; void *
0x18005a6c2  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18005a6c8  mov     rbx, [rbp+Str1]
0x18005a6cc  mov     [rbp+arg_18], rbx
0x18005a6d0  mov     rdx, [rbx+8]
0x18005a6d4  mov     r8d, [rbx]
0x18005a6d7  add     r8, rdx
0x18005a6da  lea     rcx, [rdi+20h]
0x18005a6de  call    ??$assign@PEAE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAAXPEAE0@Z; std::vector<uchar>::assign<uchar *,0>(uchar *,uchar *)
0x18005a6e3  nop
0x18005a6e4  test    rbx, rbx
0x18005a6e7  jz      short loc_18005A6F2
0x18005a6e9  mov     rcx, rbx; hMem
0x18005a6ec  call    cs:__imp_LocalFree
0x18005a6f2  mov     dword ptr [rsp+48h+pDecodePara], r12d; cchNameString
0x18005a6f7  mov     qword ptr [rsp+48h+dwFlags], r12; int
0x18005a6fc  lea     r13, a2543; "2.5.4.3"
0x18005a703  mov     r9, r13; pvTypePara
0x18005a706  mov     ebx, 1
0x18005a70b  mov     r8d, ebx; dwFlags
0x18005a70e  lea     edx, [rbx+3]; dwType
0x18005a711  mov     rcx, [rdi]; pCertContext
0x18005a714  call    cs:__imp_CertGetNameStringW
0x18005a71a  mov     rcx, [rbp+40h]; this
0x18005a71e  cmp     eax, 2
0x18005a721  jnb     short loc_18005A737
0x18005a723  mov     r9d, 800B0108h; char *
0x18005a729  mov     r8, rsi; unsigned int
0x18005a72c  mov     edx, 1B8h; void *
0x18005a731  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005a737  mov     edx, eax
0x18005a739  mov     rcx, r15
0x18005a73c  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18005a741  mov     eax, [rdi+78h]
0x18005a744  cmp     qword ptr [r15+18h], 7
0x18005a749  jbe     short loc_18005A74E
0x18005a74b  mov     r15, [r15]
0x18005a74e  mov     dword ptr [rsp+48h+pDecodePara], eax; cchNameString
0x18005a752  mov     qword ptr [rsp+48h+dwFlags], r15; int
0x18005a757  mov     r9, r13; pvTypePara
0x18005a75a  mov     r8d, ebx; dwFlags
0x18005a75d  mov     ebx, 4
0x18005a762  mov     edx, ebx; dwType
0x18005a764  mov     rcx, [rdi]; pCertContext
0x18005a767  call    cs:__imp_CertGetNameStringW
0x18005a76d  mov     rcx, [rbp+40h]; this
0x18005a771  cmp     eax, 2
0x18005a774  jnb     short loc_18005A78A
0x18005a776  mov     r9d, 800B0108h; char *
0x18005a77c  mov     r8, rsi; unsigned int
0x18005a77f  mov     edx, 1C2h; void *
0x18005a784  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005a78a  mov     dword ptr [rsp+48h+pDecodePara], eax; cchNameString
0x18005a78e  mov     qword ptr [rsp+48h+dwFlags], r12; pszNameString
0x18005a793  mov     r9, r13; pvTypePara
0x18005a796  xor     r8d, r8d; dwFlags
0x18005a799  mov     edx, ebx; dwType
0x18005a79b  mov     rcx, [rdi]; pCertContext
0x18005a79e  call    cs:__imp_CertGetNameStringW
0x18005a7a4  mov     ebx, eax
0x18005a7a6  mov     edx, eax
0x18005a7a8  mov     rcx, r14
0x18005a7ab  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18005a7b0  cmp     qword ptr [r14+18h], 7
  ... truncated ...
```
