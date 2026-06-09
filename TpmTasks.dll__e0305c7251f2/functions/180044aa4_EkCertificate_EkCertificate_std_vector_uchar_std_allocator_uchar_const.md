# EkCertificate::EkCertificate(std::vector<uchar,std::allocator<uchar>> const &)

- ea: `0x180044aa4`
- end: `0x180045043`
- name: `??0EkCertificate@@QEAA@AEBV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `1439`
- prototype: `__int64 *__fastcall(__int64 *, _QWORD *)`
- caller_count: `4`
- callee_count: `13`
- tags: `registry_config, loader_planting`

## callers

- `0x180044808`
- `0x180044854`
- `0x1800449b4`
- `0x180045760`

## callees

- `0x18000d06c`
- `0x180023634`
- `0x180034158`
- `0x180044520`
- `0x18004453c`
- `0x18004455c`
- `0x180044744`
- `0x180044aa4`
- `0x180045128`
- `0x180045948`
- `0x180045970`
- `0x180045b30`
- `0x180059260`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044dff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044e98`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044dff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044e98`
- `CRYPT32!CryptDecodeObjectEx` at `0x180044b97`
- `CRYPT32!CryptDecodeObjectEx` at `0x180044b97`
- `CRYPT32!CertCreateCertificateContext` at `0x180044bcc`
- `CRYPT32!CertCreateCertificateContext` at `0x180044bcc`
- `CRYPT32!CryptDecodeObject` at `0x180044cc0`
- `CRYPT32!CryptDecodeObject` at `0x180044dcc`
- `CRYPT32!CryptDecodeObject` at `0x180044e65`
- `CRYPT32!CryptDecodeObject` at `0x180044cc0`
- `CRYPT32!CryptDecodeObject` at `0x180044dcc`
- `CRYPT32!CryptDecodeObject` at `0x180044e65`
- `CRYPT32!CertGetNameStringW` at `0x180044ec4`
- `CRYPT32!CertGetNameStringW` at `0x180044f01`
- `CRYPT32!CertGetNameStringW` at `0x180044f29`
- `CRYPT32!CertGetNameStringW` at `0x180044f63`
- `CRYPT32!CertGetNameStringW` at `0x180044ec4`
- `CRYPT32!CertGetNameStringW` at `0x180044f01`
- `CRYPT32!CertGetNameStringW` at `0x180044f29`
- `CRYPT32!CertGetNameStringW` at `0x180044f63`
- `CRYPT32!CertFindExtension` at `0x180044d8c`
- `CRYPT32!CertFindExtension` at `0x180044e20`
- `CRYPT32!CertFindExtension` at `0x180044d8c`
- `CRYPT32!CertFindExtension` at `0x180044e20`

## pseudocode

```c
__int64 *__fastcall EkCertificate::EkCertificate(__int64 *a1, _QWORD *a2)
{
  _QWORD *v4; // r14
  __int64 *v5; // r12
  unsigned int v6; // eax
  unsigned int v7; // r8d
  const char *v8; // r9
  __int64 v9; // r14
  const char *v10; // rbx
  char *v11; // rbx
  PCERT_EXTENSION Extension; // rax
  unsigned int v13; // r8d
  const char *v14; // r9
  char *v15; // rbx
  PCERT_EXTENSION v16; // rax
  unsigned int v17; // r8d
  const char *v18; // r9
  char *v19; // rbx
  DWORD NameStringW; // eax
  WCHAR *v21; // rax
  DWORD v22; // eax
  __int64 v23; // rbx
  WCHAR *v24; // rax
  unsigned int v26; // eax
  unsigned int v27; // r8d
  int dwFlags; // [rsp+20h] [rbp-28h]
  int dwFlagsa; // [rsp+20h] [rbp-28h]
  int dwFlagsb; // [rsp+20h] [rbp-28h]
  int dwFlagsc; // [rsp+20h] [rbp-28h]
  const char *pDecodePara; // [rsp+28h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+40h]
  PCCERT_CONTEXT pcbStructInfo; // [rsp+98h] [rbp+50h] BYREF
  char *Str1; // [rsp+A0h] [rbp+58h] BYREF
  char *v36; // [rsp+A8h] [rbp+60h]

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
  v4 = a1 + 10;
  a1[10] = 0;
  a1[11] = 0;
  a1[12] = 0;
  v5 = a1 + 13;
  *(_OWORD *)(a1 + 13) = 0;
  a1[15] = 0;
  a1[16] = 7;
  *((_WORD *)a1 + 52) = 0;
  *(_OWORD *)(a1 + 17) = 0;
  a1[19] = 0;
  a1[20] = 7;
  *((_WORD *)a1 + 68) = 0;
  *((_DWORD *)a1 + 42) = 2162688;
  if ( *a2 == a2[1] )
    wil::details::in1diag3::_Throw_Hr(
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
           (const BYTE *)*a2,
           *((_DWORD *)a2 + 2) - *(_DWORD *)a2,
           0,
           0,
           0,
           (DWORD *)&pcbStructInfo);
    wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
      retaddr,
      (void *)0x12C,
      (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\ekcert.cpp",
      (const char *)v6,
      (__int64)"EK Certificate decoding error.",
      pDecodePara);
  }
  pcbStructInfo = CertCreateCertificateContext(0x10001u, (const BYTE *)*a2, *((_DWORD *)a2 + 2) - *(_DWORD *)a2);
  wil::unique_any_t<wil::cert_context_t>::operator=(a1, &pcbStructInfo);
  wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&pcbStructInfo);
  if ( !*a1 )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x134, v7, v8);
  if ( !*(_DWORD *)(*(_QWORD *)(*a1 + 24) + 192LL) )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x137,
      (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\ekcert.cpp",
      (const char *)0x800B0108LL,
      dwFlags);
  if ( v4 != a2 )
    std::vector<unsigned char>::_Assign_counted_range<unsigned char *>(v4, *a2, a2[1] - *a2);
  v9 = *a1;
  v10 = *(const char **)(*(_QWORD *)(*a1 + 24) + 96LL);
  if ( !strncmp_0(v10, "1.2.840.113549", 0xEu) )
  {
    *((_DWORD *)a1 + 42) = 1;
    goto LABEL_21;
  }
  if ( strncmp_0(v10, "1.2.840.10045.2.1", 0x11u) )
  {
    v26 = wil::verify_hresult<long>(2148077570LL);
    wil::details::in1diag3::Throw_Hr(retaddr, (void *)0x170, v27, (const char *)v26, dwFlags);
  }
  *((_WORD *)a1 + 84) = 35;
  Str1 = 0;
  LODWORD(pcbStructInfo) = 8;
  if ( !CryptDecodeObject(
          0x10001u,
          *(LPCSTR *)(*(_QWORD *)(v9 + 24) + 96LL),
          *(const BYTE **)(*(_QWORD *)(v9 + 24) + 112LL),
          *(_DWORD *)(*(_QWORD *)(v9 + 24) + 104LL),
          4u,
          &Str1,
          (DWORD *)&pcbStructInfo) )
    goto LABEL_20;
  v11 = Str1;
  if ( !strncmp_0(Str1, "1.2.840.10045.3.1.7", 0x14u) )
  {
    *((_WORD *)a1 + 85) = 3;
    goto LABEL_21;
  }
  if ( !strncmp_0(v11, "1.3.132.0.34", 0xDu) )
  {
    *((_WORD *)a1 + 85) = 4;
    goto LABEL_21;
  }
  if ( !strncmp_0(v11, "1.3.132.0.35", 0xDu) )
  {
    *((_WORD *)a1 + 85) = 5;
    goto LABEL_21;
  }
  if ( !strncmp_0(v11, "1.2.156.10197.1.301", 0x14u) )
    *((_WORD *)a1 + 85) = 32;
  else
