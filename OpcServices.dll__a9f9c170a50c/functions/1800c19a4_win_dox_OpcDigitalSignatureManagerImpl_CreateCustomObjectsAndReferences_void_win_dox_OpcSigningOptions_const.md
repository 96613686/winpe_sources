# win_dox::OpcDigitalSignatureManagerImpl::CreateCustomObjectsAndReferences(void *,win_dox::OpcSigningOptions const &)

- ea: `0x1800c19a4`
- end: `0x1800c1e2b`
- name: `?CreateCustomObjectsAndReferences@OpcDigitalSignatureManagerImpl@win_dox@@AEAAXPEAXAEBVOpcSigningOptions@2@@Z`
- size: `1159`
- prototype: `void(win_dox::OpcDigitalSignatureManagerImpl *__hidden this, void *, const struct win_dox::OpcSigningOptions *)`
- caller_count: `1`
- callee_count: `29`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800a1ef4`

## callees

- `0x180008398`
- `0x180017c10`
- `0x180017dd0`
- `0x180018c2c`
- `0x18001a810`
- `0x1800460f0`
- `0x18004a558`
- `0x1800517a0`
- `0x1800654b0`
- `0x18008429c`
- `0x1800a0fec`
- `0x1800a70e4`
- `0x1800c19a4`
- `0x1800c1e34`
- `0x1800c1f70`
- `0x1800c2010`
- `0x1800c212c`
- `0x1800c226c`
- `0x1800c23e8`
- `0x1800c2524`
- `0x1800c2660`
- `0x1800c2734`
- `0x1800c2850`
- `0x1800cb070`
- `0x1800cd38c`
- `0x1800ebf38`
- `0x1800f3884`
- `0x180117740`
- `0x18012a010`

## import_xrefs

- `CRYPTXML!CryptXmlCreateReference` at `0x1800c1cb8`
- `CRYPTXML!CryptXmlCreateReference` at `0x1800c1cb8`
- `CRYPTXML!CryptXmlAddObject` at `0x1800c1a9d`
- `CRYPTXML!CryptXmlAddObject` at `0x1800c1a9d`

## string_xrefs

- `0x1800c1dc3`: `PackageReferenceUri`
- `0x1800c1d9f`: `Custom reference must not have Uri equal to "%{PackageReferenceUri}".`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
void __fastcall win_dox::OpcDigitalSignatureManagerImpl::CreateCustomObjectsAndReferences(
        win_dox::OpcDigitalSignatureManagerImpl *this,
        void *a2,
        const struct win_dox::OpcSigningOptions *a3)
{
  char v5; // bl
  __int64 CustomObjectSet; // rax
  ULONG v7; // eax
  HRESULT v8; // eax
  int v9; // edx
  const char *v10; // r8
  unsigned int v11; // r9d
  struct _GUID *v12; // rdx
  const struct _EVENT_DESCRIPTOR *v13; // rcx
  unsigned int v14; // r9d
  __int64 CustomReferenceSet; // rax
  const WCHAR *v16; // rsi
  __int64 Uri; // rax
  const WCHAR *v18; // rbx
  const WCHAR *v19; // rax
  int v20; // edx
  int v21; // ecx
  const WCHAR *v22; // rax
  enum __MIDL___MIDL_itf_msopc_0001_0076_0001 TransformMethod; // eax
  win_dox::OpcDigitalSignatureManagerImpl *v24; // rcx
  const wchar_t *CanonicalizationString; // rax
  const WCHAR *wszAlgorithm; // rcx
  ULONG cTransform; // r14d
  __int64 Type; // rax
  const WCHAR *v29; // rdi
  __int64 Id; // rax
  const WCHAR *v31; // r8
  HRESULT v32; // eax
  __int64 v33; // rdx
  const char *v34; // r8
  unsigned int v35; // r9d
  __int64 v36; // rdx
  __int64 v37; // rdx
  __int64 v38; // rdx
  __int64 v39; // rdx
  __int64 v40; // rbx
  win_musl::Formatter *v41; // rax
  struct win_musl::TStringEllipseBase *v42; // rax
  __int64 v43; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v44; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v45; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v46; // [rsp+70h] [rbp-98h] BYREF
  CRYPT_XML_ALGORITHM pDigestMethod; // [rsp+78h] [rbp-90h] BYREF
  CRYPT_XML_BLOB pEncoded; // [rsp+98h] [rbp-70h] BYREF
  CRYPT_XML_ALGORITHM rgTransform; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v50; // [rsp+C8h] [rbp-40h]
  _BYTE v51[8]; // [rsp+D0h] [rbp-38h] BYREF
  _QWORD v52[4]; // [rsp+D8h] [rbp-30h] BYREF
  _BYTE v53[8]; // [rsp+F8h] [rbp-10h] BYREF
  LPCWSTR wszURI[4]; // [rsp+100h] [rbp-8h] BYREF
  _BYTE v55[8]; // [rsp+120h] [rbp+18h] BYREF
  _QWORD v56[4]; // [rsp+128h] [rbp+20h] BYREF
  _BYTE v57[40]; // [rsp+148h] [rbp+40h] BYREF
  _BYTE v58[40]; // [rsp+170h] [rbp+68h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+198h] [rbp+90h] BYREF
  _BYTE v60[96]; // [rsp+238h] [rbp+130h] BYREF

  v50 = -2;
  v5 = 1;
  CustomObjectSet = win_dox::OpcSigningOptions::GetCustomObjectSet(a3, &v43);
  win_dox::OpcSignatureCustomObjectSet::GetEnumerator(CustomObjectSet, &v46);
  if ( v43 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    v43 = 0;
  }
  while ( (unsigned __int8)win_dox::Enumerator<IOpcSignatureCustomObjectEnumerator>::MoveNext(&v46) )
  {
    if ( v5 )
    {
      _WinSqmDWORDEvent(v13, v12, 0x1440u, v14);
      v5 = 0;
    }
    win_dox::Enumerator<IOpcSignatureCustomObjectEnumerator>::GetCurrent(&v46, &v44);
    std::vector<unsigned char>::_Buy(&pDigestMethod, 0);
    win_dox::OpcSignatureCustomObject::GetXml(&v44, &pDigestMethod);
    pEncoded.dwCharset = CRYPT_XML_CHARSET_AUTO;
    if ( pDigestMethod.wszAlgorithm )
      v7 = pDigestMethod.Encoded.dwCharset - LODWORD(pDigestMethod.wszAlgorithm);
    else
      v7 = 0;
    pEncoded.cbData = v7;
    pEncoded.pbData = (BYTE *)pDigestMethod.wszAlgorithm;
    v8 = CryptXmlAddObject(a2, 0, 0, 0, &pEncoded, 0);
    if ( v8 < 0 )
      SplException::RealThrowFromHR((SplException *)(unsigned int)v8, v9, v10, v11);
    std::vector<unsigned char>::_Tidy(&pDigestMethod);
    if ( v44 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
      v44 = 0;
    }
  }
  CustomReferenceSet = win_dox::OpcSigningOptions::GetCustomReferenceSet(a3, &v45);
  win_dox::OpcSignatureReferenceSet::GetEnumerator(CustomReferenceSet, &v44);
  if ( v45 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    v45 = 0;
  }
  if ( (unsigned __int8)win_dox::Enumerator<IOpcSignatureCustomObjectEnumerator>::MoveNext(&v44) )
  {
    *(_QWORD *)&pDigestMethod.cbSize = 32;
    memset(&pDigestMethod.wszAlgorithm, 0, 24);
    *(_QWORD *)&rgTransform.cbSize = 32;
    memset(&rgTransform.wszAlgorithm, 0, 24);
    win_dox::OpcSigningOptions::GetDefaultDigestMethod(a3, v55);
    v16 = (const WCHAR *)v56;
    if ( v56[3] >= 8u )
      v16 = (const WCHAR *)v56[0];
    do
    {
      win_dox::Enumerator<IOpcSignatureCustomObjectEnumerator>::GetCurrent(&v44, &v43);
      Uri = win_dox::OpcSignatureReference::GetUri(&v43, &v45);
      win_dox::Uri::GetAbsoluteUri(Uri, v53);
      if ( v45 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
        v45 = 0;
      }
      v18 = (const WCHAR *)wszURI;
      if ( wszURI[3] >= (LPCWSTR)8 )
        v18 = wszURI[0];
      v19 = v18;
      do
      {
        v20 = *(const WCHAR *)((char *)v19 + (char *)L"#idPackageObject" - (char *)v18);
        v21 = *v19 - v20;
        if ( v21 )
          break;
        ++v19;
      }
      while ( v20 );
      if ( !v21 )
      {
        std::wstring::wstring(v58, L"Custom reference must not have Uri equal to \"%{PackageReferenceUri}\".");
        v40 = win_musl::Formatter::Formatter(v60, v58);
        std::wstring::wstring(v57, L"PackageReferenceUri");
        v41 = (win_musl::Formatter *)win_musl::Formatter::insert<wchar_t [17]>(v40, v57);
        v42 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v41);
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::TSystemException *)pExceptionObject,
          0x71Bu,
          0x80510025,
          v42);
        throw (SplException::THResultException *)pExceptionObject;
      }
      win_dox::OpcSignatureReference::GetDigestMethod(&v43, v51);
      if ( v52[2] )
      {
        v22 = (const WCHAR *)v52;
        if ( v52[3] >= 8u )
          v22 = (const WCHAR *)v52[0];
      }
      else
      {
        v22 = v16;
      }
      pDigestMethod.wszAlgorithm = v22;
      TransformMethod = win_dox::OpcSignatureReference::GetTransformMethod((win_dox::OpcSignatureReference *)&v43);
      CanonicalizationString = win_dox::OpcDigitalSignatureManagerImpl::GetCanonicalizationString(v24, TransformMethod);
      wszAlgorithm = rgTransform.wszAlgorithm;
      if ( CanonicalizationString )
        wszAlgorithm = CanonicalizationString;
      rgTransform.wszAlgorithm = wszAlgorithm;
      cTransform = CanonicalizationString != 0;
      *(_QWORD *)&pEncoded.dwCharset = 0;
      Type = win_dox::OpcSignatureReference::GetType(&v43, v58);
      v29 = (const WCHAR *)(Type + 8);
      if ( *(_QWORD *)(Type + 32) >= 8u )
        v29 = *(const WCHAR **)v29;
      Id = win_dox::OpcSignatureReference::GetId(&v43, v57);
      v31 = (const WCHAR *)(Id + 8);
      if ( *(_QWORD *)(Id + 32) >= 8u )
        v31 = *(const WCHAR **)v31;
      v32 = CryptXmlCreateReference(
              a2,
              0,
              v31,
              v18,
              v29,
              &pDigestMethod,
              cTransform,
              &rgTransform,
              (HCRYPTXML *)&pEncoded);
      if ( v32 < 0 )
        SplException::RealThrowFromHR((SplException *)(unsigned int)v32, v33, v34, v35);
      LOBYTE(v33) = 1;
      std::wstring::_Tidy(v57, v33, 0);
      LOBYTE(v36) = 1;
      std::wstring::_Tidy(v58, v36, 0);
      LOBYTE(v37) = 1;
      std::wstring::_Tidy(v51, v37, 0);
      LOBYTE(v38) = 1;
      std::wstring::_Tidy(v53, v38, 0);
      if ( v43 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
        v43 = 0;
      }
    }
    while ( (unsigned __int8)win_dox::Enumerator<IOpcSignatureCustomObjectEnumerator>::MoveNext(&v44) );
    LOBYTE(v39) = 1;
    std::wstring::_Tidy(v55, v39, 0);
  }
  if ( v44 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
  if ( v46 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
}

```

