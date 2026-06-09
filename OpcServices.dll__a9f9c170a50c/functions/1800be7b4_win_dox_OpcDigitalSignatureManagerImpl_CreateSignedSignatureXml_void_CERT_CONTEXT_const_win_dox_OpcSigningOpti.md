# win_dox::OpcDigitalSignatureManagerImpl::CreateSignedSignatureXml(void *,_CERT_CONTEXT const *,win_dox::OpcSigningOptions const &,_CRYPT_XML_ALGORITHM const &)

- ea: `0x1800be7b4`
- end: `0x1800bea59`
- name: `?CreateSignedSignatureXml@OpcDigitalSignatureManagerImpl@win_dox@@AEAAXPEAXPEBU_CERT_CONTEXT@@AEBVOpcSigningOptions@2@AEBU_CRYPT_XML_ALGORITHM@@@Z`
- size: `677`
- prototype: `void(win_dox::OpcDigitalSignatureManagerImpl *__hidden this, void *, const struct _CERT_CONTEXT *, const struct win_dox::OpcSigningOptions *, const struct _CRYPT_XML_ALGORITHM *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x1800a1ef4`

## callees

- `0x1800016b0`
- `0x180002e94`
- `0x180017dd0`
- `0x180018c2c`
- `0x1800517a0`
- `0x180079ca0`
- `0x1800a2940`
- `0x1800be7b4`
- `0x1800bea60`
- `0x1800bece4`
- `0x1800cd38c`
- `0x1800d5fe4`
- `0x1800ebe64`
- `0x180117740`
- `0x18012a010`

## import_xrefs

- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x1800be82b`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x1800be82b`
- `CRYPTXML!CryptXmlSign` at `0x1800be9f6`
- `CRYPTXML!CryptXmlSign` at `0x1800be9f6`

## string_xrefs

