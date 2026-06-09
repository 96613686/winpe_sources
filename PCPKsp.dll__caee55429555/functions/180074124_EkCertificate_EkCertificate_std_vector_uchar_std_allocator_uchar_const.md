# EkCertificate::EkCertificate(std::vector<uchar,std::allocator<uchar>> const &)

- ea: `0x180074124`
- end: `0x180074713`
- name: `??0EkCertificate@@QEAA@AEBV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `1519`
- prototype: ``
- caller_count: `6`
- callee_count: `11`
- tags: `registry_config, loader_planting`

## callers

- `0x180090de8`
- `0x18009108c`
- `0x180091f6c`
- `0x1800c1d20`
- `0x1800c1db8`
- `0x1800c2650`

## callees

- `0x180023764`
- `0x18005b6fc`
- `0x180068eb8`
- `0x18006d3ec`
- `0x180074124`
- `0x18007471c`
- `0x1800c1d7c`
- `0x1800c293c`
- `0x1800c29ac`
- `0x1800c2a24`
- `0x1800c2cd4`

## import_xrefs

- `CRYPT32!CryptDecodeObjectEx` at `0x180074226`
- `CRYPT32!CryptDecodeObjectEx` at `0x180074226`
- `CRYPT32!CryptDecodeObject` at `0x180074371`
- `CRYPT32!CryptDecodeObject` at `0x180074498`
- `CRYPT32!CryptDecodeObject` at `0x18007455b`
- `CRYPT32!CryptDecodeObject` at `0x180074371`
- `CRYPT32!CryptDecodeObject` at `0x180074498`
- `CRYPT32!CryptDecodeObject` at `0x18007455b`
- `CRYPT32!CertFindExtension` at `0x18007444d`
- `CRYPT32!CertFindExtension` at `0x18007450e`
- `CRYPT32!CertFindExtension` at `0x18007444d`
- `CRYPT32!CertFindExtension` at `0x18007450e`
- `CRYPT32!CertGetNameStringW` at `0x1800745d5`
- `CRYPT32!CertGetNameStringW` at `0x18007462c`
- `CRYPT32!CertGetNameStringW` at `0x180074669`
- `CRYPT32!CertGetNameStringW` at `0x1800746a5`
- `CRYPT32!CertGetNameStringW` at `0x1800745d5`
- `CRYPT32!CertGetNameStringW` at `0x18007462c`
- `CRYPT32!CertGetNameStringW` at `0x180074669`
- `CRYPT32!CertGetNameStringW` at `0x1800746a5`
- `CRYPT32!CertCreateCertificateContext` at `0x180074261`
- `CRYPT32!CertCreateCertificateContext` at `0x180074261`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 *__fastcall EkCertificate::EkCertificate(__int64 *a1, _QWORD *a2)
{
  _QWORD *v4; // r12
  WCHAR *v5; // r15
  WCHAR *v6; // r14
  unsigned int v7; // eax
  unsigned int v8; // r8d
  const char *v9; // r9
  __int64 v10; // r13
  const char *v11; // rsi
  char *v12; // rsi
  PCERT_EXTENSION Extension; // rax
  unsigned int v14; // r8d
  const char *v15; // r9
  PCERT_EXTENSION v16; // rax
  unsigned int v17; // r8d
  const char *v18; // r9
  DWORD NameStringW; // eax
  DWORD v20; // eax
  DWORD v21; // esi
  int dwFlags; // [rsp+20h] [rbp-38h]
  int dwFlagsa; // [rsp+20h] [rbp-38h]
  int dwFlagsb; // [rsp+20h] [rbp-38h]
  int dwFlagsc; // [rsp+20h] [rbp-38h]
  const char *pDecodePara; // [rsp+28h] [rbp-30h]
  _QWORD v28[3]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]
  PCCERT_CONTEXT pcbStructInfo; // [rsp+A8h] [rbp+50h] BYREF
  char *Str1; // [rsp+B0h] [rbp+58h] BYREF
  __int64 v32; // [rsp+B8h] [rbp+60h] BYREF

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
  v5 = (WCHAR *)(a1 + 13);
  *(_OWORD *)(a1 + 13) = 0;
  a1[15] = 0;
  a1[16] = 7;
  *((_WORD *)a1 + 52) = 0;
  v6 = (WCHAR *)(a1 + 17);
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
    v7 = CryptDecodeObjectEx(
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
      (const char *)v7,
      (int)"EK Certificate decoding error.",
      pDecodePara);
  }
  pcbStructInfo = CertCreateCertificateContext(0x10001u, (const BYTE *)*a2, *((_DWORD *)a2 + 2) - *(_DWORD *)a2);
  wil::unique_any_t<wil::cert_context_t>::operator=(a1, &pcbStructInfo);
  wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&pcbStructInfo);
  if ( !*a1 )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x134, v8, v9);
  if ( !*(_DWORD *)(*(_QWORD *)(*a1 + 24) + 192LL) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x137,
      (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\ekcert.cpp",
      (const char *)0x800B0108LL,
      dwFlags);
  if ( v4 != a2 )
    std::vector<unsigned char>::_Assign_counted_range<unsigned char const *>(v4, *a2, a2[1] - *a2);
  v10 = *a1;
  v11 = *(const char **)(*(_QWORD *)(*a1 + 24) + 96LL);
  if ( !strncmp_0(v11, "1.2.840.113549", 0xEu) )
  {
    *((_DWORD *)a1 + 42) = 1;
    goto LABEL_24;
  }
  if ( strncmp_0(v11, "1.2.840.10045.2.1", 0x11u) )
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
          *(LPCSTR *)(*(_QWORD *)(v10 + 24) + 96LL),
          *(const BYTE **)(*(_QWORD *)(v10 + 24) + 112LL),
          *(_DWORD *)(*(_QWORD *)(v10 + 24) + 104LL),
          4u,
          &Str1,
          (DWORD *)&pcbStructInfo) )
    goto LABEL_23;
  v12 = Str1;
  if ( !strncmp_0(Str1, "1.2.840.10045.3.1.7", 0x14u) )
  {
    *((_WORD *)a1 + 85) = 3;
    goto LABEL_24;
  }
  if ( !strncmp_0(v12, "1.3.132.0.34", 0xDu) )
  {
    *((_WORD *)a1 + 85) = 4;
    goto LABEL_24;
  }
  if ( !strncmp_0(v12, "1.3.132.0.35", 0xDu) )
  {
    *((_WORD *)a1 + 85) = 5;
    goto LABEL_24;
  }
  if ( !strncmp_0(v12, "1.2.156.10197.1.301", 0x14u) )
    *((_WORD *)a1 + 85) = 32;
  else
LABEL_23:
    *((_WORD *)a1 + 85) = 33;
LABEL_24:
  Extension = CertFindExtension(
                "2.5.29.35",
                *(_DWORD *)(*(_QWORD *)(*a1 + 24) + 192LL),
                *(CERT_EXTENSION **)(*(_QWORD *)(*a1 + 24) + 200LL));
  if ( Extension )
  {
    v32 = 0;
    Str1 = 0;
    LODWORD(pcbStructInfo) = 0;
    if ( !CryptDecodeObject(
            1u,
            (LPCSTR)0x1F,
            Extension->Value.pbData,
            Extension->Value.cbData,
            0x8001u,
            &v32,
            (DWORD *)&pcbStructInfo) )
      wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x189, v14, v15);
    v28[0] = 0;
    wistd::unique_ptr<_CRYPTOAPI_BLOB,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
      &Str1,
      v32);
    wistd::unique_ptr<_CRYPTOAPI_BLOB,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
      v28,
      0);
    std::vector<unsigned char>::_Assign_counted_range<unsigned char const *>(
      a1 + 1,
      *((_QWORD *)Str1 + 1),
      *(unsigned int *)Str1);
    wistd::unique_ptr<_CRYPTOAPI_BLOB,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
      &Str1,
      0);
  }
  v16 = CertFindExtension(
          "2.5.29.14",
          *(_DWORD *)(*(_QWORD *)(*a1 + 24) + 192LL),
          *(CERT_EXTENSION **)(*(_QWORD *)(*a1 + 24) + 200LL));
  if ( v16 )
  {
    v32 = 0;
    Str1 = 0;
    LODWORD(pcbStructInfo) = 0;
    if ( !CryptDecodeObject(
            1u,
            "2.5.29.14",
            v16->Value.pbData,
            v16->Value.cbData,
            0x8001u,
            &v32,
            (DWORD *)&pcbStructInfo) )
      wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x1A6, v17, v18);
    v28[0] = 0;
    wistd::unique_ptr<_CRYPTOAPI_BLOB,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
      &Str1,
      v32);
    wistd::unique_ptr<_CRYPTOAPI_BLOB,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
      v28,
      0);
    std::vector<unsigned char>::_Assign_counted_range<unsigned char const *>(
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
  std::wstring::resize(v5, NameStringW);
  if ( *((_QWORD *)v5 + 3) > 7u )
    v5 = *(WCHAR **)v5;
  v20 = CertGetNameStringW((PCCERT_CONTEXT)*a1, 4u, 1u, "2.5.4.3", v5, *((_DWORD *)a1 + 30));
  if ( v20 < 2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\ekcert.cpp",
      (const char *)0x800B0108LL,
      dwFlagsb);
  v21 = CertGetNameStringW((PCCERT_CONTEXT)*a1, 4u, 0, "2.5.4.3", 0, v20);
  std::wstring::resize(v6, v21);
  if ( *((_QWORD *)v6 + 3) > 7u )
    v6 = *(WCHAR **)v6;
  if ( CertGetNameStringW((PCCERT_CONTEXT)*a1, 4u, 0, "2.5.4.3", v6, v21) < 2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1D5,
      (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\ekcert.cpp",
      (const char *)0x800B0108LL,
      dwFlagsc);
  std::vector<unsigned char>::_Assign_counted_range<unsigned char const *>(
    a1 + 7,
    *(_QWORD *)(*(_QWORD *)(*a1 + 24) + 16LL),
    *(unsigned int *)(*(_QWORD *)(*a1 + 24) + 8LL));
  return a1;
}

```

