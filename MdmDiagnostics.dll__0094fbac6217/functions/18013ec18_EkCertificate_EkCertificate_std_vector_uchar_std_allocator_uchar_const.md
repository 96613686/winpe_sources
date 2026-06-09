# EkCertificate::EkCertificate(std::vector<uchar,std::allocator<uchar>> const &)

- ea: `0x18013ec18`
- end: `0x18013f1bb`
- name: `??0EkCertificate@@QEAA@AEBV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `1443`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `13`
- tags: `registry_config, loader_planting`

## callers

- `0x18013e994`
- `0x18013e9e0`
- `0x18013eb6c`
- `0x18013fe9c`

## callees

- `0x1800e61cc`
- `0x1800ef188`
- `0x1800f7bdc`
- `0x18011150c`
- `0x180127ddc`
- `0x18013e304`
- `0x18013e390`
- `0x18013ec18`
- `0x18013f2c8`
- `0x18013f38c`
- `0x180140548`
- `0x180140698`
- `0x18015a7f0`

## import_xrefs

- `CRYPT32!CertFindExtension` at `0x18013eef2`
- `CRYPT32!CertFindExtension` at `0x18013ef86`
- `CRYPT32!CertFindExtension` at `0x18013eef2`
- `CRYPT32!CertFindExtension` at `0x18013ef86`
- `CRYPT32!CryptDecodeObjectEx` at `0x18013ed08`
- `CRYPT32!CryptDecodeObjectEx` at `0x18013ed08`
- `CRYPT32!CertCreateCertificateContext` at `0x18013ed3d`
- `CRYPT32!CertCreateCertificateContext` at `0x18013ed3d`
- `CRYPT32!CryptDecodeObject` at `0x18013ee26`
- `CRYPT32!CryptDecodeObject` at `0x18013ef32`
- `CRYPT32!CryptDecodeObject` at `0x18013efcb`
- `CRYPT32!CryptDecodeObject` at `0x18013ee26`
- `CRYPT32!CryptDecodeObject` at `0x18013ef32`
- `CRYPT32!CryptDecodeObject` at `0x18013efcb`
- `CRYPT32!CertGetNameStringW` at `0x18013f02a`
- `CRYPT32!CertGetNameStringW` at `0x18013f06a`
- `CRYPT32!CertGetNameStringW` at `0x18013f092`
- `CRYPT32!CertGetNameStringW` at `0x18013f0cf`
- `CRYPT32!CertGetNameStringW` at `0x18013f02a`
- `CRYPT32!CertGetNameStringW` at `0x18013f06a`
- `CRYPT32!CertGetNameStringW` at `0x18013f092`
- `CRYPT32!CertGetNameStringW` at `0x18013f0cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18013ef65`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18013effe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18013ef65`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18013effe`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 *__fastcall EkCertificate::EkCertificate(__int64 *a1, __int64 a2)
{
  __int64 *v4; // r12
  unsigned int v5; // eax
  const char *v6; // r9
  __int64 v7; // r14
  const char *v8; // rbx
  char *v9; // rbx
  PCERT_EXTENSION Extension; // rax
  const char *v11; // r9
  char *v12; // rbx
  PCERT_EXTENSION v13; // rax
  const char *v14; // r9
  char *v15; // rbx
  DWORD NameStringW; // eax
  WCHAR *v17; // rax
  DWORD v18; // eax
  __int64 v19; // rbx
  WCHAR *v20; // rax
  unsigned int v22; // eax
  int dwFlags; // [rsp+20h] [rbp-28h]
  int dwFlagsa; // [rsp+20h] [rbp-28h]
  int dwFlagsb; // [rsp+20h] [rbp-28h]
  int dwFlagsc; // [rsp+20h] [rbp-28h]
  const char *pDecodePara; // [rsp+28h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+40h]
  PCCERT_CONTEXT pcbStructInfo; // [rsp+98h] [rbp+50h] BYREF
  char *Str1; // [rsp+A0h] [rbp+58h] BYREF
  char *v31; // [rsp+A8h] [rbp+60h]

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
  v4 = a1 + 13;
  *(_OWORD *)(a1 + 13) = 0;
  a1[15] = 0;
  a1[16] = 7;
  *((_WORD *)a1 + 52) = 0;
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
    v5 = CryptDecodeObjectEx(
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
      (const char *)v5,
      (__int64)"EK Certificate decoding error.",
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
      v6);
  if ( !*(_DWORD *)(*(_QWORD *)(*a1 + 24) + 192LL) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x137,
      (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\ekcert.cpp",
      (const char *)0x800B0108LL,
      dwFlags);
  std::vector<unsigned char>::operator=(a1 + 10, a2);
  v7 = *a1;
  v8 = *(const char **)(*(_QWORD *)(*a1 + 24) + 96LL);
  if ( !strncmp_0(v8, "1.2.840.113549", 0xEu) )
  {
    *((_DWORD *)a1 + 42) = 1;
    goto LABEL_19;
  }
  if ( strncmp_0(v8, "1.2.840.10045.2.1", 0x11u) )
  {
    v22 = wil::verify_hresult<long>(2148077570LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x170,
      (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\ekcert.cpp",
      (const char *)v22,
      dwFlags);
  }
  *((_WORD *)a1 + 84) = 35;
  Str1 = 0;
  LODWORD(pcbStructInfo) = 8;
  if ( !CryptDecodeObject(
          0x10001u,
          *(LPCSTR *)(*(_QWORD *)(v7 + 24) + 96LL),
          *(const BYTE **)(*(_QWORD *)(v7 + 24) + 112LL),
          *(_DWORD *)(*(_QWORD *)(v7 + 24) + 104LL),
          4u,
          &Str1,
          (DWORD *)&pcbStructInfo) )
    goto LABEL_18;
  v9 = Str1;
  if ( !strncmp_0(Str1, "1.2.840.10045.3.1.7", 0x14u) )
  {
    *((_WORD *)a1 + 85) = 3;
    goto LABEL_19;
  }
  if ( !strncmp_0(v9, "1.3.132.0.34", 0xDu) )
  {
    *((_WORD *)a1 + 85) = 4;
    goto LABEL_19;
  }
  if ( !strncmp_0(v9, "1.3.132.0.35", 0xDu) )
  {
    *((_WORD *)a1 + 85) = 5;
    goto LABEL_19;
  }
  if ( !strncmp_0(v9, "1.2.156.10197.1.301", 0x14u) )
    *((_WORD *)a1 + 85) = 32;
  else
LABEL_18:
    *((_WORD *)a1 + 85) = 33;
LABEL_19:
  Extension = CertFindExtension(
                "2.5.29.35",
                *(_DWORD *)(*(_QWORD *)(*a1 + 24) + 192LL),
                *(CERT_EXTENSION **)(*(_QWORD *)(*a1 + 24) + 200LL));
  if ( Extension )
  {
    Str1 = 0;
    v31 = 0;
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
        v11);
    v12 = Str1;
    v31 = Str1;
    std::vector<unsigned char>::_Assign_counted_range<unsigned char *>(
      a1 + 1,
      *((_QWORD *)Str1 + 1),
      *(unsigned int *)Str1);
    if ( v12 )
      LocalFree(v12);
  }
  v13 = CertFindExtension(
          "2.5.29.14",
          *(_DWORD *)(*(_QWORD *)(*a1 + 24) + 192LL),
          *(CERT_EXTENSION **)(*(_QWORD *)(*a1 + 24) + 200LL));
  if ( v13 )
  {
    Str1 = 0;
    v31 = 0;
    LODWORD(pcbStructInfo) = 0;
    if ( !CryptDecodeObject(
            1u,
            "2.5.29.14",
            v13->Value.pbData,
            v13->Value.cbData,
            0x8001u,
            &Str1,
            (DWORD *)&pcbStructInfo) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x1A6,
        (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\ekcert.cpp",
        v14);
    v15 = Str1;
    v31 = Str1;
    std::vector<unsigned char>::_Assign_counted_range<unsigned char *>(
      a1 + 4,
      *((_QWORD *)Str1 + 1),
      *(unsigned int *)Str1);
    if ( v15 )
      LocalFree(v15);
  }
  NameStringW = CertGetNameStringW((PCCERT_CONTEXT)*a1, 4u, 1u, "2.5.4.3", 0, 0);
  if ( NameStringW < 2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1B8,
      (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\ekcert.cpp",
      (const char *)0x800B0108LL,
      dwFlagsa);
  std::wstring::resize(v4, NameStringW, 0);
  v17 = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v4);
  v18 = CertGetNameStringW((PCCERT_CONTEXT)*a1, 4u, 1u, "2.5.4.3", v17, *((_DWORD *)a1 + 30));
  if ( v18 < 2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\ekcert.cpp",
      (const char *)0x800B0108LL,
      dwFlagsb);
  v19 = CertGetNameStringW((PCCERT_CONTEXT)*a1, 4u, 0, "2.5.4.3", 0, v18);
  std::wstring::resize(a1 + 17, v19, 0);
  v20 = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 17);
  if ( CertGetNameStringW((PCCERT_CONTEXT)*a1, 4u, 0, "2.5.4.3", v20, v19) < 2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1D5,
      (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\ekcert.cpp",
      (const char *)0x800B0108LL,
      dwFlagsc);
  std::vector<unsigned char>::_Assign_counted_range<unsigned char *>(
    a1 + 7,
    *(_QWORD *)(*(_QWORD *)(*a1 + 24) + 16LL),
    *(unsigned int *)(*(_QWORD *)(*a1 + 24) + 8LL));
  return a1;
}

```

