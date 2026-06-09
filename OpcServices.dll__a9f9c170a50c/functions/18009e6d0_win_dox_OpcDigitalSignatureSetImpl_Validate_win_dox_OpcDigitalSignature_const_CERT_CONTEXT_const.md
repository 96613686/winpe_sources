# win_dox::OpcDigitalSignatureSetImpl::Validate(win_dox::OpcDigitalSignature const &,_CERT_CONTEXT const *)

- ea: `0x18009e6d0`
- end: `0x18009eb03`
- name: `?Validate@OpcDigitalSignatureSetImpl@win_dox@@QEAA?AW4OPC_SIGNATURE_VALIDATION_RESULT@@AEBVOpcDigitalSignature@2@PEBU_CERT_CONTEXT@@@Z`
- size: `1075`
- prototype: `enum OPC_SIGNATURE_VALIDATION_RESULT __fastcall(win_dox::OpcDigitalSignatureSetImpl *__hidden this, const struct win_dox::OpcDigitalSignature *, const struct _CERT_CONTEXT *)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18009e580`

## callees

- `0x1800016b0`
- `0x180001abc`
- `0x180012fa0`
- `0x180015a68`
- `0x180018c00`
- `0x18001cb40`
- `0x18004ae68`
- `0x1800517a0`
- `0x180079ca0`
- `0x18009c21c`
- `0x18009e6d0`
- `0x18009eee4`
- `0x18009f00c`
- `0x18009f9c4`
- `0x1800a3984`
- `0x1800a4724`
- `0x1800cd38c`
- `0x1800d04d8`
- `0x1800d5fe4`
- `0x1800ff8dc`
- `0x180117740`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009e7c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009e7c7`
- `CRYPT32!CryptImportPublicKeyInfoEx2` at `0x18009e880`
- `CRYPT32!CryptImportPublicKeyInfoEx2` at `0x18009e880`
- `CRYPTXML!CryptXmlVerifySignature` at `0x18009e90f`
- `CRYPTXML!CryptXmlVerifySignature` at `0x18009e90f`
- `CRYPTXML!CryptXmlGetStatus` at `0x18009e98e`
- `CRYPTXML!CryptXmlGetStatus` at `0x18009e98e`
- `bcrypt!BCryptDestroyKey` at `0x18009e860`
- `bcrypt!BCryptDestroyKey` at `0x18009e860`

## string_xrefs

- `0x18009e92f`: `Call to CryptXmlVerifySignature failed with HResult 0x%X.`
- `0x18009e9ae`: `Call to CryptXmlGetStatus failed with HResult 0x%X.`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall win_dox::OpcDigitalSignatureSetImpl::Validate(
        win_dox::OpcDigitalSignatureSetImpl *this,
        const struct win_dox::OpcDigitalSignature *a2,
        const struct _CERT_CONTEXT *a3)
{
  const char *v5; // rdx
  unsigned int v6; // r8d
  _QWORD **v7; // rax
  BCRYPT_KEY_HANDLE *v8; // rax
  BCRYPT_KEY_HANDLE *phKey; // rbx
  win_scope::counted_strong_weak_base *v10; // rax
  win_scope::counted_strong_weak_base *v11; // rdi
  win_musl::detail *v12; // rcx
  unsigned int LastErrorAsFailHR; // ebx
  HRESULT v14; // esi
  HRESULT Status; // esi
  bool v16; // zf
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v20; // [rsp+48h] [rbp-C0h] BYREF
  HCRYPTXML *v21; // [rsp+50h] [rbp-B8h]
  BCRYPT_KEY_HANDLE *v22; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v23; // [rsp+60h] [rbp-A8h] BYREF
  LPVOID v24; // [rsp+70h] [rbp-98h] BYREF
  __int64 v25; // [rsp+78h] [rbp-90h]
  LPVOID v26; // [rsp+80h] [rbp-88h] BYREF
  int v27; // [rsp+88h] [rbp-80h]
  __int64 v28; // [rsp+90h] [rbp-78h]
  CRYPT_XML_STATUS pStatus; // [rsp+98h] [rbp-70h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+A8h] [rbp-60h] BYREF
  wchar_t v31[512]; // [rsp+148h] [rbp+40h] BYREF

  v28 = -2;
  win_dox::OpcDigitalSignatureSetImpl::Storage::GetDigitalSignatureInfo(*((_QWORD *)this + 1), &v20, a2);
  if ( !v20 || !v21 )
  {
    if ( v20 )
    {
      v16 = v21 == 0;
LABEL_50:
      if ( !v16 )
        win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(&v20);
    }
    return 0xFFFFFFFFLL;
  }
  if ( *((_BYTE *)v21 + 56) )
  {
    win_dox::OpcDigitalSignature::GetSignatureXml(v21 + 6, &v26);
    v24 = v26;
    LODWORD(v25) = v27;
    v7 = (_QWORD **)win_dox::OpcSignatureRelationshipReference::OpcSignatureRelationshipReference(
                      (win_dox::OpcSignatureRelationshipReference *)&v22,
                      (win_dox::OpcDigitalSignatureSetImpl *)((char *)this + 16));
    win_dox::SignatureXmlParser::ParseSignatureXml(
      (const WCHAR *)&v23,
      (const struct win_dox::OpcPartUri *)v21,
      (__int64)&v24,
      v7,
      1,
      (__int64)&v20);
    if ( (_QWORD)v23 && *((_QWORD *)&v23 + 1) )
      win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(&v23);
    *((_BYTE *)v21 + 56) = 0;
    if ( v26 )
      CoTaskMemFree(v26);
  }
  v8 = (BCRYPT_KEY_HANDLE *)operator new(8u, v5, v6);
  phKey = v8;
  v22 = v8;
  if ( v8 )
    *v8 = 0;
  else
    phKey = 0;
  v23 = 0;
  v22 = phKey;
  if ( phKey )
  {
    v10 = (win_scope::counted_strong_weak_base *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
    v11 = v10;
    if ( !v10 )
    {
      win_scope::close_delete::close<win_dox::BCryptKeyHandleHolder>(&v22);
      win_scope::report_policy_throw::report_init_failure();
    }
    *((_QWORD *)v10 + 1) = 0;
    *(_QWORD *)v10 = &win_scope::counted_strong_weak<win_dox::BCryptKeyHandleHolder *,win_scope::const_policies<win_scope::resource_policies>>::`vftable';
    *((_QWORD *)v10 + 2) = phKey;
    *(_QWORD *)&v23 = v10;
    win_scope::counted_strong_weak_base::AddRef(v10);
    *((_QWORD *)&v23 + 1) = phKey;
  }
  else
  {
    phKey = (BCRYPT_KEY_HANDLE *)*((_QWORD *)&v23 + 1);
    v11 = (win_scope::counted_strong_weak_base *)v23;
  }
  if ( *phKey )
  {
    BCryptDestroyKey(*phKey);
    *phKey = 0;
  }
  if ( !CryptImportPublicKeyInfoEx2(1u, &a3->pCertInfo->SubjectPublicKeyInfo, 0, 0, phKey) )
  {
    LastErrorAsFailHR = win_musl::detail::GetLastErrorAsFailHR(v12);
    memset_0(v31, 0, sizeof(v31));
    StringCchPrintfW(v31, 0x200u, L"Call to CryptImportPublicKeyInfoEx2 failed with HResult 0x%X.", LastErrorAsFailHR);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x7Eu,
      LastErrorAsFailHR,
      (struct win_musl::TStringEllipseBase *)v31);
    throw (SplException::THResultException *)pExceptionObject;
  }
  *(_QWORD *)&pStatus.cbSize = 0;
  pStatus.dwInfoStatus = 0;
  v14 = CryptXmlVerifySignature(v21[5], *phKey, 0);
  if ( v14 < 0 )
  {
    memset_0(v31, 0, sizeof(v31));
    StringCchPrintfW(v31, 0x200u, L"Call to CryptXmlVerifySignature failed with HResult 0x%X.", (unsigned int)v14);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x8Eu,
      v14,
      (struct win_musl::TStringEllipseBase *)v31);
    throw (SplException::THResultException *)pExceptionObject;
  }
  Status = CryptXmlGetStatus(v21[5], &pStatus);
  if ( Status < 0 )
  {
    memset_0(v31, 0, sizeof(v31));
    StringCchPrintfW(v31, 0x200u, L"Call to CryptXmlGetStatus failed with HResult 0x%X.", (unsigned int)Status);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x98u,
      Status,
      (struct win_musl::TStringEllipseBase *)v31);
    throw (SplException::THResultException *)pExceptionObject;
  }
  if ( pStatus.dwErrorStatus )
  {
    if ( v11 && phKey )
      win_scope::counted_strong_weak_base::Release(v11);
    goto LABEL_29;
  }
  v17 = win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(
          &v24,
          &v20);
  if ( !(unsigned __int8)win_dox::OpcDigitalSignatureSetImpl::VerifyPartReferences(this, v17) )
  {
    if ( v11 && phKey )
      win_scope::counted_strong_weak_base::Release(v11);
    goto LABEL_29;
  }
  v18 = win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(
          &v24,
          &v20);
  if ( !(unsigned __int8)win_dox::OpcDigitalSignatureSetImpl::VerifyRelationshipsReferences(this, v18) )
  {
    if ( v11 && phKey )
      win_scope::counted_strong_weak_base::Release(v11);
LABEL_29:
    if ( v20 )
    {
      v16 = v21 == 0;
      goto LABEL_50;
    }
    return 0xFFFFFFFFLL;
  }
  if ( v11 && phKey )
    win_scope::counted_strong_weak_base::Release(v11);
  if ( v20 && v21 )
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(&v20);
  return 0;
}

