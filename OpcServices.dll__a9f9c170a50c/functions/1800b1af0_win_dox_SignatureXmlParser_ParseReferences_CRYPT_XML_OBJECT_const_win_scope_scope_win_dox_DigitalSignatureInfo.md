# win_dox::SignatureXmlParser::ParseReferences(_CRYPT_XML_OBJECT * const,win_scope::scope<win_dox::DigitalSignatureInfo *,win_scope::const_policies<win_scope::shared_policies>>,win_scope::scope<win_dox::OpcEnumerableSetImpl<win_dox::OpcSignaturePartReference,IOpcSignaturePartReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignaturePartReference>> *,win_scope::const_policies<win_scope::shared_policies>>,win_scope::scope<win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureRelationshipReference,IOpcSignatureRelationshipReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>> *,win_scope::const_policies<win_scope::shared_policies>>)

- ea: `0x1800b1af0`
- end: `0x1800b218e`
- name: `?ParseReferences@SignatureXmlParser@win_dox@@CAXQEAU_CRYPT_XML_OBJECT@@V?$scope@PEAVDigitalSignatureInfo@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAV?$OpcEnumerableSetImpl@VOpcSignaturePartReference@win_dox@@UIOpcSignaturePartReferenceEnumerator@@U?$com_wrapper_less@VOpcSignaturePartReference@win_dox@@@2@@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@5@V?$scope@PEAV?$OpcEnumerableSetImpl@VOpcSignatureRelationshipReference@win_dox@@UIOpcSignatureRelationshipReferenceEnumerator@@U?$com_wrapper_less@VOpcSignatureRelationshipReference@win_dox@@@2@@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@5@@Z`
- size: `1694`
- prototype: ``
- caller_count: `1`
- callee_count: `33`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18009f9c4`

## callees

- `0x1800016b0`
- `0x180001abc`
- `0x180008398`
- `0x180015a68`
- `0x180017dd0`
- `0x180018c00`
- `0x18001a810`
- `0x18003fe40`
- `0x1800425d8`
- `0x18004ae68`
- `0x1800517a0`
- `0x18005f2c4`
- `0x180084b24`
- `0x18009b574`
- `0x1800a0e38`
- `0x1800a3f18`
- `0x1800a6204`
- `0x1800a66c0`
- `0x1800a7370`
- `0x1800ab16c`
- `0x1800b1af0`
- `0x1800cd38c`
- `0x1800d5fe4`
- `0x1800ded2c`
- `0x1800ec504`
- `0x1800f8ab0`
- `0x1800f8b48`
- `0x1801025cc`
- `0x1801045a0`
- `0x180104828`
- `0x180104920`
- `0x180117740`
- `0x18012a010`

## import_xrefs

- `CRYPTXML!CryptXmlGetReference` at `0x1800b1ba2`
- `CRYPTXML!CryptXmlGetReference` at `0x1800b1ba2`
- `CRYPTXML!CryptXmlGetStatus` at `0x1800b1bc2`
- `CRYPTXML!CryptXmlGetStatus` at `0x1800b1bc2`

## string_xrefs

- `0x1800b2031`: `Call to CryptXmlGetStatus failed with HResult 0x%X.`
- `0x1800b20a6`: `Call to CryptXmlGetReference failed with HResult 0x%X.`

## pseudocode

```c
// Hidden C++ exception states: #wind=36
void __fastcall win_dox::SignatureXmlParser::ParseReferences(__int64 a1, __int64 a2, _QWORD *a3, _QWORD *a4)
{
  _QWORD *v6; // rsi
  __int64 v7; // r13
  int v8; // edi
  unsigned int i; // eax
  __int64 v10; // r12
  HRESULT Reference; // ebx
  HRESULT Status; // ebx
  const char *v13; // rdx
  unsigned int v14; // r8d
  void *v15; // r12
  int v16; // edi
  enum __MIDL___MIDL_itf_msopc_0001_0076_0001 CombinedCanonicalizationMethod; // ebx
  LPCWSTR v18; // rdx
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rax
  _QWORD *v22; // r13
  CRYPT_XML_REFERENCE *v23; // rbx
  __int64 v24; // rdx
  __int64 v25; // rbx
  unsigned __int64 v26; // rax
  __int64 v27; // r8
  unsigned __int64 v28; // rdx
  const char *v29; // rdx
  unsigned int v30; // r8d
  void *v31; // r12
  int v32; // edi
  enum __MIDL___MIDL_itf_msopc_0001_0076_0001 v33; // ebx
  LPCWSTR wszAlgorithm; // rdx
  int SourceUri; // eax
  __int64 v36; // rax
  __int64 v37; // rdx
  __int64 v38; // rax
  _QWORD *v39; // r13
  CRYPT_XML_REFERENCE *v40; // rbx
  __int64 v41; // rdx
  __int64 v42; // rbx
  unsigned __int64 v43; // rax
  __int64 v44; // r8
  unsigned __int64 v45; // rdx
  win_dox *v46; // [rsp+20h] [rbp-E0h]
  CRYPT_XML_REFERENCE *ppStruct; // [rsp+48h] [rbp-B8h] BYREF
  enum __MIDL___MIDL_itf_msopc_0001_0076_0001 v48; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v49; // [rsp+54h] [rbp-ACh]
  __int64 v50; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v51; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v52; // [rsp+68h] [rbp-98h] BYREF
  __MIDL___MIDL_itf_msopc_0001_0076_0003 v53; // [rsp+70h] [rbp-90h] BYREF
  __int64 v54; // [rsp+78h] [rbp-88h] BYREF
  __int64 v55; // [rsp+80h] [rbp-80h]
  __int64 v56; // [rsp+88h] [rbp-78h] BYREF
  __int64 v57; // [rsp+90h] [rbp-70h]
  __int64 v58; // [rsp+98h] [rbp-68h]
  _BYTE v59[8]; // [rsp+A0h] [rbp-60h] BYREF
  HCRYPTXML v60; // [rsp+A8h] [rbp-58h]
  _BYTE v61[8]; // [rsp+B0h] [rbp-50h] BYREF
  HCRYPTXML hReference; // [rsp+B8h] [rbp-48h]
  __int128 v63; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v64; // [rsp+D0h] [rbp-30h]
  __int64 v65[10]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v66[16]; // [rsp+128h] [rbp+28h] BYREF
  _BYTE v67[16]; // [rsp+138h] [rbp+38h] BYREF
  _BYTE v68[16]; // [rsp+148h] [rbp+48h] BYREF
  CRYPT_XML_STATUS pStatus; // [rsp+158h] [rbp+58h] BYREF
  _BYTE v70[8]; // [rsp+168h] [rbp+68h] BYREF
  __int16 v71; // [rsp+170h] [rbp+70h]
  __int64 v72; // [rsp+180h] [rbp+80h]
  __int64 v73; // [rsp+188h] [rbp+88h]
  int v74[12]; // [rsp+190h] [rbp+90h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+1C0h] [rbp+C0h] BYREF
  wchar_t v76[512]; // [rsp+260h] [rbp+160h] BYREF

  v65[4] = -2;
  v6 = (_QWORD *)a2;
  v7 = a1;
  v58 = a1;
  v65[5] = a2;
  v65[6] = (__int64)a3;
  v65[7] = (__int64)a4;
  v8 = 0;
  ppStruct = 0;
  *(_QWORD *)&pStatus.cbSize = 0;
  pStatus.dwInfoStatus = 0;
  v63 = 0;
  v64 = 0;
  v73 = 7;
  v72 = 0;
  v71 = 0;
  for ( i = 0; ; i = v49 + 1 )
  {
    v49 = i;
    if ( i >= *(_DWORD *)(v7 + 40) )
      break;
    v10 = i;
    Reference = CryptXmlGetReference(
                  *(HCRYPTXML *)(*(_QWORD *)(*(_QWORD *)(v7 + 48) + 8LL * i) + 8LL),
                  (const CRYPT_XML_REFERENCE **)&ppStruct);
    if ( Reference < 0 )
    {
      memset_0(v76, 0, sizeof(v76));
      StringCchPrintfW(v76, 0x200u, L"Call to CryptXmlGetReference failed with HResult 0x%X.", (unsigned int)Reference);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x16Eu,
        Reference,
        (struct win_musl::TStringEllipseBase *)v76);
      throw (SplException::THResultException *)pExceptionObject;
    }
    Status = CryptXmlGetStatus(*(HCRYPTXML *)(*(_QWORD *)(*(_QWORD *)(v7 + 48) + 8 * v10) + 8LL), &pStatus);
    if ( Status < 0 )
    {
      memset_0(v76, 0, sizeof(v76));
      StringCchPrintfW(v76, 0x200u, L"Call to CryptXmlGetStatus failed with HResult 0x%X.", (unsigned int)Status);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x178u,
        Status,
        (struct win_musl::TStringEllipseBase *)v76);
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( (pStatus.dwErrorStatus & 1) != 0 && (pStatus.dwInfoStatus & 1) == 0 )
    {
      win_dox::SignatureXmlParser::ParseReferenceUri(ppStruct->wszUri, &v63, v70);
      if ( win_dox::OpcPartUri::IsRelationshipsPartUri((win_dox::OpcPartUri *)&v63) )
      {
        v53 = OPC_RELATIONSHIP_SIGN_USING_SELECTORS;
        v48 = OPC_CANONICALIZATION_NONE;
        v52 = 0;
        win_dox::SignatureXmlParser::ParseRelationshipReference(
          ppStruct,
          &v53,
          &v48,
          (struct win_dox::OpcRelationshipSelectorSet *)&v52);
        v31 = operator new(0x68u, v29, v30);
        v65[9] = (__int64)v31;
        if ( v31 )
        {
          std::vector<unsigned char>::_Construct<unsigned char *>(
            v65,
            ppStruct->DigestValue.pbData,
            &ppStruct->DigestValue.pbData[ppStruct->DigestValue.cbData]);
          v32 = v8 | 4;
          v33 = v48;
          wszAlgorithm = &psz;
          if ( ppStruct->DigestMethod.wszAlgorithm )
            wszAlgorithm = ppStruct->DigestMethod.wszAlgorithm;
          std::wstring::wstring(v74, wszAlgorithm);
          SourceUri = win_dox::OpcPartUri::GetSourceUri(&v63, v67);
          v8 = v32 | 0x18;
          v36 = win_dox::OpcSignatureRelationshipReferenceImpl::OpcSignatureRelationshipReferenceImpl(
                  (int)v31,
                  SourceUri,
                  (int)v74,
                  v53,
                  (struct win_dox::OpcSignatureRelationshipReference *)&v52,
                  v33,
                  (__int64)v65);
        }
        else
        {
          v36 = 0;
        }
        win_scope::scope<win_dox::OpcSignatureRelationshipReferenceImpl *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::OpcSignatureRelationshipReferenceImpl *,win_scope::const_policies<win_scope::shared_policies>>(
          &v56,
          v36);
        if ( (v8 & 0x10) != 0 )
        {
          v8 &= ~0x10u;
          win_dox::OpcUri::~OpcUri((win_dox::OpcUri *)v67);
        }
        if ( (v8 & 8) != 0 )
        {
          v8 &= ~8u;
          LOBYTE(v37) = 1;
          std::wstring::_Tidy(v74, v37, 0);
        }
        if ( (v8 & 4) != 0 )
        {
          v8 &= ~4u;
          std::vector<unsigned char>::_Tidy(v65);
        }
        v38 = win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(
                v68,
                &v56);
        win_dox::CreateInstanceFromInner<IOpcSignatureRelationshipReference,win_scope::scope<win_dox::OpcSignatureRelationshipReferenceImpl *,win_scope::const_policies<win_scope::shared_policies>>>(
          &v51,
          v38);
        win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureRelationshipReference,IOpcSignatureRelationshipReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>>::Add(
          a4[1],
          &v51);
        v39 = (_QWORD *)v6[1];
        v40 = ppStruct;
        win_dox::OpcSignatureRelationshipReference::OpcSignatureRelationshipReference(
          (win_dox::OpcSignatureRelationshipReference *)v61,
          (const struct win_dox::OpcSignatureRelationshipReference *)&v51);
        hReference = v40->hReference;
        if ( v39[13] )
          v41 = (__int64)(v39[15] - v39[13]) >> 4;
        else
          v41 = 0;
        v42 = v39[14];
        v43 = std::vector<win_scope::scope<win_musl::consumption::XmlParser<win_dox::OpcRelationshipsTransform::DummyMemberSetter> *,win_scope::const_policies<win_scope::shared_policies>>>::size(
                v39 + 12,
                v41);
        if ( v43 >= v45 )
        {
          std::vector<std::pair<win_dox::OpcSignatureRelationshipReference,void *>>::_Insert_n(v39 + 12, v42, v44, v61);
        }
        else
        {
          std::_Uninit_fill_n<std::pair<win_dox::OpcSignaturePartReference,void *> *,unsigned __int64,std::pair<win_dox::OpcSignaturePartReference,void *>,std::allocator<std::pair<win_dox::OpcSignaturePartReference,void *>>>(
            v42,
            1,
            v61);
          v39[14] = v42 + 16;
        }
        win_dox::Uri::~Uri((win_dox::Uri *)v61);
        if ( v51 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
          v51 = 0;
        }
        if ( v56 && v57 )
        {
          win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(&v56);
          v56 = 0;
          v57 = 0;
        }
        if ( v52 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
      }
      else
      {
        v15 = operator new(0x98u, v13, v14);
        v65[8] = (__int64)v15;
        if ( v15 )
        {
          std::vector<unsigned char>::_Construct<unsigned char *>(
            v65,
            ppStruct->DigestValue.pbData,
            &ppStruct->DigestValue.pbData[ppStruct->DigestValue.cbData]);
          v16 = v8 | 1;
          CombinedCanonicalizationMethod = win_dox::SignatureXmlParser::GetCombinedCanonicalizationMethod(ppStruct);
          v18 = &psz;
          if ( ppStruct->DigestMethod.wszAlgorithm )
            v18 = ppStruct->DigestMethod.wszAlgorithm;
          std::wstring::wstring(v74, v18);
          v8 = v16 | 2;
          LODWORD(v46) = CombinedCanonicalizationMethod;
          v19 = win_dox::OpcSignaturePartReferenceImpl::OpcSignaturePartReferenceImpl(
                  (_DWORD)v15,
                  (unsigned int)&v63,
                  (unsigned int)v70,
                  (unsigned int)v74,
                  v46,
                  (__int64)v65);
        }
        else
        {
          v19 = 0;
        }
        win_scope::scope<win_dox::OpcSignaturePartReferenceImpl *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::OpcSignaturePartReferenceImpl *,win_scope::const_policies<win_scope::shared_policies>>(
          &v54,
          v19);
        if ( (v8 & 2) != 0 )
        {
          v8 &= ~2u;
          LOBYTE(v20) = 1;
          std::wstring::_Tidy(v74, v20, 0);
        }
        if ( (v8 & 1) != 0 )
        {
          v8 &= ~1u;
          std::vector<unsigned char>::_Tidy(v65);
        }
        v21 = win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(
                v66,
                &v54);
        win_dox::CreateInstanceFromInner<IOpcSignaturePartReference,win_scope::scope<win_dox::OpcSignaturePartReferenceImpl *,win_scope::const_policies<win_scope::shared_policies>>>(
          &v50,
          v21);
        win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureRelationshipReference,IOpcSignatureRelationshipReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>>::Add(
          a3[1],
          &v50);
        v22 = (_QWORD *)v6[1];
        v23 = ppStruct;
        win_dox::OpcSignatureRelationshipReference::OpcSignatureRelationshipReference(
          (win_dox::OpcSignatureRelationshipReference *)v59,
          (const struct win_dox::OpcSignatureRelationshipReference *)&v50);
        v60 = v23->hReference;
        if ( v22[9] )
          v24 = (__int64)(v22[11] - v22[9]) >> 4;
        else
          v24 = 0;
        v25 = v22[10];
        v26 = std::vector<win_scope::scope<win_musl::consumption::XmlParser<win_dox::OpcRelationshipsTransform::DummyMemberSetter> *,win_scope::const_policies<win_scope::shared_policies>>>::size(
                v22 + 8,
                v24);
        if ( v26 >= v28 )
        {
          std::vector<std::pair<win_dox::OpcSignatureRelationshipReference,void *>>::_Insert_n(v22 + 8, v25, v27, v59);
        }
        else
        {
          std::_Uninit_fill_n<std::pair<win_dox::OpcSignaturePartReference,void *> *,unsigned __int64,std::pair<win_dox::OpcSignaturePartReference,void *>,std::allocator<std::pair<win_dox::OpcSignaturePartReference,void *>>>(
            v25,
            1,
            v59);
          v22[10] = v25 + 16;
        }
        win_dox::Uri::~Uri((win_dox::Uri *)v59);
        if ( v50 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
          v50 = 0;
        }
        if ( v54 )
        {
          if ( v55 )
          {
            win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(&v54);
            v54 = 0;
            v55 = 0;
          }
        }
      }
      v7 = v58;
    }
  }
  LOBYTE(a2) = 1;
  std::wstring::_Tidy(v70, a2, 0);
  win_dox::OpcPartUri::~OpcPartUri((win_dox::OpcPartUri *)&v63);
  if ( *v6 && v6[1] )
  {
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(v6);
    *v6 = 0;
    v6[1] = 0;
  }
  if ( *a3 && a3[1] )
  {
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(a3);
    *a3 = 0;
    a3[1] = 0;
  }
  if ( *a4 && a4[1] )
  {
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(a4);
    *a4 = 0;
    a4[1] = 0;
  }
}

