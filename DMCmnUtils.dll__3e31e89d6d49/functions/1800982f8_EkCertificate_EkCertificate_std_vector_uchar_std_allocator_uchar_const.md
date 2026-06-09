# EkCertificate::EkCertificate(std::vector<uchar,std::allocator<uchar>> const &)

- ea: `0x1800982f8`
- end: `0x18009890d`
- name: `??0EkCertificate@@QEAA@AEBV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `1557`
- prototype: ``
- caller_count: `4`
- callee_count: `13`
- tags: `registry_config, loader_planting`

## callers

- `0x180097f70`
- `0x180097fbc`
- `0x180098284`
- `0x180099274`

## callees

- `0x180053990`
- `0x18005bb6c`
- `0x18005bb94`
- `0x180097e08`
- `0x1800982f8`
- `0x180098978`
- `0x180098a68`
- `0x180099820`
- `0x180099950`
- `0x180099a00`
- `0x180099ab0`
- `0x180099b38`
- `0x1800b2684`

## import_xrefs

- `CRYPT32!CertFindExtension` at `0x1800985ee`
- `CRYPT32!CertFindExtension` at `0x1800986a7`
- `CRYPT32!CertFindExtension` at `0x1800985ee`
- `CRYPT32!CertFindExtension` at `0x1800986a7`
- `CRYPT32!CryptDecodeObject` at `0x18009851c`
- `CRYPT32!CryptDecodeObject` at `0x180098638`
- `CRYPT32!CryptDecodeObject` at `0x1800986f3`
- `CRYPT32!CryptDecodeObject` at `0x18009851c`
- `CRYPT32!CryptDecodeObject` at `0x180098638`
- `CRYPT32!CryptDecodeObject` at `0x1800986f3`
- `CRYPT32!CertCreateCertificateContext` at `0x180098422`
- `CRYPT32!CertCreateCertificateContext` at `0x180098422`
- `CRYPT32!CryptDecodeObjectEx` at `0x1800983e7`
- `CRYPT32!CryptDecodeObjectEx` at `0x1800983e7`
- `CRYPT32!CertGetNameStringW` at `0x180098766`
- `CRYPT32!CertGetNameStringW` at `0x1800987b2`
- `CRYPT32!CertGetNameStringW` at `0x1800987e0`
- `CRYPT32!CertGetNameStringW` at `0x180098823`
- `CRYPT32!CertGetNameStringW` at `0x180098766`
- `CRYPT32!CertGetNameStringW` at `0x1800987b2`
- `CRYPT32!CertGetNameStringW` at `0x1800987e0`
- `CRYPT32!CertGetNameStringW` at `0x180098823`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 *__fastcall EkCertificate::EkCertificate(__int64 *a1, _QWORD *a2)
{
  _QWORD *v4; // r14
  __int64 *v5; // r15
  unsigned int v6; // eax
  unsigned int v7; // r8d
  const char *v8; // r9
  __int64 v9; // r14
  const char *v10; // rbx
  char *v11; // rbx
  PCERT_EXTENSION Extension; // rax
  unsigned int v13; // r8d
  const char *v14; // r9
  PCERT_EXTENSION v15; // rax
  unsigned int v16; // r8d
  const char *v17; // r9
  DWORD NameStringW; // eax
  WCHAR *v19; // rax
  DWORD v20; // eax
  __int64 v21; // rbx
  WCHAR *v22; // rax
  unsigned int v24; // eax
  int dwFlags; // [rsp+20h] [rbp-38h]
  int dwFlagsa; // [rsp+20h] [rbp-38h]
  int dwFlagsb; // [rsp+20h] [rbp-38h]
  int dwFlagsc; // [rsp+20h] [rbp-38h]
  const char *pDecodePara; // [rsp+28h] [rbp-30h]
  _QWORD v30[3]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]
  PCCERT_CONTEXT pcbStructInfo; // [rsp+A8h] [rbp+50h] BYREF
  char *Str1; // [rsp+B0h] [rbp+58h] BYREF
  __int64 v34; // [rsp+B8h] [rbp+60h] BYREF

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
    wil::details::in1diag3::Throw_Hr(
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
    v24 = wil::verify_hresult<long>(2148077570LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x170,
      (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\ekcert.cpp",
      (const char *)v24,
      dwFlags);
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
    v34 = 0;
    Str1 = 0;
    LODWORD(pcbStructInfo) = 0;
    if ( !CryptDecodeObject(
            1u,
            (LPCSTR)0x1F,
            Extension->Value.pbData,
            Extension->Value.cbData,
            0x8001u,
            &v34,
            (DWORD *)&pcbStructInfo) )
      wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x189, v13, v14);
    v30[0] = 0;
    wistd::unique_ptr<_CRYPTOAPI_BLOB,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
      &Str1,
      v34);
    wistd::unique_ptr<_CRYPTOAPI_BLOB,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
      v30,
      0);
    std::vector<unsigned char>::_Assign_counted_range<unsigned char *>(
      a1 + 1,
      *((_QWORD *)Str1 + 1),
      *(unsigned int *)Str1);
    wistd::unique_ptr<_CRYPTOAPI_BLOB,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
      &Str1,
      0);
  }
  v15 = CertFindExtension(
          "2.5.29.14",
          *(_DWORD *)(*(_QWORD *)(*a1 + 24) + 192LL),
          *(CERT_EXTENSION **)(*(_QWORD *)(*a1 + 24) + 200LL));
  if ( v15 )
  {
    v34 = 0;
    Str1 = 0;
    LODWORD(pcbStructInfo) = 0;
    if ( !CryptDecodeObject(
            1u,
            "2.5.29.14",
            v15->Value.pbData,
            v15->Value.cbData,
            0x8001u,
            &v34,
            (DWORD *)&pcbStructInfo) )
      wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x1A6, v16, v17);
    v30[0] = 0;
    wistd::unique_ptr<_CRYPTOAPI_BLOB,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
      &Str1,
      v34);
    wistd::unique_ptr<_CRYPTOAPI_BLOB,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
      v30,
      0);
    std::vector<unsigned char>::_Assign_counted_range<unsigned char *>(
      a1 + 4,
      *((_QWORD *)Str1 + 1),
      *(unsigned int *)Str1);
    wistd::unique_ptr<_CRYPTOAPI_BLOB,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
      &Str1,
      0);
  }
  NameStringW = CertGetNameStringW((PCCERT_CONTEXT)*a1, 4u, 1u, "2.5.4.3", 0, 0);
  if ( NameStringW < 2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1B8,
      (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\ekcert.cpp",
      (const char *)0x800B0108LL,
      dwFlagsa);
  std::wstring::resize(v5, NameStringW, 0);
  v19 = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v5);
  v20 = CertGetNameStringW((PCCERT_CONTEXT)*a1, 4u, 1u, "2.5.4.3", v19, *((_DWORD *)a1 + 30));
  if ( v20 < 2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\ekcert.cpp",
      (const char *)0x800B0108LL,
      dwFlagsb);
  v21 = CertGetNameStringW((PCCERT_CONTEXT)*a1, 4u, 0, "2.5.4.3", 0, v20);
  std::wstring::resize(a1 + 17, v21, 0);
  v22 = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 17);
  if ( CertGetNameStringW((PCCERT_CONTEXT)*a1, 4u, 0, "2.5.4.3", v22, v21) < 2 )
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
0x1800982f8  mov     [rsp-40h+arg_0], rcx
0x1800982fd  push    rbp
0x1800982fe  push    rbx
0x1800982ff  push    rsi
0x180098300  push    rdi
0x180098301  push    r12
0x180098303  push    r13
0x180098305  push    r14
0x180098307  push    r15
0x180098309  mov     rbp, rsp
0x18009830c  sub     rsp, 58h
0x180098310  mov     rbx, rdx
0x180098313  mov     rdi, rcx
0x180098316  xor     r8d, r8d
0x180098319  mov     [rcx], r8
0x18009831c  mov     [rcx+8], r8
0x180098320  mov     [rcx+10h], r8
0x180098324  mov     [rcx+18h], r8
0x180098328  mov     [rcx+20h], r8
0x18009832c  mov     [rcx+28h], r8
0x180098330  mov     [rcx+30h], r8
0x180098334  mov     [rcx+38h], r8
0x180098338  mov     [rcx+40h], r8
0x18009833c  mov     [rcx+48h], r8
0x180098340  lea     r14, [rcx+50h]
0x180098344  mov     [r14], r8
0x180098347  mov     [r14+8], r8
0x18009834b  mov     [r14+10h], r8
0x18009834f  lea     r15, [rcx+68h]
0x180098353  xorps   xmm0, xmm0
0x180098356  movups  xmmword ptr [r15], xmm0
0x18009835a  mov     [r15+10h], r8
0x18009835e  lea     edx, [r8+7]
0x180098362  mov     [r15+18h], rdx
0x180098366  mov     [r15], r8w
0x18009836a  movups  xmmword ptr [rcx+88h], xmm0
0x180098371  mov     [rcx+98h], r8
0x180098378  mov     [rcx+0A0h], rdx
0x18009837f  mov     [rcx+88h], r8w
0x180098387  mov     dword ptr [rcx+0A8h], 210000h
0x180098391  mov     rcx, [rbp+40h]; this
0x180098395  mov     rax, [rbx+8]
0x180098399  cmp     [rbx], rax
0x18009839c  jz      loc_180098898
0x1800983a2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AMD_P384_EK_Cert@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AMD_P384_EK_Cert@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AMD_P384_EK_Cert> `wil::Feature<__WilFeatureTraits_Feature_AMD_P384_EK_Cert>::GetImpl(void)'::`2'::impl
0x1800983a9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AMD_P384_EK_Cert@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AMD_P384_EK_Cert>::__private_IsEnabled(void)
0x1800983ae  lea     rsi, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\tpmhli\\lib\\ekce"...
0x1800983b5  xor     ecx, ecx
0x1800983b7  test    al, al
0x1800983b9  jz      short loc_180098413
0x1800983bb  mov     dword ptr [rbp+arg_8], ecx
0x1800983be  mov     r9d, [rbx+8]
0x1800983c2  sub     r9d, [rbx]; cbEncoded
0x1800983c5  lea     rax, [rbp+arg_8]
0x1800983c9  mov     [rsp+58h+pcbStructInfo], rax; pcbStructInfo
0x1800983ce  mov     [rsp+58h+pvStructInfo], rcx; pvStructInfo
0x1800983d3  mov     [rsp+58h+pDecodePara], rcx; char *
0x1800983d8  mov     [rsp+58h+dwFlags], ecx; dwFlags
0x1800983dc  mov     r8, [rbx]; pbEncoded
0x1800983df  lea     edx, [rcx+1]; lpszStructType
0x1800983e2  mov     ecx, 10001h; dwCertEncodingType
0x1800983e7  call    cs:__imp_CryptDecodeObjectEx
0x1800983ee  nop     dword ptr [rax+rax+00h]
0x1800983f3  mov     rcx, [rbp+40h]; this
0x1800983f7  lea     rdx, aEkCertificateD; "EK Certificate decoding error."
0x1800983fe  mov     qword ptr [rsp+58h+dwFlags], rdx; int
0x180098403  mov     r9d, eax; char *
0x180098406  mov     r8, rsi; unsigned int
0x180098409  mov     edx, 12Ch; void *
0x18009840e  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x180098413  mov     r8d, [rbx+8]
0x180098417  sub     r8d, [rbx]; cbCertEncoded
0x18009841a  mov     rdx, [rbx]; pbCertEncoded
0x18009841d  mov     ecx, 10001h; dwCertEncodingType
0x180098422  call    cs:__imp_CertCreateCertificateContext
0x180098429  nop     dword ptr [rax+rax+00h]
0x18009842e  mov     [rbp+arg_8], rax
0x180098432  lea     rdx, [rbp+arg_8]
0x180098436  mov     rcx, rdi
0x180098439  call    ??4?$unique_any_t@Ucert_context_t@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::cert_context_t>::operator=(wil::unique_any_t<wil::cert_context_t> &&)
0x18009843e  lea     rcx, [rbp+arg_8]
0x180098442  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x180098447  mov     rax, [rdi]
0x18009844a  mov     rcx, [rbp+40h]; this
0x18009844e  test    rax, rax
0x180098451  jz      loc_1800988B0
0x180098457  mov     rcx, [rbp+40h]; this
0x18009845b  mov     rax, [rax+18h]
0x18009845f  cmp     dword ptr [rax+0C0h], 1
0x180098466  jb      loc_1800988BB
0x18009846c  cmp     r14, rbx
0x18009846f  jz      short loc_180098483
0x180098471  mov     r8, [rbx+8]
0x180098475  sub     r8, [rbx]
0x180098478  mov     rdx, [rbx]
0x18009847b  mov     rcx, r14
0x18009847e  call    ??$_Assign_counted_range@PEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAXPEAE_K@Z; std::vector<uchar>::_Assign_counted_range<uchar *>(uchar *,unsigned __int64)
0x180098483  mov     r14, [rdi]
0x180098486  mov     rax, [r14+18h]
0x18009848a  mov     rbx, [rax+60h]
0x18009848e  mov     r8d, 0Eh; MaxCount
0x180098494  lea     rdx, Str2; "1.2.840.113549"
0x18009849b  mov     rcx, rbx; Str1
0x18009849e  call    strncmp_0
0x1800984a3  test    eax, eax
0x1800984a5  jnz     short loc_1800984B8
0x1800984a7  lea     ebx, [rax+1]
0x1800984aa  mov     [rdi+0A8h], ebx
0x1800984b0  xor     r14d, r14d
0x1800984b3  jmp     loc_1800985D3
0x1800984b8  mov     r8d, 11h; MaxCount
0x1800984be  lea     rdx, a128401004521; "1.2.840.10045.2.1"
0x1800984c5  mov     rcx, rbx; Str1
0x1800984c8  call    strncmp_0
0x1800984cd  test    eax, eax
0x1800984cf  jnz     loc_180098879
0x1800984d5  mov     word ptr [rdi+0A8h], 23h ; '#'
0x1800984de  mov     [rbp+Str1], 0
0x1800984e6  mov     dword ptr [rbp+arg_8], 8
0x1800984ed  mov     rdx, [r14+18h]
0x1800984f1  lea     rax, [rbp+arg_8]
0x1800984f5  mov     [rsp+58h+pvStructInfo], rax; pcbStructInfo
0x1800984fa  lea     rax, [rbp+Str1]
0x1800984fe  mov     [rsp+58h+pDecodePara], rax; pvStructInfo
0x180098503  mov     [rsp+58h+dwFlags], 4; dwFlags
0x18009850b  mov     r9d, [rdx+68h]; cbEncoded
0x18009850f  mov     r8, [rdx+70h]; pbEncoded
0x180098513  mov     rdx, [rdx+60h]; lpszStructType
0x180098517  mov     ecx, 10001h; dwCertEncodingType
0x18009851c  call    cs:__imp_CryptDecodeObject
0x180098523  nop     dword ptr [rax+rax+00h]
0x180098528  xor     r14d, r14d
0x18009852b  test    eax, eax
0x18009852d  jz      loc_1800985C5
0x180098533  lea     r8d, [r14+14h]; MaxCount
0x180098537  lea     rdx, a1284010045317; "1.2.840.10045.3.1.7"
0x18009853e  mov     rbx, [rbp+Str1]
0x180098542  mov     rcx, rbx; Str1
0x180098545  call    strncmp_0
0x18009854a  test    eax, eax
0x18009854c  jnz     short loc_180098559
0x18009854e  mov     word ptr [rdi+0AAh], 3
0x180098557  jmp     short loc_1800985CE
0x180098559  mov     r8d, 0Dh; MaxCount
0x18009855f  lea     rdx, a13132034; "1.3.132.0.34"
0x180098566  mov     rcx, rbx; Str1
0x180098569  call    strncmp_0
0x18009856e  test    eax, eax
0x180098570  jnz     short loc_18009857D
0x180098572  mov     word ptr [rdi+0AAh], 4
0x18009857b  jmp     short loc_1800985CE
0x18009857d  mov     r8d, 0Dh; MaxCount
0x180098583  lea     rdx, a13132035; "1.3.132.0.35"
0x18009858a  mov     rcx, rbx; Str1
0x18009858d  call    strncmp_0
0x180098592  test    eax, eax
0x180098594  jnz     short loc_1800985A1
0x180098596  mov     word ptr [rdi+0AAh], 5
0x18009859f  jmp     short loc_1800985CE
0x1800985a1  mov     r8d, 14h; MaxCount
0x1800985a7  lea     rdx, a12156101971301; "1.2.156.10197.1.301"
0x1800985ae  mov     rcx, rbx; Str1
0x1800985b1  call    strncmp_0
0x1800985b6  test    eax, eax
0x1800985b8  jnz     short loc_1800985C5
0x1800985ba  mov     word ptr [rdi+0AAh], 20h ; ' '
0x1800985c3  jmp     short loc_1800985CE
0x1800985c5  mov     word ptr [rdi+0AAh], 21h ; '!'
0x1800985ce  mov     ebx, 1
0x1800985d3  mov     rax, [rdi]
0x1800985d6  mov     rdx, [rax+18h]
0x1800985da  mov     r8, [rdx+0C8h]; rgExtensions
0x1800985e1  mov     edx, [rdx+0C0h]; cExtensions
0x1800985e7  lea     rcx, pszObjId; "2.5.29.35"
0x1800985ee  call    cs:__imp_CertFindExtension
0x1800985f5  nop     dword ptr [rax+rax+00h]
0x1800985fa  test    rax, rax
0x1800985fd  jz      loc_18009868C
0x180098603  mov     [rbp+arg_18], r14
0x180098607  mov     [rbp+Str1], r14
0x18009860b  mov     dword ptr [rbp+arg_8], r14d
0x18009860f  lea     rcx, [rbp+arg_8]
0x180098613  mov     [rsp+58h+pvStructInfo], rcx; pcbStructInfo
0x180098618  lea     rcx, [rbp+arg_18]
0x18009861c  mov     [rsp+58h+pDecodePara], rcx; pvStructInfo
0x180098621  mov     [rsp+58h+dwFlags], 8001h; dwFlags
0x180098629  mov     r9d, [rax+10h]; cbEncoded
0x18009862d  mov     r8, [rax+18h]; pbEncoded
0x180098631  mov     edx, 1Fh; lpszStructType
0x180098636  mov     ecx, ebx; dwCertEncodingType
0x180098638  call    cs:__imp_CryptDecodeObject
0x18009863f  nop     dword ptr [rax+rax+00h]
0x180098644  mov     rcx, [rbp+40h]; this
0x180098648  test    eax, eax
0x18009864a  jz      loc_1800988CF
0x180098650  mov     [rbp+var_18], r14
0x180098654  mov     rdx, [rbp+arg_18]
0x180098658  lea     rcx, [rbp+Str1]
0x18009865c  call    ?reset@?$unique_ptr@U_CRYPTOAPI_BLOB@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAU_CRYPTOAPI_BLOB@@@Z; wistd::unique_ptr<_CRYPTOAPI_BLOB,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(_CRYPTOAPI_BLOB *)
0x180098661  xor     edx, edx
0x180098663  lea     rcx, [rbp+var_18]
0x180098667  call    ?reset@?$unique_ptr@U_CRYPTOAPI_BLOB@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAU_CRYPTOAPI_BLOB@@@Z; wistd::unique_ptr<_CRYPTOAPI_BLOB,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(_CRYPTOAPI_BLOB *)
0x18009866c  mov     rdx, [rbp+Str1]
0x180098670  mov     r8d, [rdx]
0x180098673  mov     rdx, [rdx+8]
0x180098677  lea     rcx, [rdi+8]
0x18009867b  call    ??$_Assign_counted_range@PEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAXPEAE_K@Z; std::vector<uchar>::_Assign_counted_range<uchar *>(uchar *,unsigned __int64)
0x180098680  nop
0x180098681  xor     edx, edx
0x180098683  lea     rcx, [rbp+Str1]
0x180098687  call    ?reset@?$unique_ptr@U_CRYPTOAPI_BLOB@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAU_CRYPTOAPI_BLOB@@@Z; wistd::unique_ptr<_CRYPTOAPI_BLOB,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(_CRYPTOAPI_BLOB *)
0x18009868c  mov     rax, [rdi]
0x18009868f  mov     rdx, [rax+18h]
0x180098693  mov     r8, [rdx+0C8h]; rgExtensions
0x18009869a  mov     edx, [rdx+0C0h]; cExtensions
0x1800986a0  lea     rcx, a252914; "2.5.29.14"
0x1800986a7  call    cs:__imp_CertFindExtension
0x1800986ae  nop     dword ptr [rax+rax+00h]
0x1800986b3  test    rax, rax
0x1800986b6  jz      loc_180098747
0x1800986bc  mov     [rbp+arg_18], r14
0x1800986c0  mov     [rbp+Str1], r14
0x1800986c4  mov     dword ptr [rbp+arg_8], r14d
0x1800986c8  lea     rcx, [rbp+arg_8]
0x1800986cc  mov     [rsp+58h+pvStructInfo], rcx; pcbStructInfo
0x1800986d1  lea     rcx, [rbp+arg_18]
0x1800986d5  mov     [rsp+58h+pDecodePara], rcx; pvStructInfo
0x1800986da  mov     [rsp+58h+dwFlags], 8001h; dwFlags
0x1800986e2  mov     r9d, [rax+10h]; cbEncoded
0x1800986e6  mov     r8, [rax+18h]; pbEncoded
0x1800986ea  lea     rdx, a252914; "2.5.29.14"
0x1800986f1  mov     ecx, ebx; dwCertEncodingType
0x1800986f3  call    cs:__imp_CryptDecodeObject
0x1800986fa  nop     dword ptr [rax+rax+00h]
0x1800986ff  mov     rcx, [rbp+40h]; this
0x180098703  test    eax, eax
0x180098705  jz      loc_1800988DA
0x18009870b  mov     [rbp+var_18], r14
0x18009870f  mov     rdx, [rbp+arg_18]
0x180098713  lea     rcx, [rbp+Str1]
0x180098717  call    ?reset@?$unique_ptr@U_CRYPTOAPI_BLOB@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAU_CRYPTOAPI_BLOB@@@Z; wistd::unique_ptr<_CRYPTOAPI_BLOB,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(_CRYPTOAPI_BLOB *)
0x18009871c  xor     edx, edx
0x18009871e  lea     rcx, [rbp+var_18]
0x180098722  call    ?reset@?$unique_ptr@U_CRYPTOAPI_BLOB@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAU_CRYPTOAPI_BLOB@@@Z; wistd::unique_ptr<_CRYPTOAPI_BLOB,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(_CRYPTOAPI_BLOB *)
0x180098727  mov     rdx, [rbp+Str1]
0x18009872b  mov     r8d, [rdx]
0x18009872e  mov     rdx, [rdx+8]
0x180098732  lea     rcx, [rdi+20h]
0x180098736  call    ??$_Assign_counted_range@PEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAXPEAE_K@Z; std::vector<uchar>::_Assign_counted_range<uchar *>(uchar *,unsigned __int64)
0x18009873b  nop
0x18009873c  xor     edx, edx
0x18009873e  lea     rcx, [rbp+Str1]
0x180098742  call    ?reset@?$unique_ptr@U_CRYPTOAPI_BLOB@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAU_CRYPTOAPI_BLOB@@@Z; wistd::unique_ptr<_CRYPTOAPI_BLOB,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(_CRYPTOAPI_BLOB *)
0x180098747  mov     dword ptr [rsp+58h+pDecodePara], r14d; cchNameString
0x18009874c  mov     qword ptr [rsp+58h+dwFlags], r14; int
0x180098751  lea     r12, a2543; "2.5.4.3"
0x180098758  mov     r9, r12; pvTypePara
0x18009875b  mov     r8d, ebx; dwFlags
0x18009875e  mov     edx, 4; dwType
0x180098763  mov     rcx, [rdi]; pCertContext
0x180098766  call    cs:__imp_CertGetNameStringW
0x18009876d  nop     dword ptr [rax+rax+00h]
0x180098772  mov     rcx, [rbp+40h]; this
0x180098776  cmp     eax, 2
0x180098779  jb      loc_1800988E5
0x18009877f  xor     r8d, r8d
0x180098782  mov     edx, eax
0x180098784  mov     rcx, r15
0x180098787  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18009878c  mov     rcx, r15
0x18009878f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180098794  mov     ecx, [rdi+78h]
0x180098797  mov     dword ptr [rsp+58h+pDecodePara], ecx; cchNameString
0x18009879b  mov     qword ptr [rsp+58h+dwFlags], rax; int
0x1800987a0  mov     r9, r12; pvTypePara
0x1800987a3  mov     r8d, ebx; dwFlags
0x1800987a6  mov     r15d, 4
0x1800987ac  mov     edx, r15d; dwType
0x1800987af  mov     rcx, [rdi]; pCertContext
0x1800987b2  call    cs:__imp_CertGetNameStringW
0x1800987b9  nop     dword ptr [rax+rax+00h]
0x1800987be  mov     rcx, [rbp+40h]; this
0x1800987c2  cmp     eax, 2
0x1800987c5  jb      loc_1800988F9
0x1800987cb  mov     dword ptr [rsp+58h+pDecodePara], eax; cchNameString
0x1800987cf  mov     qword ptr [rsp+58h+dwFlags], r14; pszNameString
0x1800987d4  mov     r9, r12; pvTypePara
0x1800987d7  xor     r8d, r8d; dwFlags
0x1800987da  mov     edx, r15d; dwType
0x1800987dd  mov     rcx, [rdi]; pCertContext
0x1800987e0  call    cs:__imp_CertGetNameStringW
0x1800987e7  nop     dword ptr [rax+rax+00h]
0x1800987ec  mov     ebx, eax
0x1800987ee  xor     r8d, r8d
0x1800987f1  mov     edx, eax
0x1800987f3  lea     r14, [rdi+88h]
0x1800987fa  mov     rcx, r14
0x1800987fd  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180098802  mov     rcx, r14
0x180098805  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
  ... truncated ...
```
