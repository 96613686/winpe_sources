# win_dox::OpcDigitalSignatureManagerImpl::InternalSignPackage(_CERT_CONTEXT const *,win_dox::OpcSigningOptions const &,win_dox::OpcPart &)

- ea: `0x1800a1ef4`
- end: `0x1800a2937`
- name: `?InternalSignPackage@OpcDigitalSignatureManagerImpl@win_dox@@AEAA?AVOpcDigitalSignature@2@PEBU_CERT_CONTEXT@@AEBVOpcSigningOptions@2@AEAVOpcPart@2@@Z`
- size: `2627`
- prototype: `struct win_dox::OpcDigitalSignature __high(const struct _CERT_CONTEXT *, const struct win_dox::OpcSigningOptions *, struct win_dox::OpcPart *)`
- caller_count: `1`
- callee_count: `64`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800a3270`

## callees

- `0x1800016b0`
- `0x180001abc`
- `0x180002e04`
- `0x180008398`
- `0x180017dd0`
- `0x180018b9c`
- `0x180018c00`
- `0x180018c2c`
- `0x1800425d8`
- `0x180042834`
- `0x1800517a0`
- `0x180054afc`
- `0x18008429c`
- `0x18009ace4`
- `0x18009b7b8`
- `0x18009c1c8`
- `0x18009f310`
- `0x1800a07b0`
- `0x1800a0a48`
- `0x1800a14f8`
- `0x1800a1ef4`
- `0x1800a2940`
- `0x1800a2a80`
- `0x1800a2c84`
- `0x1800a2d4c`
- `0x1800a2e88`
- `0x1800a2fb8`
- `0x1800a3f18`
- `0x1800a4ae0`
- `0x1800a6408`
- `0x1800a9a70`
- `0x1800aa540`
- `0x1800aa8bc`
- `0x1800b8068`
- `0x1800bb128`
- `0x1800be7b4`
- `0x1800bea60`
- `0x1800beea0`
- `0x1800c1898`
- `0x1800c19a4`
- `0x1800c49d8`
- `0x1800cd38c`
- `0x1800dea00`
- `0x1800ebe64`
- `0x1800ebf38`
- `0x1800ec054`
- `0x1800ec3e8`
- `0x1800ecb84`
- `0x1800ed63c`
- `0x1800f8534`

## import_xrefs

- `CRYPTXML!CryptXmlOpenToEncode` at `0x1800a1fc9`
- `CRYPTXML!CryptXmlOpenToEncode` at `0x1800a1fc9`
- `CRYPTXML!CryptXmlEncode` at `0x1800a22cd`
- `CRYPTXML!CryptXmlEncode` at `0x1800a22cd`
- `CRYPTXML!CryptXmlCreateReference` at `0x1800a2070`
- `CRYPTXML!CryptXmlCreateReference` at `0x1800a2070`
- `CRYPTXML!CryptXmlAddObject` at `0x1800a21a1`
- `CRYPTXML!CryptXmlAddObject` at `0x1800a21a1`
- `CRYPTXML!CryptXmlGetStatus` at `0x1800a21e5`
- `CRYPTXML!CryptXmlGetStatus` at `0x1800a21e5`

## string_xrefs

- `0x1800a2055`: `http://www.w3.org/2000/09/xmldsig#Object`

## pseudocode

