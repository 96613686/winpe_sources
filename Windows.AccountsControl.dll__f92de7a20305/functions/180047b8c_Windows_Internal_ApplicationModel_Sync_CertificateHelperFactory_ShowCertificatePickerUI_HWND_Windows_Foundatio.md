# Windows::Internal::ApplicationModel::Sync::CertificateHelperFactory::ShowCertificatePickerUI(HWND__ *,Windows::Foundation::Collections::IIterable<Windows::Security::Cryptography::Certificates::Certificate *> *,Windows::Security::Cryptography::Certificates::ICertificate * *)

- ea: `0x180047b8c`
- end: `0x180047fd3`
- name: `?ShowCertificatePickerUI@CertificateHelperFactory@Sync@ApplicationModel@Internal@Windows@@CAJPEAUHWND__@@PEAU?$IIterable@PEAVCertificate@Certificates@Cryptography@Security@Windows@@@Collections@Foundation@5@PEAPEAUICertificate@Certificates@Cryptography@Security@5@@Z`
- size: `1095`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800460cc`

## callees

- `0x180006e8c`
- `0x180006eac`
- `0x180008d78`
- `0x18000e87c`
- `0x180011ffc`
- `0x180045fbc`
- `0x180045fec`
- `0x180046060`
- `0x180046080`
- `0x180046768`
- `0x180047230`
- `0x180047b8c`
- `0x18004878c`
- `0x180048810`
- `0x180069730`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047cc2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047ce9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047eb9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047f15`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047f82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047cc2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047ce9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047eb9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047f15`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047f82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180047d53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180047d53`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047c5f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047eda`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047f36`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047fa3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047c5f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047eda`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047f36`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047fa3`
- `CRYPT32!CertFindCertificateInStore` at `0x180047e43`
- `CRYPT32!CertFindCertificateInStore` at `0x180047e43`
- `CRYPT32!CertOpenStore` at `0x180047bd3`
- `CRYPT32!CertOpenStore` at `0x180047bd3`
- `CRYPT32!CertAddSerializedElementToStore` at `0x180047e01`
- `CRYPT32!CertAddSerializedElementToStore` at `0x180047e01`
- `ext-ms-win-security-credui-l1-1-0!CredUIPromptForWindowsCredentialsW` at `0x180047db0`
- `ext-ms-win-security-credui-l1-1-0!CredUIPromptForWindowsCredentialsW` at `0x180047db0`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall Windows::Internal::ApplicationModel::Sync::CertificateHelperFactory::ShowCertificatePickerUI(
        HWND a1,
        __int64 a2,
        struct Windows::Security::Cryptography::Certificates::ICertificate **a3)
{
  HCERTSTORE v5; // rbx
  const char *v6; // r9
  unsigned int LastError; // ebx
  int v8; // edi
  HLOCAL v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rsi
  __int64 (__fastcall *v12)(__int64, __int64, HSTRING *); // rdi
  DWORD v13; // edi
  const char *v14; // r9
  const struct _CERT_CONTEXT *CertificateInStore; // rax
  const char *v16; // r9
  int CertificateFromContext; // eax
  HLOCAL v18; // rcx
  HLOCAL v20; // rcx
  HLOCAL v21; // rcx
  int pvPara; // [rsp+20h] [rbp-99h]
  int pvParaa; // [rsp+20h] [rbp-99h]
  int pvParab; // [rsp+20h] [rbp-99h]
  HSTRING string; // [rsp+50h] [rbp-69h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-61h] BYREF
  ULONG ulInAuthBufferSize[2]; // [rsp+60h] [rbp-59h] BYREF
  __int64 v28; // [rsp+68h] [rbp-51h] BYREF
  BYTE *pbElement; // [rsp+70h] [rbp-49h] BYREF
  ULONG cbElement; // [rsp+78h] [rbp-41h] BYREF
  ULONG pulAuthPackage; // [rsp+7Ch] [rbp-3Dh] BYREF
  const struct _CERT_CONTEXT *v32; // [rsp+80h] [rbp-39h] BYREF
  HCERTSTORE v33; // [rsp+88h] [rbp-31h] BYREF
  _CREDUI_INFOW pUiInfo; // [rsp+90h] [rbp-29h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+B8h] [rbp-1h] BYREF
  __int64 v36; // [rsp+D0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  *a3 = 0;
  v5 = CertOpenStore((LPCSTR)2, 0, 0, 0x200u, 0);
  v33 = v5;
  if ( !v5 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x76,
                  (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\certificatehelper.cpp",
                  v6);
LABEL_23:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v33);
    return LastError;
  }
  ulInAuthBufferSize[0] = 0;
  hMem = 0;
  hstringHeader.Reserved.Reserved1 = &hMem;
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
  hstringHeader.Reserved.Reserved2[16] = 1;
  v8 = Windows::Internal::ApplicationModel::Sync::CertificateHelperFactory::ObtainSerializedBlob(v5);
  wil::details::out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&hstringHeader);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7A,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\certificatehelper.cpp",
      (const char *)(unsigned int)v8,
      pvPara);
LABEL_5:
    v9 = hMem;
    hMem = 0;
    if ( v9 )
      LocalFree(v9);
    LastError = v8;
    goto LABEL_23;
  }
  v28 = 0;
  string = 0;
  v36 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.ApplicationModel.Sync.AccountsResourceHelper",
    0x3Eu,
    0x3Du);
  v8 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::ApplicationModel::Sync::IAccountsResourceHelperStatics>>(
         v36,
         &v28);
  if ( v8 < 0 )
  {
    v10 = 128;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\certificatehelper.cpp",
      (const char *)(unsigned int)v8,
      pvPara);
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
    goto LABEL_5;
  }
  v11 = v28;
  v12 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)v28 + 80LL);
  WindowsDeleteString(string);
  string = 0;
  v36 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"CertPickerCaption", 0x12u, 0x11u);
  v8 = v12(v11, v36, &string);
  if ( v8 < 0 )
  {
    v10 = 129;
    goto LABEL_10;
  }
  *(_QWORD *)&pUiInfo.cbSize = 40;
  memset(&pUiInfo.pszMessageText, 0, 24);
  pUiInfo.hwndParent = a1;
  pUiInfo.pszCaptionText = WindowsGetStringRawBuffer(string, 0);
  pulAuthPackage = -509;
  pbElement = 0;
  cbElement = 0;
  hstringHeader.Reserved.Reserved1 = &pbElement;
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
  hstringHeader.Reserved.Reserved2[16] = 1;
  v13 = CredUIPromptForWindowsCredentialsW(
          &pUiInfo,
          0,
          &pulAuthPackage,
          hMem,
          ulInAuthBufferSize[0],
          (LPVOID *)&hstringHeader.Reserved.Reserved2[8],
          &cbElement,
          0,
          0x10u);
  wil::details::out_param_t<wistd::unique_ptr<void,wil::cotaskmem_secure_deleter>>::~out_param_t<wistd::unique_ptr<void,wil::cotaskmem_secure_deleter>>(&hstringHeader);
  if ( v13 )
  {
    if ( (int)v13 > 0 )
      v13 = (unsigned __int16)v13 | 0x80070000;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB3,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\certificatehelper.cpp",
      (const char *)v13,
      pvParaa);
    wistd::unique_ptr<void,wil::cotaskmem_secure_deleter>::reset(&pbElement, 0);
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
    v21 = hMem;
    hMem = 0;
    if ( v21 )
      LocalFree(v21);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v33);
    return v13;
  }
  else
  {
    *(_QWORD *)ulInAuthBufferSize = 0;
    wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::reset(
      ulInAuthBufferSize,
      0);
    if ( !CertAddSerializedElementToStore(0, pbElement, cbElement, 4u, 0, 2u, 0, (const void **)ulInAuthBufferSize) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0xA2,
                    (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\certificatehelper.cpp",
                    v14);
      goto LABEL_21;
    }
    CertificateInStore = CertFindCertificateInStore(v5, 0x10001u, 0, 0xD0000u, *(const void **)ulInAuthBufferSize, 0);
    v32 = CertificateInStore;
    if ( !CertificateInStore )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0xAC,
                    (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\certificatehelper.cpp",
                    v16);
LABEL_20:
      wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&v32);
LABEL_21:
      wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(ulInAuthBufferSize);
      wistd::unique_ptr<void,wil::cotaskmem_secure_deleter>::reset(&pbElement, 0);
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
      v18 = hMem;
      hMem = 0;
      if ( v18 )
        LocalFree(v18);
      goto LABEL_23;
    }
    CertificateFromContext = Windows::Internal::ApplicationModel::Sync::CertificateHelperFactory::CreateCertificateFromContext(
                               CertificateInStore,
                               a3);
    LastError = CertificateFromContext;
    if ( CertificateFromContext < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAD,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\certificatehelper.cpp",
        (const char *)(unsigned int)CertificateFromContext,
        pvParab);
      goto LABEL_20;
    }
    wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&v32);
    wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(ulInAuthBufferSize);
    wistd::unique_ptr<void,wil::cotaskmem_secure_deleter>::reset(&pbElement, 0);
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
    v20 = hMem;
    hMem = 0;
    if ( v20 )
      LocalFree(v20);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v33);
    return 0;
  }
}

```