## disassembly

```asm
0x1800c19a4  mov     rax, rsp
0x1800c19a7  push    rbp
0x1800c19a8  push    rdi
0x1800c19a9  push    r12
0x1800c19ab  push    r14
0x1800c19ad  push    r15
0x1800c19af  lea     rbp, [rax-1C8h]
0x1800c19b6  sub     rsp, 2A0h
0x1800c19bd  mov     [rbp+1C0h+var_200], 0FFFFFFFFFFFFFFFEh
0x1800c19c5  mov     [rax+8], rbx
0x1800c19c9  mov     [rax+20h], rsi
0x1800c19cd  mov     rax, cs:__security_cookie
0x1800c19d4  xor     rax, rsp
0x1800c19d7  mov     [rbp+1C0h+var_30], rax
0x1800c19de  mov     rdi, r8
0x1800c19e1  mov     r15, rdx
0x1800c19e4  mov     bl, 1
0x1800c19e6  lea     rdx, [rsp+2C0h+var_270]
0x1800c19eb  mov     rcx, r8
0x1800c19ee  call    ?GetCustomObjectSet@OpcSigningOptions@win_dox@@QEBA?AVOpcSignatureCustomObjectSet@2@XZ; win_dox::OpcSigningOptions::GetCustomObjectSet(void)
0x1800c19f3  nop
0x1800c19f4  lea     rdx, [rsp+2C0h+var_258]
0x1800c19f9  mov     rcx, rax
0x1800c19fc  call    ?GetEnumerator@OpcSignatureCustomObjectSet@win_dox@@QEAA?AV?$Enumerator@UIOpcSignatureCustomObjectEnumerator@@@2@XZ; win_dox::OpcSignatureCustomObjectSet::GetEnumerator(void)
0x1800c1a01  nop
0x1800c1a02  mov     rcx, [rsp+2C0h+var_270]
0x1800c1a07  xor     r12d, r12d
0x1800c1a0a  test    rcx, rcx
0x1800c1a0d  jz      short loc_1800C1A20
0x1800c1a0f  mov     rax, [rcx]
0x1800c1a12  mov     rax, [rax+10h]
0x1800c1a16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1a1b  mov     [rsp+2C0h+var_270], r12
0x1800c1a20  jmp     loc_1800C1AD1
0x1800c1a25  test    bl, bl
0x1800c1a27  jz      short loc_1800C1A37
0x1800c1a29  mov     r8d, 1440h; unsigned int
0x1800c1a2f  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x1800c1a34  mov     bl, r12b
0x1800c1a37  lea     rdx, [rsp+2C0h+var_268]
0x1800c1a3c  lea     rcx, [rsp+2C0h+var_258]
0x1800c1a41  call    ?GetCurrent@?$Enumerator@UIOpcSignatureCustomObjectEnumerator@@@win_dox@@QEBA?AVOpcSignatureCustomObject@2@XZ; win_dox::Enumerator<IOpcSignatureCustomObjectEnumerator>::GetCurrent(void)
0x1800c1a46  nop
0x1800c1a47  xor     edx, edx
0x1800c1a49  lea     rcx, [rsp+2C0h+pDigestMethod]
0x1800c1a4e  call    ?_Buy@?$vector@EV?$allocator@E@std@@@std@@IEAA_N_K@Z; std::vector<uchar>::_Buy(unsigned __int64)
0x1800c1a53  nop
0x1800c1a54  lea     rdx, [rsp+2C0h+pDigestMethod]
0x1800c1a59  lea     rcx, [rsp+2C0h+var_268]
0x1800c1a5e  call    ?GetXml@OpcSignatureCustomObject@win_dox@@QEAAXAEAV?$vector@EV?$allocator@E@std@@@std@@@Z; win_dox::OpcSignatureCustomObject::GetXml(std::vector<uchar> &)
0x1800c1a63  mov     [rbp+1C0h+var_230.dwCharset], r12d
0x1800c1a67  mov     rcx, [rsp+2C0h+pDigestMethod.wszAlgorithm]
0x1800c1a6c  test    rcx, rcx
0x1800c1a6f  jnz     short loc_1800C1A76
0x1800c1a71  mov     rax, r12
0x1800c1a74  jmp     short loc_1800C1A7D
0x1800c1a76  mov     rax, qword ptr [rbp+1C0h+pDigestMethod.Encoded.dwCharset]
0x1800c1a7a  sub     rax, rcx
0x1800c1a7d  mov     [rbp+1C0h+var_230.cbData], eax
0x1800c1a80  mov     [rbp+1C0h+var_230.pbData], rcx
0x1800c1a84  mov     [rsp+2C0h+ppObject], r12; ppObject
0x1800c1a89  lea     rax, [rbp+1C0h+var_230]
0x1800c1a8d  mov     [rsp+2C0h+pEncoded], rax; pEncoded
0x1800c1a92  xor     r9d, r9d; cProperty
0x1800c1a95  xor     r8d, r8d; rgProperty
0x1800c1a98  xor     edx, edx; dwFlags
0x1800c1a9a  mov     rcx, r15; hSignatureOrObject
0x1800c1a9d  call    cs:__imp_CryptXmlAddObject
0x1800c1aa3  test    eax, eax
0x1800c1aa5  js      loc_1800C1C0A
0x1800c1aab  lea     rcx, [rsp+2C0h+pDigestMethod]
0x1800c1ab0  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@IEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800c1ab5  nop
0x1800c1ab6  mov     rcx, [rsp+2C0h+var_268]
0x1800c1abb  test    rcx, rcx
0x1800c1abe  jz      short loc_1800C1AD1
0x1800c1ac0  mov     rax, [rcx]
0x1800c1ac3  mov     rax, [rax+10h]
0x1800c1ac7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1acc  mov     [rsp+2C0h+var_268], r12
0x1800c1ad1  lea     rcx, [rsp+2C0h+var_258]
0x1800c1ad6  call    ?MoveNext@?$Enumerator@UIOpcSignatureCustomObjectEnumerator@@@win_dox@@QEAA_NXZ; win_dox::Enumerator<IOpcSignatureCustomObjectEnumerator>::MoveNext(void)
0x1800c1adb  test    al, al
0x1800c1add  jnz     loc_1800C1A25
0x1800c1ae3  lea     rdx, [rsp+2C0h+var_260]
0x1800c1ae8  mov     rcx, rdi
0x1800c1aeb  call    ?GetCustomReferenceSet@OpcSigningOptions@win_dox@@QEBA?AVOpcSignatureReferenceSet@2@XZ; win_dox::OpcSigningOptions::GetCustomReferenceSet(void)
0x1800c1af0  nop
0x1800c1af1  lea     rdx, [rsp+2C0h+var_268]
0x1800c1af6  mov     rcx, rax
0x1800c1af9  call    ?GetEnumerator@OpcSignatureReferenceSet@win_dox@@QEAA?AV?$Enumerator@UIOpcSignatureReferenceEnumerator@@@2@XZ; win_dox::OpcSignatureReferenceSet::GetEnumerator(void)
0x1800c1afe  nop
0x1800c1aff  mov     rcx, [rsp+2C0h+var_260]
0x1800c1b04  test    rcx, rcx
0x1800c1b07  jz      short loc_1800C1B1A
0x1800c1b09  mov     rax, [rcx]
0x1800c1b0c  mov     rax, [rax+10h]
0x1800c1b10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1b15  mov     [rsp+2C0h+var_260], r12
0x1800c1b1a  lea     rcx, [rsp+2C0h+var_268]
0x1800c1b1f  call    ?MoveNext@?$Enumerator@UIOpcSignatureCustomObjectEnumerator@@@win_dox@@QEAA_NXZ; win_dox::Enumerator<IOpcSignatureCustomObjectEnumerator>::MoveNext(void)
0x1800c1b24  test    al, al
0x1800c1b26  jz      loc_1800C1D3E
0x1800c1b2c  mov     qword ptr [rsp+2C0h+pDigestMethod.cbSize], 20h ; ' '
0x1800c1b35  mov     [rsp+2C0h+pDigestMethod.wszAlgorithm], r12
0x1800c1b3a  mov     qword ptr [rbp+1C0h+pDigestMethod.Encoded.dwCharset], r12
0x1800c1b3e  mov     [rbp+1C0h+pDigestMethod.Encoded.pbData], r12
0x1800c1b42  mov     qword ptr [rbp+1C0h+var_220.cbSize], 20h ; ' '
0x1800c1b4a  mov     [rbp+1C0h+var_220.wszAlgorithm], r12
0x1800c1b4e  mov     qword ptr [rbp+1C0h+var_220.Encoded.dwCharset], r12
0x1800c1b52  mov     [rbp+1C0h+var_220.Encoded.pbData], r12
0x1800c1b56  lea     rdx, [rbp+1C0h+var_1A8]
0x1800c1b5a  mov     rcx, rdi
0x1800c1b5d  call    ?GetDefaultDigestMethod@OpcSigningOptions@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ; win_dox::OpcSigningOptions::GetDefaultDigestMethod(void)
0x1800c1b62  nop
0x1800c1b63  lea     rsi, [rbp+1C0h+var_1A0]
0x1800c1b67  cmp     [rbp+1C0h+var_188], 8
0x1800c1b6c  cmovnb  rsi, [rbp+1C0h+var_1A0]
0x1800c1b71  lea     rdx, [rsp+2C0h+var_270]
0x1800c1b76  lea     rcx, [rsp+2C0h+var_268]
0x1800c1b7b  call    ?GetCurrent@?$Enumerator@UIOpcSignatureCustomObjectEnumerator@@@win_dox@@QEBA?AVOpcSignatureCustomObject@2@XZ; win_dox::Enumerator<IOpcSignatureCustomObjectEnumerator>::GetCurrent(void)
0x1800c1b80  nop
0x1800c1b81  lea     rdx, [rsp+2C0h+var_260]
0x1800c1b86  lea     rcx, [rsp+2C0h+var_270]
0x1800c1b8b  call    ?GetUri@OpcSignatureReference@win_dox@@QEBA?AVUri@2@XZ; win_dox::OpcSignatureReference::GetUri(void)
0x1800c1b90  nop
0x1800c1b91  lea     rdx, [rbp+1C0h+var_1D0]
0x1800c1b95  mov     rcx, rax
0x1800c1b98  call    ?GetAbsoluteUri@Uri@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ; win_dox::Uri::GetAbsoluteUri(void)
0x1800c1b9d  nop
0x1800c1b9e  mov     rcx, [rsp+2C0h+var_260]
0x1800c1ba3  test    rcx, rcx
0x1800c1ba6  jz      short loc_1800C1BB9
0x1800c1ba8  mov     rax, [rcx]
0x1800c1bab  mov     rax, [rax+10h]
0x1800c1baf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1bb4  mov     [rsp+2C0h+var_260], r12
0x1800c1bb9  lea     rbx, [rbp+1C0h+wszURI]
0x1800c1bbd  cmp     [rbp+1C0h+var_1B0], 8
0x1800c1bc2  cmovnb  rbx, [rbp+1C0h+wszURI]
0x1800c1bc7  mov     rax, rbx
0x1800c1bca  lea     r8, ?gc_packageReferenceUri@Value@DigitalSignatures@win_musl@@3QB_WB; "#idPackageObject"
0x1800c1bd1  sub     r8, rbx
0x1800c1bd4  movzx   ecx, word ptr [rax]
0x1800c1bd7  movzx   edx, word ptr [rax+r8]
0x1800c1bdc  sub     ecx, edx
0x1800c1bde  jnz     short loc_1800C1BE8
0x1800c1be0  add     rax, 2
0x1800c1be4  test    edx, edx
0x1800c1be6  jnz     short loc_1800C1BD4
0x1800c1be8  test    ecx, ecx
0x1800c1bea  jz      loc_1800C1D9F
0x1800c1bf0  lea     rdx, [rbp+1C0h+var_1F8]
0x1800c1bf4  lea     rcx, [rsp+2C0h+var_270]
0x1800c1bf9  call    ?GetDigestMethod@OpcSignatureReference@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ; win_dox::OpcSignatureReference::GetDigestMethod(void)
0x1800c1bfe  nop
0x1800c1bff  cmp     [rbp+1C0h+var_1E0], r12
0x1800c1c03  jnz     short loc_1800C1C12
0x1800c1c05  mov     rax, rsi
0x1800c1c08  jmp     short loc_1800C1C20
0x1800c1c0a  mov     ecx, eax; this
0x1800c1c0c  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x1800c1c12  lea     rax, [rbp+1C0h+var_1F0]
0x1800c1c16  cmp     [rbp+1C0h+var_1D8], 8
0x1800c1c1b  cmovnb  rax, [rbp+1C0h+var_1F0]
0x1800c1c20  mov     [rsp+2C0h+pDigestMethod.wszAlgorithm], rax
0x1800c1c25  lea     rcx, [rsp+2C0h+var_270]; this
0x1800c1c2a  call    ?GetTransformMethod@OpcSignatureReference@win_dox@@QEBA?AW4__MIDL___MIDL_itf_msopc_0001_0076_0001@@XZ; win_dox::OpcSignatureReference::GetTransformMethod(void)
0x1800c1c2f  mov     edx, eax; enum __MIDL___MIDL_itf_msopc_0001_0076_0001
0x1800c1c31  call    ?GetCanonicalizationString@OpcDigitalSignatureManagerImpl@win_dox@@AEAAPEB_WW4__MIDL___MIDL_itf_msopc_0001_0076_0001@@@Z; win_dox::OpcDigitalSignatureManagerImpl::GetCanonicalizationString(__MIDL___MIDL_itf_msopc_0001_0076_0001)
0x1800c1c36  mov     rcx, [rbp+1C0h+var_220.wszAlgorithm]
0x1800c1c3a  test    rax, rax
0x1800c1c3d  cmovnz  rcx, rax
0x1800c1c41  mov     [rbp+1C0h+var_220.wszAlgorithm], rcx
0x1800c1c45  mov     r14d, r12d
0x1800c1c48  setnz   r14b
0x1800c1c4c  mov     qword ptr [rbp+1C0h+var_230.dwCharset], r12
0x1800c1c50  lea     rdx, [rbp+1C0h+var_158]
0x1800c1c54  lea     rcx, [rsp+2C0h+var_270]
0x1800c1c59  call    ?GetType@OpcSignatureReference@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ; win_dox::OpcSignatureReference::GetType(void)
0x1800c1c5e  nop
0x1800c1c5f  lea     rdi, [rax+8]
0x1800c1c63  cmp     qword ptr [rax+20h], 8
0x1800c1c68  jb      short loc_1800C1C6D
0x1800c1c6a  mov     rdi, [rdi]
0x1800c1c6d  lea     rdx, [rbp+1C0h+var_180]
0x1800c1c71  lea     rcx, [rsp+2C0h+var_270]
0x1800c1c76  call    ?GetId@OpcSignatureReference@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ; win_dox::OpcSignatureReference::GetId(void)
0x1800c1c7b  nop
0x1800c1c7c  lea     r8, [rax+8]
0x1800c1c80  cmp     qword ptr [rax+20h], 8
0x1800c1c85  jb      short loc_1800C1C8A
0x1800c1c87  mov     r8, [r8]; wszId
0x1800c1c8a  lea     rax, [rbp+1C0h+var_230]
0x1800c1c8e  mov     [rsp+2C0h+phReference], rax; phReference
0x1800c1c93  lea     rax, [rbp+1C0h+var_220]
0x1800c1c97  mov     [rsp+2C0h+rgTransform], rax; rgTransform
0x1800c1c9c  mov     [rsp+2C0h+cTransform], r14d; cTransform
0x1800c1ca1  lea     rax, [rsp+2C0h+pDigestMethod]
0x1800c1ca6  mov     [rsp+2C0h+ppObject], rax; pDigestMethod
0x1800c1cab  mov     [rsp+2C0h+pEncoded], rdi; wszType
0x1800c1cb0  mov     r9, rbx; wszURI
0x1800c1cb3  xor     edx, edx; dwFlags
0x1800c1cb5  mov     rcx, r15; hCryptXml
0x1800c1cb8  call    cs:__imp_CryptXmlCreateReference
0x1800c1cbe  test    eax, eax
0x1800c1cc0  js      loc_1800C1D97
0x1800c1cc6  xor     r8d, r8d
0x1800c1cc9  mov     dl, 1
0x1800c1ccb  lea     rcx, [rbp+1C0h+var_180]
0x1800c1ccf  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800c1cd4  nop
0x1800c1cd5  xor     r8d, r8d
0x1800c1cd8  mov     dl, 1
0x1800c1cda  lea     rcx, [rbp+1C0h+var_158]
0x1800c1cde  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800c1ce3  nop
0x1800c1ce4  xor     r8d, r8d
0x1800c1ce7  mov     dl, 1
0x1800c1ce9  lea     rcx, [rbp+1C0h+var_1F8]
0x1800c1ced  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800c1cf2  nop
0x1800c1cf3  xor     r8d, r8d
0x1800c1cf6  mov     dl, 1
0x1800c1cf8  lea     rcx, [rbp+1C0h+var_1D0]
0x1800c1cfc  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800c1d01  nop
0x1800c1d02  mov     rcx, [rsp+2C0h+var_270]
0x1800c1d07  test    rcx, rcx
0x1800c1d0a  jz      short loc_1800C1D1D
0x1800c1d0c  mov     rax, [rcx]
0x1800c1d0f  mov     rax, [rax+10h]
0x1800c1d13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1d18  mov     [rsp+2C0h+var_270], r12
0x1800c1d1d  lea     rcx, [rsp+2C0h+var_268]
0x1800c1d22  call    ?MoveNext@?$Enumerator@UIOpcSignatureCustomObjectEnumerator@@@win_dox@@QEAA_NXZ; win_dox::Enumerator<IOpcSignatureCustomObjectEnumerator>::MoveNext(void)
0x1800c1d27  test    al, al
0x1800c1d29  jnz     loc_1800C1B71
0x1800c1d2f  xor     r8d, r8d
0x1800c1d32  mov     dl, 1
0x1800c1d34  lea     rcx, [rbp+1C0h+var_1A8]
0x1800c1d38  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800c1d3d  nop
0x1800c1d3e  mov     rcx, [rsp+2C0h+var_268]
0x1800c1d43  test    rcx, rcx
0x1800c1d46  jz      short loc_1800C1D55
0x1800c1d48  mov     rax, [rcx]
0x1800c1d4b  mov     rax, [rax+10h]
0x1800c1d4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1d54  nop
0x1800c1d55  mov     rcx, [rsp+2C0h+var_258]
0x1800c1d5a  test    rcx, rcx
0x1800c1d5d  jz      short loc_1800C1D6C
0x1800c1d5f  mov     rax, [rcx]
0x1800c1d62  mov     rax, [rax+10h]
0x1800c1d66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1d6b  nop
0x1800c1d6c  mov     rcx, [rbp+1C0h+var_30]
0x1800c1d73  xor     rcx, rsp; StackCookie
0x1800c1d76  call    __security_check_cookie
0x1800c1d7b  lea     r11, [rsp+2C0h+var_20]
0x1800c1d83  mov     rbx, [r11+30h]
0x1800c1d87  mov     rsi, [r11+48h]
0x1800c1d8b  mov     rsp, r11
0x1800c1d8e  pop     r15
0x1800c1d90  pop     r14
0x1800c1d92  pop     r12
0x1800c1d94  pop     rdi
0x1800c1d95  pop     rbp
0x1800c1d96  retn
0x1800c1d97  mov     ecx, eax; this
0x1800c1d99  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x1800c1d9f  lea     rdx, aCustomReferenc; "Custom reference must not have Uri equa"...
0x1800c1da6  lea     rcx, [rbp+1C0h+var_158]
0x1800c1daa  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x1800c1daf  nop
0x1800c1db0  lea     rdx, [rbp+1C0h+var_158]
0x1800c1db4  lea     rcx, [rbp+1C0h+var_90]
0x1800c1dbb  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x1800c1dc0  mov     rbx, rax
0x1800c1dc3  lea     rdx, aPackagereferen; "PackageReferenceUri"
0x1800c1dca  lea     rcx, [rbp+1C0h+var_180]
0x1800c1dce  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x1800c1dd3  nop
0x1800c1dd4  lea     rdx, [rbp+1C0h+var_180]
0x1800c1dd8  mov     rcx, rbx
0x1800c1ddb  call    ??$insert@$$BY0BB@_W@Formatter@win_musl@@QEAAAEAV01@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@AEAY0BB@$$CB_W@Z; win_musl::Formatter::insert<wchar_t [17]>(std::wstring const &,wchar_t const (&)[17])
0x1800c1de0  mov     rcx, rax; this
0x1800c1de3  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x1800c1de8  mov     qword ptr [rsp+2C0h+cTransform], rax; struct win_musl::TStringEllipseBase *
0x1800c1ded  mov     dword ptr [rsp+2C0h+ppObject], 80510025h; unsigned int
0x1800c1df5  mov     dword ptr [rsp+2C0h+pEncoded], 71Bh; unsigned int
0x1800c1dfd  lea     r9, word_18013A0B6
0x1800c1e04  lea     r8, aNoFilename; "(no filename)"
0x1800c1e0b  lea     rcx, [rbp+1C0h+pExceptionObject]; this
0x1800c1e12  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800c1e17  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800c1e1e  lea     rcx, [rbp+1C0h+pExceptionObject]; pExceptionObject
0x1800c1e25  call    _CxxThrowException_0
```