```c
// Hidden C++ exception states: #wind=64
const char *__fastcall win_dox::OpcDigitalSignatureManagerImpl::InternalSignPackage(
        __int64 a1,
        const char *a2,
        struct _CERT_CONTEXT *a3,
        win_dox::OpcSigningOptions *a4,
        __int64 a5)
{
  char v8; // si
  win_dox::OpcCertificateSetImpl *v9; // rax
  win_dox::HCRYPTXMLHolder *v10; // rbx
  HCRYPTXML *phSignature; // rax
  const WCHAR *v12; // r8
  HRESULT v13; // eax
  int v14; // edx
  const char *v15; // r8
  unsigned int v16; // r9d
  void *v17; // rdi
  const WCHAR *v18; // rbx
  HRESULT v19; // eax
  const char *v20; // rdx
  const char *v21; // r8
  unsigned int v22; // r9d
  win_dox::OpcCertificateSetImpl *v23; // rax
  __int64 v24; // rax
  const char *v25; // rdx
  unsigned int v26; // r8d
  win_dox::OpcCertificateSetImpl *v27; // rax
  __int64 v28; // rax
  enum __MIDL___MIDL_itf_msopc_0001_0076_0005 TimeFormatW; // eax
  HRESULT v30; // eax
  int v31; // edx
  win_dox::OpcDigitalSignatureManagerImpl *v32; // rcx
  const char *v33; // r8
  unsigned int v34; // r9d
  win_dox::OpcDigitalSignatureManagerImpl *v35; // rcx
  HRESULT Status; // eax
  int v37; // edx
  const char *v38; // r8
  unsigned int v39; // r9d
  void *v40; // rbx
  HRESULT v41; // eax
  int v42; // edx
  const char *v43; // r8
  unsigned int v44; // r9d
  const char *v45; // rdx
  unsigned int v46; // r8d
  win_dox::OpcCertificateSetImpl *v47; // rax
  __int64 Name; // rdx
  struct win_dox::OpcPartUri *v49; // r13
  const char *v50; // rdx
  unsigned int v51; // r8d
  int CertificateSet; // eax
  struct _CERT_CONTEXT *v53; // rbx
  __int64 v54; // rax
  __int64 v55; // rax
  win_dox::OpcCertificateSetImpl *v56; // rax
  __int64 v57; // rax
  __int64 v58; // rax
  struct _CERT_CONTEXT *v59; // rbx
  __int64 v60; // rcx
  __int64 v61; // rcx
  __int64 v62; // rdx
  __int64 *v63; // rax
  unsigned int v64; // r8d
  __int64 v65; // rdi
  const char *v66; // rdx
  void *v67; // r12
  __int64 v68; // rax
  __int64 v69; // rbx
  enum __MIDL___MIDL_itf_msopc_0001_0076_0005 v70; // edi
  __int64 SignatureMethod; // rax
  __int64 v72; // rax
  __int64 v73; // rdx
  __int64 v74; // rax
  const char *v75; // rbx
  __int64 v76; // rdx
  __int64 v77; // rdx
  __int64 v78; // rdx
  const struct _CRYPT_XML_ALGORITHM *cProperty; // [rsp+20h] [rbp-E0h]
  __int64 v81; // [rsp+88h] [rbp-78h] BYREF
  win_dox::OpcCertificateSetImpl *v82; // [rsp+90h] [rbp-70h]
  struct _CERT_CONTEXT *v83; // [rsp+98h] [rbp-68h] BYREF
  __int64 v84; // [rsp+A0h] [rbp-60h] BYREF
  struct _CERT_CONTEXT *v85; // [rsp+A8h] [rbp-58h]
  char v86[8]; // [rsp+B0h] [rbp-50h] BYREF
  HCRYPTXML hSignatureOrObject; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v88; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v89; // [rsp+C8h] [rbp-38h] BYREF
  struct win_dox::OpcPartUri *v90; // [rsp+D0h] [rbp-30h]
  int v91; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v92; // [rsp+E0h] [rbp-20h] BYREF
  int v93; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v94; // [rsp+F8h] [rbp-8h] BYREF
  BYTE *v95; // [rsp+100h] [rbp+0h]
  __int64 v96; // [rsp+108h] [rbp+8h] BYREF
  win_dox::OpcCertificateSetImpl *v97; // [rsp+110h] [rbp+10h]
  __int64 v98; // [rsp+118h] [rbp+18h] BYREF
  __int64 v99; // [rsp+120h] [rbp+20h]
  _QWORD v100[2]; // [rsp+128h] [rbp+28h] BYREF
  _QWORD v101[2]; // [rsp+138h] [rbp+38h] BYREF
  _QWORD v102[2]; // [rsp+148h] [rbp+48h] BYREF
  __int128 v103; // [rsp+158h] [rbp+58h] BYREF
  __int128 v104; // [rsp+168h] [rbp+68h] BYREF
  __int64 v105; // [rsp+178h] [rbp+78h] BYREF
  win_dox::HCRYPTXMLHolder *v106; // [rsp+180h] [rbp+80h]
  _BYTE v107[24]; // [rsp+188h] [rbp+88h] BYREF
  const char *v108; // [rsp+1A0h] [rbp+A0h]
  CRYPT_XML_BLOB v109; // [rsp+1A8h] [rbp+A8h] BYREF
  CRYPT_XML_PROPERTY rgProperty; // [rsp+1B8h] [rbp+B8h] BYREF
  CRYPT_XML_ALGORITHM pDigestMethod; // [rsp+1D0h] [rbp+D0h] BYREF
  _BYTE v112[16]; // [rsp+1F0h] [rbp+F0h] BYREF
  _BYTE v113[24]; // [rsp+200h] [rbp+100h] BYREF
  __int64 v114; // [rsp+218h] [rbp+118h]
  const char *v115; // [rsp+220h] [rbp+120h]
  _BYTE v116[48]; // [rsp+228h] [rbp+128h] BYREF
  CRYPT_XML_STATUS pStatus; // [rsp+258h] [rbp+158h] BYREF
  char v118[8]; // [rsp+268h] [rbp+168h] BYREF
  LPCWSTR wszId[4]; // [rsp+270h] [rbp+170h] BYREF
  char v120[8]; // [rsp+290h] [rbp+190h] BYREF
  __int16 v121; // [rsp+298h] [rbp+198h]
  __int64 v122; // [rsp+2A8h] [rbp+1A8h]
  __int64 v123; // [rsp+2B0h] [rbp+1B0h]
  char v124[8]; // [rsp+2B8h] [rbp+1B8h] BYREF
  _QWORD v125[4]; // [rsp+2C0h] [rbp+1C0h] BYREF
  _BYTE v126[48]; // [rsp+2E0h] [rbp+1E0h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+310h] [rbp+210h] BYREF

  v114 = -2;
  v83 = a3;
  v108 = a2;
  v115 = a2;
  v8 = 0;
  v9 = (win_dox::OpcCertificateSetImpl *)operator new(8u, a2, (unsigned int)a3);
  v82 = v9;
  if ( v9 )
    *(_QWORD *)v9 = 0;
  else
    v9 = 0;
  win_scope::scope<win_dox::HCRYPTXMLHolder *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::HCRYPTXMLHolder *,win_scope::const_policies<win_scope::shared_policies>>(
    &v105,
    v9);
  win_dox::OpcSigningOptions::GetSignatureId(a4, v118);
  v10 = v106;
  phSignature = win_dox::HCRYPTXMLHolder::Replace(v106);
  v12 = (const WCHAR *)wszId;
  if ( wszId[3] >= (LPCWSTR)8 )
    v12 = wszId[0];
  v13 = CryptXmlOpenToEncode(0, 0xE0000000, v12, 0, 0, 0, phSignature);
  if ( v13 < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)v13, v14, v15, v16);
  v17 = *(void **)v10;
  win_dox::OpcSigningOptions::GetDefaultDigestMethod(a4, v124);
  v18 = (const WCHAR *)v125;
  if ( v125[3] >= 8u )
    v18 = (const WCHAR *)v125[0];
  *(_QWORD *)&pDigestMethod.cbSize = 32;
  pDigestMethod.wszAlgorithm = v18;
  *(_QWORD *)&pDigestMethod.Encoded.dwCharset = 0;
  pDigestMethod.Encoded.pbData = 0;
  hSignatureOrObject = 0;
  v19 = CryptXmlCreateReference(
          v17,
          1u,
          0,
          L"#idPackageObject",
          L"http://www.w3.org/2000/09/xmldsig#Object",
          &pDigestMethod,
          1u,
          &win_dox::gc_canonicalizationC14NTransform,
          &hSignatureOrObject);
  if ( v19 < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)v19, (int)v20, v21, v22);
  v23 = (win_dox::OpcCertificateSetImpl *)operator new(0x10u, v20, (unsigned int)v21);
  v82 = v23;
  if ( v23 )
    v23 = (win_dox::OpcCertificateSetImpl *)win_dox::OpcEnumerableSetImpl<win_dox::OpcRelationshipSelector,IOpcRelationshipSelectorEnumerator,win_dox::com_wrapper_less<win_dox::OpcRelationshipSelector>>::OpcEnumerableSetImpl<win_dox::OpcRelationshipSelector,IOpcRelationshipSelectorEnumerator,win_dox::com_wrapper_less<win_dox::OpcRelationshipSelector>>(v23);
  win_scope::scope<win_dox::SimpleEnumerator<win_scope::scope<win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureRelationshipReference,IOpcSignatureRelationshipReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>>::Storage *,win_scope::const_policies<win_scope::shared_policies>>,win_dox::OpcSignatureRelationshipReference,std::_Tree<std::_Tset_traits<win_dox::OpcSignatureRelationshipReference,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>,std::allocator<win_dox::OpcSignatureRelationshipReference>,0>>::const_iterator> *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::SimpleEnumerator<win_scope::scope<win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureRelationshipReference,IOpcSignatureRelationshipReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>>::Storage *,win_scope::const_policies<win_scope::shared_policies>>,win_dox::OpcSignatureRelationshipReference,std::_Tree<std::_Tset_traits<win_dox::OpcSignatureRelationshipReference,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>,std::allocator<win_dox::OpcSignatureRelationshipReference>,0>>::const_iterator> *,win_scope::const_policies<win_scope::shared_policies>>(
    v101,
    v23);
  v24 = win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(
          &v89,
          v101);
  win_dox::OpcDigitalSignatureManagerImpl::CreateAndDigestPartReferences(
    a1,
    (_DWORD)hSignatureOrObject,
    (_DWORD)a4,
    (_DWORD)v18,
    v24);
  v27 = (win_dox::OpcCertificateSetImpl *)operator new(0x10u, v25, v26);
  v82 = v27;
  if ( v27 )
    v27 = (win_dox::OpcCertificateSetImpl *)win_dox::OpcEnumerableSetImpl<win_dox::OpcRelationshipSelector,IOpcRelationshipSelectorEnumerator,win_dox::com_wrapper_less<win_dox::OpcRelationshipSelector>>::OpcEnumerableSetImpl<win_dox::OpcRelationshipSelector,IOpcRelationshipSelectorEnumerator,win_dox::com_wrapper_less<win_dox::OpcRelationshipSelector>>(v27);
  win_scope::scope<win_dox::SimpleEnumerator<win_scope::scope<win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureRelationshipReference,IOpcSignatureRelationshipReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>>::Storage *,win_scope::const_policies<win_scope::shared_policies>>,win_dox::OpcSignatureRelationshipReference,std::_Tree<std::_Tset_traits<win_dox::OpcSignatureRelationshipReference,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>,std::allocator<win_dox::OpcSignatureRelationshipReference>,0>>::const_iterator> *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::SimpleEnumerator<win_scope::scope<win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureRelationshipReference,IOpcSignatureRelationshipReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>>::Storage *,win_scope::const_policies<win_scope::shared_policies>>,win_dox::OpcSignatureRelationshipReference,std::_Tree<std::_Tset_traits<win_dox::OpcSignatureRelationshipReference,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>,std::allocator<win_dox::OpcSignatureRelationshipReference>,0>>::const_iterator> *,win_scope::const_policies<win_scope::shared_policies>>(
    v100,
    v27);
  v28 = win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(
          &v89,
          v100);
  win_dox::OpcDigitalSignatureManagerImpl::CreateAndDigestRelationshipReferences(
    a1,
    (_DWORD)hSignatureOrObject,
    (_DWORD)a4,
    (_DWORD)v18,
    v28);
  v81 = 0;
  v123 = 7;
  v122 = 0;
  v121 = 0;
  TimeFormatW = win_dox::OpcSigningOptions::GetTimeFormatW(a4);
  win_dox::OpcSignaturePropertiesWriter::Write(&v94, (unsigned int)TimeFormatW, v118, &v81, v120);
  v109.dwCharset = CRYPT_XML_CHARSET_UTF8;
  v109.cbData = v81;
  v109.pbData = v95;
  v30 = CryptXmlAddObject(hSignatureOrObject, 0, 0, 0, &v109, 0);
  if ( v30 < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)v30, v31, v33, v34);
  win_dox::OpcDigitalSignatureManagerImpl::CreateCustomObjectsAndReferences(v32, v17, a4);
  win_dox::OpcDigitalSignatureManagerImpl::CreateSignedSignatureXml(v35, v17, a3, a4, cProperty);
  *(_QWORD *)&pStatus.cbSize = 0;
  pStatus.dwInfoStatus = 0;
  Status = CryptXmlGetStatus(v17, &pStatus);
  if ( Status < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)Status, v37, v38, v39);
  if ( (pStatus.dwErrorStatus & 1) != 0 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x340u,
      0x80092108,
      (struct win_musl::TStringEllipseBase *)L"Sign failed");
    throw (SplException::THResultException *)pExceptionObject;
  }
  win_dox::OpcPart::GetContentStream(a5, v86);
  v40 = *(void **)win_dox::Stream::GetInterface(v86, &v81);
  if ( v81 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
    v81 = 0;
  }
  v91 = 1;
  *(_QWORD *)&rgProperty.dwPropId = 4;
  rgProperty.pvValue = &v91;
  *(_QWORD *)&rgProperty.cbValue = 4;
  v41 = CryptXmlEncode(v17, CRYPT_XML_CHARSET_UTF8, &rgProperty, 1u, v40, win_dox::CryptXmlWrite);
  if ( v41 < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)v41, v42, v43, v44);
  win_dox::Stream::Commit((win_dox::Stream *)v86, 0);
  v47 = (win_dox::OpcCertificateSetImpl *)operator new(0x80u, v45, v46);
  v82 = v47;
  if ( v47 )
  {
    *(_QWORD *)v47 = 0;
    *((_QWORD *)v47 + 1) = 0;
    *((_QWORD *)v47 + 2) = 0;
    *((_QWORD *)v47 + 3) = 0;
    *((_QWORD *)v47 + 4) = 0;
    *((_QWORD *)v47 + 6) = 0;
    *((_BYTE *)v47 + 56) = 0;
    *((_QWORD *)v47 + 9) = 0;
    *((_QWORD *)v47 + 10) = 0;
    *((_QWORD *)v47 + 11) = 0;
    *((_QWORD *)v47 + 13) = 0;
    *((_QWORD *)v47 + 14) = 0;
    *((_QWORD *)v47 + 15) = 0;
  }
  else
  {
    v47 = 0;
  }
  win_scope::scope<win_dox::DigitalSignatureInfo *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::DigitalSignatureInfo *,win_scope::const_policies<win_scope::shared_policies>>(
    &v89,
    v47);
  Name = win_dox::OpcPart::GetName(a5, v107);
  v49 = v90;
  win_dox::OpcPartUri::operator=(v90, Name);
  win_dox::OpcPartUri::~OpcPartUri((win_dox::OpcPartUri *)v107);
  std::_Tree<std::_Tset_traits<win_dox::OpcPartUri,std::less<win_dox::OpcPartUri>,std::allocator<win_dox::OpcPartUri>,0>>::_Init(v113);
  if ( win_dox::OpcSigningOptions::GetCertificateEmbeddingOption(a4) )
  {
    v53 = v83;
  }
  else
  {
    if ( !*(_BYTE *)(a1 + 33) )
      win_dox::OpcDigitalSignatureManagerImpl::LoadCertificatesFromPackage((win_dox::OpcDigitalSignatureManagerImpl *)a1);
    CertificateSet = win_dox::OpcSigningOptions::GetCertificateSet(a4, &v88);
    v53 = v83;
    win_dox::OpcDigitalSignatureManagerImpl::SaveCertificatesToParts(a1, a5, (_DWORD)v83, CertificateSet, (__int64)v113);
    if ( v88 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
  }
  if ( *(_BYTE *)(a1 + 33) )
  {
    v82 = (win_dox::OpcCertificateSetImpl *)&v92;
    std::_Tree<std::_Tset_traits<win_dox::OpcPartUri,std::less<win_dox::OpcPartUri>,std::allocator<win_dox::OpcPartUri>,0>>::_Tree<std::_Tset_traits<win_dox::OpcPartUri,std::less<win_dox::OpcPartUri>,std::allocator<win_dox::OpcPartUri>,0>>(
      &v92,
      v113);
    v54 = win_dox::OpcPartUri::OpcPartUri((win_dox::OpcPartUri *)v107, v49);
    v55 = std::make_pair<win_dox::OpcPartUri,std::set<win_dox::OpcPartUri>>(v116, v54, &v92);
    std::pair<win_dox::OpcPartUri const,std::set<win_dox::OpcPartUri>>::pair<win_dox::OpcPartUri const,std::set<win_dox::OpcPartUri>>(
      v126,
      v55);
    std::_Tree<std::_Tmap_traits<win_dox::OpcPartUri,std::set<win_dox::OpcPartUri>,std::less<win_dox::OpcPartUri>,std::allocator<std::pair<win_dox::OpcPartUri const,std::set<win_dox::OpcPartUri>>>,0>>::insert(
      a1 + 80,
      v112,
      v126);
    std::pair<win_dox::OpcPartUri const,std::set<win_dox::OpcPartUri>>::~pair<win_dox::OpcPartUri const,std::set<win_dox::OpcPartUri>>((win_dox::OpcPartUri *)v126);
    std::pair<win_dox::OpcPartUri const,std::set<win_dox::OpcPartUri>>::~pair<win_dox::OpcPartUri const,std::set<win_dox::OpcPartUri>>((win_dox::OpcPartUri *)v116);
  }
  v56 = (win_dox::OpcCertificateSetImpl *)operator new(0x38u, v50, v51);
  v82 = v56;
  if ( v56 )
    v57 = win_dox::OpcCertificateSetImpl::OpcCertificateSetImpl(v56);
  else
    v57 = 0;
  win_scope::scope<win_dox::OpcRelationshipSenderImpl *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>>::scope<win_dox::OpcRelationshipSenderImpl *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>>(
    &v96,
    v57);
  win_dox::OpcCertificateSetImpl::Add(v97, v53, 0);
  v58 = win_dox::OpcSigningOptions::GetCertificateSet(a4, &v81);
  win_dox::OpcCertificateSet::GetEnumerator(v58, &v83);
  if ( v81 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
    v81 = 0;
  }
  while ( win_dox::OpcCertificateEnumerator::MoveNext((win_dox::OpcCertificateEnumerator *)&v83) )
  {
    win_dox::OpcCertificateEnumerator::GetCurrent(&v83, &v84);
    v59 = v85;
    win_dox::OpcCertificateSetImpl::Add(v97, v85, 0);
    if ( v84 && v59 )
    {
      win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(&v84);
      v84 = 0;
      v85 = 0;
    }
  }
  std::vector<unsigned char>::_Buy(v116, 0);
  win_dox::OpcDigitalSignatureManagerImpl::GetSignatureValue(v60, v17, v116);
  v104 = 0;
  v81 = 0;
  v103 = 0;
  win_dox::OpcDigitalSignatureManagerImpl::GetCustomObjectsAndReferences(v61, v17, &v104, &v81, &v103);
  win_dox::Stream::Seek(v86, 0, 0);
  v92 = 0;
  v93 = 0;
  win_dox::CopyStreamToBuffer(&v98, v86, &v93);
  v62 = v98;
  v98 = 0;
  v63 = (__int64 *)win_scope::scope<unsigned char *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_delete_array>>>::scope<unsigned char *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_delete_array>>>(
                     &v84,
                     v62);
  v99 = *v63;
  v65 = v99;
  v82 = (win_dox::OpcCertificateSetImpl *)v63[1];
  v66 = (const char *)v82;
  *(_OWORD *)v63 = v92;
  *(_QWORD *)&v92 = v65;
  *((_QWORD *)&v92 + 1) = v66;
  if ( v84 && v85 )
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(&v84);
  v67 = operator new(0x138u, v66, v64);
  v102[0] = v67;
  if ( v67 )
  {
    v68 = win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(
            v112,
            &v96);
    v69 = win_dox::CreateInstanceFromInner<IOpcCertificateSet,win_scope::scope<win_dox::OpcCertificateSetImpl *,win_scope::const_policies<win_scope::shared_policies>>>(
            &v88,
            v68);
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Init(v107);
    v70 = win_dox::OpcSigningOptions::GetTimeFormatW(a4);
    SignatureMethod = win_dox::OpcSigningOptions::GetSignatureMethod(a4, v126);
    v8 = 7;
    v72 = win_dox::OpcDigitalSignatureImpl::OpcDigitalSignatureImpl(
            v67,
            v49,
            v118,
            SignatureMethod,
            1,
            v70,
            v120,
            v116,
            v107,
            &v104,
            v101,
            v100,
            &v103,
            &v81,
            v69,
            &v92,
            7);
    v65 = v99;
  }
  else
  {
    v72 = 0;
  }
  win_scope::scope<win_dox::OpcDigitalSignatureImpl *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::OpcDigitalSignatureImpl *,win_scope::const_policies<win_scope::shared_policies>>(
    v102,
    v72);
  if ( (v8 & 4) != 0 )
  {
    v8 &= ~4u;
    LOBYTE(v73) = 1;
    std::wstring::_Tidy(v126, v73, 0);
  }
  if ( (v8 & 2) != 0 )
  {
    v8 &= ~2u;
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Tidy(v107);
  }
  if ( (v8 & 1) != 0 && v88 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
    v88 = 0;
  }
  v74 = win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(
          &v84,
          v102);
  v75 = v108;
  win_dox::CreateInstanceFromInner<IOpcDigitalSignature,win_scope::scope<win_dox::OpcDigitalSignatureImpl *,win_scope::const_policies<win_scope::shared_policies>>>(
    v108,
    v74);
  win_musl::production::MXContentHandler::operator=((char *)v49 + 48, v75);
  *((_BYTE *)v49 + 56) = 1;
  win_dox::OpcDigitalSignatureSetImpl::Storage::AddSignatureInfo(*(_QWORD *)(*(_QWORD *)(a1 + 48) + 8LL), v49, &v89, 0);
  if ( v102[0] && v102[1] )
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(v102);
  if ( v65 && v82 )
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(&v92);
  if ( (_QWORD)v103 && *((_QWORD *)&v103 + 1) )
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(&v103);
  if ( v81 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
  if ( (_QWORD)v104 && *((_QWORD *)&v104 + 1) )
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(&v104);
  std::vector<unsigned char>::_Tidy(v116);
  if ( v83 )
    (*(void (__fastcall **)(struct _CERT_CONTEXT *))(*(_QWORD *)&v83->dwCertEncodingType + 16LL))(v83);
  if ( v96 && v97 )
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(&v96);
  std::_Tree<std::_Tset_traits<win_dox::OpcPartUri,std::less<win_dox::OpcPartUri>,std::allocator<win_dox::OpcPartUri>,0>>::_Tidy(v113);
  if ( v89 && v49 )
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(&v89);
  win_dox::Uri::~Uri((win_dox::Uri *)v86);
  if ( v94 && v95 )
  {
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(&v94);
    v94 = 0;
    v95 = 0;
  }
  LOBYTE(v76) = 1;
  std::wstring::_Tidy(v120, v76, 0);
  if ( v100[0] && v100[1] )
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(v100);
  if ( v101[0] && v101[1] )
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(v101);
  LOBYTE(v77) = 1;
  std::wstring::_Tidy(v124, v77, 0);
  LOBYTE(v78) = 1;
  std::wstring::_Tidy(v118, v78, 0);
  if ( v105 && v106 )
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(&v105);
  return v75;
}

```