```

## disassembly

```asm
0x18009e6d0  mov     rax, rsp
0x18009e6d3  push    rbp
0x18009e6d4  push    rsi
0x18009e6d5  push    rdi
0x18009e6d6  push    r14
0x18009e6d8  push    r15
0x18009e6da  lea     rbp, [rax-478h]
0x18009e6e1  sub     rsp, 550h
0x18009e6e8  mov     [rbp+470h+var_4E8], 0FFFFFFFFFFFFFFFEh
0x18009e6f0  mov     [rax+20h], rbx
0x18009e6f4  mov     rax, cs:__security_cookie
0x18009e6fb  xor     rax, rsp
0x18009e6fe  mov     [rbp+470h+var_30], rax
0x18009e705  mov     rsi, r8
0x18009e708  mov     r14, rcx
0x18009e70b  mov     r8, rdx
0x18009e70e  lea     rdx, [rsp+570h+var_530]
0x18009e713  mov     rcx, [rcx+8]
0x18009e717  call    ?GetDigitalSignatureInfo@Storage@OpcDigitalSignatureSetImpl@win_dox@@QEAA?AV?$scope@PEAVDigitalSignatureInfo@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@AEBVOpcDigitalSignature@3@@Z; win_dox::OpcDigitalSignatureSetImpl::Storage::GetDigitalSignatureInfo(win_dox::OpcDigitalSignature const &)
0x18009e71c  nop
0x18009e71d  mov     rax, [rsp+570h+var_528]
0x18009e722  mov     rcx, [rsp+570h+var_530]
0x18009e727  xor     r15d, r15d
0x18009e72a  test    rcx, rcx
0x18009e72d  jz      loc_18009EAC5
0x18009e733  test    rax, rax
0x18009e736  jz      loc_18009EAC5
0x18009e73c  cmp     [rax+38h], r15b
0x18009e740  jz      loc_18009E7CD
0x18009e746  lea     rcx, [rax+30h]
0x18009e74a  lea     rdx, [rsp+570h+var_4F8]
0x18009e74f  call    ?GetSignatureXml@OpcDigitalSignature@win_dox@@QEBA?AU?$SMART_VECTOR@V?$scope@PEAEU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@@2@XZ; win_dox::OpcDigitalSignature::GetSignatureXml(void)
0x18009e754  nop
0x18009e755  mov     rax, [rsp+570h+var_4F8]
0x18009e75a  mov     [rsp+570h+var_508], rax
0x18009e75f  mov     eax, [rbp+470h+var_4F0]
0x18009e762  mov     dword ptr [rsp+570h+var_500], eax
0x18009e766  lea     rdx, [r14+10h]; struct win_dox::OpcSignatureRelationshipReference *
0x18009e76a  lea     rcx, [rsp+570h+var_520]; this
0x18009e76f  call    ??0OpcSignatureRelationshipReference@win_dox@@QEAA@AEBV01@@Z; win_dox::OpcSignatureRelationshipReference::OpcSignatureRelationshipReference(win_dox::OpcSignatureRelationshipReference const &)
0x18009e774  lea     rcx, [rsp+570h+var_530]
0x18009e779  mov     qword ptr [rsp+570h+var_548], rcx
0x18009e77e  mov     byte ptr [rsp+570h+phKey], 1
0x18009e783  mov     r9, rax
0x18009e786  lea     r8, [rsp+570h+var_508]
0x18009e78b  mov     rdx, [rsp+570h+var_528]
0x18009e790  lea     rcx, [rsp+570h+var_520+8]
0x18009e795  call    ?ParseSignatureXml@SignatureXmlParser@win_dox@@SA?AV?$scope@PEAVDigitalSignatureInfo@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@AEBVOpcPartUri@2@PEBU?$SMART_VECTOR@PEBE@2@VOpcPackage@2@_NAEAV34@@Z; win_dox::SignatureXmlParser::ParseSignatureXml(win_dox::OpcPartUri const &,win_dox::SMART_VECTOR<uchar const *> const *,win_dox::OpcPackage,bool,win_scope::scope<win_dox::DigitalSignatureInfo *,win_scope::const_policies<win_scope::shared_policies>> &)
0x18009e79a  nop
0x18009e79b  cmp     qword ptr [rsp+570h+var_520+8], r15
0x18009e7a0  jz      short loc_18009E7B4
0x18009e7a2  cmp     [rsp+570h+var_510], r15
0x18009e7a7  jz      short loc_18009E7B4
0x18009e7a9  lea     rcx, [rsp+570h+var_520+8]
0x18009e7ae  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x18009e7b3  nop
0x18009e7b4  mov     rax, [rsp+570h+var_528]
0x18009e7b9  mov     [rax+38h], r15b
0x18009e7bd  mov     rcx, [rsp+570h+var_4F8]; pv
0x18009e7c2  test    rcx, rcx
0x18009e7c5  jz      short loc_18009E7CD
0x18009e7c7  call    cs:__imp_CoTaskMemFree
0x18009e7cd  mov     ecx, 8; unsigned __int64
0x18009e7d2  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x18009e7d7  mov     rbx, rax
0x18009e7da  mov     qword ptr [rsp+570h+var_520], rax
0x18009e7df  test    rax, rax
0x18009e7e2  jz      short loc_18009E7E9
0x18009e7e4  mov     [rax], r15
0x18009e7e7  jmp     short loc_18009E7EC
0x18009e7e9  mov     rbx, r15
0x18009e7ec  xorps   xmm0, xmm0
0x18009e7ef  movdqu  [rsp+570h+var_520+8], xmm0
0x18009e7f5  mov     qword ptr [rsp+570h+var_520], rbx
0x18009e7fa  test    rbx, rbx
0x18009e7fd  jz      short loc_18009E84E
0x18009e7ff  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18009e806  mov     ecx, 18h; unsigned __int64
0x18009e80b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18009e810  mov     rdi, rax
0x18009e813  test    rax, rax
0x18009e816  jz      short loc_18009E83E
0x18009e818  mov     [rax+8], r15
0x18009e81c  lea     rax, ??_7?$counted_strong_weak@PEAVBCryptKeyHandleHolder@win_dox@@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@6B@; const win_scope::counted_strong_weak<win_dox::BCryptKeyHandleHolder *,win_scope::const_policies<win_scope::resource_policies>>::`vftable'
0x18009e823  mov     [rdi], rax
0x18009e826  mov     [rdi+10h], rbx
0x18009e82a  mov     qword ptr [rsp+570h+var_520+8], rdi
0x18009e82f  mov     rcx, rdi; this
0x18009e832  call    ?AddRef@counted_strong_weak_base@win_scope@@QEAAKXZ; win_scope::counted_strong_weak_base::AddRef(void)
0x18009e837  mov     [rsp+570h+var_510], rbx
0x18009e83c  jmp     short loc_18009E858
0x18009e83e  lea     rcx, [rsp+570h+var_520]
0x18009e843  call    ??$close@VBCryptKeyHandleHolder@win_dox@@@close_delete@win_scope@@SAXPEAPEAVBCryptKeyHandleHolder@win_dox@@@Z; win_scope::close_delete::close<win_dox::BCryptKeyHandleHolder>(win_dox::BCryptKeyHandleHolder * *)
0x18009e848  call    ?report_init_failure@report_policy_throw@win_scope@@SAXXZ; win_scope::report_policy_throw::report_init_failure(void)
0x18009e84e  mov     rbx, [rsp+570h+var_510]
0x18009e853  mov     rdi, qword ptr [rsp+570h+var_520+8]
0x18009e858  mov     rcx, [rbx]; hKey
0x18009e85b  test    rcx, rcx
0x18009e85e  jz      short loc_18009E869
0x18009e860  call    cs:__imp_BCryptDestroyKey
0x18009e866  mov     [rbx], r15
0x18009e869  mov     rdx, [rsi+18h]
0x18009e86d  add     rdx, 60h ; '`'; pInfo
0x18009e871  mov     [rsp+570h+phKey], rbx; phKey
0x18009e876  xor     r9d, r9d; pvAuxInfo
0x18009e879  xor     r8d, r8d; dwFlags
0x18009e87c  lea     ecx, [r9+1]; dwCertEncodingType
0x18009e880  call    cs:__imp_CryptImportPublicKeyInfoEx2
0x18009e886  test    eax, eax
0x18009e888  jnz     short loc_18009E8F7
0x18009e88a  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x18009e88f  mov     ebx, eax
0x18009e891  xor     edx, edx; Val
0x18009e893  mov     r8d, 400h; Size
0x18009e899  lea     rcx, [rbp+470h+var_430]; void *
0x18009e89d  call    memset_0
0x18009e8a2  mov     r9d, ebx
0x18009e8a5  lea     r8, aCallToCryptimp; "Call to CryptImportPublicKeyInfoEx2 fai"...
0x18009e8ac  mov     edx, 200h; unsigned __int64
0x18009e8b1  lea     rcx, [rbp+470h+var_430]; wchar_t *
0x18009e8b5  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18009e8ba  lea     rax, [rbp+470h+var_430]
0x18009e8be  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x18009e8c3  mov     [rsp+570h+var_548], ebx; unsigned int
0x18009e8c7  mov     dword ptr [rsp+570h+phKey], 7Eh ; '~'; unsigned int
0x18009e8cf  lea     r9, word_18013A0B6
0x18009e8d6  lea     r8, aNoFilename; "(no filename)"
0x18009e8dd  lea     rcx, [rbp+470h+pExceptionObject]; this
0x18009e8e1  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18009e8e6  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18009e8ed  lea     rcx, [rbp+470h+pExceptionObject]; pExceptionObject
0x18009e8f1  call    _CxxThrowException_0
0x18009e8f7  xor     eax, eax
0x18009e8f9  mov     qword ptr [rbp+470h+pStatus.cbSize], rax
0x18009e8fd  mov     [rbp+470h+pStatus.dwInfoStatus], eax
0x18009e900  xor     r8d, r8d; dwFlags
0x18009e903  mov     rdx, [rbx]; hKey
0x18009e906  mov     rcx, [rsp+570h+var_528]
0x18009e90b  mov     rcx, [rcx+28h]; hSignature
0x18009e90f  call    cs:__imp_CryptXmlVerifySignature
0x18009e915  mov     esi, eax
0x18009e917  test    eax, eax
0x18009e919  jns     short loc_18009E981
0x18009e91b  xor     edx, edx; Val
0x18009e91d  mov     r8d, 400h; Size
0x18009e923  lea     rcx, [rbp+470h+var_430]; void *
0x18009e927  call    memset_0
0x18009e92c  mov     r9d, esi
0x18009e92f  lea     r8, aCallToCryptxml_2; "Call to CryptXmlVerifySignature failed "...
0x18009e936  mov     edx, 200h; unsigned __int64
0x18009e93b  lea     rcx, [rbp+470h+var_430]; wchar_t *
0x18009e93f  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18009e944  lea     rax, [rbp+470h+var_430]
0x18009e948  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x18009e94d  mov     [rsp+570h+var_548], esi; unsigned int
0x18009e951  mov     dword ptr [rsp+570h+phKey], 8Eh; unsigned int
0x18009e959  lea     r9, word_18013A0B6
0x18009e960  lea     r8, aNoFilename; "(no filename)"
0x18009e967  lea     rcx, [rbp+470h+pExceptionObject]; this
0x18009e96b  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18009e970  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18009e977  lea     rcx, [rbp+470h+pExceptionObject]; pExceptionObject
0x18009e97b  call    _CxxThrowException_0
0x18009e981  lea     rdx, [rbp+470h+pStatus]; pStatus
0x18009e985  mov     rcx, [rsp+570h+var_528]
0x18009e98a  mov     rcx, [rcx+28h]; hCryptXml
0x18009e98e  call    cs:__imp_CryptXmlGetStatus
0x18009e994  mov     esi, eax
0x18009e996  test    eax, eax
0x18009e998  jns     short loc_18009EA00
0x18009e99a  xor     edx, edx; Val
0x18009e99c  mov     r8d, 400h; Size
0x18009e9a2  lea     rcx, [rbp+470h+var_430]; void *
0x18009e9a6  call    memset_0
0x18009e9ab  mov     r9d, esi
0x18009e9ae  lea     r8, aCallToCryptxml; "Call to CryptXmlGetStatus failed with H"...
0x18009e9b5  mov     edx, 200h; unsigned __int64
0x18009e9ba  lea     rcx, [rbp+470h+var_430]; wchar_t *
0x18009e9be  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18009e9c3  lea     rax, [rbp+470h+var_430]
0x18009e9c7  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x18009e9cc  mov     [rsp+570h+var_548], esi; unsigned int
0x18009e9d0  mov     dword ptr [rsp+570h+phKey], 98h; unsigned int
0x18009e9d8  lea     r9, word_18013A0B6
0x18009e9df  lea     r8, aNoFilename; "(no filename)"
0x18009e9e6  lea     rcx, [rbp+470h+pExceptionObject]; this
0x18009e9ea  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18009e9ef  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18009e9f6  lea     rcx, [rbp+470h+pExceptionObject]; pExceptionObject
0x18009e9fa  call    _CxxThrowException_0
0x18009ea00  cmp     [rbp+470h+pStatus.dwErrorStatus], r15d
0x18009ea04  jz      short loc_18009EA2E
0x18009ea06  test    rdi, rdi
0x18009ea09  jz      short loc_18009EA19
0x18009ea0b  test    rbx, rbx
0x18009ea0e  jz      short loc_18009EA19
0x18009ea10  mov     rcx, rdi; this
0x18009ea13  call    ?Release@counted_strong_weak_base@win_scope@@QEAAKXZ; win_scope::counted_strong_weak_base::Release(void)
0x18009ea18  nop
0x18009ea19  cmp     [rsp+570h+var_530], r15
0x18009ea1e  jz      loc_18009EADA
0x18009ea24  cmp     [rsp+570h+var_528], r15
0x18009ea29  jmp     loc_18009EACD
0x18009ea2e  lea     rdx, [rsp+570h+var_530]
0x18009ea33  lea     rcx, [rsp+570h+var_508]
0x18009ea38  call    ??0?$scope@PEBU_CERT_CONTEXT@@U?$const_policies@U?$shared_close_policies@U?$close_function@P6AHPEBU_CERT_CONTEXT@@@Z$1?CertFreeCertificateContext@@YAH0@Z@win_scope@@@win_scope@@@win_scope@@@win_scope@@QEAA@AEBV01@@Z; win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>> const &)
0x18009ea3d  mov     rdx, rax
0x18009ea40  mov     rcx, r14
0x18009ea43  call    ?VerifyPartReferences@OpcDigitalSignatureSetImpl@win_dox@@AEAA_NV?$scope@PEAVDigitalSignatureInfo@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@Z; win_dox::OpcDigitalSignatureSetImpl::VerifyPartReferences(win_scope::scope<win_dox::DigitalSignatureInfo *,win_scope::const_policies<win_scope::shared_policies>>)
0x18009ea48  test    al, al
0x18009ea4a  jnz     short loc_18009EA61
0x18009ea4c  test    rdi, rdi
0x18009ea4f  jz      short loc_18009EA5F
0x18009ea51  test    rbx, rbx
0x18009ea54  jz      short loc_18009EA5F
0x18009ea56  mov     rcx, rdi; this
0x18009ea59  call    ?Release@counted_strong_weak_base@win_scope@@QEAAKXZ; win_scope::counted_strong_weak_base::Release(void)
0x18009ea5e  nop
0x18009ea5f  jmp     short loc_18009EA19
0x18009ea61  lea     rdx, [rsp+570h+var_530]
0x18009ea66  lea     rcx, [rsp+570h+var_508]
0x18009ea6b  call    ??0?$scope@PEBU_CERT_CONTEXT@@U?$const_policies@U?$shared_close_policies@U?$close_function@P6AHPEBU_CERT_CONTEXT@@@Z$1?CertFreeCertificateContext@@YAH0@Z@win_scope@@@win_scope@@@win_scope@@@win_scope@@QEAA@AEBV01@@Z; win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>> const &)
0x18009ea70  mov     rdx, rax
0x18009ea73  mov     rcx, r14
0x18009ea76  call    ?VerifyRelationshipsReferences@OpcDigitalSignatureSetImpl@win_dox@@AEAA_NV?$scope@PEAVDigitalSignatureInfo@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@Z; win_dox::OpcDigitalSignatureSetImpl::VerifyRelationshipsReferences(win_scope::scope<win_dox::DigitalSignatureInfo *,win_scope::const_policies<win_scope::shared_policies>>)
0x18009ea7b  nop
0x18009ea7c  test    al, al
0x18009ea7e  jnz     short loc_18009EA95
0x18009ea80  test    rdi, rdi
0x18009ea83  jz      short loc_18009EA93
0x18009ea85  test    rbx, rbx
0x18009ea88  jz      short loc_18009EA93
0x18009ea8a  mov     rcx, rdi; this
0x18009ea8d  call    ?Release@counted_strong_weak_base@win_scope@@QEAAKXZ; win_scope::counted_strong_weak_base::Release(void)
0x18009ea92  nop
0x18009ea93  jmp     short loc_18009EA19
0x18009ea95  test    rdi, rdi
0x18009ea98  jz      short loc_18009EAA8
0x18009ea9a  test    rbx, rbx
0x18009ea9d  jz      short loc_18009EAA8
0x18009ea9f  mov     rcx, rdi; this
0x18009eaa2  call    ?Release@counted_strong_weak_base@win_scope@@QEAAKXZ; win_scope::counted_strong_weak_base::Release(void)
0x18009eaa7  nop
0x18009eaa8  cmp     [rsp+570h+var_530], r15
0x18009eaad  jz      short loc_18009EAC1
0x18009eaaf  cmp     [rsp+570h+var_528], r15
0x18009eab4  jz      short loc_18009EAC1
0x18009eab6  lea     rcx, [rsp+570h+var_530]
0x18009eabb  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x18009eac0  nop
0x18009eac1  xor     eax, eax
0x18009eac3  jmp     short loc_18009EADD
0x18009eac5  test    rcx, rcx
0x18009eac8  jz      short loc_18009EADA
0x18009eaca  test    rax, rax
0x18009eacd  jz      short loc_18009EADA
0x18009eacf  lea     rcx, [rsp+570h+var_530]
0x18009ead4  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x18009ead9  nop
0x18009eada  or      eax, 0FFFFFFFFh
0x18009eadd  mov     rcx, [rbp+470h+var_30]
0x18009eae4  xor     rcx, rsp; StackCookie
0x18009eae7  call    __security_check_cookie
0x18009eaec  mov     rbx, [rsp+570h+arg_18]
0x18009eaf4  add     rsp, 550h
0x18009eafb  pop     r15
0x18009eafd  pop     r14
0x18009eaff  pop     rdi
0x18009eb00  pop     rsi
0x18009eb01  pop     rbp
0x18009eb02  retn
```