- `0x1800be881`: `Unexpected - CryptAcquireCertificatePrivateKey() requires the key handle to be released by the caller even though CRYPT_ACQUIRE_CACHE_FLAG flag is used`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall win_dox::OpcDigitalSignatureManagerImpl::CreateSignedSignatureXml(
        win_dox::OpcDigitalSignatureManagerImpl *this,
        void *a2,
        const struct _CERT_CONTEXT *a3,
        const struct win_dox::OpcSigningOptions *a4)
{
  win_musl::detail *v7; // rcx
  __m128i v8; // xmm6
  CRYPT_XML_KEYINFO_SPEC v9; // r14d
  __int64 CertificateSet; // rax
  __int64 v11; // rax
  unsigned __int64 v12; // rbx
  _BYTE *v13; // rdi
  const WCHAR *v14; // rax
  HRESULT v15; // eax
  __int64 v16; // rdx
  const char *v17; // r8
  unsigned int v18; // r9d
  unsigned int pfCallerFreeProvOrNCryptKey; // [rsp+30h] [rbp-D8h]
  BOOL v20; // [rsp+48h] [rbp-C0h] BYREF
  int v21; // [rsp+4Ch] [rbp-BCh] BYREF
  DWORD dwKeySpec[2]; // [rsp+50h] [rbp-B8h] BYREF
  HCRYPTPROV_OR_NCRYPT_KEY_HANDLE phCryptProvOrNCryptKey; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v24; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v25; // [rsp+68h] [rbp-A0h]
  __int64 v26; // [rsp+70h] [rbp-98h] BYREF
  CRYPT_XML_ALGORITHM pSignatureMethod; // [rsp+78h] [rbp-90h] BYREF
  __m128i v28; // [rsp+98h] [rbp-70h] BYREF
  __int64 v29; // [rsp+A8h] [rbp-60h]
  __m128i v30; // [rsp+B8h] [rbp-50h] BYREF
  _BYTE pvKeyInfoSpec[40]; // [rsp+C8h] [rbp-40h] BYREF
  int v32; // [rsp+F0h] [rbp-18h]
  unsigned __int64 v33; // [rsp+F8h] [rbp-10h]
  char v34[8]; // [rsp+118h] [rbp+10h] BYREF
  _QWORD v35[5]; // [rsp+120h] [rbp+18h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+148h] [rbp+40h] BYREF

  v29 = -2;
  phCryptProvOrNCryptKey = 0;
  dwKeySpec[0] = 0;
  v20 = 0;
  if ( !CryptAcquireCertificatePrivateKey(a3, 0x10001u, 0, &phCryptProvOrNCryptKey, dwKeySpec, &v20) )
  {
    pfCallerFreeProvOrNCryptKey = win_musl::detail::GetLastErrorAsFailHR(v7);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x604u,
      pfCallerFreeProvOrNCryptKey,
      (struct win_musl::TStringEllipseBase *)L"Invalid certificate");
    throw (SplException::THResultException *)pExceptionObject;
  }
  if ( v20 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x60Fu,
      0x8000FFFF,
      (struct win_musl::TStringEllipseBase *)L"Unexpected - CryptAcquireCertificatePrivateKey() requires the key handle to"
                                              " be released by the caller even though CRYPT_ACQUIRE_CACHE_FLAG flag is used");
    throw (SplException::THResultException *)pExceptionObject;
  }
  memset_0(pvKeyInfoSpec, 0, 0x48u);
  v8.m128i_i64[0] = 0;
  v28 = 0;
  if ( win_dox::OpcSigningOptions::GetCertificateEmbeddingOption(a4) == OPC_CERTIFICATE_IN_SIGNATURE_PART )
  {
    v9 = CRYPT_XML_KEYINFO_SPEC_PARAM;
    v21 = 0;
    CertificateSet = win_dox::OpcSigningOptions::GetCertificateSet(a4, &v26);
    v11 = win_dox::OpcDigitalSignatureManagerImpl::CreateCertBlobs(&v21, &v24, a3, CertificateSet, &v21);
    win_scope::scope<win_musl::DataBuffer::BufferObject *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_musl::DataBuffer::BufferObject *,win_scope::const_policies<win_scope::shared_policies>>(
      &v30,
      v11);
    v8 = v30;
    v28 = v30;
    if ( v24 && v25 )
    {
      win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(&v24);
      v24 = 0;
      v25 = 0;
    }
    if ( v26 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    v32 = v21;
    v12 = _mm_srli_si128(v8, 8).m128i_u64[0];
    v33 = v12;
    v13 = pvKeyInfoSpec;
  }
  else
  {
    v9 = CRYPT_XML_KEYINFO_SPEC_NONE;
    v12 = 0;
    v13 = 0;
  }
  win_dox::OpcSigningOptions::GetSignatureMethod(a4, v34);
  *(_QWORD *)&pSignatureMethod.cbSize = 32;
  v14 = (const WCHAR *)v35;
  if ( v35[3] >= 8u )
    v14 = (const WCHAR *)v35[0];
  pSignatureMethod.wszAlgorithm = v14;
  *(_QWORD *)&pSignatureMethod.Encoded.dwCharset = 0;
  pSignatureMethod.Encoded.pbData = 0;
  v15 = CryptXmlSign(
          a2,
          phCryptProvOrNCryptKey,
          dwKeySpec[0],
          0,
          v9,
          v13,
          &pSignatureMethod,
          &win_dox::gc_canonicalizationC14NTransform);
  if ( v15 < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)v15, v16, v17, v18);
  LOBYTE(v16) = 1;
  std::wstring::_Tidy(v34, v16, 0);
  if ( v8.m128i_i64[0] )
  {
    if ( v12 )
      win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(&v28);
  }
}