```

## disassembly

```asm
0x1800b1af0  push    rbp
0x1800b1af2  push    rbx
0x1800b1af3  push    rsi
0x1800b1af4  push    rdi
0x1800b1af5  push    r12
0x1800b1af7  push    r13
0x1800b1af9  push    r14
0x1800b1afb  push    r15
0x1800b1afd  lea     rbp, [rsp-578h]
0x1800b1b05  sub     rsp, 678h
0x1800b1b0c  mov     [rbp+5B0h+var_5B8], 0FFFFFFFFFFFFFFFEh
0x1800b1b14  mov     rax, cs:__security_cookie
0x1800b1b1b  xor     rax, rsp
0x1800b1b1e  mov     [rbp+5B0h+var_50], rax
0x1800b1b25  mov     r14, r9
0x1800b1b28  mov     r15, r8
0x1800b1b2b  mov     rsi, rdx
0x1800b1b2e  mov     r13, rcx
0x1800b1b31  mov     [rbp+5B0h+var_618], rcx
0x1800b1b35  mov     [rbp+5B0h+var_5B0], rdx
0x1800b1b39  mov     [rbp+5B0h+var_5A8], r8
0x1800b1b3d  mov     [rbp+5B0h+var_5A0], r9
0x1800b1b41  xor     r12d, r12d
0x1800b1b44  mov     edi, r12d
0x1800b1b47  mov     [rsp+6B0h+var_670], r12d
0x1800b1b4c  mov     [rsp+6B0h+ppStruct], r12
0x1800b1b51  xor     eax, eax
0x1800b1b53  mov     qword ptr [rbp+5B0h+pStatus.cbSize], rax
0x1800b1b57  mov     [rbp+5B0h+pStatus.dwInfoStatus], eax
0x1800b1b5a  xorps   xmm0, xmm0
0x1800b1b5d  movdqu  [rbp+5B0h+var_5F0], xmm0
0x1800b1b62  mov     [rbp+5B0h+var_5E0], r12
0x1800b1b66  mov     [rbp+5B0h+var_528], 7
0x1800b1b71  mov     [rbp+5B0h+var_530], r12
0x1800b1b78  mov     [rbp+5B0h+var_540], r12w
0x1800b1b7d  mov     eax, r12d
0x1800b1b80  mov     [rsp+6B0h+var_65C], eax
0x1800b1b84  cmp     eax, [r13+28h]
0x1800b1b88  jnb     loc_1800B2104
0x1800b1b8e  mov     r12d, eax
0x1800b1b91  mov     rax, [r13+30h]
0x1800b1b95  mov     rcx, [rax+r12*8]
0x1800b1b99  lea     rdx, [rsp+6B0h+ppStruct]; ppStruct
0x1800b1b9e  mov     rcx, [rcx+8]; hCryptXml
0x1800b1ba2  call    cs:__imp_CryptXmlGetReference
0x1800b1ba8  mov     ebx, eax
0x1800b1baa  test    eax, eax
0x1800b1bac  js      loc_1800B208F
0x1800b1bb2  mov     rax, [r13+30h]
0x1800b1bb6  mov     rcx, [rax+r12*8]
0x1800b1bba  lea     rdx, [rbp+5B0h+pStatus]; pStatus
0x1800b1bbe  mov     rcx, [rcx+8]; hCryptXml
0x1800b1bc2  call    cs:__imp_CryptXmlGetStatus
0x1800b1bc8  mov     ebx, eax
0x1800b1bca  xor     r12d, r12d
0x1800b1bcd  test    eax, eax
0x1800b1bcf  js      loc_1800B201A
0x1800b1bd5  mov     eax, [rbp+5B0h+pStatus.dwErrorStatus]
0x1800b1bd8  test    al, 1
0x1800b1bda  jz      loc_1800B200F
0x1800b1be0  mov     eax, [rbp+5B0h+pStatus.dwInfoStatus]
0x1800b1be3  test    al, 1
0x1800b1be5  jnz     loc_1800B200F
0x1800b1beb  lea     r8, [rbp+5B0h+var_548]
0x1800b1bef  lea     rdx, [rbp+5B0h+var_5F0]
0x1800b1bf3  mov     rcx, [rsp+6B0h+ppStruct]
0x1800b1bf8  mov     rcx, [rcx+18h]
0x1800b1bfc  call    ?ParseReferenceUri@SignatureXmlParser@win_dox@@CAXPEB_WAEAVOpcPartUri@2@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_dox::SignatureXmlParser::ParseReferenceUri(wchar_t const *,win_dox::OpcPartUri &,std::wstring &)
0x1800b1c01  lea     rcx, [rbp+5B0h+var_5F0]; this
0x1800b1c05  call    ?IsRelationshipsPartUri@OpcPartUri@win_dox@@QEBA_NXZ; win_dox::OpcPartUri::IsRelationshipsPartUri(void)
0x1800b1c0a  test    al, al
0x1800b1c0c  jnz     loc_1800B1DDD
0x1800b1c12  mov     ecx, 98h; unsigned __int64
0x1800b1c17  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x1800b1c1c  mov     r12, rax
0x1800b1c1f  mov     [rbp+5B0h+var_598], rax
0x1800b1c23  test    rax, rax
0x1800b1c26  jz      loc_1800B1CAC
0x1800b1c2c  mov     rcx, [rsp+6B0h+ppStruct]
0x1800b1c31  mov     rdx, [rcx+50h]
0x1800b1c35  mov     r8d, [rcx+48h]
0x1800b1c39  add     r8, rdx
0x1800b1c3c  lea     rcx, [rbp+5B0h+var_5D8]
0x1800b1c40  call    ??$_Construct@PEAE@?$vector@EV?$allocator@E@std@@@std@@QEAAXPEAE0Uinput_iterator_tag@1@@Z; std::vector<uchar>::_Construct<uchar *>(uchar *,uchar *,std::input_iterator_tag)
0x1800b1c45  nop
0x1800b1c46  or      edi, 1
0x1800b1c49  mov     [rsp+6B0h+var_670], edi
0x1800b1c4d  mov     rcx, [rsp+6B0h+ppStruct]; struct _CRYPT_XML_REFERENCE *
0x1800b1c52  call    ?GetCombinedCanonicalizationMethod@SignatureXmlParser@win_dox@@CA?AW4__MIDL___MIDL_itf_msopc_0001_0076_0001@@PEBU_CRYPT_XML_REFERENCE@@@Z; win_dox::SignatureXmlParser::GetCombinedCanonicalizationMethod(_CRYPT_XML_REFERENCE const *)
0x1800b1c57  mov     ebx, eax
0x1800b1c59  mov     rcx, [rsp+6B0h+ppStruct]
0x1800b1c5e  lea     rdx, psz
0x1800b1c65  cmp     qword ptr [rcx+30h], 0
0x1800b1c6a  cmovnz  rdx, [rcx+30h]
0x1800b1c6f  lea     rcx, [rbp+5B0h+var_520]
0x1800b1c76  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x1800b1c7b  nop
0x1800b1c7c  or      edi, 2
0x1800b1c7f  mov     [rsp+6B0h+var_670], edi
0x1800b1c83  lea     rax, [rbp+5B0h+var_5D8]
0x1800b1c87  mov     qword ptr [rsp+6B0h+var_688], rax
0x1800b1c8c  mov     dword ptr [rsp+6B0h+var_690], ebx
0x1800b1c90  lea     r9, [rbp+5B0h+var_520]
0x1800b1c97  lea     r8, [rbp+5B0h+var_548]
0x1800b1c9b  lea     rdx, [rbp+5B0h+var_5F0]
0x1800b1c9f  mov     rcx, r12
0x1800b1ca2  call    ??0OpcSignaturePartReferenceImpl@win_dox@@QEAA@AEBVOpcPartUri@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@1W4__MIDL___MIDL_itf_msopc_0001_0076_0001@@AEBV?$vector@EV?$allocator@E@std@@@4@@Z; win_dox::OpcSignaturePartReferenceImpl::OpcSignaturePartReferenceImpl(win_dox::OpcPartUri const &,std::wstring const &,std::wstring const &,__MIDL___MIDL_itf_msopc_0001_0076_0001,std::vector<uchar> const &)
0x1800b1ca7  xor     r12d, r12d
0x1800b1caa  jmp     short loc_1800B1CB2
0x1800b1cac  xor     r12d, r12d
0x1800b1caf  mov     eax, r12d
0x1800b1cb2  mov     rdx, rax
0x1800b1cb5  lea     rcx, [rsp+6B0h+var_638]
0x1800b1cba  call    ??0?$scope@PEAVOpcSignaturePartReferenceImpl@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@QEAA@PEAVOpcSignaturePartReferenceImpl@win_dox@@@Z; win_scope::scope<win_dox::OpcSignaturePartReferenceImpl *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::OpcSignaturePartReferenceImpl *,win_scope::const_policies<win_scope::shared_policies>>(win_dox::OpcSignaturePartReferenceImpl *)
0x1800b1cbf  nop
0x1800b1cc0  test    dil, 2
0x1800b1cc4  jz      short loc_1800B1CDF
0x1800b1cc6  and     edi, 0FFFFFFFDh
0x1800b1cc9  mov     [rsp+6B0h+var_670], edi
0x1800b1ccd  xor     r8d, r8d
0x1800b1cd0  mov     dl, 1
0x1800b1cd2  lea     rcx, [rbp+5B0h+var_520]
0x1800b1cd9  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800b1cde  nop
0x1800b1cdf  test    dil, 1
0x1800b1ce3  jz      short loc_1800B1CF5
0x1800b1ce5  and     edi, 0FFFFFFFEh
0x1800b1ce8  mov     [rsp+6B0h+var_670], edi
0x1800b1cec  lea     rcx, [rbp+5B0h+var_5D8]
0x1800b1cf0  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@IEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800b1cf5  lea     rdx, [rsp+6B0h+var_638]
0x1800b1cfa  lea     rcx, [rbp+5B0h+var_588]
0x1800b1cfe  call    ??0?$scope@PEBU_CERT_CONTEXT@@U?$const_policies@U?$shared_close_policies@U?$close_function@P6AHPEBU_CERT_CONTEXT@@@Z$1?CertFreeCertificateContext@@YAH0@Z@win_scope@@@win_scope@@@win_scope@@@win_scope@@QEAA@AEBV01@@Z; win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>> const &)
0x1800b1d03  mov     rdx, rax
0x1800b1d06  lea     rcx, [rsp+6B0h+var_658]
0x1800b1d0b  call    ??$CreateInstanceFromInner@UIOpcSignaturePartReference@@V?$scope@PEAVOpcSignaturePartReferenceImpl@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@win_dox@@YA?AVOpcSignaturePartReference@0@V?$scope@PEAVOpcSignaturePartReferenceImpl@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@Z; win_dox::CreateInstanceFromInner<IOpcSignaturePartReference,win_scope::scope<win_dox::OpcSignaturePartReferenceImpl *,win_scope::const_policies<win_scope::shared_policies>>>(win_scope::scope<win_dox::OpcSignaturePartReferenceImpl *,win_scope::const_policies<win_scope::shared_policies>>)
0x1800b1d10  nop
0x1800b1d11  lea     rdx, [rsp+6B0h+var_658]
0x1800b1d16  mov     rcx, [r15+8]
0x1800b1d1a  call    ?Add@?$OpcEnumerableSetImpl@VOpcSignatureRelationshipReference@win_dox@@UIOpcSignatureRelationshipReferenceEnumerator@@U?$com_wrapper_less@VOpcSignatureRelationshipReference@win_dox@@@2@@win_dox@@QEAAXAEBVOpcSignatureRelationshipReference@2@@Z; win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureRelationshipReference,IOpcSignatureRelationshipReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>>::Add(win_dox::OpcSignatureRelationshipReference const &)
0x1800b1d1f  mov     r13, [rsi+8]
0x1800b1d23  mov     rbx, [rsp+6B0h+ppStruct]
0x1800b1d28  lea     rdx, [rsp+6B0h+var_658]; struct win_dox::OpcSignatureRelationshipReference *
0x1800b1d2d  lea     rcx, [rbp+5B0h+var_610]; this
0x1800b1d31  call    ??0OpcSignatureRelationshipReference@win_dox@@QEAA@AEBV01@@Z; win_dox::OpcSignatureRelationshipReference::OpcSignatureRelationshipReference(win_dox::OpcSignatureRelationshipReference const &)
0x1800b1d36  mov     rax, [rbx+8]
0x1800b1d3a  mov     [rbp+5B0h+var_608], rax
0x1800b1d3e  cmp     [r13+48h], r12
0x1800b1d42  jnz     short loc_1800B1D49
0x1800b1d44  mov     rdx, r12
0x1800b1d47  jmp     short loc_1800B1D55
0x1800b1d49  mov     rdx, [r13+58h]
0x1800b1d4d  sub     rdx, [r13+48h]
0x1800b1d51  sar     rdx, 4
0x1800b1d55  mov     rbx, [r13+50h]
0x1800b1d59  lea     rcx, [r13+40h]
0x1800b1d5d  call    ?size@?$vector@V?$scope@PEAV?$XmlParser@VDummyMemberSetter@OpcRelationshipsTransform@win_dox@@@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$allocator@V?$scope@PEAV?$XmlParser@VDummyMemberSetter@OpcRelationshipsTransform@win_dox@@@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@std@@@std@@QEBA_KXZ; std::vector<win_scope::scope<win_musl::consumption::XmlParser<win_dox::OpcRelationshipsTransform::DummyMemberSetter> *,win_scope::const_policies<win_scope::shared_policies>>>::size(void)
0x1800b1d62  cmp     rax, rdx
0x1800b1d65  jnb     short loc_1800B1D82
0x1800b1d67  lea     r8, [rbp+5B0h+var_610]
0x1800b1d6b  mov     edx, 1
0x1800b1d70  mov     rcx, rbx
0x1800b1d73  call    ??$_Uninit_fill_n@PEAU?$pair@VOpcSignaturePartReference@win_dox@@PEAX@std@@_KU12@V?$allocator@U?$pair@VOpcSignaturePartReference@win_dox@@PEAX@std@@@2@@std@@YAXPEAU?$pair@VOpcSignaturePartReference@win_dox@@PEAX@0@_KAEBU10@AEAV?$allocator@U?$pair@VOpcSignaturePartReference@win_dox@@PEAX@std@@@0@U_Nonscalar_ptr_iterator_tag@0@U_Range_checked_iterator_tag@0@@Z; std::_Uninit_fill_n<std::pair<win_dox::OpcSignaturePartReference,void *> *,unsigned __int64,std::pair<win_dox::OpcSignaturePartReference,void *>,std::allocator<std::pair<win_dox::OpcSignaturePartReference,void *>>>(std::pair<win_dox::OpcSignaturePartReference,void *> *,unsigned __int64,std::pair<win_dox::OpcSignaturePartReference,void *> const &,std::allocator<std::pair<win_dox::OpcSignaturePartReference,void *>> &,std::_Nonscalar_ptr_iterator_tag,std::_Range_checked_iterator_tag)
0x1800b1d78  add     rbx, 10h
0x1800b1d7c  mov     [r13+50h], rbx
0x1800b1d80  jmp     short loc_1800B1D93
0x1800b1d82  lea     r9, [rbp+5B0h+var_610]
0x1800b1d86  mov     rdx, rbx
0x1800b1d89  lea     rcx, [r13+40h]
0x1800b1d8d  call    ?_Insert_n@?$vector@U?$pair@VOpcSignatureRelationshipReference@win_dox@@PEAX@std@@V?$allocator@U?$pair@VOpcSignatureRelationshipReference@win_dox@@PEAX@std@@@2@@std@@IEAAXV?$_Vector_iterator@U?$pair@VOpcSignatureRelationshipReference@win_dox@@PEAX@std@@V?$allocator@U?$pair@VOpcSignatureRelationshipReference@win_dox@@PEAX@std@@@2@@2@_KAEBU?$pair@VOpcSignatureRelationshipReference@win_dox@@PEAX@2@@Z; std::vector<std::pair<win_dox::OpcSignatureRelationshipReference,void *>>::_Insert_n(std::_Vector_iterator<std::pair<win_dox::OpcSignatureRelationshipReference,void *>>,unsigned __int64,std::pair<win_dox::OpcSignatureRelationshipReference,void *> const &)
0x1800b1d92  nop
0x1800b1d93  lea     rcx, [rbp+5B0h+var_610]; this
0x1800b1d97  call    ??1Uri@win_dox@@QEAA@XZ; win_dox::Uri::~Uri(void)
0x1800b1d9c  nop
0x1800b1d9d  mov     rcx, [rsp+6B0h+var_658]
0x1800b1da2  test    rcx, rcx
0x1800b1da5  jz      short loc_1800B1DB8
0x1800b1da7  mov     rax, [rcx]
0x1800b1daa  mov     rax, [rax+10h]
0x1800b1dae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1db3  mov     [rsp+6B0h+var_658], r12
0x1800b1db8  cmp     [rsp+6B0h+var_638], r12
0x1800b1dbd  jz      short loc_1800B1DD8
0x1800b1dbf  cmp     [rbp+5B0h+var_630], r12
0x1800b1dc3  jz      short loc_1800B1DD8
0x1800b1dc5  lea     rcx, [rsp+6B0h+var_638]
0x1800b1dca  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x1800b1dcf  mov     [rsp+6B0h+var_638], r12
0x1800b1dd4  mov     [rbp+5B0h+var_630], r12
0x1800b1dd8  jmp     loc_1800B200B
0x1800b1ddd  mov     [rsp+6B0h+var_640], r12d
0x1800b1de2  mov     [rsp+6B0h+var_660], r12d
0x1800b1de7  mov     [rsp+6B0h+var_648], r12
0x1800b1dec  lea     r9, [rsp+6B0h+var_648]; struct win_dox::OpcRelationshipSelectorSet *
0x1800b1df1  lea     r8, [rsp+6B0h+var_660]; enum __MIDL___MIDL_itf_msopc_0001_0076_0001 *
0x1800b1df6  lea     rdx, [rsp+6B0h+var_640]; enum __MIDL___MIDL_itf_msopc_0001_0076_0003 *
0x1800b1dfb  mov     rcx, [rsp+6B0h+ppStruct]; struct _CRYPT_XML_REFERENCE *
0x1800b1e00  call    ?ParseRelationshipReference@SignatureXmlParser@win_dox@@CAXPEBU_CRYPT_XML_REFERENCE@@PEAW4__MIDL___MIDL_itf_msopc_0001_0076_0003@@PEAW4__MIDL___MIDL_itf_msopc_0001_0076_0001@@PEAVOpcRelationshipSelectorSet@2@@Z; win_dox::SignatureXmlParser::ParseRelationshipReference(_CRYPT_XML_REFERENCE const *,__MIDL___MIDL_itf_msopc_0001_0076_0003 *,__MIDL___MIDL_itf_msopc_0001_0076_0001 *,win_dox::OpcRelationshipSelectorSet *)
0x1800b1e05  mov     ecx, 68h ; 'h'; unsigned __int64
0x1800b1e0a  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x1800b1e0f  mov     r12, rax
0x1800b1e12  mov     [rbp+5B0h+var_590], rax
0x1800b1e16  test    rax, rax
0x1800b1e19  jz      loc_1800B1EB6
0x1800b1e1f  mov     rcx, [rsp+6B0h+ppStruct]
0x1800b1e24  mov     rdx, [rcx+50h]
0x1800b1e28  mov     r8d, [rcx+48h]
0x1800b1e2c  add     r8, rdx
0x1800b1e2f  lea     rcx, [rbp+5B0h+var_5D8]
0x1800b1e33  call    ??$_Construct@PEAE@?$vector@EV?$allocator@E@std@@@std@@QEAAXPEAE0Uinput_iterator_tag@1@@Z; std::vector<uchar>::_Construct<uchar *>(uchar *,uchar *,std::input_iterator_tag)
0x1800b1e38  nop
0x1800b1e39  or      edi, 4
0x1800b1e3c  mov     [rsp+6B0h+var_670], edi
0x1800b1e40  mov     ebx, [rsp+6B0h+var_660]
0x1800b1e44  mov     rax, [rsp+6B0h+ppStruct]
0x1800b1e49  lea     rdx, psz
0x1800b1e50  cmp     qword ptr [rax+30h], 0
0x1800b1e55  cmovnz  rdx, [rax+30h]
0x1800b1e5a  lea     rcx, [rbp+5B0h+var_520]
0x1800b1e61  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x1800b1e66  nop
0x1800b1e67  or      edi, 8
0x1800b1e6a  mov     [rsp+6B0h+var_670], edi
0x1800b1e6e  lea     rdx, [rbp+5B0h+var_578]
0x1800b1e72  lea     rcx, [rbp+5B0h+var_5F0]
0x1800b1e76  call    ?GetSourceUri@OpcPartUri@win_dox@@QEBA?AVOpcUri@2@XZ; win_dox::OpcPartUri::GetSourceUri(void)
0x1800b1e7b  nop
0x1800b1e7c  or      edi, 10h
0x1800b1e7f  mov     [rsp+6B0h+var_670], edi
0x1800b1e83  lea     rcx, [rbp+5B0h+var_5D8]
0x1800b1e87  mov     [rsp+6B0h+var_680], rcx; __int64
0x1800b1e8c  mov     [rsp+6B0h+var_688], ebx; int
0x1800b1e90  lea     rcx, [rsp+6B0h+var_648]
0x1800b1e95  mov     [rsp+6B0h+var_690], rcx; struct win_dox::OpcSignatureRelationshipReference *
0x1800b1e9a  mov     r9d, [rsp+6B0h+var_640]; int
0x1800b1e9f  lea     r8, [rbp+5B0h+var_520]; int
0x1800b1ea6  mov     rdx, rax; int
0x1800b1ea9  mov     rcx, r12; int
0x1800b1eac  call    ??0OpcSignatureRelationshipReferenceImpl@win_dox@@QEAA@AEBVOpcUri@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@W4__MIDL___MIDL_itf_msopc_0001_0076_0003@@AEBVOpcRelationshipSelectorSet@1@W4__MIDL___MIDL_itf_msopc_0001_0076_0001@@AEBV?$vector@EV?$allocator@E@std@@@4@@Z; win_dox::OpcSignatureRelationshipReferenceImpl::OpcSignatureRelationshipReferenceImpl(win_dox::OpcUri const &,std::wstring const &,__MIDL___MIDL_itf_msopc_0001_0076_0003,win_dox::OpcRelationshipSelectorSet const &,__MIDL___MIDL_itf_msopc_0001_0076_0001,std::vector<uchar> const &)
0x1800b1eb1  xor     r12d, r12d
0x1800b1eb4  jmp     short loc_1800B1EBC
0x1800b1eb6  xor     r12d, r12d
0x1800b1eb9  mov     eax, r12d
0x1800b1ebc  mov     rdx, rax
0x1800b1ebf  lea     rcx, [rbp+5B0h+var_628]
0x1800b1ec3  call    ??0?$scope@PEAVOpcSignatureRelationshipReferenceImpl@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@QEAA@PEAVOpcSignatureRelationshipReferenceImpl@win_dox@@@Z; win_scope::scope<win_dox::OpcSignatureRelationshipReferenceImpl *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::OpcSignatureRelationshipReferenceImpl *,win_scope::const_policies<win_scope::shared_policies>>(win_dox::OpcSignatureRelationshipReferenceImpl *)
0x1800b1ec8  nop
0x1800b1ec9  test    dil, 10h
0x1800b1ecd  jz      short loc_1800B1EE0
0x1800b1ecf  and     edi, 0FFFFFFEFh
0x1800b1ed2  mov     [rsp+6B0h+var_670], edi
0x1800b1ed6  lea     rcx, [rbp+5B0h+var_578]; this
0x1800b1eda  call    ??1OpcUri@win_dox@@QEAA@XZ; win_dox::OpcUri::~OpcUri(void)
0x1800b1edf  nop
0x1800b1ee0  test    dil, 8
0x1800b1ee4  jz      short loc_1800B1EFF
0x1800b1ee6  and     edi, 0FFFFFFF7h
0x1800b1ee9  mov     [rsp+6B0h+var_670], edi
0x1800b1eed  xor     r8d, r8d
0x1800b1ef0  mov     dl, 1
0x1800b1ef2  lea     rcx, [rbp+5B0h+var_520]
0x1800b1ef9  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800b1efe  nop
0x1800b1eff  test    dil, 4
0x1800b1f03  jz      short loc_1800B1F15
0x1800b1f05  and     edi, 0FFFFFFFBh
0x1800b1f08  mov     [rsp+6B0h+var_670], edi
0x1800b1f0c  lea     rcx, [rbp+5B0h+var_5D8]
0x1800b1f10  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@IEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800b1f15  lea     rdx, [rbp+5B0h+var_628]
0x1800b1f19  lea     rcx, [rbp+5B0h+var_568]
0x1800b1f1d  call    ??0?$scope@PEBU_CERT_CONTEXT@@U?$const_policies@U?$shared_close_policies@U?$close_function@P6AHPEBU_CERT_CONTEXT@@@Z$1?CertFreeCertificateContext@@YAH0@Z@win_scope@@@win_scope@@@win_scope@@@win_scope@@QEAA@AEBV01@@Z; win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>> const &)
0x1800b1f22  mov     rdx, rax
0x1800b1f25  lea     rcx, [rsp+6B0h+var_650]
0x1800b1f2a  call    ??$CreateInstanceFromInner@UIOpcSignatureRelationshipReference@@V?$scope@PEAVOpcSignatureRelationshipReferenceImpl@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@win_dox@@YA?AVOpcSignatureRelationshipReference@0@V?$scope@PEAVOpcSignatureRelationshipReferenceImpl@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@Z; win_dox::CreateInstanceFromInner<IOpcSignatureRelationshipReference,win_scope::scope<win_dox::OpcSignatureRelationshipReferenceImpl *,win_scope::const_policies<win_scope::shared_policies>>>(win_scope::scope<win_dox::OpcSignatureRelationshipReferenceImpl *,win_scope::const_policies<win_scope::shared_policies>>)
0x1800b1f2f  nop
0x1800b1f30  lea     rdx, [rsp+6B0h+var_650]
0x1800b1f35  mov     rcx, [r14+8]
0x1800b1f39  call    ?Add@?$OpcEnumerableSetImpl@VOpcSignatureRelationshipReference@win_dox@@UIOpcSignatureRelationshipReferenceEnumerator@@U?$com_wrapper_less@VOpcSignatureRelationshipReference@win_dox@@@2@@win_dox@@QEAAXAEBVOpcSignatureRelationshipReference@2@@Z; win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureRelationshipReference,IOpcSignatureRelationshipReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>>::Add(win_dox::OpcSignatureRelationshipReference const &)
0x1800b1f3e  mov     r13, [rsi+8]
0x1800b1f42  mov     rbx, [rsp+6B0h+ppStruct]
0x1800b1f47  lea     rdx, [rsp+6B0h+var_650]; struct win_dox::OpcSignatureRelationshipReference *
0x1800b1f4c  lea     rcx, [rbp+5B0h+var_600]; this
0x1800b1f50  call    ??0OpcSignatureRelationshipReference@win_dox@@QEAA@AEBV01@@Z; win_dox::OpcSignatureRelationshipReference::OpcSignatureRelationshipReference(win_dox::OpcSignatureRelationshipReference const &)
0x1800b1f55  mov     rax, [rbx+8]
0x1800b1f59  mov     [rbp+5B0h+var_5F8], rax
0x1800b1f5d  cmp     [r13+68h], r12
0x1800b1f61  jnz     short loc_1800B1F68
0x1800b1f63  mov     rdx, r12
0x1800b1f66  jmp     short loc_1800B1F74
0x1800b1f68  mov     rdx, [r13+78h]
0x1800b1f6c  sub     rdx, [r13+68h]
0x1800b1f70  sar     rdx, 4
0x1800b1f74  mov     rbx, [r13+70h]
0x1800b1f78  lea     rcx, [r13+60h]
0x1800b1f7c  call    ?size@?$vector@V?$scope@PEAV?$XmlParser@VDummyMemberSetter@OpcRelationshipsTransform@win_dox@@@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$allocator@V?$scope@PEAV?$XmlParser@VDummyMemberSetter@OpcRelationshipsTransform@win_dox@@@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@std@@@std@@QEBA_KXZ; std::vector<win_scope::scope<win_musl::consumption::XmlParser<win_dox::OpcRelationshipsTransform::DummyMemberSetter> *,win_scope::const_policies<win_scope::shared_policies>>>::size(void)
0x1800b1f81  cmp     rax, rdx
0x1800b1f84  jnb     short loc_1800B1FA1
0x1800b1f86  lea     r8, [rbp+5B0h+var_600]
0x1800b1f8a  mov     edx, 1
  ... truncated ...
```