## disassembly

```asm
0x180047b8c  push    rbp
0x180047b8e  push    rbx
0x180047b8f  push    rsi
0x180047b90  push    rdi
0x180047b91  push    r12
0x180047b93  push    r14
0x180047b95  push    r15
0x180047b97  lea     rbp, [rsp-27h]
0x180047b9c  sub     rsp, 0E0h
0x180047ba3  mov     rax, cs:__security_cookie
0x180047baa  xor     rax, rsp
0x180047bad  mov     [rbp+57h+var_38], rax
0x180047bb1  mov     r14, r8
0x180047bb4  mov     rdi, rdx
0x180047bb7  mov     r15, rcx
0x180047bba  xor     r12d, r12d
0x180047bbd  mov     [r8], r12
0x180047bc0  mov     [rsp+110h+pvPara], r12; int
0x180047bc5  mov     r9d, 200h; dwFlags
0x180047bcb  xor     r8d, r8d; hCryptProv
0x180047bce  xor     edx, edx; dwEncodingType
0x180047bd0  lea     ecx, [rdx+2]; lpszStoreProvider
0x180047bd3  call    cs:__imp_CertOpenStore
0x180047bd9  mov     rbx, rax
0x180047bdc  mov     [rbp+57h+var_88], rax
0x180047be0  test    rax, rax
0x180047be3  jnz     short loc_180047BFF
0x180047be5  mov     rcx, [rbp+5Fh]; this
0x180047be9  lea     r8, aOnecoreuapShel_20; "onecoreuap\\shell\\accountscontrol\\api"...
0x180047bf0  lea     edx, [rax+76h]; void *
0x180047bf3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180047bf8  mov     ebx, eax
0x180047bfa  jmp     loc_180047EE1
0x180047bff  mov     [rbp+57h+ulInAuthBufferSize], r12d
0x180047c03  mov     [rbp+57h+hMem], r12
0x180047c07  lea     rax, [rbp+57h+hMem]
0x180047c0b  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rax
0x180047c0f  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], r12
0x180047c13  mov     byte ptr [rbp+57h+hstringHeader.Reserved+10h], 1
0x180047c17  lea     r9, [rbp+57h+ulInAuthBufferSize]
0x180047c1b  lea     r8, [rbp+57h+hstringHeader.Reserved+8]
0x180047c1f  mov     rdx, rdi
0x180047c22  mov     rcx, rbx
0x180047c25  call    ?ObtainSerializedBlob@CertificateHelperFactory@Sync@ApplicationModel@Internal@Windows@@CAJPEAXPEAU?$IIterable@PEAVCertificate@Certificates@Cryptography@Security@Windows@@@Collections@Foundation@5@PEAPEAXPEAK@Z; Windows::Internal::ApplicationModel::Sync::CertificateHelperFactory::ObtainSerializedBlob(void *,Windows::Foundation::Collections::IIterable<Windows::Security::Cryptography::Certificates::Certificate *> *,void * *,ulong *)
0x180047c2a  mov     edi, eax
0x180047c2c  lea     rcx, [rbp+57h+hstringHeader]
0x180047c30  call    ??1?$out_param_t@V?$unique_ptr@XU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180047c35  test    edi, edi
0x180047c37  jns     short loc_180047C6C
0x180047c39  mov     rcx, [rbp+5Fh]; this
0x180047c3d  mov     r9d, edi; char *
0x180047c40  lea     r8, aOnecoreuapShel_20; "onecoreuap\\shell\\accountscontrol\\api"...
0x180047c47  mov     edx, 7Ah ; 'z'; void *
0x180047c4c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047c51  nop
0x180047c52  mov     rcx, [rbp+57h+hMem]; hMem
0x180047c56  mov     [rbp+57h+hMem], r12
0x180047c5a  test    rcx, rcx
0x180047c5d  jz      short loc_180047C65
0x180047c5f  call    cs:__imp_LocalFree
0x180047c65  mov     ebx, edi
0x180047c67  jmp     loc_180047EE1
0x180047c6c  mov     [rbp+57h+var_A8], r12
0x180047c70  mov     [rbp+57h+string], r12
0x180047c74  mov     [rbp+57h+var_40], r12
0x180047c78  mov     r9d, 3Dh ; '='; unsigned int
0x180047c7e  lea     r8d, [r9+1]; unsigned int
0x180047c82  lea     rdx, ?RuntimeClass_Windows_Internal_ApplicationModel_Sync_AccountsResourceHelper@@3QBGB; "Windows.Internal.ApplicationModel.Sync."...
0x180047c89  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180047c8d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180047c92  lea     rdx, [rbp+57h+var_A8]
0x180047c96  mov     rcx, [rbp+57h+var_40]
0x180047c9a  call    ??$GetActivationFactory@V?$ComPtr@UIAccountsResourceHelperStatics@Sync@ApplicationModel@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIAccountsResourceHelperStatics@Sync@ApplicationModel@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::ApplicationModel::Sync::IAccountsResourceHelperStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::ApplicationModel::Sync::IAccountsResourceHelperStatics>>)
0x180047c9f  mov     edi, eax
0x180047ca1  test    eax, eax
0x180047ca3  jns     short loc_180047CDA
0x180047ca5  mov     edx, 80h; void *
0x180047caa  lea     r8, aOnecoreuapShel_20; "onecoreuap\\shell\\accountscontrol\\api"...
0x180047cb1  mov     r9d, edi; char *
0x180047cb4  mov     rcx, [rbp+5Fh]; this
0x180047cb8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047cbd  nop
0x180047cbe  mov     rcx, [rbp+57h+string]; string
0x180047cc2  call    cs:__imp_WindowsDeleteString
0x180047cc8  mov     [rbp+57h+string], r12
0x180047ccc  lea     rcx, [rbp+57h+var_A8]
0x180047cd0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180047cd5  jmp     loc_180047C52
0x180047cda  mov     rsi, [rbp+57h+var_A8]
0x180047cde  mov     rax, [rsi]
0x180047ce1  mov     rdi, [rax+50h]
0x180047ce5  mov     rcx, [rbp+57h+string]; string
0x180047ce9  call    cs:__imp_WindowsDeleteString
0x180047cef  mov     [rbp+57h+string], r12
0x180047cf3  mov     [rbp+57h+var_40], r12
0x180047cf7  mov     r9d, 11h; unsigned int
0x180047cfd  lea     r8d, [r9+1]; unsigned int
0x180047d01  lea     rdx, aCertpickercapt; "CertPickerCaption"
0x180047d08  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180047d0c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180047d11  nop
0x180047d12  lea     r8, [rbp+57h+string]
0x180047d16  mov     rdx, [rbp+57h+var_40]
0x180047d1a  mov     rcx, rsi
0x180047d1d  mov     rax, rdi
0x180047d20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047d25  mov     edi, eax
0x180047d27  test    eax, eax
0x180047d29  jns     short loc_180047D35
0x180047d2b  mov     edx, 81h
0x180047d30  jmp     loc_180047CAA
0x180047d35  mov     qword ptr [rbp+57h+pUiInfo.cbSize], 28h ; '('
0x180047d3d  xorps   xmm0, xmm0
0x180047d40  movdqu  xmmword ptr [rbp+57h+pUiInfo.pszMessageText], xmm0
0x180047d45  mov     [rbp+57h+pUiInfo.hbmBanner], r12
0x180047d49  mov     [rbp+57h+pUiInfo.hwndParent], r15
0x180047d4d  xor     edx, edx; length
0x180047d4f  mov     rcx, [rbp+57h+string]; string
0x180047d53  call    cs:__imp_WindowsGetStringRawBuffer
0x180047d59  mov     [rbp+57h+pUiInfo.pszCaptionText], rax
0x180047d5d  mov     [rbp+57h+pulAuthPackage], 0FFFFFE03h
0x180047d64  mov     [rbp+57h+pbElement], r12
0x180047d68  mov     [rbp+57h+cbElement], r12d
0x180047d6c  lea     rax, [rbp+57h+pbElement]
0x180047d70  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rax
0x180047d74  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], r12
0x180047d78  mov     byte ptr [rbp+57h+hstringHeader.Reserved+10h], 1
0x180047d7c  mov     [rsp+110h+dwFlags], 10h; dwFlags
0x180047d84  mov     [rsp+110h+pfSave], r12; pfSave
0x180047d89  lea     rax, [rbp+57h+cbElement]
0x180047d8d  mov     [rsp+110h+pulOutAuthBufferSize], rax; pulOutAuthBufferSize
0x180047d92  lea     rax, [rbp+57h+hstringHeader.Reserved+8]
0x180047d96  mov     [rsp+110h+ppvOutAuthBuffer], rax; ppvOutAuthBuffer
0x180047d9b  mov     eax, [rbp+57h+ulInAuthBufferSize]
0x180047d9e  mov     dword ptr [rsp+110h+pvPara], eax; int
0x180047da2  mov     r9, [rbp+57h+hMem]; pvInAuthBuffer
0x180047da6  lea     r8, [rbp+57h+pulAuthPackage]; pulAuthPackage
0x180047daa  xor     edx, edx; dwAuthError
0x180047dac  lea     rcx, [rbp+57h+pUiInfo]; pUiInfo
0x180047db0  call    cs:__imp_CredUIPromptForWindowsCredentialsW
0x180047db6  mov     edi, eax
0x180047db8  lea     rcx, [rbp+57h+hstringHeader]
0x180047dbc  call    ??1?$out_param_t@V?$unique_ptr@XUcotaskmem_secure_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<void,wil::cotaskmem_secure_deleter>>::~out_param_t<wistd::unique_ptr<void,wil::cotaskmem_secure_deleter>>(void)
0x180047dc1  test    edi, edi
0x180047dc3  jnz     loc_180047F4A
0x180047dc9  mov     qword ptr [rbp+57h+ulInAuthBufferSize], r12
0x180047dcd  xor     edx, edx
0x180047dcf  lea     rcx, [rbp+57h+ulInAuthBufferSize]
0x180047dd3  call    ?reset@?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEBU_CERT_CONTEXT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::reset(_CERT_CONTEXT const *)
0x180047dd8  lea     rax, [rbp+57h+ulInAuthBufferSize]
0x180047ddc  mov     [rsp+110h+pfSave], rax; ppvContext
0x180047de1  mov     [rsp+110h+pulOutAuthBufferSize], r12; pdwContextType
0x180047de6  mov     dword ptr [rsp+110h+ppvOutAuthBuffer], 2; dwContextTypeFlags
0x180047dee  mov     dword ptr [rsp+110h+pvPara], r12d; dwFlags
0x180047df3  lea     r9d, [rdi+4]; dwAddDisposition
0x180047df7  mov     r8d, [rbp+57h+cbElement]; cbElement
0x180047dfb  mov     rdx, [rbp+57h+pbElement]; pbElement
0x180047dff  xor     ecx, ecx; hCertStore
0x180047e01  call    cs:__imp_CertAddSerializedElementToStore
0x180047e07  test    eax, eax
0x180047e09  jnz     short loc_180047E24
0x180047e0b  mov     rcx, [rbp+5Fh]; this
0x180047e0f  lea     r8, aOnecoreuapShel_20; "onecoreuap\\shell\\accountscontrol\\api"...
0x180047e16  mov     edx, 0A2h; void *
0x180047e1b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180047e20  mov     ebx, eax
0x180047e22  jmp     short loc_180047E9F
0x180047e24  mov     [rsp+110h+ppvOutAuthBuffer], r12; pPrevCertContext
0x180047e29  mov     rax, qword ptr [rbp+57h+ulInAuthBufferSize]
0x180047e2d  mov     [rsp+110h+pvPara], rax; int
0x180047e32  mov     r9d, 0D0000h; dwFindType
0x180047e38  xor     r8d, r8d; dwFindFlags
0x180047e3b  mov     edx, 10001h; dwCertEncodingType
0x180047e40  mov     rcx, rbx; hCertStore
0x180047e43  call    cs:__imp_CertFindCertificateInStore
0x180047e49  mov     [rbp+57h+var_90], rax
0x180047e4d  test    rax, rax
0x180047e50  jnz     short loc_180047E6B
0x180047e52  mov     rcx, [rbp+5Fh]; this
0x180047e56  lea     r8, aOnecoreuapShel_20; "onecoreuap\\shell\\accountscontrol\\api"...
0x180047e5d  mov     edx, 0ACh; void *
0x180047e62  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180047e67  mov     ebx, eax
0x180047e69  jmp     short loc_180047E95
0x180047e6b  mov     rdx, r14; struct Windows::Security::Cryptography::Certificates::ICertificate **
0x180047e6e  mov     rcx, rax; struct _CERT_CONTEXT *
0x180047e71  call    ?CreateCertificateFromContext@CertificateHelperFactory@Sync@ApplicationModel@Internal@Windows@@CAJPEBU_CERT_CONTEXT@@PEAPEAUICertificate@Certificates@Cryptography@Security@5@@Z; Windows::Internal::ApplicationModel::Sync::CertificateHelperFactory::CreateCertificateFromContext(_CERT_CONTEXT const *,Windows::Security::Cryptography::Certificates::ICertificate * *)
0x180047e76  mov     ebx, eax
0x180047e78  test    eax, eax
0x180047e7a  jns     short loc_180047EF1
0x180047e7c  mov     rcx, [rbp+5Fh]; this
0x180047e80  mov     r9d, eax; char *
0x180047e83  lea     r8, aOnecoreuapShel_20; "onecoreuap\\shell\\accountscontrol\\api"...
0x180047e8a  mov     edx, 0ADh; void *
0x180047e8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047e94  nop
0x180047e95  lea     rcx, [rbp+57h+var_90]
0x180047e99  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x180047e9e  nop
0x180047e9f  lea     rcx, [rbp+57h+ulInAuthBufferSize]
0x180047ea3  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x180047ea8  nop
0x180047ea9  xor     edx, edx
0x180047eab  lea     rcx, [rbp+57h+pbElement]
0x180047eaf  call    ?reset@?$unique_ptr@XUcotaskmem_secure_deleter@wil@@@wistd@@QEAAXPEAX@Z; wistd::unique_ptr<void,wil::cotaskmem_secure_deleter>::reset(void *)
0x180047eb4  nop
0x180047eb5  mov     rcx, [rbp+57h+string]; string
0x180047eb9  call    cs:__imp_WindowsDeleteString
0x180047ebf  mov     [rbp+57h+string], r12
0x180047ec3  lea     rcx, [rbp+57h+var_A8]
0x180047ec7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180047ecc  nop
0x180047ecd  mov     rcx, [rbp+57h+hMem]; hMem
0x180047ed1  mov     [rbp+57h+hMem], r12
0x180047ed5  test    rcx, rcx
0x180047ed8  jz      short loc_180047EE1
0x180047eda  call    cs:__imp_LocalFree
0x180047ee0  nop
0x180047ee1  lea     rcx, [rbp+57h+var_88]
0x180047ee5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180047eea  mov     eax, ebx
0x180047eec  jmp     loc_180047FB5
0x180047ef1  lea     rcx, [rbp+57h+var_90]
0x180047ef5  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x180047efa  nop
0x180047efb  lea     rcx, [rbp+57h+ulInAuthBufferSize]
0x180047eff  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x180047f04  nop
0x180047f05  xor     edx, edx
0x180047f07  lea     rcx, [rbp+57h+pbElement]
0x180047f0b  call    ?reset@?$unique_ptr@XUcotaskmem_secure_deleter@wil@@@wistd@@QEAAXPEAX@Z; wistd::unique_ptr<void,wil::cotaskmem_secure_deleter>::reset(void *)
0x180047f10  nop
0x180047f11  mov     rcx, [rbp+57h+string]; string
0x180047f15  call    cs:__imp_WindowsDeleteString
0x180047f1b  mov     [rbp+57h+string], r12
0x180047f1f  lea     rcx, [rbp+57h+var_A8]
0x180047f23  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180047f28  nop
0x180047f29  mov     rcx, [rbp+57h+hMem]; hMem
0x180047f2d  mov     [rbp+57h+hMem], r12
0x180047f31  test    rcx, rcx
0x180047f34  jz      short loc_180047F3D
0x180047f36  call    cs:__imp_LocalFree
0x180047f3c  nop
0x180047f3d  lea     rcx, [rbp+57h+var_88]
0x180047f41  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180047f46  xor     eax, eax
0x180047f48  jmp     short loc_180047FB5
0x180047f4a  jle     short loc_180047F55
0x180047f4c  movzx   edi, di
0x180047f4f  or      edi, 80070000h
0x180047f55  test    edi, edi
0x180047f57  jns     short loc_180047F72
0x180047f59  mov     rcx, [rbp+5Fh]; this
0x180047f5d  mov     r9d, edi; char *
0x180047f60  lea     r8, aOnecoreuapShel_20; "onecoreuap\\shell\\accountscontrol\\api"...
0x180047f67  mov     edx, 0B3h; void *
0x180047f6c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047f71  nop
0x180047f72  xor     edx, edx
0x180047f74  lea     rcx, [rbp+57h+pbElement]
0x180047f78  call    ?reset@?$unique_ptr@XUcotaskmem_secure_deleter@wil@@@wistd@@QEAAXPEAX@Z; wistd::unique_ptr<void,wil::cotaskmem_secure_deleter>::reset(void *)
0x180047f7d  nop
0x180047f7e  mov     rcx, [rbp+57h+string]; string
0x180047f82  call    cs:__imp_WindowsDeleteString
0x180047f88  mov     [rbp+57h+string], r12
0x180047f8c  lea     rcx, [rbp+57h+var_A8]
0x180047f90  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180047f95  nop
0x180047f96  mov     rcx, [rbp+57h+hMem]; hMem
0x180047f9a  mov     [rbp+57h+hMem], r12
0x180047f9e  test    rcx, rcx
0x180047fa1  jz      short loc_180047FAA
0x180047fa3  call    cs:__imp_LocalFree
0x180047fa9  nop
0x180047faa  lea     rcx, [rbp+57h+var_88]
0x180047fae  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180047fb3  mov     eax, edi
0x180047fb5  mov     rcx, [rbp+57h+var_38]
0x180047fb9  xor     rcx, rsp; StackCookie
0x180047fbc  call    __security_check_cookie
0x180047fc1  add     rsp, 0E0h
0x180047fc8  pop     r15
0x180047fca  pop     r14
0x180047fcc  pop     r12
0x180047fce  pop     rdi
0x180047fcf  pop     rsi
0x180047fd0  pop     rbx
0x180047fd1  pop     rbp
0x180047fd2  retn
```