```

## disassembly

```asm
0x1800be7b4  mov     rax, rsp
0x1800be7b7  push    rbp
0x1800be7b8  push    rbx
0x1800be7b9  push    rsi
0x1800be7ba  push    rdi
0x1800be7bb  push    r12
0x1800be7bd  push    r14
0x1800be7bf  push    r15
0x1800be7c1  lea     rbp, [rax-138h]
0x1800be7c8  sub     rsp, 200h
0x1800be7cf  mov     [rbp+130h+var_190], 0FFFFFFFFFFFFFFFEh
0x1800be7d7  movaps  xmmword ptr [rax-48h], xmm6
0x1800be7db  mov     rax, cs:__security_cookie
0x1800be7e2  xor     rax, rsp
0x1800be7e5  mov     [rbp+130h+var_50], rax
0x1800be7ec  mov     rsi, r9
0x1800be7ef  mov     rbx, r8
0x1800be7f2  mov     r15, rdx
0x1800be7f5  xor     r12d, r12d
0x1800be7f8  mov     [rsp+230h+phCryptProvOrNCryptKey], r12
0x1800be7fd  mov     [rsp+230h+dwKeySpec], r12d
0x1800be802  mov     [rsp+230h+var_1F0], r12d
0x1800be807  lea     rax, [rsp+230h+var_1F0]
0x1800be80c  mov     [rsp+230h+pfCallerFreeProvOrNCryptKey], rax; pfCallerFreeProvOrNCryptKey
0x1800be811  lea     rax, [rsp+230h+dwKeySpec]
0x1800be816  mov     [rsp+230h+pdwKeySpec], rax; pdwKeySpec
0x1800be81b  lea     r9, [rsp+230h+phCryptProvOrNCryptKey]; phCryptProvOrNCryptKey
0x1800be820  xor     r8d, r8d; pvParameters
0x1800be823  mov     edx, 10001h; dwFlags
0x1800be828  mov     rcx, rbx; pCert
0x1800be82b  call    cs:__imp_CryptAcquireCertificatePrivateKey
0x1800be831  test    eax, eax
0x1800be833  jnz     short loc_1800BE87A
0x1800be835  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x1800be83a  lea     rcx, aInvalidCertifi; "Invalid certificate"
0x1800be841  mov     [rsp+230h+pSignatureMethod], rcx; struct win_musl::TStringEllipseBase *
0x1800be846  mov     dword ptr [rsp+230h+pfCallerFreeProvOrNCryptKey], eax; unsigned int
0x1800be84a  mov     dword ptr [rsp+230h+pdwKeySpec], 604h; unsigned int
0x1800be852  lea     r9, word_18013A0B6
0x1800be859  lea     r8, aNoFilename; "(no filename)"
0x1800be860  lea     rcx, [rbp+130h+pExceptionObject]; this
0x1800be864  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800be869  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800be870  lea     rcx, [rbp+130h+pExceptionObject]; pExceptionObject
0x1800be874  call    _CxxThrowException_0
0x1800be87a  cmp     [rsp+230h+var_1F0], r12d
0x1800be87f  jz      short loc_1800BE8C5
0x1800be881  lea     rax, aUnexpectedCryp; "Unexpected - CryptAcquireCertificatePri"...
0x1800be888  mov     [rsp+230h+pSignatureMethod], rax; struct win_musl::TStringEllipseBase *
0x1800be88d  mov     dword ptr [rsp+230h+pfCallerFreeProvOrNCryptKey], 8000FFFFh; unsigned int
0x1800be895  mov     dword ptr [rsp+230h+pdwKeySpec], 60Fh; unsigned int
0x1800be89d  lea     r9, word_18013A0B6
0x1800be8a4  lea     r8, aNoFilename; "(no filename)"
0x1800be8ab  lea     rcx, [rbp+130h+pExceptionObject]; this
0x1800be8af  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800be8b4  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800be8bb  lea     rcx, [rbp+130h+pExceptionObject]; pExceptionObject
0x1800be8bf  call    _CxxThrowException_0
0x1800be8c5  xor     edx, edx; Val
0x1800be8c7  lea     r8d, [rdx+48h]; Size
0x1800be8cb  lea     rcx, [rbp+130h+pvKeyInfoSpec]; void *
0x1800be8cf  call    memset_0
0x1800be8d4  xorps   xmm6, xmm6
0x1800be8d7  movdqa  [rbp+130h+var_1A0], xmm6
0x1800be8dc  mov     rcx, rsi; this
0x1800be8df  call    ?GetCertificateEmbeddingOption@OpcSigningOptions@win_dox@@QEBA?AW4__MIDL___MIDL_itf_msopc_0001_0076_0004@@XZ; win_dox::OpcSigningOptions::GetCertificateEmbeddingOption(void)
0x1800be8e4  cmp     eax, 1
0x1800be8e7  jnz     loc_1800BE98C
0x1800be8ed  lea     r14d, [rax+1]
0x1800be8f1  mov     [rsp+230h+var_1EC], r12d
0x1800be8f6  lea     rdx, [rsp+230h+var_1C8]
0x1800be8fb  mov     rcx, rsi
0x1800be8fe  call    ?GetCertificateSet@OpcSigningOptions@win_dox@@QEBA?AVOpcCertificateSet@2@XZ; win_dox::OpcSigningOptions::GetCertificateSet(void)
0x1800be903  nop
0x1800be904  lea     rcx, [rsp+230h+var_1EC]
0x1800be909  mov     [rsp+230h+pdwKeySpec], rcx
0x1800be90e  mov     r9, rax
0x1800be911  mov     r8, rbx
0x1800be914  lea     rdx, [rsp+230h+var_1D8]
0x1800be919  call    ?CreateCertBlobs@OpcDigitalSignatureManagerImpl@win_dox@@AEAA?AV?$scope@PEAU_CRYPTOAPI_BLOB@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@PEBU_CERT_CONTEXT@@AEBVOpcCertificateSet@2@AEAK@Z; win_dox::OpcDigitalSignatureManagerImpl::CreateCertBlobs(_CERT_CONTEXT const *,win_dox::OpcCertificateSet const &,ulong &)
0x1800be91e  nop
0x1800be91f  mov     rdx, rax
0x1800be922  lea     rcx, [rbp+130h+var_180]
0x1800be926  call    ??0?$scope@PEAUBufferObject@DataBuffer@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@QEAA@AEBV01@@Z; win_scope::scope<win_musl::DataBuffer::BufferObject *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_musl::DataBuffer::BufferObject *,win_scope::const_policies<win_scope::shared_policies>>(win_scope::scope<win_musl::DataBuffer::BufferObject *,win_scope::const_policies<win_scope::shared_policies>> const &)
0x1800be92b  movaps  xmm6, [rbp+130h+var_180]
0x1800be92f  movdqa  [rbp+130h+var_1A0], xmm6
0x1800be934  cmp     [rsp+230h+var_1D8], r12
0x1800be939  jz      short loc_1800BE956
0x1800be93b  cmp     [rsp+230h+var_1D0], r12
0x1800be940  jz      short loc_1800BE956
0x1800be942  lea     rcx, [rsp+230h+var_1D8]
0x1800be947  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x1800be94c  mov     [rsp+230h+var_1D8], r12
0x1800be951  mov     [rsp+230h+var_1D0], r12
0x1800be956  mov     rcx, [rsp+230h+var_1C8]
0x1800be95b  test    rcx, rcx
0x1800be95e  jz      short loc_1800BE96D
0x1800be960  mov     rax, [rcx]
0x1800be963  mov     rax, [rax+10h]
0x1800be967  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be96c  nop
0x1800be96d  mov     eax, [rsp+230h+var_1EC]
0x1800be971  mov     [rbp+130h+var_148], eax
0x1800be974  movdqa  xmm0, xmm6
0x1800be978  psrldq  xmm0, 8
0x1800be97d  movq    rbx, xmm0
0x1800be982  mov     [rbp+130h+var_140], rbx
0x1800be986  lea     rdi, [rbp+130h+pvKeyInfoSpec]
0x1800be98a  jmp     short loc_1800BE995
0x1800be98c  mov     r14d, r12d
0x1800be98f  mov     rbx, r12
0x1800be992  mov     rdi, r12
0x1800be995  lea     rdx, [rbp+130h+var_120]
0x1800be999  mov     rcx, rsi
0x1800be99c  call    ?GetSignatureMethod@OpcSigningOptions@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ; win_dox::OpcSigningOptions::GetSignatureMethod(void)
0x1800be9a1  nop
0x1800be9a2  mov     qword ptr [rsp+230h+var_1C0.cbSize], 20h ; ' '
0x1800be9ab  lea     rax, [rbp+130h+var_118]
0x1800be9af  cmp     [rbp+130h+var_100], 8
0x1800be9b4  cmovnb  rax, [rbp+130h+var_118]
0x1800be9b9  mov     [rsp+230h+var_1C0.wszAlgorithm], rax
0x1800be9be  mov     qword ptr [rbp+130h+var_1C0.Encoded.dwCharset], r12
0x1800be9c2  mov     [rbp+130h+var_1C0.Encoded.pbData], r12
0x1800be9c6  lea     rax, ?gc_canonicalizationC14NTransform@win_dox@@3U_CRYPT_XML_ALGORITHM@@B; _CRYPT_XML_ALGORITHM const win_dox::gc_canonicalizationC14NTransform
0x1800be9cd  mov     [rsp+230h+pCanonicalization], rax; pCanonicalization
0x1800be9d2  lea     rax, [rsp+230h+var_1C0]
0x1800be9d7  mov     [rsp+230h+pSignatureMethod], rax; pSignatureMethod
0x1800be9dc  mov     [rsp+230h+pfCallerFreeProvOrNCryptKey], rdi; pvKeyInfoSpec
0x1800be9e1  mov     dword ptr [rsp+230h+pdwKeySpec], r14d; dwKeyInfoSpec
0x1800be9e6  xor     r9d, r9d; dwFlags
0x1800be9e9  mov     r8d, [rsp+230h+dwKeySpec]; dwKeySpec
0x1800be9ee  mov     rdx, [rsp+230h+phCryptProvOrNCryptKey]; hKey
0x1800be9f3  mov     rcx, r15; hSignature
0x1800be9f6  call    cs:__imp_CryptXmlSign
0x1800be9fc  test    eax, eax
0x1800be9fe  jns     short loc_1800BEA08
0x1800bea00  mov     ecx, eax; this
0x1800bea02  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x1800bea08  xor     r8d, r8d
0x1800bea0b  mov     dl, 1
0x1800bea0d  lea     rcx, [rbp+130h+var_120]
0x1800bea11  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800bea16  nop
0x1800bea17  movq    rax, xmm6
0x1800bea1c  test    rax, rax
0x1800bea1f  jz      short loc_1800BEA30
0x1800bea21  test    rbx, rbx
0x1800bea24  jz      short loc_1800BEA30
0x1800bea26  lea     rcx, [rbp+130h+var_1A0]
0x1800bea2a  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x1800bea2f  nop
0x1800bea30  mov     rcx, [rbp+130h+var_50]
0x1800bea37  xor     rcx, rsp; StackCookie
0x1800bea3a  call    __security_check_cookie
0x1800bea3f  movaps  xmm6, [rsp+230h+var_48+8]
0x1800bea47  add     rsp, 200h
0x1800bea4e  pop     r15
0x1800bea50  pop     r14
0x1800bea52  pop     r12
0x1800bea54  pop     rdi
0x1800bea55  pop     rsi
0x1800bea56  pop     rbx
0x1800bea57  pop     rbp
0x1800bea58  retn
```
