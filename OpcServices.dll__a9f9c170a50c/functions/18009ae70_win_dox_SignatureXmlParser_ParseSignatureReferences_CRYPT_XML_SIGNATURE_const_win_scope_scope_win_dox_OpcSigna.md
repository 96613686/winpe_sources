# win_dox::SignatureXmlParser::ParseSignatureReferences(_CRYPT_XML_SIGNATURE const *,win_scope::scope<win_dox::OpcSignatureReferenceImpl *,win_scope::const_policies<win_scope::shared_policies>> *,win_scope::scope<win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureReference,IOpcSignatureReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureReference>> *,win_scope::const_policies<win_scope::shared_policies>>)

- ea: `0x18009ae70`
- end: `0x18009b4a6`
- name: `?ParseSignatureReferences@SignatureXmlParser@win_dox@@SAXPEBU_CRYPT_XML_SIGNATURE@@PEAV?$scope@PEAVOpcSignatureReferenceImpl@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAV?$OpcEnumerableSetImpl@VOpcSignatureReference@win_dox@@UIOpcSignatureReferenceEnumerator@@U?$com_wrapper_less@VOpcSignatureReference@win_dox@@@2@@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@5@@Z`
- size: `1590`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18009ace4`
- `0x18009f9c4`

## callees

- `0x1800016b0`
- `0x180001abc`
- `0x180008398`
- `0x180015a68`
- `0x180017dd0`
- `0x180018c00`
- `0x18001a810`
- `0x18001d200`
- `0x1800517a0`
- `0x18009ae70`
- `0x18009b4ac`
- `0x18009b574`
- `0x1800cd38c`
- `0x1800d5fe4`
- `0x1800ec504`
- `0x180104664`
- `0x180104828`
- `0x18010a040`
- `0x180117740`
- `0x18012a010`

## import_xrefs

- `CRYPTXML!CryptXmlGetReference` at `0x18009aef1`
- `CRYPTXML!CryptXmlGetReference` at `0x18009aef1`
- `CRYPTXML!CryptXmlGetStatus` at `0x18009af11`
- `CRYPTXML!CryptXmlGetStatus` at `0x18009af11`

## string_xrefs

- `0x18009b352`: `Call to CryptXmlGetStatus failed with HResult 0x%X.`
- `0x18009b3c1`: `Call to CryptXmlGetReference failed with HResult 0x%X.`
- `0x18009b26f`: `Invalid Signature Xml - there should be exactly one reference to the package specific reference in SignedInfo - more than one was found`
- `0x18009b2b3`: `Invalid Signature Xml - all references in the package signature must be internal`
- `0x18009b2f7`: `Invalid Signature Xml - the URI attribute is missing for Reference element`
- `0x18009b41e`: `Invalid Signature Xml - there should be exactly one reference to the package specific reference in SignedInfo - None were found`

## pseudocode

```c
// Hidden C++ exception states: #wind=26
__int64 __fastcall win_dox::SignatureXmlParser::ParseSignatureReferences(__int64 a1, __m128i *a2, _QWORD *a3)
{
  int v5; // edi
  __int64 result; // rax
  char v7; // r12
  unsigned int i; // r14d
  HRESULT Reference; // ebx
  const char *v10; // rdx
  HRESULT Status; // ebx
  unsigned int v12; // r8d
  void *v13; // r15
  int v14; // edi
  enum __MIDL___MIDL_itf_msopc_0001_0076_0001 CombinedCanonicalizationMethod; // ebx
  LPCWSTR wszAlgorithm; // rdx
  int v17; // edi
  LPCWSTR wszType; // rdx
  int v19; // edi
  LPCWSTR wszId; // rdx
  int v21; // edi
  LPCWSTR wszUri; // rdx
  int Uri; // eax
  __int64 v24; // rax
  __int64 v25; // rdx
  LPCWSTR v26; // rcx
  char *v27; // r8
  int v28; // eax
  int v29; // edx
  __m128i v30; // xmm1
  __int64 v31; // rax
  win_dox *v32; // [rsp+30h] [rbp-D8h]
  CRYPT_XML_REFERENCE *ppStruct; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v34; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v35; // [rsp+60h] [rbp-A8h]
  __int64 v36; // [rsp+68h] [rbp-A0h] BYREF
  _QWORD v37[3]; // [rsp+70h] [rbp-98h] BYREF
  __m128i *v38; // [rsp+88h] [rbp-80h]
  __int64 v39; // [rsp+90h] [rbp-78h]
  _QWORD *v40; // [rsp+98h] [rbp-70h]
  void *v41; // [rsp+A0h] [rbp-68h]
  char v42[16]; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v43[4]; // [rsp+C0h] [rbp-48h] BYREF
  CRYPT_XML_STATUS pStatus; // [rsp+E0h] [rbp-28h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+F8h] [rbp-10h] BYREF
  _BYTE v46[40]; // [rsp+198h] [rbp+90h] BYREF
  int v47[10]; // [rsp+1C0h] [rbp+B8h] BYREF
  int v48[10]; // [rsp+1E8h] [rbp+E0h] BYREF
  __int64 v49[5]; // [rsp+210h] [rbp+108h] BYREF
  wchar_t v50[512]; // [rsp+238h] [rbp+130h] BYREF

  v39 = -2;
  v38 = a2;
  v40 = a3;
  v5 = 0;
  ppStruct = 0;
  result = 0;
  *(_QWORD *)&pStatus.cbSize = 0;
  pStatus.dwInfoStatus = 0;
  v7 = 0;
  for ( i = 0; i < *(_DWORD *)(a1 + 104); ++i )
  {
    Reference = CryptXmlGetReference(
                  *(HCRYPTXML *)(*(_QWORD *)(*(_QWORD *)(a1 + 112) + 8LL * i) + 8LL),
                  (const CRYPT_XML_REFERENCE **)&ppStruct);
    if ( Reference < 0 )
    {
      memset_0(v50, 0, sizeof(v50));
      StringCchPrintfW(v50, 0x200u, L"Call to CryptXmlGetReference failed with HResult 0x%X.", (unsigned int)Reference);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x24Fu,
        Reference,
        (struct win_musl::TStringEllipseBase *)v50);
      throw (SplException::THResultException *)pExceptionObject;
    }
    Status = CryptXmlGetStatus(*(HCRYPTXML *)(*(_QWORD *)(*(_QWORD *)(a1 + 112) + 8LL * i) + 8LL), &pStatus);
    if ( Status < 0 )
    {
      memset_0(v50, 0, sizeof(v50));
      StringCchPrintfW(v50, 0x200u, L"Call to CryptXmlGetStatus failed with HResult 0x%X.", (unsigned int)Status);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x259u,
        Status,
        (struct win_musl::TStringEllipseBase *)v50);
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( !ppStruct->wszUri )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x25Eu,
        0x80510043,
        (struct win_musl::TStringEllipseBase *)L"Invalid Signature Xml - the URI attribute is missing for Reference element");
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( (pStatus.dwInfoStatus & 1) == 0 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x28Au,
        0x8051002F,
        (struct win_musl::TStringEllipseBase *)L"Invalid Signature Xml - all references in the package signature must be internal");
      throw (SplException::THResultException *)pExceptionObject;
    }
    v13 = operator new(0xA8u, v10, v12);
    v41 = v13;
    if ( v13 )
    {
      std::vector<unsigned char>::_Construct<unsigned char *>(
        v43,
        ppStruct->DigestValue.pbData,
        &ppStruct->DigestValue.pbData[ppStruct->DigestValue.cbData]);
      v14 = v5 | 1;
      CombinedCanonicalizationMethod = win_dox::SignatureXmlParser::GetCombinedCanonicalizationMethod(ppStruct);
      wszAlgorithm = &psz;
      if ( ppStruct->DigestMethod.wszAlgorithm )
        wszAlgorithm = ppStruct->DigestMethod.wszAlgorithm;
      std::wstring::wstring(v49, wszAlgorithm);
      v17 = v14 | 2;
      wszType = &psz;
      if ( ppStruct->wszType )
        wszType = ppStruct->wszType;
      std::wstring::wstring(v48, wszType);
      v19 = v17 | 4;
      wszId = &psz;
      if ( ppStruct->wszId )
        wszId = ppStruct->wszId;
      std::wstring::wstring(v47, wszId);
      v21 = v19 | 8;
      wszUri = &psz;
      if ( ppStruct->wszUri )
        wszUri = ppStruct->wszUri;
      std::wstring::wstring(v46, wszUri);
      Uri = win_dox::Uri::CreateUri(v37, v46, 1);
      v5 = v21 | 0x30;
      LODWORD(v32) = CombinedCanonicalizationMethod;
      v24 = win_dox::OpcSignatureReferenceImpl::OpcSignatureReferenceImpl(
              (int)v13,
              Uri,
              (int)v47,
              (int)v48,
              (__int64)v49,
              v32,
              (__int64)v43);
    }
    else
    {
      v24 = 0;
    }
    win_scope::scope<win_dox::OpcSignatureReferenceImpl *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::OpcSignatureReferenceImpl *,win_scope::const_policies<win_scope::shared_policies>>(
      &v34,
      v24);
    if ( (v5 & 0x20) != 0 )
    {
      v5 &= ~0x20u;
      if ( v37[0] )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v37[0] + 16LL))(v37[0]);
        v37[0] = 0;
      }
    }
    if ( (v5 & 0x10) != 0 )
    {
      v5 &= ~0x10u;
      LOBYTE(v25) = 1;
      std::wstring::_Tidy(v46, v25, 0);
    }
    if ( (v5 & 8) != 0 )
    {
      v5 &= ~8u;
      LOBYTE(v25) = 1;
      std::wstring::_Tidy(v47, v25, 0);
    }
    if ( (v5 & 4) != 0 )
    {
      v5 &= ~4u;
      LOBYTE(v25) = 1;
      std::wstring::_Tidy(v48, v25, 0);
    }
    if ( (v5 & 2) != 0 )
    {
      v5 &= ~2u;
      LOBYTE(v25) = 1;
      std::wstring::_Tidy(v49, v25, 0);
    }
    if ( (v5 & 1) != 0 )
    {
      v5 &= ~1u;
      std::vector<unsigned char>::_Tidy(v43);
    }
    v26 = ppStruct->wszUri;
    v27 = (char *)((char *)L"#idPackageObject" - (char *)v26);
    do
    {
      v28 = *(unsigned __int16 *)&v27[(_QWORD)v26];
      v29 = *v26 - v28;
      if ( v29 )
        break;
      ++v26;
    }
    while ( v28 );
    if ( v29 )
    {
      v31 = win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(
              v42,
              &v34);
      win_dox::CreateInstanceFromInner<IOpcSignatureReference,win_scope::scope<win_dox::OpcSignatureReferenceImpl *,win_scope::const_policies<win_scope::shared_policies>>>(
        &v36,
        v31);
      result = win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureRelationshipReference,IOpcSignatureRelationshipReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>>::Add(
                 a3[1],
                 &v36);
      if ( v36 )
      {
        result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
        v36 = 0;
      }
      if ( v34 && v35 )
      {
        result = win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(&v34);
        v34 = 0;
        v35 = 0;
      }
    }
    else
    {
      if ( v7 )
      {
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::TSystemException *)pExceptionObject,
          0x281u,
          0x8051002D,
          (struct win_musl::TStringEllipseBase *)L"Invalid Signature Xml - there should be exactly one reference to the pa"
                                                  "ckage specific reference in SignedInfo - more than one was found");
        throw (SplException::THResultException *)pExceptionObject;
      }
      v7 = 1;
      win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(
        &v37[1],
        &v34);
      v30 = *v38;
      *v38 = *(__m128i *)&v37[1];
      *(__m128i *)&v37[1] = v30;
      result = v30.m128i_i64[0];
      if ( v30.m128i_i64[0] )
      {
        result = _mm_srli_si128(v30, 8).m128i_u64[0];
        if ( result )
        {
          result = win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(&v37[1]);
          *(_OWORD *)&v37[1] = 0u;
        }
      }
      if ( v34 )
      {
        if ( v35 )
        {
          result = win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(&v34);
          v34 = 0;
          v35 = 0;
        }
      }
    }
  }
  if ( !v7 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x290u,
      0x8051002E,
      (struct win_musl::TStringEllipseBase *)L"Invalid Signature Xml - there should be exactly one reference to the packag"
                                              "e specific reference in SignedInfo - None were found");
    throw (SplException::THResultException *)pExceptionObject;
  }
  if ( *a3 && a3[1] )
  {
    result = win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(a3);
    *a3 = 0;
    a3[1] = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18009ae70  mov     rax, rsp
0x18009ae73  push    rbp
0x18009ae74  push    rsi
0x18009ae75  push    rdi
0x18009ae76  push    r12
0x18009ae78  push    r13
0x18009ae7a  push    r14
0x18009ae7c  push    r15
0x18009ae7e  lea     rbp, [rax-578h]
0x18009ae85  sub     rsp, 640h
0x18009ae8c  mov     [rbp+570h+var_5E8], 0FFFFFFFFFFFFFFFEh
0x18009ae94  mov     [rax+20h], rbx
0x18009ae98  mov     rax, cs:__security_cookie
0x18009ae9f  xor     rax, rsp
0x18009aea2  mov     [rbp+570h+var_40], rax
0x18009aea9  mov     rsi, r8
0x18009aeac  mov     [rbp+570h+var_5F0], rdx
0x18009aeb0  mov     r13, rcx
0x18009aeb3  mov     [rbp+570h+var_5E0], r8
0x18009aeb7  xor     ebx, ebx
0x18009aeb9  mov     edi, ebx
0x18009aebb  mov     dword ptr [rsp+670h+var_630], ebx
0x18009aebf  mov     [rsp+670h+ppStruct], rbx
0x18009aec4  xor     eax, eax
0x18009aec6  mov     qword ptr [rbp+570h+pStatus.cbSize], rax
0x18009aeca  mov     [rbp+570h+pStatus.dwInfoStatus], eax
0x18009aecd  mov     r12b, bl
0x18009aed0  mov     r14d, ebx
0x18009aed3  cmp     r14d, [r13+68h]
0x18009aed7  jnb     loc_18009B419
0x18009aedd  mov     r15d, r14d
0x18009aee0  mov     rax, [r13+70h]
0x18009aee4  mov     rcx, [rax+r15*8]
0x18009aee8  lea     rdx, [rsp+670h+ppStruct]; ppStruct
0x18009aeed  mov     rcx, [rcx+8]; hCryptXml
0x18009aef1  call    cs:__imp_CryptXmlGetReference
0x18009aef7  mov     ebx, eax
0x18009aef9  test    eax, eax
0x18009aefb  js      loc_18009B3AA
0x18009af01  mov     rax, [r13+70h]
0x18009af05  mov     rcx, [rax+r15*8]
0x18009af09  lea     rdx, [rbp+570h+pStatus]; pStatus
0x18009af0d  mov     rcx, [rcx+8]; hCryptXml
0x18009af11  call    cs:__imp_CryptXmlGetStatus
0x18009af17  mov     ebx, eax
0x18009af19  test    eax, eax
0x18009af1b  js      loc_18009B33B
0x18009af21  mov     rax, [rsp+670h+ppStruct]
0x18009af26  xor     ebx, ebx
0x18009af28  cmp     [rax+18h], rbx
0x18009af2c  jz      loc_18009B2F7
0x18009af32  mov     eax, [rbp+570h+pStatus.dwInfoStatus]
0x18009af35  test    al, 1
0x18009af37  jz      loc_18009B2B3
0x18009af3d  mov     ecx, 0A8h; unsigned __int64
0x18009af42  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x18009af47  mov     r15, rax
0x18009af4a  mov     [rbp+570h+var_5D8], rax
0x18009af4e  test    rax, rax
0x18009af51  jz      loc_18009B081
0x18009af57  mov     rcx, [rsp+670h+ppStruct]
0x18009af5c  mov     rdx, [rcx+50h]
0x18009af60  mov     r8d, [rcx+48h]
0x18009af64  add     r8, rdx
0x18009af67  lea     rcx, [rbp+570h+var_5B8]
0x18009af6b  call    ??$_Construct@PEAE@?$vector@EV?$allocator@E@std@@@std@@QEAAXPEAE0Uinput_iterator_tag@1@@Z; std::vector<uchar>::_Construct<uchar *>(uchar *,uchar *,std::input_iterator_tag)
0x18009af70  nop
0x18009af71  or      edi, 1
0x18009af74  mov     dword ptr [rsp+670h+var_630], edi
0x18009af78  mov     rcx, [rsp+670h+ppStruct]; struct _CRYPT_XML_REFERENCE *
0x18009af7d  call    ?GetCombinedCanonicalizationMethod@SignatureXmlParser@win_dox@@CA?AW4__MIDL___MIDL_itf_msopc_0001_0076_0001@@PEBU_CRYPT_XML_REFERENCE@@@Z; win_dox::SignatureXmlParser::GetCombinedCanonicalizationMethod(_CRYPT_XML_REFERENCE const *)
0x18009af82  mov     ebx, eax
0x18009af84  mov     rcx, [rsp+670h+ppStruct]
0x18009af89  lea     rdx, psz
0x18009af90  cmp     qword ptr [rcx+30h], 0
0x18009af95  cmovnz  rdx, [rcx+30h]
0x18009af9a  lea     rcx, [rbp+570h+var_468]
0x18009afa1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x18009afa6  nop
0x18009afa7  or      edi, 2
0x18009afaa  mov     dword ptr [rsp+670h+var_630], edi
0x18009afae  mov     rax, [rsp+670h+ppStruct]
0x18009afb3  lea     rdx, psz
0x18009afba  cmp     qword ptr [rax+20h], 0
0x18009afbf  cmovnz  rdx, [rax+20h]
0x18009afc4  lea     rcx, [rbp+570h+var_490]
0x18009afcb  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x18009afd0  nop
0x18009afd1  or      edi, 4
0x18009afd4  mov     dword ptr [rsp+670h+var_630], edi
0x18009afd8  mov     rax, [rsp+670h+ppStruct]
0x18009afdd  lea     rdx, psz
0x18009afe4  cmp     qword ptr [rax+10h], 0
0x18009afe9  cmovnz  rdx, [rax+10h]
0x18009afee  lea     rcx, [rbp+570h+var_4B8]
0x18009aff5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x18009affa  nop
0x18009affb  or      edi, 8
0x18009affe  mov     dword ptr [rsp+670h+var_630], edi
0x18009b002  mov     rax, [rsp+670h+ppStruct]
0x18009b007  lea     rdx, psz
0x18009b00e  cmp     qword ptr [rax+18h], 0
0x18009b013  cmovnz  rdx, [rax+18h]
0x18009b018  lea     rcx, [rbp+570h+var_4E0]
0x18009b01f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x18009b024  nop
0x18009b025  or      edi, 10h
0x18009b028  mov     dword ptr [rsp+670h+var_630], edi
0x18009b02c  mov     r8d, 1
0x18009b032  lea     rdx, [rbp+570h+var_4E0]
0x18009b039  lea     rcx, [rsp+670h+var_608]
0x18009b03e  call    ?CreateUri@Uri@win_dox@@SA?AV12@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@K@Z; win_dox::Uri::CreateUri(std::wstring const &,ulong)
0x18009b043  nop
0x18009b044  or      edi, 20h
0x18009b047  mov     dword ptr [rsp+670h+var_630], edi
0x18009b04b  lea     rcx, [rbp+570h+var_5B8]
0x18009b04f  mov     [rsp+30h], rcx; __int64
0x18009b054  mov     dword ptr [rsp+670h+var_648], ebx; win_dox *
0x18009b058  lea     rcx, [rbp+570h+var_468]
0x18009b05f  mov     qword ptr [rsp+670h+var_650], rcx; __int64
0x18009b064  lea     r9, [rbp+570h+var_490]; int
0x18009b06b  lea     r8, [rbp+570h+var_4B8]; int
0x18009b072  mov     rdx, rax; int
0x18009b075  mov     rcx, r15; int
0x18009b078  call    ??0OpcSignatureReferenceImpl@win_dox@@QEAA@AEBVUri@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@11W4__MIDL___MIDL_itf_msopc_0001_0076_0001@@AEBV?$vector@EV?$allocator@E@std@@@4@@Z; win_dox::OpcSignatureReferenceImpl::OpcSignatureReferenceImpl(win_dox::Uri const &,std::wstring const &,std::wstring const &,std::wstring const &,__MIDL___MIDL_itf_msopc_0001_0076_0001,std::vector<uchar> const &)
0x18009b07d  xor     ebx, ebx
0x18009b07f  jmp     short loc_18009B084
0x18009b081  mov     rax, rbx
0x18009b084  mov     rdx, rax
0x18009b087  lea     rcx, [rsp+670h+var_620]
0x18009b08c  call    ??0?$scope@PEAVOpcSignatureReferenceImpl@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@QEAA@PEAVOpcSignatureReferenceImpl@win_dox@@@Z; win_scope::scope<win_dox::OpcSignatureReferenceImpl *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::OpcSignatureReferenceImpl *,win_scope::const_policies<win_scope::shared_policies>>(win_dox::OpcSignatureReferenceImpl *)
0x18009b091  nop
0x18009b092  test    dil, 20h
0x18009b096  jz      short loc_18009B0BA
0x18009b098  and     edi, 0FFFFFFDFh
0x18009b09b  mov     dword ptr [rsp+670h+var_630], edi
0x18009b09f  mov     rcx, qword ptr [rsp+670h+var_608]
0x18009b0a4  test    rcx, rcx
0x18009b0a7  jz      short loc_18009B0BA
0x18009b0a9  mov     rax, [rcx]
0x18009b0ac  mov     rax, [rax+10h]
0x18009b0b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b0b5  mov     qword ptr [rsp+670h+var_608], rbx
0x18009b0ba  test    dil, 10h
0x18009b0be  jz      short loc_18009B0D9
0x18009b0c0  and     edi, 0FFFFFFEFh
0x18009b0c3  mov     dword ptr [rsp+670h+var_630], edi
0x18009b0c7  xor     r8d, r8d
0x18009b0ca  mov     dl, 1
0x18009b0cc  lea     rcx, [rbp+570h+var_4E0]
0x18009b0d3  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18009b0d8  nop
0x18009b0d9  test    dil, 8
0x18009b0dd  jz      short loc_18009B0F8
0x18009b0df  and     edi, 0FFFFFFF7h
0x18009b0e2  mov     dword ptr [rsp+670h+var_630], edi
0x18009b0e6  xor     r8d, r8d
0x18009b0e9  mov     dl, 1
0x18009b0eb  lea     rcx, [rbp+570h+var_4B8]
0x18009b0f2  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18009b0f7  nop
0x18009b0f8  test    dil, 4
0x18009b0fc  jz      short loc_18009B117
0x18009b0fe  and     edi, 0FFFFFFFBh
0x18009b101  mov     dword ptr [rsp+670h+var_630], edi
0x18009b105  xor     r8d, r8d
0x18009b108  mov     dl, 1
0x18009b10a  lea     rcx, [rbp+570h+var_490]
0x18009b111  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18009b116  nop
0x18009b117  test    dil, 2
0x18009b11b  jz      short loc_18009B136
0x18009b11d  and     edi, 0FFFFFFFDh
0x18009b120  mov     dword ptr [rsp+670h+var_630], edi
0x18009b124  xor     r8d, r8d
0x18009b127  mov     dl, 1
0x18009b129  lea     rcx, [rbp+570h+var_468]
0x18009b130  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18009b135  nop
0x18009b136  test    dil, 1
0x18009b13a  jz      short loc_18009B14C
0x18009b13c  and     edi, 0FFFFFFFEh
0x18009b13f  mov     dword ptr [rsp+670h+var_630], edi
0x18009b143  lea     rcx, [rbp+570h+var_5B8]
0x18009b147  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@IEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18009b14c  mov     rax, [rsp+670h+ppStruct]
0x18009b151  mov     rcx, [rax+18h]
0x18009b155  lea     r8, ?gc_packageReferenceUri@Value@DigitalSignatures@win_musl@@3QB_WB; "#idPackageObject"
0x18009b15c  sub     r8, rcx
0x18009b15f  movzx   edx, word ptr [rcx]
0x18009b162  movzx   eax, word ptr [rcx+r8]
0x18009b167  sub     edx, eax
0x18009b169  jnz     short loc_18009B173
0x18009b16b  add     rcx, 2
0x18009b16f  test    eax, eax
0x18009b171  jnz     short loc_18009B15F
0x18009b173  test    edx, edx
0x18009b175  jnz     loc_18009B1FF
0x18009b17b  test    r12b, r12b
0x18009b17e  jnz     loc_18009B26F
0x18009b184  mov     r12b, 1
0x18009b187  lea     rdx, [rsp+670h+var_620]
0x18009b18c  lea     rcx, [rsp+670h+var_608+8]
0x18009b191  call    ??0?$scope@PEBU_CERT_CONTEXT@@U?$const_policies@U?$shared_close_policies@U?$close_function@P6AHPEBU_CERT_CONTEXT@@@Z$1?CertFreeCertificateContext@@YAH0@Z@win_scope@@@win_scope@@@win_scope@@@win_scope@@QEAA@AEBV01@@Z; win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>> const &)
0x18009b196  mov     rbx, [rbp+570h+var_5F0]
0x18009b19a  movups  xmm1, xmmword ptr [rbx]
0x18009b19d  movaps  xmm0, xmmword ptr [rsp+670h+var_608+8]
0x18009b1a2  movdqu  xmmword ptr [rbx], xmm0
0x18009b1a6  movdqa  xmmword ptr [rsp+670h+var_608+8], xmm1
0x18009b1ac  movq    rax, xmm1
0x18009b1b1  xor     ebx, ebx
0x18009b1b3  test    rax, rax
0x18009b1b6  jz      short loc_18009B1DB
0x18009b1b8  psrldq  xmm1, 8
0x18009b1bd  movq    rax, xmm1
0x18009b1c2  test    rax, rax
0x18009b1c5  jz      short loc_18009B1DB
0x18009b1c7  lea     rcx, [rsp+670h+var_608+8]
0x18009b1cc  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x18009b1d1  mov     qword ptr [rsp+670h+var_608+8], rbx
0x18009b1d6  mov     qword ptr [rsp+670h+var_608+10h], rbx
0x18009b1db  cmp     [rsp+670h+var_620], rbx
0x18009b1e0  jz      short loc_18009B1FD
0x18009b1e2  cmp     [rsp+670h+var_618], rbx
0x18009b1e7  jz      short loc_18009B1FD
0x18009b1e9  lea     rcx, [rsp+670h+var_620]
0x18009b1ee  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x18009b1f3  mov     [rsp+670h+var_620], rbx
0x18009b1f8  mov     [rsp+670h+var_618], rbx
0x18009b1fd  jmp     short loc_18009B267
0x18009b1ff  lea     rdx, [rsp+670h+var_620]
0x18009b204  lea     rcx, [rbp+570h+var_5C8]
0x18009b208  call    ??0?$scope@PEBU_CERT_CONTEXT@@U?$const_policies@U?$shared_close_policies@U?$close_function@P6AHPEBU_CERT_CONTEXT@@@Z$1?CertFreeCertificateContext@@YAH0@Z@win_scope@@@win_scope@@@win_scope@@@win_scope@@QEAA@AEBV01@@Z; win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>> const &)
0x18009b20d  mov     rdx, rax
0x18009b210  lea     rcx, [rsp+670h+var_610]
0x18009b215  call    ??$CreateInstanceFromInner@UIOpcSignatureReference@@V?$scope@PEAVOpcSignatureReferenceImpl@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@win_dox@@YA?AVOpcSignatureReference@0@V?$scope@PEAVOpcSignatureReferenceImpl@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@Z; win_dox::CreateInstanceFromInner<IOpcSignatureReference,win_scope::scope<win_dox::OpcSignatureReferenceImpl *,win_scope::const_policies<win_scope::shared_policies>>>(win_scope::scope<win_dox::OpcSignatureReferenceImpl *,win_scope::const_policies<win_scope::shared_policies>>)
0x18009b21a  nop
0x18009b21b  lea     rdx, [rsp+670h+var_610]
0x18009b220  mov     rcx, [rsi+8]
0x18009b224  call    ?Add@?$OpcEnumerableSetImpl@VOpcSignatureRelationshipReference@win_dox@@UIOpcSignatureRelationshipReferenceEnumerator@@U?$com_wrapper_less@VOpcSignatureRelationshipReference@win_dox@@@2@@win_dox@@QEAAXAEBVOpcSignatureRelationshipReference@2@@Z; win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureRelationshipReference,IOpcSignatureRelationshipReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>>::Add(win_dox::OpcSignatureRelationshipReference const &)
0x18009b229  nop
0x18009b22a  mov     rcx, [rsp+670h+var_610]
0x18009b22f  test    rcx, rcx
0x18009b232  jz      short loc_18009B245
0x18009b234  mov     rax, [rcx]
0x18009b237  mov     rax, [rax+10h]
0x18009b23b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b240  mov     [rsp+670h+var_610], rbx
0x18009b245  cmp     [rsp+670h+var_620], rbx
0x18009b24a  jz      short loc_18009B267
0x18009b24c  cmp     [rsp+670h+var_618], rbx
0x18009b251  jz      short loc_18009B267
0x18009b253  lea     rcx, [rsp+670h+var_620]
0x18009b258  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x18009b25d  mov     [rsp+670h+var_620], rbx
0x18009b262  mov     [rsp+670h+var_618], rbx
0x18009b267  inc     r14d
0x18009b26a  jmp     loc_18009AED3
0x18009b26f  lea     rax, aInvalidSignatu_0; "Invalid Signature Xml - there should be"...
0x18009b276  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x18009b27b  mov     dword ptr [rsp+670h+var_648], 8051002Dh; unsigned int
0x18009b283  mov     [rsp+670h+var_650], 281h; unsigned int
0x18009b28b  lea     r9, word_18013A0B6
0x18009b292  lea     r8, aNoFilename; "(no filename)"
0x18009b299  lea     rcx, [rbp+570h+pExceptionObject]; this
0x18009b29d  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18009b2a2  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18009b2a9  lea     rcx, [rbp+570h+pExceptionObject]; pExceptionObject
0x18009b2ad  call    _CxxThrowException_0
0x18009b2b3  lea     rax, aInvalidSignatu_8; "Invalid Signature Xml - all references "...
0x18009b2ba  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x18009b2bf  mov     dword ptr [rsp+670h+var_648], 8051002Fh; unsigned int
0x18009b2c7  mov     [rsp+670h+var_650], 28Ah; unsigned int
0x18009b2cf  lea     r9, word_18013A0B6
0x18009b2d6  lea     r8, aNoFilename; "(no filename)"
0x18009b2dd  lea     rcx, [rbp+570h+pExceptionObject]; this
0x18009b2e1  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18009b2e6  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18009b2ed  lea     rcx, [rbp+570h+pExceptionObject]; pExceptionObject
0x18009b2f1  call    _CxxThrowException_0
0x18009b2f7  lea     rax, aInvalidSignatu_5; "Invalid Signature Xml - the URI attribu"...
0x18009b2fe  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x18009b303  mov     dword ptr [rsp+670h+var_648], 80510043h; unsigned int
0x18009b30b  mov     [rsp+670h+var_650], 25Eh; unsigned int
0x18009b313  lea     r9, word_18013A0B6
0x18009b31a  lea     r8, aNoFilename; "(no filename)"
0x18009b321  lea     rcx, [rbp+570h+pExceptionObject]; this
0x18009b325  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18009b32a  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18009b331  lea     rcx, [rbp+570h+pExceptionObject]; pExceptionObject
0x18009b335  call    _CxxThrowException_0
0x18009b33b  xor     edx, edx; Val
0x18009b33d  mov     r8d, 400h; Size
0x18009b343  lea     rcx, [rbp+570h+var_440]; void *
0x18009b34a  call    memset_0
0x18009b34f  mov     r9d, ebx
0x18009b352  lea     r8, aCallToCryptxml; "Call to CryptXmlGetStatus failed with H"...
0x18009b359  mov     edx, 200h; unsigned __int64
0x18009b35e  lea     rcx, [rbp+570h+var_440]; wchar_t *
0x18009b365  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
  ... truncated ...
```