## disassembly

```asm
0x180074124  mov     [rsp-40h+arg_0], rcx
0x180074129  push    rbp
0x18007412a  push    rbx
0x18007412b  push    rsi
0x18007412c  push    rdi
0x18007412d  push    r12
0x18007412f  push    r13
0x180074131  push    r14
0x180074133  push    r15
0x180074135  mov     rbp, rsp
0x180074138  sub     rsp, 58h
0x18007413c  mov     rsi, rdx
0x18007413f  mov     rbx, rcx
0x180074142  xor     r13d, r13d
0x180074145  mov     [rcx], r13
0x180074148  mov     [rcx+8], r13
0x18007414c  mov     [rcx+10h], r13
0x180074150  mov     [rcx+18h], r13
0x180074154  mov     [rcx+20h], r13
0x180074158  mov     [rcx+28h], r13
0x18007415c  mov     [rcx+30h], r13
0x180074160  mov     [rcx+38h], r13
0x180074164  mov     [rcx+40h], r13
0x180074168  mov     [rcx+48h], r13
0x18007416c  lea     r12, [rcx+50h]
0x180074170  mov     [r12], r13
0x180074174  mov     [r12+8], r13
0x180074179  mov     [r12+10h], r13
0x18007417e  lea     r15, [rcx+68h]
0x180074182  xorps   xmm0, xmm0
0x180074185  movups  xmmword ptr [r15], xmm0
0x180074189  mov     [r15+10h], r13
0x18007418d  lea     ecx, [r13+7]
0x180074191  mov     [r15+18h], rcx
0x180074195  mov     [r15], r13w
0x180074199  lea     r14, [rbx+88h]
0x1800741a0  movups  xmmword ptr [r14], xmm0
0x1800741a4  mov     [r14+10h], r13
0x1800741a8  mov     [r14+18h], rcx
0x1800741ac  mov     [r14], r13w
0x1800741b0  mov     dword ptr [rbx+0A8h], 210000h
0x1800741ba  mov     rcx, [rbp+40h]; this
0x1800741be  mov     rax, [rdx+8]
0x1800741c2  cmp     [rdx], rax
0x1800741c5  jnz     short loc_1800741DF
0x1800741c7  mov     r9d, 80070057h; char *
0x1800741cd  lea     r8, aOnecoreBaseNgs_28; "onecore\\base\\ngscb\\tpmhli\\lib\\ekce"...
0x1800741d4  mov     edx, 11Dh; void *
0x1800741d9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800741df  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AMD_P384_EK_Cert@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AMD_P384_EK_Cert@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AMD_P384_EK_Cert> `wil::Feature<__WilFeatureTraits_Feature_AMD_P384_EK_Cert>::GetImpl(void)'::`2'::impl
0x1800741e6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AMD_P384_EK_Cert@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AMD_P384_EK_Cert>::__private_IsEnabled(void)
0x1800741eb  lea     rdi, aOnecoreBaseNgs_28; "onecore\\base\\ngscb\\tpmhli\\lib\\ekce"...
0x1800741f2  test    al, al
0x1800741f4  jz      short loc_180074252
0x1800741f6  mov     dword ptr [rbp+arg_8], r13d
0x1800741fa  mov     r9d, [rsi+8]
0x1800741fe  sub     r9d, [rsi]; cbEncoded
0x180074201  lea     rax, [rbp+arg_8]
0x180074205  mov     [rsp+58h+pcbStructInfo], rax; pcbStructInfo
0x18007420a  mov     [rsp+58h+pvStructInfo], r13; pvStructInfo
0x18007420f  mov     [rsp+58h+pDecodePara], r13; char *
0x180074214  mov     [rsp+58h+dwFlags], r13d; dwFlags
0x180074219  mov     r8, [rsi]; pbEncoded
0x18007421c  mov     edx, 1; lpszStructType
0x180074221  mov     ecx, 10001h; dwCertEncodingType
0x180074226  call    cs:__imp_CryptDecodeObjectEx
0x18007422d  nop     dword ptr [rax+rax+00h]
0x180074232  mov     rcx, [rbp+40h]; this
0x180074236  lea     rdx, aEkCertificateD; "EK Certificate decoding error."
0x18007423d  mov     qword ptr [rsp+58h+dwFlags], rdx; int
0x180074242  mov     r9d, eax; char *
0x180074245  mov     r8, rdi; unsigned int
0x180074248  mov     edx, 12Ch; void *
0x18007424d  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x180074252  mov     r8d, [rsi+8]
0x180074256  sub     r8d, [rsi]; cbCertEncoded
0x180074259  mov     rdx, [rsi]; pbCertEncoded
0x18007425c  mov     ecx, 10001h; dwCertEncodingType
0x180074261  call    cs:__imp_CertCreateCertificateContext
0x180074268  nop     dword ptr [rax+rax+00h]
0x18007426d  mov     [rbp+arg_8], rax
0x180074271  lea     rdx, [rbp+arg_8]
0x180074275  mov     rcx, rbx
0x180074278  call    ??4?$unique_any_t@Ucert_context_t@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::cert_context_t>::operator=(wil::unique_any_t<wil::cert_context_t> &&)
0x18007427d  lea     rcx, [rbp+arg_8]
0x180074281  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x180074286  mov     rax, [rbx]
0x180074289  mov     rcx, [rbp+40h]; this
0x18007428d  test    rax, rax
0x180074290  jnz     short loc_18007429D
0x180074292  mov     edx, 134h; void *
0x180074297  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18007429d  mov     rcx, [rbp+40h]; this
0x1800742a1  mov     rax, [rax+18h]
0x1800742a5  cmp     dword ptr [rax+0C0h], 1
0x1800742ac  jnb     short loc_1800742C2
0x1800742ae  mov     r9d, 800B0108h; char *
0x1800742b4  mov     r8, rdi; unsigned int
0x1800742b7  mov     edx, 137h; void *
0x1800742bc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800742c2  cmp     r12, rsi
0x1800742c5  jz      short loc_1800742D9
0x1800742c7  mov     r8, [rsi+8]
0x1800742cb  sub     r8, [rsi]
0x1800742ce  mov     rdx, [rsi]
0x1800742d1  mov     rcx, r12
0x1800742d4  call    ??$_Assign_counted_range@PEBE@?$vector@EV?$allocator@E@std@@@std@@AEAAXPEBE_K@Z; std::vector<uchar>::_Assign_counted_range<uchar const *>(uchar const *,unsigned __int64)
0x1800742d9  mov     r13, [rbx]
0x1800742dc  mov     rax, [r13+18h]
0x1800742e0  mov     rsi, [rax+60h]
0x1800742e4  mov     r8d, 0Eh; MaxCount
0x1800742ea  lea     rdx, Str2; "1.2.840.113549"
0x1800742f1  mov     rcx, rsi; Str1
0x1800742f4  call    strncmp_0
0x1800742f9  xor     r12d, r12d
0x1800742fc  test    eax, eax
0x1800742fe  jnz     short loc_180074311
0x180074300  lea     r13d, [r12+1]
0x180074305  mov     [rbx+0A8h], r13d
0x18007430c  jmp     loc_18007442D
0x180074311  mov     r8d, 11h; MaxCount
0x180074317  lea     rdx, a128401004521; "1.2.840.10045.2.1"
0x18007431e  mov     rcx, rsi; Str1
0x180074321  call    strncmp_0
0x180074326  test    eax, eax
0x180074328  jnz     loc_1800746FB
0x18007432e  mov     word ptr [rbx+0A8h], 23h ; '#'
0x180074337  mov     [rbp+Str1], r12
0x18007433b  mov     dword ptr [rbp+arg_8], 8
0x180074342  mov     rdx, [r13+18h]
0x180074346  lea     rax, [rbp+arg_8]
0x18007434a  mov     [rsp+58h+pvStructInfo], rax; pcbStructInfo
0x18007434f  lea     rax, [rbp+Str1]
0x180074353  mov     [rsp+58h+pDecodePara], rax; pvStructInfo
0x180074358  mov     [rsp+58h+dwFlags], 4; dwFlags
0x180074360  mov     r9d, [rdx+68h]; cbEncoded
0x180074364  mov     r8, [rdx+70h]; pbEncoded
0x180074368  mov     rdx, [rdx+60h]; lpszStructType
0x18007436c  mov     ecx, 10001h; dwCertEncodingType
0x180074371  call    cs:__imp_CryptDecodeObject
0x180074378  nop     dword ptr [rax+rax+00h]
0x18007437d  test    eax, eax
0x18007437f  jz      loc_18007441E
0x180074385  mov     r8d, 14h; MaxCount
0x18007438b  lea     rdx, a1284010045317; "1.2.840.10045.3.1.7"
0x180074392  mov     rsi, [rbp+Str1]
0x180074396  mov     rcx, rsi; Str1
0x180074399  call    strncmp_0
0x18007439e  test    eax, eax
0x1800743a0  jnz     short loc_1800743AD
0x1800743a2  mov     word ptr [rbx+0AAh], 3
0x1800743ab  jmp     short loc_180074427
0x1800743ad  mov     r13d, 0Dh
0x1800743b3  mov     r8d, r13d; MaxCount
0x1800743b6  lea     rdx, a13132034; "1.3.132.0.34"
0x1800743bd  mov     rcx, rsi; Str1
0x1800743c0  call    strncmp_0
0x1800743c5  test    eax, eax
0x1800743c7  jnz     short loc_1800743D9
0x1800743c9  lea     esi, [rax+4]
0x1800743cc  mov     [rbx+0AAh], si
0x1800743d3  lea     r13d, [rax+1]
0x1800743d7  jmp     short loc_180074432
0x1800743d9  mov     r8d, r13d; MaxCount
0x1800743dc  lea     rdx, a13132035; "1.3.132.0.35"
0x1800743e3  mov     rcx, rsi; Str1
0x1800743e6  call    strncmp_0
0x1800743eb  test    eax, eax
0x1800743ed  jnz     short loc_1800743FA
0x1800743ef  mov     word ptr [rbx+0AAh], 5
0x1800743f8  jmp     short loc_180074427
0x1800743fa  mov     r8d, 14h; MaxCount
0x180074400  lea     rdx, a12156101971301; "1.2.156.10197.1.301"
0x180074407  mov     rcx, rsi; Str1
0x18007440a  call    strncmp_0
0x18007440f  test    eax, eax
0x180074411  jnz     short loc_18007441E
0x180074413  mov     word ptr [rbx+0AAh], 20h ; ' '
0x18007441c  jmp     short loc_180074427
0x18007441e  mov     word ptr [rbx+0AAh], 21h ; '!'
0x180074427  mov     r13d, 1
0x18007442d  mov     esi, 4
0x180074432  mov     rax, [rbx]
0x180074435  mov     rdx, [rax+18h]
0x180074439  mov     r8, [rdx+0C8h]; rgExtensions
0x180074440  mov     edx, [rdx+0C0h]; cExtensions
0x180074446  lea     rcx, pszObjId; "2.5.29.35"
0x18007444d  call    cs:__imp_CertFindExtension
0x180074454  nop     dword ptr [rax+rax+00h]
0x180074459  test    rax, rax
0x18007445c  jz      loc_1800744F3
0x180074462  mov     [rbp+arg_18], r12
0x180074466  mov     [rbp+Str1], r12
0x18007446a  mov     dword ptr [rbp+arg_8], r12d
0x18007446e  lea     rcx, [rbp+arg_8]
0x180074472  mov     [rsp+58h+pvStructInfo], rcx; pcbStructInfo
0x180074477  lea     rcx, [rbp+arg_18]
0x18007447b  mov     [rsp+58h+pDecodePara], rcx; pvStructInfo
0x180074480  mov     [rsp+58h+dwFlags], 8001h; dwFlags
0x180074488  mov     r9d, [rax+10h]; cbEncoded
0x18007448c  mov     r8, [rax+18h]; pbEncoded
0x180074490  mov     edx, 1Fh; lpszStructType
0x180074495  mov     ecx, r13d; dwCertEncodingType
0x180074498  call    cs:__imp_CryptDecodeObject
0x18007449f  nop     dword ptr [rax+rax+00h]
0x1800744a4  mov     rcx, [rbp+40h]; this
0x1800744a8  test    eax, eax
0x1800744aa  jnz     short loc_1800744B7
0x1800744ac  mov     edx, 189h; void *
0x1800744b1  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800744b7  mov     [rbp+var_18], r12
0x1800744bb  mov     rdx, [rbp+arg_18]
0x1800744bf  lea     rcx, [rbp+Str1]
0x1800744c3  call    ?reset@?$unique_ptr@U_CRYPTOAPI_BLOB@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAU_CRYPTOAPI_BLOB@@@Z; wistd::unique_ptr<_CRYPTOAPI_BLOB,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(_CRYPTOAPI_BLOB *)
0x1800744c8  xor     edx, edx
0x1800744ca  lea     rcx, [rbp+var_18]
0x1800744ce  call    ?reset@?$unique_ptr@U_CRYPTOAPI_BLOB@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAU_CRYPTOAPI_BLOB@@@Z; wistd::unique_ptr<_CRYPTOAPI_BLOB,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(_CRYPTOAPI_BLOB *)
0x1800744d3  mov     rdx, [rbp+Str1]
0x1800744d7  mov     r8d, [rdx]
0x1800744da  mov     rdx, [rdx+8]
0x1800744de  lea     rcx, [rbx+8]
0x1800744e2  call    ??$_Assign_counted_range@PEBE@?$vector@EV?$allocator@E@std@@@std@@AEAAXPEBE_K@Z; std::vector<uchar>::_Assign_counted_range<uchar const *>(uchar const *,unsigned __int64)
0x1800744e7  nop
0x1800744e8  xor     edx, edx
0x1800744ea  lea     rcx, [rbp+Str1]
0x1800744ee  call    ?reset@?$unique_ptr@U_CRYPTOAPI_BLOB@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAU_CRYPTOAPI_BLOB@@@Z; wistd::unique_ptr<_CRYPTOAPI_BLOB,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(_CRYPTOAPI_BLOB *)
0x1800744f3  mov     rax, [rbx]
0x1800744f6  mov     rdx, [rax+18h]
0x1800744fa  mov     r8, [rdx+0C8h]; rgExtensions
0x180074501  mov     edx, [rdx+0C0h]; cExtensions
0x180074507  lea     rcx, szStructType; "2.5.29.14"
0x18007450e  call    cs:__imp_CertFindExtension
0x180074515  nop     dword ptr [rax+rax+00h]
0x18007451a  test    rax, rax
0x18007451d  jz      loc_1800745B6
0x180074523  mov     [rbp+arg_18], r12
0x180074527  mov     [rbp+Str1], r12
0x18007452b  mov     dword ptr [rbp+arg_8], r12d
0x18007452f  lea     rcx, [rbp+arg_8]
0x180074533  mov     [rsp+58h+pvStructInfo], rcx; pcbStructInfo
0x180074538  lea     rcx, [rbp+arg_18]
0x18007453c  mov     [rsp+58h+pDecodePara], rcx; pvStructInfo
0x180074541  mov     [rsp+58h+dwFlags], 8001h; dwFlags
0x180074549  mov     r9d, [rax+10h]; cbEncoded
0x18007454d  mov     r8, [rax+18h]; pbEncoded
0x180074551  lea     rdx, szStructType; "2.5.29.14"
0x180074558  mov     ecx, r13d; dwCertEncodingType
0x18007455b  call    cs:__imp_CryptDecodeObject
0x180074562  nop     dword ptr [rax+rax+00h]
0x180074567  mov     rcx, [rbp+40h]; this
0x18007456b  test    eax, eax
0x18007456d  jnz     short loc_18007457A
0x18007456f  mov     edx, 1A6h; void *
0x180074574  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18007457a  mov     [rbp+var_18], r12
0x18007457e  mov     rdx, [rbp+arg_18]
0x180074582  lea     rcx, [rbp+Str1]
0x180074586  call    ?reset@?$unique_ptr@U_CRYPTOAPI_BLOB@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAU_CRYPTOAPI_BLOB@@@Z; wistd::unique_ptr<_CRYPTOAPI_BLOB,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(_CRYPTOAPI_BLOB *)
0x18007458b  xor     edx, edx
0x18007458d  lea     rcx, [rbp+var_18]
0x180074591  call    ?reset@?$unique_ptr@U_CRYPTOAPI_BLOB@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAU_CRYPTOAPI_BLOB@@@Z; wistd::unique_ptr<_CRYPTOAPI_BLOB,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(_CRYPTOAPI_BLOB *)
0x180074596  mov     rdx, [rbp+Str1]
0x18007459a  mov     r8d, [rdx]
0x18007459d  mov     rdx, [rdx+8]
0x1800745a1  lea     rcx, [rbx+20h]
0x1800745a5  call    ??$_Assign_counted_range@PEBE@?$vector@EV?$allocator@E@std@@@std@@AEAAXPEBE_K@Z; std::vector<uchar>::_Assign_counted_range<uchar const *>(uchar const *,unsigned __int64)
0x1800745aa  nop
0x1800745ab  xor     edx, edx
0x1800745ad  lea     rcx, [rbp+Str1]
0x1800745b1  call    ?reset@?$unique_ptr@U_CRYPTOAPI_BLOB@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAU_CRYPTOAPI_BLOB@@@Z; wistd::unique_ptr<_CRYPTOAPI_BLOB,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(_CRYPTOAPI_BLOB *)
0x1800745b6  mov     dword ptr [rsp+58h+pDecodePara], r12d; cchNameString
0x1800745bb  mov     qword ptr [rsp+58h+dwFlags], r12; int
0x1800745c0  lea     r13, a2543; "2.5.4.3"
0x1800745c7  mov     r9, r13; pvTypePara
0x1800745ca  mov     r8d, 1; dwFlags
0x1800745d0  mov     edx, esi; dwType
0x1800745d2  mov     rcx, [rbx]; pCertContext
0x1800745d5  call    cs:__imp_CertGetNameStringW
0x1800745dc  nop     dword ptr [rax+rax+00h]
0x1800745e1  mov     rcx, [rbp+40h]; this
0x1800745e5  cmp     eax, 2
0x1800745e8  jnb     short loc_1800745FE
0x1800745ea  mov     r9d, 800B0108h; char *
0x1800745f0  mov     r8, rdi; unsigned int
0x1800745f3  mov     edx, 1B8h; void *
0x1800745f8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800745fe  mov     edx, eax
0x180074600  mov     rcx, r15
0x180074603  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180074608  mov     eax, [rbx+78h]
0x18007460b  cmp     qword ptr [r15+18h], 7
0x180074610  jbe     short loc_180074615
0x180074612  mov     r15, [r15]
0x180074615  mov     dword ptr [rsp+58h+pDecodePara], eax; cchNameString
0x180074619  mov     qword ptr [rsp+58h+dwFlags], r15; int
0x18007461e  mov     r9, r13; pvTypePara
0x180074621  mov     r8d, 1; dwFlags
0x180074627  mov     edx, esi; dwType
0x180074629  mov     rcx, [rbx]; pCertContext
0x18007462c  call    cs:__imp_CertGetNameStringW
  ... truncated ...
```