LABEL_20:
    *((_WORD *)a1 + 85) = 33;
LABEL_21:
  Extension = CertFindExtension(
                "2.5.29.35",
                *(_DWORD *)(*(_QWORD *)(*a1 + 24) + 192LL),
                *(CERT_EXTENSION **)(*(_QWORD *)(*a1 + 24) + 200LL));
  if ( Extension )
  {
    Str1 = 0;
    v36 = 0;
    LODWORD(pcbStructInfo) = 0;
    if ( !CryptDecodeObject(
            1u,
            (LPCSTR)0x1F,
            Extension->Value.pbData,
            Extension->Value.cbData,
            0x8001u,
            &Str1,
            (DWORD *)&pcbStructInfo) )
      wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x189, v13, v14);
    v15 = Str1;
    v36 = Str1;
    std::vector<unsigned char>::_Assign_counted_range<unsigned char *>(
      a1 + 1,
      *((_QWORD *)Str1 + 1),
      *(unsigned int *)Str1);
    if ( v15 )
      LocalFree(v15);
  }
  v16 = CertFindExtension(
          "2.5.29.14",
          *(_DWORD *)(*(_QWORD *)(*a1 + 24) + 192LL),
          *(CERT_EXTENSION **)(*(_QWORD *)(*a1 + 24) + 200LL));
  if ( v16 )
  {
    Str1 = 0;
    v36 = 0;
    LODWORD(pcbStructInfo) = 0;
    if ( !CryptDecodeObject(
            1u,
            "2.5.29.14",
            v16->Value.pbData,
            v16->Value.cbData,
            0x8001u,
            &Str1,
            (DWORD *)&pcbStructInfo) )
      wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x1A6, v17, v18);
    v19 = Str1;
    v36 = Str1;
    std::vector<unsigned char>::_Assign_counted_range<unsigned char *>(
      a1 + 4,
      *((_QWORD *)Str1 + 1),
      *(unsigned int *)Str1);
    if ( v19 )
      LocalFree(v19);
  }
  NameStringW = CertGetNameStringW((PCCERT_CONTEXT)*a1, 4u, 1u, "2.5.4.3", 0, 0);
  if ( NameStringW < 2 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1B8,
      (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\ekcert.cpp",
      (const char *)0x800B0108LL,
      dwFlagsa);
  std::wstring::resize(v5, NameStringW);
  v21 = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v5);
  v22 = CertGetNameStringW((PCCERT_CONTEXT)*a1, 4u, 1u, "2.5.4.3", v21, *((_DWORD *)a1 + 30));
  if ( v22 < 2 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\ekcert.cpp",
      (const char *)0x800B0108LL,
      dwFlagsb);
  v23 = CertGetNameStringW((PCCERT_CONTEXT)*a1, 4u, 0, "2.5.4.3", 0, v22);
  std::wstring::resize(a1 + 17, v23);
  v24 = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 17);
  if ( CertGetNameStringW((PCCERT_CONTEXT)*a1, 4u, 0, "2.5.4.3", v24, v23) < 2 )
    wil::details::in1diag3::_Throw_Hr(
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
0x180044aa4  mov     [rsp-40h+arg_0], rcx
0x180044aa9  push    rbp
0x180044aaa  push    rbx
0x180044aab  push    rsi
0x180044aac  push    rdi
0x180044aad  push    r12
0x180044aaf  push    r13
0x180044ab1  push    r14
0x180044ab3  push    r15
0x180044ab5  mov     rbp, rsp
0x180044ab8  sub     rsp, 48h
0x180044abc  mov     rbx, rdx
0x180044abf  mov     rdi, rcx
0x180044ac2  xor     r8d, r8d
0x180044ac5  mov     [rcx], r8
0x180044ac8  mov     [rcx+8], r8
0x180044acc  mov     [rcx+10h], r8
0x180044ad0  mov     [rcx+18h], r8
0x180044ad4  mov     [rcx+20h], r8
0x180044ad8  mov     [rcx+28h], r8
0x180044adc  mov     [rcx+30h], r8
0x180044ae0  mov     [rcx+38h], r8
0x180044ae4  mov     [rcx+40h], r8
0x180044ae8  mov     [rcx+48h], r8
0x180044aec  lea     r14, [rcx+50h]
0x180044af0  mov     [r14], r8
0x180044af3  mov     [r14+8], r8
0x180044af7  mov     [r14+10h], r8
0x180044afb  lea     r12, [rcx+68h]
0x180044aff  xorps   xmm0, xmm0
0x180044b02  movups  xmmword ptr [r12], xmm0
0x180044b07  mov     [r12+10h], r8
0x180044b0c  lea     edx, [r8+7]
0x180044b10  mov     [r12+18h], rdx
0x180044b15  mov     [r12], r8w
0x180044b1a  movups  xmmword ptr [rcx+88h], xmm0
0x180044b21  mov     [rcx+98h], r8
0x180044b28  mov     [rcx+0A0h], rdx
0x180044b2f  mov     [rcx+88h], r8w
0x180044b37  mov     dword ptr [rcx+0A8h], 210000h
0x180044b41  mov     rcx, [rbp+40h]; this
0x180044b45  mov     rax, [rbx+8]
0x180044b49  cmp     [rbx], rax
0x180044b4c  jz      loc_180044FCE
0x180044b52  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AMD_P384_EK_Cert@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AMD_P384_EK_Cert@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AMD_P384_EK_Cert> `wil::Feature<__WilFeatureTraits_Feature_AMD_P384_EK_Cert>::GetImpl(void)'::`2'::impl
0x180044b59  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AMD_P384_EK_Cert@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AMD_P384_EK_Cert>::__private_IsEnabled(void)
0x180044b5e  lea     rsi, aOnecoreBaseNgs_3; "onecore\\base\\ngscb\\tpmhli\\lib\\ekce"...
0x180044b65  xor     ecx, ecx
0x180044b67  test    al, al
0x180044b69  jz      short loc_180044BBD
0x180044b6b  mov     dword ptr [rbp+arg_8], ecx
0x180044b6e  mov     r9d, [rbx+8]
0x180044b72  sub     r9d, [rbx]; cbEncoded
0x180044b75  lea     rax, [rbp+arg_8]
0x180044b79  mov     [rsp+48h+pcbStructInfo], rax; pcbStructInfo
0x180044b7e  mov     [rsp+48h+pvStructInfo], rcx; pvStructInfo
0x180044b83  mov     [rsp+48h+pDecodePara], rcx; char *
0x180044b88  mov     [rsp+48h+dwFlags], ecx; dwFlags
0x180044b8c  mov     r8, [rbx]; pbEncoded
0x180044b8f  lea     edx, [rcx+1]; lpszStructType
0x180044b92  mov     ecx, 10001h; dwCertEncodingType
0x180044b97  call    cs:__imp_CryptDecodeObjectEx
0x180044b9d  mov     rcx, [rbp+40h]; this
0x180044ba1  lea     rdx, aEkCertificateD; "EK Certificate decoding error."
0x180044ba8  mov     qword ptr [rsp+48h+dwFlags], rdx; int
0x180044bad  mov     r9d, eax; char *
0x180044bb0  mov     r8, rsi; unsigned int
0x180044bb3  mov     edx, 12Ch; void *
0x180044bb8  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x180044bbd  mov     r8d, [rbx+8]
0x180044bc1  sub     r8d, [rbx]; cbCertEncoded
0x180044bc4  mov     rdx, [rbx]; pbCertEncoded
0x180044bc7  mov     ecx, 10001h; dwCertEncodingType
0x180044bcc  call    cs:__imp_CertCreateCertificateContext
0x180044bd2  mov     [rbp+arg_8], rax
0x180044bd6  lea     rdx, [rbp+arg_8]
0x180044bda  mov     rcx, rdi
0x180044bdd  call    ??4?$unique_any_t@Ucert_context_t@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::cert_context_t>::operator=(wil::unique_any_t<wil::cert_context_t> &&)
0x180044be2  lea     rcx, [rbp+arg_8]
0x180044be6  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x180044beb  mov     rax, [rdi]
0x180044bee  mov     rcx, [rbp+40h]; this
0x180044bf2  test    rax, rax
0x180044bf5  jz      loc_180044FE6
0x180044bfb  mov     rcx, [rbp+40h]; this
0x180044bff  mov     rax, [rax+18h]
0x180044c03  cmp     dword ptr [rax+0C0h], 1
0x180044c0a  jb      loc_180044FF1
0x180044c10  cmp     r14, rbx
0x180044c13  jz      short loc_180044C27
0x180044c15  mov     r8, [rbx+8]
0x180044c19  sub     r8, [rbx]
0x180044c1c  mov     rdx, [rbx]
0x180044c1f  mov     rcx, r14
0x180044c22  call    ??$_Assign_counted_range@PEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAXPEAE_K@Z; std::vector<uchar>::_Assign_counted_range<uchar *>(uchar *,unsigned __int64)
0x180044c27  mov     r14, [rdi]
0x180044c2a  mov     rax, [r14+18h]
0x180044c2e  mov     rbx, [rax+60h]
0x180044c32  mov     r8d, 0Eh; MaxCount
0x180044c38  lea     rdx, a12840113549; "1.2.840.113549"
0x180044c3f  mov     rcx, rbx; Str1
0x180044c42  call    strncmp_0
0x180044c47  test    eax, eax
0x180044c49  jnz     short loc_180044C5C
0x180044c4b  lea     ebx, [rax+1]
0x180044c4e  mov     [rdi+0A8h], ebx
0x180044c54  xor     r14d, r14d
0x180044c57  jmp     loc_180044D71
0x180044c5c  mov     r8d, 11h; MaxCount
0x180044c62  lea     rdx, a128401004521; "1.2.840.10045.2.1"
0x180044c69  mov     rcx, rbx; Str1
0x180044c6c  call    strncmp_0
0x180044c71  test    eax, eax
0x180044c73  jnz     loc_180044FB2
0x180044c79  mov     word ptr [rdi+0A8h], 23h ; '#'
0x180044c82  mov     [rbp+Str1], 0
0x180044c8a  mov     dword ptr [rbp+arg_8], 8
0x180044c91  mov     rdx, [r14+18h]
0x180044c95  lea     rax, [rbp+arg_8]
0x180044c99  mov     [rsp+48h+pvStructInfo], rax; pcbStructInfo
0x180044c9e  lea     rax, [rbp+Str1]
0x180044ca2  mov     [rsp+48h+pDecodePara], rax; pvStructInfo
0x180044ca7  mov     [rsp+48h+dwFlags], 4; dwFlags
0x180044caf  mov     r9d, [rdx+68h]; cbEncoded
0x180044cb3  mov     r8, [rdx+70h]; pbEncoded
0x180044cb7  mov     rdx, [rdx+60h]; lpszStructType
0x180044cbb  mov     ecx, 10001h; dwCertEncodingType
0x180044cc0  call    cs:__imp_CryptDecodeObject
0x180044cc6  xor     r14d, r14d
0x180044cc9  test    eax, eax
0x180044ccb  jz      loc_180044D63
0x180044cd1  lea     r8d, [r14+14h]; MaxCount
0x180044cd5  lea     rdx, a1284010045317; "1.2.840.10045.3.1.7"
0x180044cdc  mov     rbx, [rbp+Str1]
0x180044ce0  mov     rcx, rbx; Str1
0x180044ce3  call    strncmp_0
0x180044ce8  test    eax, eax
0x180044cea  jnz     short loc_180044CF7
0x180044cec  mov     word ptr [rdi+0AAh], 3
0x180044cf5  jmp     short loc_180044D6C
0x180044cf7  mov     r8d, 0Dh; MaxCount
0x180044cfd  lea     rdx, a13132034; "1.3.132.0.34"
0x180044d04  mov     rcx, rbx; Str1
0x180044d07  call    strncmp_0
0x180044d0c  test    eax, eax
0x180044d0e  jnz     short loc_180044D1B
0x180044d10  mov     word ptr [rdi+0AAh], 4
0x180044d19  jmp     short loc_180044D6C
0x180044d1b  mov     r8d, 0Dh; MaxCount
0x180044d21  lea     rdx, a13132035; "1.3.132.0.35"
0x180044d28  mov     rcx, rbx; Str1
0x180044d2b  call    strncmp_0
0x180044d30  test    eax, eax
0x180044d32  jnz     short loc_180044D3F
0x180044d34  mov     word ptr [rdi+0AAh], 5
0x180044d3d  jmp     short loc_180044D6C
0x180044d3f  mov     r8d, 14h; MaxCount
0x180044d45  lea     rdx, a12156101971301; "1.2.156.10197.1.301"
0x180044d4c  mov     rcx, rbx; Str1
0x180044d4f  call    strncmp_0
0x180044d54  test    eax, eax
0x180044d56  jnz     short loc_180044D63
0x180044d58  mov     word ptr [rdi+0AAh], 20h ; ' '
0x180044d61  jmp     short loc_180044D6C
0x180044d63  mov     word ptr [rdi+0AAh], 21h ; '!'
0x180044d6c  mov     ebx, 1
0x180044d71  mov     rax, [rdi]
0x180044d74  mov     rdx, [rax+18h]
0x180044d78  mov     r8, [rdx+0C8h]; rgExtensions
0x180044d7f  mov     edx, [rdx+0C0h]; cExtensions
0x180044d85  lea     rcx, pszObjId; "2.5.29.35"
0x180044d8c  call    cs:__imp_CertFindExtension
0x180044d92  test    rax, rax
0x180044d95  jz      short loc_180044E05
0x180044d97  mov     [rbp+Str1], r14
0x180044d9b  mov     [rbp+arg_18], r14
0x180044d9f  mov     dword ptr [rbp+arg_8], r14d
0x180044da3  lea     rcx, [rbp+arg_8]
0x180044da7  mov     [rsp+48h+pvStructInfo], rcx; pcbStructInfo
0x180044dac  lea     rcx, [rbp+Str1]
0x180044db0  mov     [rsp+48h+pDecodePara], rcx; pvStructInfo
0x180044db5  mov     [rsp+48h+dwFlags], 8001h; dwFlags
0x180044dbd  mov     r9d, [rax+10h]; cbEncoded
0x180044dc1  mov     r8, [rax+18h]; pbEncoded
0x180044dc5  mov     edx, 1Fh; lpszStructType
0x180044dca  mov     ecx, ebx; dwCertEncodingType
0x180044dcc  call    cs:__imp_CryptDecodeObject
0x180044dd2  mov     rcx, [rbp+40h]; this
0x180044dd6  test    eax, eax
0x180044dd8  jz      loc_180045005
0x180044dde  mov     rbx, [rbp+Str1]
0x180044de2  mov     [rbp+arg_18], rbx
0x180044de6  mov     r8d, [rbx]
0x180044de9  mov     rdx, [rbx+8]
0x180044ded  lea     rcx, [rdi+8]
0x180044df1  call    ??$_Assign_counted_range@PEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAXPEAE_K@Z; std::vector<uchar>::_Assign_counted_range<uchar *>(uchar *,unsigned __int64)
0x180044df6  nop
0x180044df7  test    rbx, rbx
0x180044dfa  jz      short loc_180044E05
0x180044dfc  mov     rcx, rbx; hMem
0x180044dff  call    cs:__imp_LocalFree
0x180044e05  mov     rax, [rdi]
0x180044e08  mov     rdx, [rax+18h]
0x180044e0c  mov     r8, [rdx+0C8h]; rgExtensions
0x180044e13  mov     edx, [rdx+0C0h]; cExtensions
0x180044e19  lea     rcx, szStructType; "2.5.29.14"
0x180044e20  call    cs:__imp_CertFindExtension
0x180044e26  test    rax, rax
0x180044e29  jz      short loc_180044E9E
0x180044e2b  mov     [rbp+Str1], r14
0x180044e2f  mov     [rbp+arg_18], r14
0x180044e33  mov     dword ptr [rbp+arg_8], r14d
0x180044e37  lea     rcx, [rbp+arg_8]
0x180044e3b  mov     [rsp+48h+pvStructInfo], rcx; pcbStructInfo
0x180044e40  lea     rcx, [rbp+Str1]
0x180044e44  mov     [rsp+48h+pDecodePara], rcx; pvStructInfo
0x180044e49  mov     [rsp+48h+dwFlags], 8001h; dwFlags
0x180044e51  mov     r9d, [rax+10h]; cbEncoded
0x180044e55  mov     r8, [rax+18h]; pbEncoded
0x180044e59  lea     rdx, szStructType; "2.5.29.14"
0x180044e60  mov     ecx, 1; dwCertEncodingType
0x180044e65  call    cs:__imp_CryptDecodeObject
0x180044e6b  mov     rcx, [rbp+40h]; this
0x180044e6f  test    eax, eax
0x180044e71  jz      loc_180045010
0x180044e77  mov     rbx, [rbp+Str1]
0x180044e7b  mov     [rbp+arg_18], rbx
0x180044e7f  mov     r8d, [rbx]
0x180044e82  mov     rdx, [rbx+8]
0x180044e86  lea     rcx, [rdi+20h]
0x180044e8a  call    ??$_Assign_counted_range@PEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAXPEAE_K@Z; std::vector<uchar>::_Assign_counted_range<uchar *>(uchar *,unsigned __int64)
0x180044e8f  nop
0x180044e90  test    rbx, rbx
0x180044e93  jz      short loc_180044E9E
0x180044e95  mov     rcx, rbx; hMem
0x180044e98  call    cs:__imp_LocalFree
0x180044e9e  mov     dword ptr [rsp+48h+pDecodePara], r14d; cchNameString
0x180044ea3  mov     qword ptr [rsp+48h+dwFlags], r14; int
0x180044ea8  lea     r15, a2543; "2.5.4.3"
0x180044eaf  mov     r9, r15; pvTypePara
0x180044eb2  mov     ebx, 1
0x180044eb7  mov     r8d, ebx; dwFlags
0x180044eba  lea     r13d, [rbx+3]
0x180044ebe  mov     edx, r13d; dwType
0x180044ec1  mov     rcx, [rdi]; pCertContext
0x180044ec4  call    cs:__imp_CertGetNameStringW
0x180044eca  mov     rcx, [rbp+40h]; this
0x180044ece  cmp     eax, 2
0x180044ed1  jb      loc_18004501B
0x180044ed7  mov     edx, eax
0x180044ed9  mov     rcx, r12
0x180044edc  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180044ee1  mov     rcx, r12
0x180044ee4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180044ee9  mov     ecx, [rdi+78h]
0x180044eec  mov     dword ptr [rsp+48h+pDecodePara], ecx; cchNameString
0x180044ef0  mov     qword ptr [rsp+48h+dwFlags], rax; int
0x180044ef5  mov     r9, r15; pvTypePara
0x180044ef8  mov     r8d, ebx; dwFlags
0x180044efb  mov     edx, r13d; dwType
0x180044efe  mov     rcx, [rdi]; pCertContext
0x180044f01  call    cs:__imp_CertGetNameStringW
0x180044f07  mov     rcx, [rbp+40h]; this
0x180044f0b  cmp     eax, 2
0x180044f0e  jb      loc_18004502F
0x180044f14  mov     dword ptr [rsp+48h+pDecodePara], eax; cchNameString
0x180044f18  mov     qword ptr [rsp+48h+dwFlags], r14; pszNameString
0x180044f1d  mov     r9, r15; pvTypePara
0x180044f20  xor     r8d, r8d; dwFlags
0x180044f23  mov     edx, r13d; dwType
0x180044f26  mov     rcx, [rdi]; pCertContext
0x180044f29  call    cs:__imp_CertGetNameStringW
0x180044f2f  mov     ebx, eax
0x180044f31  mov     edx, eax
0x180044f33  lea     r14, [rdi+88h]
0x180044f3a  mov     rcx, r14
0x180044f3d  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180044f42  mov     rcx, r14
0x180044f45  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180044f4a  mov     r14, [rbp+40h]
0x180044f4e  mov     dword ptr [rsp+48h+pDecodePara], ebx; cchNameString
0x180044f52  mov     qword ptr [rsp+48h+dwFlags], rax; int
0x180044f57  mov     r9, r15; pvTypePara
0x180044f5a  xor     r8d, r8d; dwFlags
0x180044f5d  mov     edx, r13d; dwType
0x180044f60  mov     rcx, [rdi]; pCertContext
0x180044f63  call    cs:__imp_CertGetNameStringW
0x180044f69  cmp     eax, 2
0x180044f6c  jb      short loc_180044F9B
0x180044f6e  mov     rax, [rdi]
0x180044f71  mov     rdx, [rax+18h]
0x180044f75  mov     r8d, [rdx+8]
0x180044f79  mov     rdx, [rdx+10h]
0x180044f7d  lea     rcx, [rdi+38h]
0x180044f81  call    ??$_Assign_counted_range@PEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAXPEAE_K@Z; std::vector<uchar>::_Assign_counted_range<uchar *>(uchar *,unsigned __int64)
0x180044f86  nop
0x180044f87  mov     rax, rdi
0x180044f8a  add     rsp, 48h
0x180044f8e  pop     r15
0x180044f90  pop     r14
  ... truncated ...
```