## disassembly

```asm
0x18013ec18  mov     [rsp-40h+arg_0], rcx
0x18013ec1d  push    rbp
0x18013ec1e  push    rbx
0x18013ec1f  push    rsi
0x18013ec20  push    rdi
0x18013ec21  push    r12
0x18013ec23  push    r13
0x18013ec25  push    r14
0x18013ec27  push    r15
0x18013ec29  mov     rbp, rsp
0x18013ec2c  sub     rsp, 48h
0x18013ec30  mov     rbx, rdx
0x18013ec33  mov     rdi, rcx
0x18013ec36  xor     r8d, r8d
0x18013ec39  mov     [rcx], r8
0x18013ec3c  mov     [rcx+8], r8
0x18013ec40  mov     [rcx+10h], r8
0x18013ec44  mov     [rcx+18h], r8
0x18013ec48  mov     [rcx+20h], r8
0x18013ec4c  mov     [rcx+28h], r8
0x18013ec50  mov     [rcx+30h], r8
0x18013ec54  mov     [rcx+38h], r8
0x18013ec58  mov     [rcx+40h], r8
0x18013ec5c  mov     [rcx+48h], r8
0x18013ec60  mov     [rcx+50h], r8
0x18013ec64  mov     [rcx+58h], r8
0x18013ec68  mov     [rcx+60h], r8
0x18013ec6c  lea     r12, [rcx+68h]
0x18013ec70  xorps   xmm0, xmm0
0x18013ec73  movups  xmmword ptr [r12], xmm0
0x18013ec78  mov     [r12+10h], r8
0x18013ec7d  lea     edx, [r8+7]
0x18013ec81  mov     [r12+18h], rdx
0x18013ec86  mov     [r12], r8w
0x18013ec8b  movups  xmmword ptr [rcx+88h], xmm0
0x18013ec92  mov     [rcx+98h], r8
0x18013ec99  mov     [rcx+0A0h], rdx
0x18013eca0  mov     [rcx+88h], r8w
0x18013eca8  mov     dword ptr [rcx+0A8h], 210000h
0x18013ecb2  mov     rcx, [rbp+40h]; this
0x18013ecb6  mov     rax, [rbx+8]
0x18013ecba  cmp     [rbx], rax
0x18013ecbd  jz      loc_18013F13D
0x18013ecc3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AMD_P384_EK_Cert@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AMD_P384_EK_Cert@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AMD_P384_EK_Cert> `wil::Feature<__WilFeatureTraits_Feature_AMD_P384_EK_Cert>::GetImpl(void)'::`2'::impl
0x18013ecca  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AMD_P384_EK_Cert@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AMD_P384_EK_Cert>::__private_IsEnabled(void)
0x18013eccf  lea     rsi, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\tpmhli\\lib\\ekce"...
0x18013ecd6  xor     ecx, ecx
0x18013ecd8  test    al, al
0x18013ecda  jz      short loc_18013ED2E
0x18013ecdc  mov     dword ptr [rbp+arg_8], ecx
0x18013ecdf  mov     r9d, [rbx+8]
0x18013ece3  sub     r9d, [rbx]; cbEncoded
0x18013ece6  lea     rax, [rbp+arg_8]
0x18013ecea  mov     [rsp+48h+pcbStructInfo], rax; pcbStructInfo
0x18013ecef  mov     [rsp+48h+pvStructInfo], rcx; pvStructInfo
0x18013ecf4  mov     [rsp+48h+pDecodePara], rcx; char *
0x18013ecf9  mov     [rsp+48h+dwFlags], ecx; dwFlags
0x18013ecfd  mov     r8, [rbx]; pbEncoded
0x18013ed00  lea     edx, [rcx+1]; lpszStructType
0x18013ed03  mov     ecx, 10001h; dwCertEncodingType
0x18013ed08  call    cs:__imp_CryptDecodeObjectEx
0x18013ed0e  mov     rcx, [rbp+40h]; this
0x18013ed12  lea     rdx, aEkCertificateD; "EK Certificate decoding error."
0x18013ed19  mov     qword ptr [rsp+48h+dwFlags], rdx; int
0x18013ed1e  mov     r9d, eax; char *
0x18013ed21  mov     r8, rsi; unsigned int
0x18013ed24  mov     edx, 12Ch; void *
0x18013ed29  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x18013ed2e  mov     r8d, [rbx+8]
0x18013ed32  sub     r8d, [rbx]; cbCertEncoded
0x18013ed35  mov     rdx, [rbx]; pbCertEncoded
0x18013ed38  mov     ecx, 10001h; dwCertEncodingType
0x18013ed3d  call    cs:__imp_CertCreateCertificateContext
0x18013ed43  mov     [rbp+arg_8], rax
0x18013ed47  lea     rdx, [rbp+arg_8]
0x18013ed4b  mov     rcx, rdi
0x18013ed4e  call    ??4?$unique_any_t@Ucert_context_t@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::cert_context_t>::operator=(wil::unique_any_t<wil::cert_context_t> &&)
0x18013ed53  lea     rcx, [rbp+arg_8]
0x18013ed57  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x18013ed5c  mov     rax, [rdi]
0x18013ed5f  mov     rcx, [rbp+40h]; this
0x18013ed63  test    rax, rax
0x18013ed66  jz      loc_18013F155
0x18013ed6c  mov     rcx, [rbp+40h]; this
0x18013ed70  mov     rax, [rax+18h]
0x18013ed74  cmp     dword ptr [rax+0C0h], 1
0x18013ed7b  jb      loc_18013F163
0x18013ed81  mov     rdx, rbx
0x18013ed84  lea     rcx, [rdi+50h]
0x18013ed88  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> const &)
0x18013ed8d  mov     r14, [rdi]
0x18013ed90  mov     rax, [r14+18h]
0x18013ed94  mov     rbx, [rax+60h]
0x18013ed98  mov     r8d, 0Eh; MaxCount
0x18013ed9e  lea     rdx, Str2; "1.2.840.113549"
0x18013eda5  mov     rcx, rbx; Str1
0x18013eda8  call    strncmp_0
0x18013edad  test    eax, eax
0x18013edaf  jnz     short loc_18013EDC2
0x18013edb1  lea     ebx, [rax+1]
0x18013edb4  mov     [rdi+0A8h], ebx
0x18013edba  xor     r14d, r14d
0x18013edbd  jmp     loc_18013EED7
0x18013edc2  mov     r8d, 11h; MaxCount
0x18013edc8  lea     rdx, a128401004521; "1.2.840.10045.2.1"
0x18013edcf  mov     rcx, rbx; Str1
0x18013edd2  call    strncmp_0
0x18013edd7  test    eax, eax
0x18013edd9  jnz     loc_18013F11E
0x18013eddf  mov     word ptr [rdi+0A8h], 23h ; '#'
0x18013ede8  mov     [rbp+Str1], 0
0x18013edf0  mov     dword ptr [rbp+arg_8], 8
0x18013edf7  mov     rdx, [r14+18h]
0x18013edfb  lea     rax, [rbp+arg_8]
0x18013edff  mov     [rsp+48h+pvStructInfo], rax; pcbStructInfo
0x18013ee04  lea     rax, [rbp+Str1]
0x18013ee08  mov     [rsp+48h+pDecodePara], rax; pvStructInfo
0x18013ee0d  mov     [rsp+48h+dwFlags], 4; dwFlags
0x18013ee15  mov     r9d, [rdx+68h]; cbEncoded
0x18013ee19  mov     r8, [rdx+70h]; pbEncoded
0x18013ee1d  mov     rdx, [rdx+60h]; lpszStructType
0x18013ee21  mov     ecx, 10001h; dwCertEncodingType
0x18013ee26  call    cs:__imp_CryptDecodeObject
0x18013ee2c  xor     r14d, r14d
0x18013ee2f  test    eax, eax
0x18013ee31  jz      loc_18013EEC9
0x18013ee37  lea     r8d, [r14+14h]; MaxCount
0x18013ee3b  lea     rdx, a1284010045317; "1.2.840.10045.3.1.7"
0x18013ee42  mov     rbx, [rbp+Str1]
0x18013ee46  mov     rcx, rbx; Str1
0x18013ee49  call    strncmp_0
0x18013ee4e  test    eax, eax
0x18013ee50  jnz     short loc_18013EE5D
0x18013ee52  mov     word ptr [rdi+0AAh], 3
0x18013ee5b  jmp     short loc_18013EED2
0x18013ee5d  mov     r8d, 0Dh; MaxCount
0x18013ee63  lea     rdx, a13132034; "1.3.132.0.34"
0x18013ee6a  mov     rcx, rbx; Str1
0x18013ee6d  call    strncmp_0
0x18013ee72  test    eax, eax
0x18013ee74  jnz     short loc_18013EE81
0x18013ee76  mov     word ptr [rdi+0AAh], 4
0x18013ee7f  jmp     short loc_18013EED2
0x18013ee81  mov     r8d, 0Dh; MaxCount
0x18013ee87  lea     rdx, a13132035; "1.3.132.0.35"
0x18013ee8e  mov     rcx, rbx; Str1
0x18013ee91  call    strncmp_0
0x18013ee96  test    eax, eax
0x18013ee98  jnz     short loc_18013EEA5
0x18013ee9a  mov     word ptr [rdi+0AAh], 5
0x18013eea3  jmp     short loc_18013EED2
0x18013eea5  mov     r8d, 14h; MaxCount
0x18013eeab  lea     rdx, a12156101971301; "1.2.156.10197.1.301"
0x18013eeb2  mov     rcx, rbx; Str1
0x18013eeb5  call    strncmp_0
0x18013eeba  test    eax, eax
0x18013eebc  jnz     short loc_18013EEC9
0x18013eebe  mov     word ptr [rdi+0AAh], 20h ; ' '
0x18013eec7  jmp     short loc_18013EED2
0x18013eec9  mov     word ptr [rdi+0AAh], 21h ; '!'
0x18013eed2  mov     ebx, 1
0x18013eed7  mov     rax, [rdi]
0x18013eeda  mov     rdx, [rax+18h]
0x18013eede  mov     r8, [rdx+0C8h]; rgExtensions
0x18013eee5  mov     edx, [rdx+0C0h]; cExtensions
0x18013eeeb  lea     rcx, pszObjId; "2.5.29.35"
0x18013eef2  call    cs:__imp_CertFindExtension
0x18013eef8  test    rax, rax
0x18013eefb  jz      short loc_18013EF6B
0x18013eefd  mov     [rbp+Str1], r14
0x18013ef01  mov     [rbp+arg_18], r14
0x18013ef05  mov     dword ptr [rbp+arg_8], r14d
0x18013ef09  lea     rcx, [rbp+arg_8]
0x18013ef0d  mov     [rsp+48h+pvStructInfo], rcx; pcbStructInfo
0x18013ef12  lea     rcx, [rbp+Str1]
0x18013ef16  mov     [rsp+48h+pDecodePara], rcx; pvStructInfo
0x18013ef1b  mov     [rsp+48h+dwFlags], 8001h; dwFlags
0x18013ef23  mov     r9d, [rax+10h]; cbEncoded
0x18013ef27  mov     r8, [rax+18h]; pbEncoded
0x18013ef2b  mov     edx, 1Fh; lpszStructType
0x18013ef30  mov     ecx, ebx; dwCertEncodingType
0x18013ef32  call    cs:__imp_CryptDecodeObject
0x18013ef38  mov     rcx, [rbp+40h]; this
0x18013ef3c  test    eax, eax
0x18013ef3e  jz      loc_18013F177
0x18013ef44  mov     rbx, [rbp+Str1]
0x18013ef48  mov     [rbp+arg_18], rbx
0x18013ef4c  mov     r8d, [rbx]
0x18013ef4f  mov     rdx, [rbx+8]
0x18013ef53  lea     rcx, [rdi+8]
0x18013ef57  call    ??$_Assign_counted_range@PEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAXPEAE_K@Z; std::vector<uchar>::_Assign_counted_range<uchar *>(uchar *,unsigned __int64)
0x18013ef5c  nop
0x18013ef5d  test    rbx, rbx
0x18013ef60  jz      short loc_18013EF6B
0x18013ef62  mov     rcx, rbx; hMem
0x18013ef65  call    cs:__imp_LocalFree
0x18013ef6b  mov     rax, [rdi]
0x18013ef6e  mov     rdx, [rax+18h]
0x18013ef72  mov     r8, [rdx+0C8h]; rgExtensions
0x18013ef79  mov     edx, [rdx+0C0h]; cExtensions
0x18013ef7f  lea     rcx, a252914; "2.5.29.14"
0x18013ef86  call    cs:__imp_CertFindExtension
0x18013ef8c  test    rax, rax
0x18013ef8f  jz      short loc_18013F004
0x18013ef91  mov     [rbp+Str1], r14
0x18013ef95  mov     [rbp+arg_18], r14
0x18013ef99  mov     dword ptr [rbp+arg_8], r14d
0x18013ef9d  lea     rcx, [rbp+arg_8]
0x18013efa1  mov     [rsp+48h+pvStructInfo], rcx; pcbStructInfo
0x18013efa6  lea     rcx, [rbp+Str1]
0x18013efaa  mov     [rsp+48h+pDecodePara], rcx; pvStructInfo
0x18013efaf  mov     [rsp+48h+dwFlags], 8001h; dwFlags
0x18013efb7  mov     r9d, [rax+10h]; cbEncoded
0x18013efbb  mov     r8, [rax+18h]; pbEncoded
0x18013efbf  lea     rdx, a252914; "2.5.29.14"
0x18013efc6  mov     ecx, 1; dwCertEncodingType
0x18013efcb  call    cs:__imp_CryptDecodeObject
0x18013efd1  mov     rcx, [rbp+40h]; this
0x18013efd5  test    eax, eax
0x18013efd7  jz      loc_18013F185
0x18013efdd  mov     rbx, [rbp+Str1]
0x18013efe1  mov     [rbp+arg_18], rbx
0x18013efe5  mov     r8d, [rbx]
0x18013efe8  mov     rdx, [rbx+8]
0x18013efec  lea     rcx, [rdi+20h]
0x18013eff0  call    ??$_Assign_counted_range@PEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAXPEAE_K@Z; std::vector<uchar>::_Assign_counted_range<uchar *>(uchar *,unsigned __int64)
0x18013eff5  nop
0x18013eff6  test    rbx, rbx
0x18013eff9  jz      short loc_18013F004
0x18013effb  mov     rcx, rbx; hMem
0x18013effe  call    cs:__imp_LocalFree
0x18013f004  mov     dword ptr [rsp+48h+pDecodePara], r14d; cchNameString
0x18013f009  mov     qword ptr [rsp+48h+dwFlags], r14; int
0x18013f00e  lea     r15, a2543; "2.5.4.3"
0x18013f015  mov     r9, r15; pvTypePara
0x18013f018  mov     ebx, 1
0x18013f01d  mov     r8d, ebx; dwFlags
0x18013f020  lea     r13d, [rbx+3]
0x18013f024  mov     edx, r13d; dwType
0x18013f027  mov     rcx, [rdi]; pCertContext
0x18013f02a  call    cs:__imp_CertGetNameStringW
0x18013f030  mov     rcx, [rbp+40h]; this
0x18013f034  cmp     eax, 2
0x18013f037  jb      loc_18013F193
0x18013f03d  xor     r8d, r8d
0x18013f040  mov     edx, eax
0x18013f042  mov     rcx, r12
0x18013f045  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18013f04a  mov     rcx, r12
0x18013f04d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18013f052  mov     ecx, [rdi+78h]
0x18013f055  mov     dword ptr [rsp+48h+pDecodePara], ecx; cchNameString
0x18013f059  mov     qword ptr [rsp+48h+dwFlags], rax; int
0x18013f05e  mov     r9, r15; pvTypePara
0x18013f061  mov     r8d, ebx; dwFlags
0x18013f064  mov     edx, r13d; dwType
0x18013f067  mov     rcx, [rdi]; pCertContext
0x18013f06a  call    cs:__imp_CertGetNameStringW
0x18013f070  mov     rcx, [rbp+40h]; this
0x18013f074  cmp     eax, 2
0x18013f077  jb      loc_18013F1A7
0x18013f07d  mov     dword ptr [rsp+48h+pDecodePara], eax; cchNameString
0x18013f081  mov     qword ptr [rsp+48h+dwFlags], r14; pszNameString
0x18013f086  mov     r9, r15; pvTypePara
0x18013f089  xor     r8d, r8d; dwFlags
0x18013f08c  mov     edx, r13d; dwType
0x18013f08f  mov     rcx, [rdi]; pCertContext
0x18013f092  call    cs:__imp_CertGetNameStringW
0x18013f098  mov     ebx, eax
0x18013f09a  xor     r8d, r8d
0x18013f09d  mov     edx, eax
0x18013f09f  lea     r14, [rdi+88h]
0x18013f0a6  mov     rcx, r14
0x18013f0a9  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18013f0ae  mov     rcx, r14
0x18013f0b1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18013f0b6  mov     r14, [rbp+40h]
0x18013f0ba  mov     dword ptr [rsp+48h+pDecodePara], ebx; cchNameString
0x18013f0be  mov     qword ptr [rsp+48h+dwFlags], rax; int
0x18013f0c3  mov     r9, r15; pvTypePara
0x18013f0c6  xor     r8d, r8d; dwFlags
0x18013f0c9  mov     edx, r13d; dwType
0x18013f0cc  mov     rcx, [rdi]; pCertContext
0x18013f0cf  call    cs:__imp_CertGetNameStringW
0x18013f0d5  cmp     eax, 2
0x18013f0d8  jb      short loc_18013F107
0x18013f0da  mov     rax, [rdi]
0x18013f0dd  mov     rdx, [rax+18h]
0x18013f0e1  mov     r8d, [rdx+8]
0x18013f0e5  mov     rdx, [rdx+10h]
0x18013f0e9  lea     rcx, [rdi+38h]
0x18013f0ed  call    ??$_Assign_counted_range@PEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAXPEAE_K@Z; std::vector<uchar>::_Assign_counted_range<uchar *>(uchar *,unsigned __int64)
0x18013f0f2  nop
0x18013f0f3  mov     rax, rdi
0x18013f0f6  add     rsp, 48h
0x18013f0fa  pop     r15
0x18013f0fc  pop     r14
0x18013f0fe  pop     r13
0x18013f100  pop     r12
0x18013f102  pop     rdi
  ... truncated ...
```