## disassembly

```asm
0x1800a1ef4  push    rbp
0x1800a1ef6  push    rbx
0x1800a1ef7  push    rsi
0x1800a1ef8  push    rdi
0x1800a1ef9  push    r12
0x1800a1efb  push    r13
0x1800a1efd  push    r14
0x1800a1eff  push    r15
0x1800a1f01  lea     rbp, [rsp-2C8h]
0x1800a1f09  sub     rsp, 3C8h
0x1800a1f10  mov     [rbp+300h+var_1E8], 0FFFFFFFFFFFFFFFEh
0x1800a1f1b  mov     rax, cs:__security_cookie
0x1800a1f22  xor     rax, rsp
0x1800a1f25  mov     [rbp+300h+var_50], rax
0x1800a1f2c  mov     r14, r9
0x1800a1f2f  mov     r13, r8
0x1800a1f32  mov     [rbp+300h+var_368], r8
0x1800a1f36  mov     [rbp+300h+var_260], rdx
0x1800a1f3d  mov     r15, rcx
0x1800a1f40  mov     [rbp+300h+var_1E0], rdx
0x1800a1f47  mov     r12, [rbp+300h+arg_20]
0x1800a1f4e  xor     edi, edi
0x1800a1f50  mov     esi, edi
0x1800a1f52  mov     [rbp+300h+var_380], edi
0x1800a1f55  lea     ecx, [rdi+8]; unsigned __int64
0x1800a1f58  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x1800a1f5d  mov     [rbp+300h+var_370], rax
0x1800a1f61  test    rax, rax
0x1800a1f64  jz      short loc_1800A1F6B
0x1800a1f66  mov     [rax], rdi
0x1800a1f69  jmp     short loc_1800A1F6E
0x1800a1f6b  mov     rax, rdi
0x1800a1f6e  mov     rdx, rax
0x1800a1f71  lea     rcx, [rbp+300h+var_288]
0x1800a1f75  call    ??0?$scope@PEAVHCRYPTXMLHolder@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@QEAA@PEAVHCRYPTXMLHolder@win_dox@@@Z; win_scope::scope<win_dox::HCRYPTXMLHolder *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::HCRYPTXMLHolder *,win_scope::const_policies<win_scope::shared_policies>>(win_dox::HCRYPTXMLHolder *)
0x1800a1f7a  nop
0x1800a1f7b  lea     rdx, [rbp+300h+var_198]
0x1800a1f82  mov     rcx, r14
0x1800a1f85  call    ?GetSignatureId@OpcSigningOptions@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ; win_dox::OpcSigningOptions::GetSignatureId(void)
0x1800a1f8a  nop
0x1800a1f8b  mov     rbx, [rbp+300h+var_280]
0x1800a1f92  mov     rcx, rbx; this
0x1800a1f95  call    ?Replace@HCRYPTXMLHolder@win_dox@@QEAAPEAPEAXXZ; win_dox::HCRYPTXMLHolder::Replace(void)
0x1800a1f9a  lea     r8, [rbp+300h+wszId]
0x1800a1fa1  cmp     [rbp+300h+var_178], 8
0x1800a1fa9  cmovnb  r8, [rbp+300h+wszId]; wszId
0x1800a1fb1  mov     [rsp+400h+phSignature], rax; phSignature
0x1800a1fb6  mov     [rsp+400h+pEncoded], rdi; pEncoded
0x1800a1fbb  mov     [rsp+400h+cProperty], edi; cProperty
0x1800a1fbf  xor     r9d, r9d; rgProperty
0x1800a1fc2  mov     edx, 0E0000000h; dwFlags
0x1800a1fc7  xor     ecx, ecx; pConfig
0x1800a1fc9  call    cs:__imp_CryptXmlOpenToEncode
0x1800a1fcf  test    eax, eax
0x1800a1fd1  jns     short loc_1800A1FDB
0x1800a1fd3  mov     ecx, eax; this
0x1800a1fd5  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x1800a1fdb  mov     rdi, [rbx]
0x1800a1fde  lea     rdx, [rbp+300h+var_148]
0x1800a1fe5  mov     rcx, r14
0x1800a1fe8  call    ?GetDefaultDigestMethod@OpcSigningOptions@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ; win_dox::OpcSigningOptions::GetDefaultDigestMethod(void)
0x1800a1fed  nop
0x1800a1fee  lea     rbx, [rbp+300h+var_140]
0x1800a1ff5  cmp     [rbp+300h+var_128], 8
0x1800a1ffd  cmovnb  rbx, [rbp+300h+var_140]
0x1800a2005  mov     qword ptr [rbp+300h+pDigestMethod.cbSize], 20h ; ' '
0x1800a2010  mov     [rbp+300h+pDigestMethod.wszAlgorithm], rbx
0x1800a2017  xor     eax, eax
0x1800a2019  mov     qword ptr [rbp+300h+pDigestMethod.Encoded.dwCharset], rax
0x1800a2020  mov     [rbp+300h+pDigestMethod.Encoded.pbData], rax
0x1800a2027  mov     [rbp+300h+hSignatureOrObject], rax
0x1800a202b  lea     rax, [rbp+300h+hSignatureOrObject]
0x1800a202f  mov     [rsp+400h+phReference], rax; phReference
0x1800a2034  lea     rax, ?gc_canonicalizationC14NTransform@win_dox@@3U_CRYPT_XML_ALGORITHM@@B; _CRYPT_XML_ALGORITHM const win_dox::gc_canonicalizationC14NTransform
0x1800a203b  mov     [rsp+400h+rgTransform], rax; rgTransform
0x1800a2040  mov     ecx, 1
0x1800a2045  mov     dword ptr [rsp+400h+phSignature], ecx; cTransform
0x1800a2049  lea     rax, [rbp+300h+pDigestMethod]
0x1800a2050  mov     [rsp+400h+pEncoded], rax; pDigestMethod
0x1800a2055  lea     rax, ?gc_objectReferenceType@Value@DigitalSignatures@win_musl@@3QB_WB; "http://www.w3.org/2000/09/xmldsig#Objec"...
0x1800a205c  mov     qword ptr [rsp+400h+cProperty], rax; wszType
0x1800a2061  lea     r9, ?gc_packageReferenceUri@Value@DigitalSignatures@win_musl@@3QB_WB; "#idPackageObject"
0x1800a2068  xor     r8d, r8d; wszId
0x1800a206b  mov     edx, ecx; dwFlags
0x1800a206d  mov     rcx, rdi; hCryptXml
0x1800a2070  call    cs:__imp_CryptXmlCreateReference
0x1800a2076  test    eax, eax
0x1800a2078  jns     short loc_1800A2082
0x1800a207a  mov     ecx, eax; this
0x1800a207c  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x1800a2082  mov     ecx, 10h; unsigned __int64
0x1800a2087  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x1800a208c  mov     [rbp+300h+var_370], rax
0x1800a2090  test    rax, rax
0x1800a2093  jz      short loc_1800A209E
0x1800a2095  mov     rcx, rax
0x1800a2098  call    ??0?$OpcEnumerableSetImpl@VOpcRelationshipSelector@win_dox@@UIOpcRelationshipSelectorEnumerator@@U?$com_wrapper_less@VOpcRelationshipSelector@win_dox@@@2@@win_dox@@QEAA@XZ; win_dox::OpcEnumerableSetImpl<win_dox::OpcRelationshipSelector,IOpcRelationshipSelectorEnumerator,win_dox::com_wrapper_less<win_dox::OpcRelationshipSelector>>::OpcEnumerableSetImpl<win_dox::OpcRelationshipSelector,IOpcRelationshipSelectorEnumerator,win_dox::com_wrapper_less<win_dox::OpcRelationshipSelector>>(void)
0x1800a209d  nop
0x1800a209e  mov     rdx, rax
0x1800a20a1  lea     rcx, [rbp+300h+var_2C8]
0x1800a20a5  call    ??0?$scope@PEAV?$SimpleEnumerator@V?$scope@PEAVStorage@?$OpcEnumerableSetImpl@VOpcSignatureRelationshipReference@win_dox@@UIOpcSignatureRelationshipReferenceEnumerator@@U?$com_wrapper_less@VOpcSignatureRelationshipReference@win_dox@@@2@@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@VOpcSignatureRelationshipReference@win_dox@@Vconst_iterator@?$_Tree@V?$_Tset_traits@VOpcSignatureRelationshipReference@win_dox@@U?$com_wrapper_less@VOpcSignatureRelationshipReference@win_dox@@@2@V?$allocator@VOpcSignatureRelationshipReference@win_dox@@@std@@$0A@@std@@@std@@@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@QEAA@PEAV?$SimpleEnumerator@V?$scope@PEAVStorage@?$OpcEnumerableSetImpl@VOpcSignatureRelationshipReference@win_dox@@UIOpcSignatureRelationshipReferenceEnumerator@@U?$com_wrapper_less@VOpcSignatureRelationshipReference@win_dox@@@2@@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@VOpcSignatureRelationshipReference@win_dox@@Vconst_iterator@?$_Tree@V?$_Tset_traits@VOpcSignatureRelationshipReference@win_dox@@U?$com_wrapper_less@VOpcSignatureRelationshipReference@win_dox@@@2@V?$allocator@VOpcSignatureRelationshipReference@win_dox@@@std@@$0A@@std@@@std@@@win_dox@@@Z; win_scope::scope<win_dox::SimpleEnumerator<win_scope::scope<win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureRelationshipReference,IOpcSignatureRelationshipReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>>::Storage *,win_scope::const_policies<win_scope::shared_policies>>,win_dox::OpcSignatureRelationshipReference,std::_Tree<std::_Tset_traits<win_dox::OpcSignatureRelationshipReference,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>,std::allocator<win_dox::OpcSignatureRelationshipReference>,0>>::const_iterator> *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::SimpleEnumerator<win_scope::scope<win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureRelationshipReference,IOpcSignatureRelationshipReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>>::Storage *,win_scope::const_policies<win_scope::shared_policies>>,win_dox::OpcSignatureRelationshipReference,std::_Tree<std::_Tset_traits<win_dox::OpcSignatureRelationshipReference,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>,std::allocator<win_dox::OpcSignatureRelationshipReference>,0>>::const_iterator> *,win_scope::const_policies<win_scope::shared_policies>>(win_dox::SimpleEnumerator<win_scope::scope<win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureRelationshipReference,IOpcSignatureRelationshipReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>>::Storage *,win_scope::const_policies<win_scope::shared_policies>>,win_dox::OpcSignatureRelationshipReference,std::_Tree<std::_Tset_traits<win_dox::OpcSignatureRelationshipReference,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>,std::allocator<win_dox::OpcSignatureRelationshipReference>,0>>::const_iterator> *)
0x1800a20aa  nop
0x1800a20ab  lea     rdx, [rbp+300h+var_2C8]
0x1800a20af  lea     rcx, [rbp+300h+var_338]
0x1800a20b3  call    ??0?$scope@PEBU_CERT_CONTEXT@@U?$const_policies@U?$shared_close_policies@U?$close_function@P6AHPEBU_CERT_CONTEXT@@@Z$1?CertFreeCertificateContext@@YAH0@Z@win_scope@@@win_scope@@@win_scope@@@win_scope@@QEAA@AEBV01@@Z; win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>> const &)
0x1800a20b8  mov     qword ptr [rsp+400h+cProperty], rax
0x1800a20bd  mov     r9, rbx
0x1800a20c0  mov     r8, r14
0x1800a20c3  mov     rdx, [rbp+300h+hSignatureOrObject]
0x1800a20c7  mov     rcx, r15
0x1800a20ca  call    ?CreateAndDigestPartReferences@OpcDigitalSignatureManagerImpl@win_dox@@AEAAXPEAXAEBVOpcSigningOptions@2@PEB_WV?$scope@PEAV?$OpcEnumerableSetImpl@VOpcSignaturePartReference@win_dox@@UIOpcSignaturePartReferenceEnumerator@@U?$com_wrapper_less@VOpcSignaturePartReference@win_dox@@@2@@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@Z; win_dox::OpcDigitalSignatureManagerImpl::CreateAndDigestPartReferences(void *,win_dox::OpcSigningOptions const &,wchar_t const *,win_scope::scope<win_dox::OpcEnumerableSetImpl<win_dox::OpcSignaturePartReference,IOpcSignaturePartReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignaturePartReference>> *,win_scope::const_policies<win_scope::shared_policies>>)
0x1800a20cf  mov     ecx, 10h; unsigned __int64
0x1800a20d4  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x1800a20d9  mov     [rbp+300h+var_370], rax
0x1800a20dd  test    rax, rax
0x1800a20e0  jz      short loc_1800A20EB
0x1800a20e2  mov     rcx, rax
0x1800a20e5  call    ??0?$OpcEnumerableSetImpl@VOpcRelationshipSelector@win_dox@@UIOpcRelationshipSelectorEnumerator@@U?$com_wrapper_less@VOpcRelationshipSelector@win_dox@@@2@@win_dox@@QEAA@XZ; win_dox::OpcEnumerableSetImpl<win_dox::OpcRelationshipSelector,IOpcRelationshipSelectorEnumerator,win_dox::com_wrapper_less<win_dox::OpcRelationshipSelector>>::OpcEnumerableSetImpl<win_dox::OpcRelationshipSelector,IOpcRelationshipSelectorEnumerator,win_dox::com_wrapper_less<win_dox::OpcRelationshipSelector>>(void)
0x1800a20ea  nop
0x1800a20eb  mov     rdx, rax
0x1800a20ee  lea     rcx, [rbp+300h+var_2D8]
0x1800a20f2  call    ??0?$scope@PEAV?$SimpleEnumerator@V?$scope@PEAVStorage@?$OpcEnumerableSetImpl@VOpcSignatureRelationshipReference@win_dox@@UIOpcSignatureRelationshipReferenceEnumerator@@U?$com_wrapper_less@VOpcSignatureRelationshipReference@win_dox@@@2@@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@VOpcSignatureRelationshipReference@win_dox@@Vconst_iterator@?$_Tree@V?$_Tset_traits@VOpcSignatureRelationshipReference@win_dox@@U?$com_wrapper_less@VOpcSignatureRelationshipReference@win_dox@@@2@V?$allocator@VOpcSignatureRelationshipReference@win_dox@@@std@@$0A@@std@@@std@@@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@QEAA@PEAV?$SimpleEnumerator@V?$scope@PEAVStorage@?$OpcEnumerableSetImpl@VOpcSignatureRelationshipReference@win_dox@@UIOpcSignatureRelationshipReferenceEnumerator@@U?$com_wrapper_less@VOpcSignatureRelationshipReference@win_dox@@@2@@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@VOpcSignatureRelationshipReference@win_dox@@Vconst_iterator@?$_Tree@V?$_Tset_traits@VOpcSignatureRelationshipReference@win_dox@@U?$com_wrapper_less@VOpcSignatureRelationshipReference@win_dox@@@2@V?$allocator@VOpcSignatureRelationshipReference@win_dox@@@std@@$0A@@std@@@std@@@win_dox@@@Z; win_scope::scope<win_dox::SimpleEnumerator<win_scope::scope<win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureRelationshipReference,IOpcSignatureRelationshipReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>>::Storage *,win_scope::const_policies<win_scope::shared_policies>>,win_dox::OpcSignatureRelationshipReference,std::_Tree<std::_Tset_traits<win_dox::OpcSignatureRelationshipReference,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>,std::allocator<win_dox::OpcSignatureRelationshipReference>,0>>::const_iterator> *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::SimpleEnumerator<win_scope::scope<win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureRelationshipReference,IOpcSignatureRelationshipReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>>::Storage *,win_scope::const_policies<win_scope::shared_policies>>,win_dox::OpcSignatureRelationshipReference,std::_Tree<std::_Tset_traits<win_dox::OpcSignatureRelationshipReference,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>,std::allocator<win_dox::OpcSignatureRelationshipReference>,0>>::const_iterator> *,win_scope::const_policies<win_scope::shared_policies>>(win_dox::SimpleEnumerator<win_scope::scope<win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureRelationshipReference,IOpcSignatureRelationshipReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>>::Storage *,win_scope::const_policies<win_scope::shared_policies>>,win_dox::OpcSignatureRelationshipReference,std::_Tree<std::_Tset_traits<win_dox::OpcSignatureRelationshipReference,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>,std::allocator<win_dox::OpcSignatureRelationshipReference>,0>>::const_iterator> *)
0x1800a20f7  nop
0x1800a20f8  lea     rdx, [rbp+300h+var_2D8]
0x1800a20fc  lea     rcx, [rbp+300h+var_338]
0x1800a2100  call    ??0?$scope@PEBU_CERT_CONTEXT@@U?$const_policies@U?$shared_close_policies@U?$close_function@P6AHPEBU_CERT_CONTEXT@@@Z$1?CertFreeCertificateContext@@YAH0@Z@win_scope@@@win_scope@@@win_scope@@@win_scope@@QEAA@AEBV01@@Z; win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>> const &)
0x1800a2105  mov     qword ptr [rsp+400h+cProperty], rax
0x1800a210a  mov     r9, rbx
0x1800a210d  mov     r8, r14
0x1800a2110  mov     rdx, [rbp+300h+hSignatureOrObject]
0x1800a2114  mov     rcx, r15
0x1800a2117  call    ?CreateAndDigestRelationshipReferences@OpcDigitalSignatureManagerImpl@win_dox@@AEAAXPEAXAEBVOpcSigningOptions@2@PEB_WV?$scope@PEAV?$OpcEnumerableSetImpl@VOpcSignatureRelationshipReference@win_dox@@UIOpcSignatureRelationshipReferenceEnumerator@@U?$com_wrapper_less@VOpcSignatureRelationshipReference@win_dox@@@2@@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@Z; win_dox::OpcDigitalSignatureManagerImpl::CreateAndDigestRelationshipReferences(void *,win_dox::OpcSigningOptions const &,wchar_t const *,win_scope::scope<win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureRelationshipReference,IOpcSignatureRelationshipReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>> *,win_scope::const_policies<win_scope::shared_policies>>)
0x1800a211c  xor     ebx, ebx
0x1800a211e  mov     [rbp+300h+var_378], rbx
0x1800a2122  mov     [rbp+300h+var_150], 7
0x1800a212d  mov     [rbp+300h+var_158], rbx
0x1800a2134  mov     [rbp+300h+var_168], bx
0x1800a213b  mov     rcx, r14; this
0x1800a213e  call    ?GetTimeFormatW@OpcSigningOptions@win_dox@@QEBA?AW4__MIDL___MIDL_itf_msopc_0001_0076_0005@@XZ; win_dox::OpcSigningOptions::GetTimeFormatW(void)
0x1800a2143  mov     edx, eax
0x1800a2145  lea     rax, [rbp+300h+var_170]
0x1800a214c  mov     qword ptr [rsp+400h+cProperty], rax
0x1800a2151  lea     r9, [rbp+300h+var_378]
0x1800a2155  lea     r8, [rbp+300h+var_198]
0x1800a215c  lea     rcx, [rbp+300h+var_308]
0x1800a2160  call    ?Write@OpcSignaturePropertiesWriter@win_dox@@SA?AV?$scope@PEAEU?$const_policies@U?$shared_close_policies@Uclose_delete_array@win_scope@@@win_scope@@@win_scope@@@win_scope@@W4__MIDL___MIDL_itf_msopc_0001_0076_0005@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@AEA_KAEAV67@@Z; win_dox::OpcSignaturePropertiesWriter::Write(__MIDL___MIDL_itf_msopc_0001_0076_0005,std::wstring const &,unsigned __int64 &,std::wstring &)
0x1800a2165  nop
0x1800a2166  mov     [rbp+300h+var_258.dwCharset], 1
0x1800a2170  mov     eax, dword ptr [rbp+300h+var_378]
0x1800a2173  mov     [rbp+300h+var_258.cbData], eax
0x1800a2179  mov     rax, [rbp+300h+var_300]
0x1800a217d  mov     [rbp+300h+var_258.pbData], rax
0x1800a2184  mov     [rsp+400h+pEncoded], rbx; ppObject
0x1800a2189  lea     rax, [rbp+300h+var_258]
0x1800a2190  mov     qword ptr [rsp+400h+cProperty], rax; struct _CRYPT_XML_ALGORITHM *
0x1800a2195  xor     r9d, r9d; cProperty
0x1800a2198  xor     r8d, r8d; rgProperty
0x1800a219b  xor     edx, edx; dwFlags
0x1800a219d  mov     rcx, [rbp+300h+hSignatureOrObject]; hSignatureOrObject
0x1800a21a1  call    cs:__imp_CryptXmlAddObject
0x1800a21a7  test    eax, eax
0x1800a21a9  jns     short loc_1800A21B3
0x1800a21ab  mov     ecx, eax; this
0x1800a21ad  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x1800a21b3  mov     r8, r14; struct win_dox::OpcSigningOptions *
0x1800a21b6  mov     rdx, rdi; void *
0x1800a21b9  call    ?CreateCustomObjectsAndReferences@OpcDigitalSignatureManagerImpl@win_dox@@AEAAXPEAXAEBVOpcSigningOptions@2@@Z; win_dox::OpcDigitalSignatureManagerImpl::CreateCustomObjectsAndReferences(void *,win_dox::OpcSigningOptions const &)
0x1800a21be  mov     r9, r14; struct win_dox::OpcSigningOptions *
0x1800a21c1  mov     r8, r13; struct _CERT_CONTEXT *
0x1800a21c4  mov     rdx, rdi; void *
0x1800a21c7  call    ?CreateSignedSignatureXml@OpcDigitalSignatureManagerImpl@win_dox@@AEAAXPEAXPEBU_CERT_CONTEXT@@AEBVOpcSigningOptions@2@AEBU_CRYPT_XML_ALGORITHM@@@Z; win_dox::OpcDigitalSignatureManagerImpl::CreateSignedSignatureXml(void *,_CERT_CONTEXT const *,win_dox::OpcSigningOptions const &,_CRYPT_XML_ALGORITHM const &)
0x1800a21cc  xor     eax, eax
0x1800a21ce  mov     qword ptr [rbp+300h+pStatus.cbSize], rax
0x1800a21d5  mov     [rbp+300h+pStatus.dwInfoStatus], eax
0x1800a21db  lea     rdx, [rbp+300h+pStatus]; pStatus
0x1800a21e2  mov     rcx, rdi; hCryptXml
0x1800a21e5  call    cs:__imp_CryptXmlGetStatus
0x1800a21eb  xor     r13d, r13d
0x1800a21ee  test    eax, eax
0x1800a21f0  jns     short loc_1800A21FA
0x1800a21f2  mov     ecx, eax; this
0x1800a21f4  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x1800a21fa  mov     eax, [rbp+300h+pStatus.dwErrorStatus]
0x1800a2200  test    al, 1
0x1800a2202  jz      short loc_1800A224E
0x1800a2204  lea     rax, aSignFailed; "Sign failed"
0x1800a220b  mov     [rsp+400h+phSignature], rax; struct win_musl::TStringEllipseBase *
0x1800a2210  mov     dword ptr [rsp+400h+pEncoded], 80092108h; unsigned int
0x1800a2218  mov     [rsp+400h+cProperty], 340h; unsigned int
0x1800a2220  lea     r9, word_18013A0B6
0x1800a2227  lea     r8, aNoFilename; "(no filename)"
0x1800a222e  lea     rcx, [rbp+300h+pExceptionObject]; this
0x1800a2235  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800a223a  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800a2241  lea     rcx, [rbp+300h+pExceptionObject]; pExceptionObject
0x1800a2248  call    _CxxThrowException_0
0x1800a224e  lea     rdx, [rbp+300h+var_350]
0x1800a2252  mov     rcx, r12
0x1800a2255  call    ?GetContentStream@OpcPart@win_dox@@QEBA?AVStream@2@XZ; win_dox::OpcPart::GetContentStream(void)
0x1800a225a  nop
0x1800a225b  lea     rdx, [rbp+300h+var_378]
0x1800a225f  lea     rcx, [rbp+300h+var_350]
0x1800a2263  call    ?GetInterface@Stream@win_dox@@QEAA?AV?$scope@PEAUIStream@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@XZ; win_dox::Stream::GetInterface(void)
0x1800a2268  mov     rbx, [rax]
0x1800a226b  mov     rcx, [rbp+300h+var_378]
0x1800a226f  test    rcx, rcx
0x1800a2272  jz      short loc_1800A2284
0x1800a2274  mov     rax, [rcx]
0x1800a2277  mov     rax, [rax+10h]
0x1800a227b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2280  mov     [rbp+300h+var_378], r13
0x1800a2284  mov     ecx, 1
0x1800a2289  mov     [rbp+300h+var_328], ecx
0x1800a228c  mov     qword ptr [rbp+300h+rgProperty.dwPropId], 4
0x1800a2297  lea     rax, [rbp+300h+var_328]
0x1800a229b  mov     [rbp+300h+rgProperty.pvValue], rax
0x1800a22a2  mov     qword ptr [rbp+300h+rgProperty.cbValue], 4
0x1800a22ad  lea     rax, ?CryptXmlWrite@win_dox@@YAJPEAXPEBEK@Z; win_dox::CryptXmlWrite(void *,uchar const *,ulong)
0x1800a22b4  mov     [rsp+400h+pEncoded], rax; pfnWrite
0x1800a22b9  mov     qword ptr [rsp+400h+cProperty], rbx; pvCallbackState
0x1800a22be  mov     r9d, ecx; cProperty
0x1800a22c1  lea     r8, [rbp+300h+rgProperty]; rgProperty
0x1800a22c8  mov     edx, ecx; dwCharset
0x1800a22ca  mov     rcx, rdi; hCryptXml
0x1800a22cd  call    cs:__imp_CryptXmlEncode
0x1800a22d3  test    eax, eax
0x1800a22d5  jns     short loc_1800A22DF
0x1800a22d7  mov     ecx, eax; this
0x1800a22d9  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x1800a22df  xor     edx, edx; unsigned int
0x1800a22e1  lea     rcx, [rbp+300h+var_350]; this
0x1800a22e5  call    ?Commit@Stream@win_dox@@QEAAXI@Z; win_dox::Stream::Commit(uint)
0x1800a22ea  mov     ecx, 80h; unsigned __int64
0x1800a22ef  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x1800a22f4  mov     [rbp+300h+var_370], rax
0x1800a22f8  test    rax, rax
0x1800a22fb  jz      short loc_1800A2332
0x1800a22fd  mov     [rax], r13
0x1800a2300  mov     [rax+8], r13
0x1800a2304  mov     [rax+10h], r13
0x1800a2308  mov     [rax+18h], r13
0x1800a230c  mov     [rax+20h], r13
0x1800a2310  mov     [rax+30h], r13
0x1800a2314  mov     [rax+38h], r13b
0x1800a2318  mov     [rax+48h], r13
0x1800a231c  mov     [rax+50h], r13
0x1800a2320  mov     [rax+58h], r13
0x1800a2324  mov     [rax+68h], r13
0x1800a2328  mov     [rax+70h], r13
0x1800a232c  mov     [rax+78h], r13
0x1800a2330  jmp     short loc_1800A2335
0x1800a2332  mov     rax, r13
0x1800a2335  mov     rdx, rax
0x1800a2338  lea     rcx, [rbp+300h+var_338]
0x1800a233c  call    ??0?$scope@PEAVDigitalSignatureInfo@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@QEAA@PEAVDigitalSignatureInfo@win_dox@@@Z; win_scope::scope<win_dox::DigitalSignatureInfo *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::DigitalSignatureInfo *,win_scope::const_policies<win_scope::shared_policies>>(win_dox::DigitalSignatureInfo *)
0x1800a2341  nop
0x1800a2342  lea     rdx, [rbp+300h+var_278]
0x1800a2349  mov     rcx, r12
0x1800a234c  call    ?GetName@OpcPart@win_dox@@QEBA?AVOpcPartUri@2@XZ; win_dox::OpcPart::GetName(void)
0x1800a2351  nop
0x1800a2352  mov     rdx, rax
0x1800a2355  mov     r13, [rbp+300h+var_330]
0x1800a2359  mov     rcx, r13
0x1800a235c  call    ??4OpcPartUri@win_dox@@QEAAAEAV01@AEBV01@@Z; win_dox::OpcPartUri::operator=(win_dox::OpcPartUri const &)
0x1800a2361  nop
0x1800a2362  lea     rcx, [rbp+300h+var_278]; this
0x1800a2369  call    ??1OpcPartUri@win_dox@@QEAA@XZ; win_dox::OpcPartUri::~OpcPartUri(void)
0x1800a236e  lea     rcx, [rbp+300h+var_200]
0x1800a2375  call    ?_Init@?$_Tree@V?$_Tset_traits@VOpcPartUri@win_dox@@U?$less@VOpcPartUri@win_dox@@@std@@V?$allocator@VOpcPartUri@win_dox@@@4@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tset_traits<win_dox::OpcPartUri,std::less<win_dox::OpcPartUri>,std::allocator<win_dox::OpcPartUri>,0>>::_Init(void)
0x1800a237a  nop
0x1800a237b  mov     rcx, r14; this
0x1800a237e  call    ?GetCertificateEmbeddingOption@OpcSigningOptions@win_dox@@QEBA?AW4__MIDL___MIDL_itf_msopc_0001_0076_0004@@XZ; win_dox::OpcSigningOptions::GetCertificateEmbeddingOption(void)
0x1800a2383  test    eax, eax
0x1800a2385  jnz     short loc_1800A23DF
0x1800a2387  cmp     [r15+21h], al
0x1800a238b  jnz     short loc_1800A2395
0x1800a238d  mov     rcx, r15; this
0x1800a2390  call    ?LoadCertificatesFromPackage@OpcDigitalSignatureManagerImpl@win_dox@@AEAAXXZ; win_dox::OpcDigitalSignatureManagerImpl::LoadCertificatesFromPackage(void)
0x1800a2395  lea     rdx, [rbp+300h+var_340]
0x1800a2399  mov     rcx, r14
0x1800a239c  call    ?GetCertificateSet@OpcSigningOptions@win_dox@@QEBA?AVOpcCertificateSet@2@XZ; win_dox::OpcSigningOptions::GetCertificateSet(void)
0x1800a23a1  nop
0x1800a23a2  lea     rcx, [rbp+300h+var_200]
0x1800a23a9  mov     qword ptr [rsp+400h+cProperty], rcx
0x1800a23ae  mov     r9, rax
0x1800a23b1  mov     rbx, [rbp+300h+var_368]
0x1800a23b5  mov     r8, rbx
0x1800a23b8  mov     rdx, r12
0x1800a23bb  mov     rcx, r15
0x1800a23be  call    ?SaveCertificatesToParts@OpcDigitalSignatureManagerImpl@win_dox@@AEAAXAEBVOpcPart@2@PEBU_CERT_CONTEXT@@AEBVOpcCertificateSet@2@AEAV?$set@VOpcPartUri@win_dox@@U?$less@VOpcPartUri@win_dox@@@std@@V?$allocator@VOpcPartUri@win_dox@@@4@@std@@@Z; win_dox::OpcDigitalSignatureManagerImpl::SaveCertificatesToParts(win_dox::OpcPart const &,_CERT_CONTEXT const *,win_dox::OpcCertificateSet const &,std::set<win_dox::OpcPartUri> &)
0x1800a23c3  nop
0x1800a23c4  mov     rcx, [rbp+300h+var_340]
0x1800a23c8  xor     r12d, r12d
0x1800a23cb  test    rcx, rcx
0x1800a23ce  jz      short loc_1800A23DD
0x1800a23d0  mov     rax, [rcx]
0x1800a23d3  mov     rax, [rax+10h]
0x1800a23d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a23dc  nop
0x1800a23dd  jmp     short loc_1800A23E6
  ... truncated ...
```
