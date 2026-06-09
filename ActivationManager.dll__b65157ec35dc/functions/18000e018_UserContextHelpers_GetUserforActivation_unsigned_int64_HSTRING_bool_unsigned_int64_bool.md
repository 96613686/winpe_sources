# UserContextHelpers::GetUserforActivation(unsigned __int64,HSTRING__ *,bool,unsigned __int64 *,bool *)

- ea: `0x18000e018`
- end: `0x18000e893`
- name: `?GetUserforActivation@UserContextHelpers@@QEAAJ_KPEAUHSTRING__@@_NPEA_KPEA_N@Z`
- size: `2171`
- prototype: `int(UserContextHelpers *__hidden this, unsigned __int64, HSTRING, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `29`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18006b040`

## callees

- `0x18000b5c0`
- `0x18000cbc0`
- `0x18000e018`
- `0x18000e89c`
- `0x18000eb18`
- `0x18000f960`
- `0x18000fa48`
- `0x180011328`
- `0x18001baa4`
- `0x18001e5ac`
- `0x180024770`
- `0x180024840`
- `0x180031540`
- `0x18003e9d8`
- `0x180044408`
- `0x18004d078`
- `0x1800572a4`
- `0x180059df8`
- `0x18005ae90`
- `0x18005b37c`
- `0x18005b3c4`
- `0x18005ba40`
- `0x180067e64`
- `0x18007bb0c`
- `0x18007c02c`
- `0x18007c0a8`
- `0x18007d250`
- `0x18007d2e8`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000e50c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000e50c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e0ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e0ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e1ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e1ba`
- `ntdll!RtlIsMultiSessionSku` at `0x18000e273`
- `ntdll!RtlIsMultiSessionSku` at `0x18000e273`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000e398`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000e41b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000e817`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000e398`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000e41b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000e817`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000e4f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000e4f6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000e0df`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000e153`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000e0df`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000e153`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000e18f`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000e18f`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18000e2b0`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18000e2b0`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18000e089`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18000e089`

## string_xrefs

- `0x18000e123`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x18000e164`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x18000e23b`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x18000e4ef`: `Windows.Internal.PlatformExtensions.UserSelection`
- `0x18000e534`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall UserContextHelpers::GetUserforActivation(
        UserContextHelpers *this,
        unsigned __int64 a2,
        HSTRING a3,
        char a4,
        unsigned __int64 *a5,
        bool *a6)
{
  int v8; // r12d
  char *v9; // rcx
  int v10; // eax
  PSID *v11; // rbx
  __int64 v12; // rdi
  const char *v13; // r9
  PSID *v14; // rsi
  int LastError; // edi
  const char *v16; // r9
  char v17; // di
  int v18; // eax
  unsigned int v19; // ebx
  __int64 v20; // rdx
  const char *v21; // r9
  const unsigned __int16 *StringRawBuffer; // rbx
  unsigned __int64 v24; // rdx
  unsigned __int8 v25; // cl
  __int64 v26; // rdx
  unsigned __int64 v27; // rsi
  AAMTraceProvider *v28; // rcx
  __int64 v29; // rcx
  const unsigned __int16 *v30; // rbx
  HRESULT v31; // eax
  __int64 v32; // r8
  int v33; // eax
  unsigned __int64 v34; // rcx
  unsigned __int64 v35; // rbx
  __int64 v36; // rax
  __int64 (__fastcall *v37)(unsigned __int64, __int64, HSTRING); // rdi
  int v38; // eax
  __int64 v39; // rdx
  __int64 (__fastcall *v40)(unsigned __int64, HSTRING, _QWORD, int *); // rdi
  int (__fastcall ***v41)(_QWORD, GUID *, __int64 *); // rdi
  HRESULT v42; // edx
  __int64 v43; // r8
  __int64 v44; // rdi
  __int64 (__fastcall *v45)(__int64, HANDLE *); // rbx
  int v46; // eax
  int v47; // eax
  __int64 v48; // rdx
  bool *v49; // rdi
  unsigned __int64 v50; // rbx
  bool v51; // di
  const unsigned __int16 *v52; // rax
  unsigned __int64 v53; // rcx
  int *ReturnLength; // [rsp+20h] [rbp-E0h]
  int ReturnLengtha; // [rsp+20h] [rbp-E0h]
  char v56[8]; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE TokenHandle; // [rsp+38h] [rbp-C8h] BYREF
  DWORD TokenInformationLength[2]; // [rsp+40h] [rbp-C0h] BYREF
  char v59; // [rsp+48h] [rbp-B8h]
  unsigned __int64 v60; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v61; // [rsp+58h] [rbp-A8h] BYREF
  int v62[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v63; // [rsp+68h] [rbp-98h] BYREF
  bool *v64; // [rsp+70h] [rbp-90h]
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp-88h] BYREF
  HSTRING string; // [rsp+90h] [rbp-70h] BYREF
  void **v67; // [rsp+A0h] [rbp-60h] BYREF
  int v68; // [rsp+A8h] [rbp-58h] BYREF
  char v69; // [rsp+ACh] [rbp-54h]
  int v70; // [rsp+D0h] [rbp-30h] BYREF
  const char *v71; // [rsp+D8h] [rbp-28h]
  __int64 v72; // [rsp+E0h] [rbp-20h]
  char v73; // [rsp+E8h] [rbp-18h]
  int v74; // [rsp+F0h] [rbp-10h]
  char v75[152]; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v76; // [rsp+190h] [rbp+90h]
  int v77; // [rsp+1A0h] [rbp+A0h]
  __int64 v78; // [rsp+1A8h] [rbp+A8h]
  int *v79; // [rsp+1B0h] [rbp+B0h]
  __int64 v80; // [rsp+1B8h] [rbp+B8h]
  __int64 v81; // [rsp+1C0h] [rbp+C0h]
  void ***v82; // [rsp+1C8h] [rbp+C8h]
  __int64 v83; // [rsp+1D0h] [rbp+D0h]
  int v84; // [rsp+1D8h] [rbp+D8h]
  int *v85; // [rsp+1E0h] [rbp+E0h]
  char v86; // [rsp+1E8h] [rbp+E8h]
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+138h]

  v59 = a4;
  v60 = a2;
  v64 = a6;
  *a6 = 0;
  v8 = 0;
  v9 = 0;
  TokenHandle = 0;
  if ( !*a5 )
  {
LABEL_17:
    if ( (unsigned __int64)(v9 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v9);
    goto LABEL_19;
  }
  v10 = UMgrQueryUserToken(*a5, &TokenHandle);
  if ( v10 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x52,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\usercontexthelpers.cpp",
      (const char *)(unsigned int)v10,
      (int)ReturnLength);
LABEL_16:
    v9 = (char *)TokenHandle;
    goto LABEL_17;
  }
  v11 = 0;
  v12 = -6;
  if ( TokenHandle )
    v12 = (__int64)TokenHandle;
  TokenInformationLength[0] = 0;
  if ( GetTokenInformation((HANDLE)v12, TokenUser, 0, 0, TokenInformationLength) || GetLastError() != 122 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x117,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
                  v13);
  }
  else
  {
    v14 = (PSID *)operator new(TokenInformationLength[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( !v14 )
    {
      LastError = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x119,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
        (const char *)0x8007000ELL,
        (int)ReturnLength);
LABEL_26:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x56,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\usercontexthelpers.cpp",
        (const char *)(unsigned int)LastError,
        (int)ReturnLength);
      goto LABEL_32;
    }
    if ( GetTokenInformation((HANDLE)v12, TokenUser, v14, TokenInformationLength[0], TokenInformationLength) )
    {
      v11 = v14;
      goto LABEL_13;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x11A,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
                  v16);
    operator delete(v14);
  }
  if ( LastError < 0 )
    goto LABEL_26;
LABEL_13:
  if ( IsWellKnownSid(*v11, WinLocalAccountAndAdministratorSid|WinCreatorGroupSid) )
  {
    v8 = 1;
    goto LABEL_15;
  }
  if ( (unsigned __int8)RtlIsMultiSessionSku()
    || !*(_BYTE *)this
    || (int)UserContextHelpers::GetResourceAccountSid(this) < 0 )
  {
    goto LABEL_15;
  }
  TokenInformationLength[0] = 0;
  if ( !(unsigned int)CheckTokenMembershipEx(TokenHandle, (char *)this + 4, 0, TokenInformationLength) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x61,
                  (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\usercontexthelpers.cpp",
                  v21);
    operator delete(v11);
LABEL_32:
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    if ( LastError < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB5,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\usercontexthelpers.cpp",
        (const char *)(unsigned int)LastError,
        (int)ReturnLength);
      return (unsigned int)LastError;
    }
    goto LABEL_19;
  }
  if ( !TokenInformationLength[0] )
  {
LABEL_15:
    operator delete(v11);
    goto LABEL_16;
  }
  v8 = 2;
  operator delete(v11);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
LABEL_19:
  v17 = 0;
  if ( !*(_BYTE *)this || v8 != 2 )
    goto LABEL_46;
  v56[0] = 0;
  if ( (int)UserContextHelpers::GetResourceAccountSid(this) >= 0 )
  {
    v61 = 0;
    string = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Microsoft.ResourceAccountManager.ResourceAccountPolicy",
      0x37u,
      0x36u);
    v18 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Microsoft::ResourceAccountManager::IResourceAccountPolicy>>(
            (__int64)string,
            &v61);
    v19 = v18;
    if ( v18 < 0 )
    {
      v20 = 191;
LABEL_38:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v20,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\usercontexthelpers.cpp",
        (const char *)(unsigned int)v18,
        (int)ReturnLength);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v61);
      return v19;
    }
    v18 = (*(__int64 (__fastcall **)(__int64, HSTRING, char *))(*(_QWORD *)v61 + 48LL))(v61, a3, v56);
    v19 = v18;
    if ( v18 < 0 )
    {
      v20 = 192;
      goto LABEL_38;
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v61);
  }
  if ( !v56[0] )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(a3, 0);
    if ( AAMTraceProvider::IsEnabled(v25, v24) )
    {
      AAMTraceProvider::Instance();
      v27 = v60;
      AAMTraceProvider::BlockUserForActivation_(v28, v60, StringRawBuffer, 2u);
    }
    else
    {
      v27 = v60;
    }
    v17 = 1;
    *a5 = 0;
    LOBYTE(v26) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_UserSelectionForRA>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_UserSelectionForRA>::GetImpl'::`2'::impl,
      v26,
      0);
  }
  else
  {
LABEL_46:
    v27 = v60;
  }
  v29 = *(unsigned int *)Feature_ShellUserSelection__descriptor;
  if ( (v29 & 4) == 0 )
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShellUserSelection>::GetCachedFeatureEnabledState(v29, &v63);
  if ( !*a5 || v59 )
  {
    v30 = WindowsGetStringRawBuffer(a3, 0);
    v68 = 0;
    v69 = 0;
    v73 = 0;
    v70 = 0;
    v71 = "UserSelectionPromptActivity";
    v72 = 0;
    v74 = 0;
    v76 = 0;
    memset_0(v75, 0, sizeof(v75));
    v77 = 1;
    v78 = 0;
    v79 = &v68;
    v80 = 0;
    v81 = 0;
    v82 = &v67;
    v83 = 0;
    v84 = 0;
    v85 = &v70;
    v86 = 0;
    v67 = &AAMTraceProvider::UserSelectionPromptActivity::`vftable';
    AAMTraceProvider::UserSelectionPromptActivity::StartActivity(
      (AAMTraceProvider::UserSelectionPromptActivity *)&v67,
      v27,
      v30,
      *a5);
    v60 = 0;
    string = 0;
    v31 = WindowsCreateStringReference(
            L"Windows.Internal.PlatformExtensions.UserSelection",
            0x31u,
            &hstringHeader,
            &string);
    if ( v31 < 0 )
    {
      RaiseException(v31, 1u, 0, 0);
      __debugbreak();
    }
    v33 = Windows::Internal::PlatformExtensions::Details::TryActivateContractExtensionInternal(string, 0, v32, &v60);
    v19 = v33;
    if ( v33 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x299,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\PlatformExtensionTools.h",
        (const char *)(unsigned int)v33,
        (int)ReturnLength);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD5,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\usercontexthelpers.cpp",
        (const char *)v19,
        ReturnLengtha);
      v34 = v60;
      if ( v60 )
      {
        v60 = 0;
        (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v34 + 16LL))(v34);
      }
      v67 = &AAMTraceProvider::UserSelectionPromptActivity::`vftable';
      wil::ActivityBase<AAMTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v67);
      wil::ActivityBase<AAMTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<AAMTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(&v67);
      return v19;
    }
    v35 = v60;
    if ( v60 )
    {
      v63 = 0;
      *(_QWORD *)v62 = 0;
      v36 = *(_QWORD *)v60;
      if ( v17 )
      {
        v37 = *(__int64 (__fastcall **)(unsigned __int64, __int64, HSTRING))(v36 + 56);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v62);
        ReturnLength = v62;
        v38 = v37(v35, 3, a3);
        v19 = v38;
        if ( v38 < 0 )
        {
          v39 = 221;
LABEL_63:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v39,
            (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\usercontexthelpers.cpp",
            (const char *)(unsigned int)v38,
            (int)ReturnLength);
LABEL_79:
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v62);
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v60);
          AAMTraceProvider::UserSelectionPromptActivity::~UserSelectionPromptActivity((AAMTraceProvider::UserSelectionPromptActivity *)&v67);
          return v19;
        }
      }
      else
      {
        v40 = *(__int64 (__fastcall **)(unsigned __int64, HSTRING, _QWORD, int *))(v36 + 48);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v62);
        v38 = v40(v35, a3, 0, v62);
        v19 = v38;
        if ( v38 < 0 )
        {
          v39 = 225;
          goto LABEL_63;
        }
      }
      AAMTraceProvider::UserSelectionPromptActivity::StartShowUserSelectionDialog();
      *(_QWORD *)TokenInformationLength = 0;
      v41 = *(int (__fastcall ****)(_QWORD, GUID *, __int64 *))v62;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(TokenInformationLength);
      v19 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>>(
              v41,
              v42,
              v43);
      if ( (v19 & 0x80000000) != 0
        || (v19 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), DWORD *))(*v41)[8])(
                    v41,
                    TokenInformationLength),
            (v19 & 0x80000000) != 0) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xE6,
          (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\usercontexthelpers.cpp",
          (const char *)v19,
          (int)ReturnLength);
        goto LABEL_78;
      }
      AAMTraceProvider::UserSelectionPromptActivity::EndUserSelectionDialog();
      TokenHandle = 0;
      v44 = *(_QWORD *)TokenInformationLength;
      v45 = *(__int64 (__fastcall **)(__int64, HANDLE *))(**(_QWORD **)TokenInformationLength + 56LL);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&TokenHandle);
      v46 = v45(v44, &TokenHandle);
      v19 = v46;
      if ( v46 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xEA,
          (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\usercontexthelpers.cpp",
          (const char *)(unsigned int)v46,
          (int)ReturnLength);
LABEL_68:
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&TokenHandle);
LABEL_78:
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(TokenInformationLength);
        goto LABEL_79;
      }
      if ( TokenHandle )
      {
        v61 = 0;
        string = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"Windows.System.Internal.UserManager",
          0x24u,
          0x23u);
        v47 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInStateManager>>(
                (__int64)string,
                (__int64)&v61);
        v19 = v47;
        if ( v47 < 0 )
        {
          v48 = 239;
LABEL_72:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v48,
            (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\usercontexthelpers.cpp",
            (const char *)(unsigned int)v47,
            (int)ReturnLength);
          string = 0;
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v61);
          goto LABEL_68;
        }
        v47 = (*(__int64 (__fastcall **)(__int64, HANDLE, unsigned __int64 *))(*(_QWORD *)v61 + 136LL))(
                v61,
                TokenHandle,
                &v63);
        v19 = v47;
        if ( v47 < 0 )
        {
          v48 = 240;
          goto LABEL_72;
        }
        *a5 = v63;
        string = 0;
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v61);
      }
      v49 = v64;
      *v64 = 1;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&TokenHandle);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(TokenInformationLength);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v62);
    }
    else
    {
      v49 = v64;
    }
    v50 = *a5;
    v51 = *v49;
    v52 = WindowsGetStringRawBuffer(a3, 0);
    AAMTraceProvider::UserSelectionPromptActivity::Stop(
      (AAMTraceProvider::UserSelectionPromptActivity *)&v67,
      v27,
      v52,
      v51,
      v50);
    v53 = v60;
    if ( v60 )
    {
      v60 = 0;
      (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v53 + 16LL))(v53);
    }
    v67 = &AAMTraceProvider::UserSelectionPromptActivity::`vftable';
    wil::ActivityBase<AAMTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v67);
    wil::ActivityBase<AAMTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<AAMTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(&v67);
  }
  return 0;
}

```

## disassembly

```asm
0x18000e018  mov     [rsp-8+arg_18], rbx
0x18000e01d  push    rbp
0x18000e01e  push    rsi
0x18000e01f  push    rdi
0x18000e020  push    r12
0x18000e022  push    r13
0x18000e024  push    r14
0x18000e026  push    r15
0x18000e028  lea     rbp, [rsp-100h]
0x18000e030  sub     rsp, 200h
0x18000e037  mov     rax, cs:__security_cookie
0x18000e03e  xor     rax, rsp
0x18000e041  mov     [rbp+130h+var_40], rax
0x18000e048  mov     [rsp+230h+var_1E8], r9b
0x18000e04d  mov     r13, r8
0x18000e050  mov     [rsp+230h+var_1E0], rdx
0x18000e055  mov     r14, rcx
0x18000e058  mov     r15, [rbp+130h+arg_20]
0x18000e05f  mov     rax, [rbp+130h+arg_28]
0x18000e066  mov     [rsp+230h+var_1C0], rax
0x18000e06b  mov     byte ptr [rax], 0
0x18000e06e  xor     r12d, r12d
0x18000e071  xor     ecx, ecx
0x18000e073  mov     [rsp+230h+TokenHandle], rcx
0x18000e078  cmp     [r15], rcx
0x18000e07b  jz      loc_18000E1B0
0x18000e081  lea     rdx, [rsp+230h+TokenHandle]
0x18000e086  mov     rcx, [r15]
0x18000e089  call    cs:__imp_UMgrQueryUserToken
0x18000e08f  mov     rcx, [rbp+138h]; this
0x18000e096  test    eax, eax
0x18000e098  jns     short loc_18000E0B3
0x18000e09a  mov     r9d, eax; char *
0x18000e09d  lea     r8, aOnecoreuapBase_30; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18000e0a4  lea     edx, [r12+52h]; void *
0x18000e0a9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000e0ae  jmp     loc_18000E1AB
0x18000e0b3  mov     rax, [rsp+230h+TokenHandle]
0x18000e0b8  xor     ebx, ebx
0x18000e0ba  lea     rdi, [rbx-6]
0x18000e0be  test    rax, rax
0x18000e0c1  cmovnz  rdi, rax
0x18000e0c5  mov     [rsp+230h+TokenInformationLength], ebx
0x18000e0c9  lea     rax, [rsp+230h+TokenInformationLength]
0x18000e0ce  mov     [rsp+230h+ReturnLength], rax; int
0x18000e0d3  xor     r9d, r9d; TokenInformationLength
0x18000e0d6  xor     r8d, r8d; TokenInformation
0x18000e0d9  lea     edx, [rbx+1]; TokenInformationClass
0x18000e0dc  mov     rcx, rdi; TokenHandle
0x18000e0df  call    cs:__imp_GetTokenInformation
0x18000e0e5  test    eax, eax
0x18000e0e7  jnz     loc_18000E234
0x18000e0ed  call    cs:__imp_GetLastError
0x18000e0f3  cmp     eax, 7Ah ; 'z'
0x18000e0f6  jnz     loc_18000E234
0x18000e0fc  mov     ecx, [rsp+230h+TokenInformationLength]; unsigned __int64
0x18000e100  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000e107  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000e10c  mov     rsi, rax
0x18000e10f  test    rax, rax
0x18000e112  jnz     short loc_18000E139
0x18000e114  mov     rcx, [rbp+138h]; this
0x18000e11b  mov     edi, 8007000Eh
0x18000e120  mov     r9d, edi; char *
0x18000e123  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000e12a  mov     edx, 119h; void *
0x18000e12f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e134  jmp     loc_18000E256
0x18000e139  lea     rax, [rsp+230h+TokenInformationLength]
0x18000e13e  mov     [rsp+230h+ReturnLength], rax; int
0x18000e143  mov     r9d, [rsp+230h+TokenInformationLength]; TokenInformationLength
0x18000e148  mov     r8, rsi; TokenInformation
0x18000e14b  mov     edx, 1; TokenInformationClass
0x18000e150  mov     rcx, rdi; TokenHandle
0x18000e153  call    cs:__imp_GetTokenInformation
0x18000e159  test    eax, eax
0x18000e15b  jnz     short loc_18000E184
0x18000e15d  mov     rcx, [rbp+138h]; this
0x18000e164  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000e16b  mov     edx, 11Ah; void *
0x18000e170  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000e175  mov     edi, eax
0x18000e177  mov     rcx, rsi; Block
0x18000e17a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e17f  jmp     loc_18000E24E
0x18000e184  mov     rbx, rsi
0x18000e187  mov     edx, 6Eh ; 'n'; WellKnownSidType
0x18000e18c  mov     rcx, [rbx]; pSid
0x18000e18f  call    cs:__imp_IsWellKnownSid
0x18000e195  test    eax, eax
0x18000e197  jz      loc_18000E273
0x18000e19d  mov     r12d, 1
0x18000e1a3  mov     rcx, rbx; Block
0x18000e1a6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e1ab  mov     rcx, [rsp+230h+TokenHandle]; hObject
0x18000e1b0  lea     rax, [rcx-1]
0x18000e1b4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000e1b8  ja      short loc_18000E1C0
0x18000e1ba  call    cs:__imp_CloseHandle
0x18000e1c0  xor     dil, dil
0x18000e1c3  cmp     [r14], dil
0x18000e1c6  jz      loc_18000E3E6
0x18000e1cc  cmp     r12d, 2
0x18000e1d0  jnz     loc_18000E3E6
0x18000e1d6  xor     r12d, r12d
0x18000e1d9  mov     [rsp+230h+var_200], r12b
0x18000e1de  mov     rcx, r14; this
0x18000e1e1  call    ?GetResourceAccountSid@UserContextHelpers@@AEAAJXZ; UserContextHelpers::GetResourceAccountSid(void)
0x18000e1e6  test    eax, eax
0x18000e1e8  js      loc_18000E38C
0x18000e1ee  mov     [rsp+230h+var_1D8], r12
0x18000e1f3  mov     [rbp+130h+string], r12
0x18000e1f7  lea     r9d, [r12+36h]; unsigned int
0x18000e1fc  lea     r8d, [r12+37h]; unsigned int
0x18000e201  lea     rdx, ?RuntimeClass_Microsoft_ResourceAccountManager_ResourceAccountPolicy@@3QBGB; "Microsoft.ResourceAccountManager.Resour"...
0x18000e208  lea     rcx, [rsp+230h+hstringHeader]; hstringHeader
0x18000e20d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18000e212  lea     rdx, [rsp+230h+var_1D8]
0x18000e217  mov     rcx, [rbp+130h+string]
0x18000e21b  call    ??$ActivateInstance@V?$ComPtr@UIResourceAccountPolicy@ResourceAccountManager@Microsoft@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIResourceAccountPolicy@ResourceAccountManager@Microsoft@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Microsoft::ResourceAccountManager::IResourceAccountPolicy>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Microsoft::ResourceAccountManager::IResourceAccountPolicy>>)
0x18000e220  mov     ebx, eax
0x18000e222  test    eax, eax
0x18000e224  jns     loc_18000E336
0x18000e22a  mov     edx, 0BFh
0x18000e22f  jmp     loc_18000E35A
0x18000e234  mov     rcx, [rbp+138h]; this
0x18000e23b  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000e242  mov     edx, 117h; void *
0x18000e247  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000e24c  mov     edi, eax
0x18000e24e  test    edi, edi
0x18000e250  jns     loc_18000E187
0x18000e256  mov     rcx, [rbp+138h]; this
0x18000e25d  mov     r9d, edi; char *
0x18000e260  lea     r8, aOnecoreuapBase_30; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18000e267  mov     edx, 56h ; 'V'; void *
0x18000e26c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e271  jmp     short loc_18000E2DA
0x18000e273  call    cs:__imp_RtlIsMultiSessionSku
0x18000e279  test    al, al
0x18000e27b  jnz     loc_18000E1A3
0x18000e281  cmp     [r14], r12b
0x18000e284  jz      loc_18000E1A3
0x18000e28a  mov     rcx, r14; this
0x18000e28d  call    ?GetResourceAccountSid@UserContextHelpers@@AEAAJXZ; UserContextHelpers::GetResourceAccountSid(void)
0x18000e292  test    eax, eax
0x18000e294  js      loc_18000E1A3
0x18000e29a  mov     [rsp+230h+TokenInformationLength], r12d
0x18000e29f  lea     rdx, [r14+4]
0x18000e2a3  lea     r9, [rsp+230h+TokenInformationLength]
0x18000e2a8  xor     r8d, r8d
0x18000e2ab  mov     rcx, [rsp+230h+TokenHandle]
0x18000e2b0  call    cs:__imp_CheckTokenMembershipEx
0x18000e2b6  test    eax, eax
0x18000e2b8  jnz     short loc_18000E30E
0x18000e2ba  mov     rcx, [rbp+138h]; this
0x18000e2c1  lea     r8, aOnecoreuapBase_30; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18000e2c8  lea     edx, [rax+61h]; void *
0x18000e2cb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000e2d0  mov     edi, eax
0x18000e2d2  mov     rcx, rbx; Block
0x18000e2d5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e2da  lea     rcx, [rsp+230h+TokenHandle]
0x18000e2df  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000e2e4  test    edi, edi
0x18000e2e6  jns     loc_18000E1C0
0x18000e2ec  mov     rcx, [rbp+138h]; this
0x18000e2f3  mov     r9d, edi; char *
0x18000e2f6  lea     r8, aOnecoreuapBase_30; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18000e2fd  mov     edx, 0B5h; void *
0x18000e302  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e307  mov     eax, edi
0x18000e309  jmp     loc_18000E869
0x18000e30e  cmp     [rsp+230h+TokenInformationLength], r12d
0x18000e313  jz      loc_18000E1A3
0x18000e319  mov     r12d, 2
0x18000e31f  mov     rcx, rbx; Block
0x18000e322  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e327  lea     rcx, [rsp+230h+TokenHandle]
0x18000e32c  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000e331  jmp     loc_18000E1C0
0x18000e336  mov     rcx, [rsp+230h+var_1D8]
0x18000e33b  mov     rax, [rcx]
0x18000e33e  lea     r8, [rsp+230h+var_200]
0x18000e343  mov     rdx, r13
0x18000e346  mov     rax, [rax+30h]
0x18000e34a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e34f  mov     ebx, eax
0x18000e351  test    eax, eax
0x18000e353  jns     short loc_18000E382
0x18000e355  mov     edx, 0C0h; void *
0x18000e35a  mov     r9d, eax; char *
0x18000e35d  lea     r8, aOnecoreuapBase_30; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18000e364  mov     rcx, [rbp+138h]; this
0x18000e36b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e370  nop
0x18000e371  lea     rcx, [rsp+230h+var_1D8]
0x18000e376  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18000e37b  mov     eax, ebx
0x18000e37d  jmp     loc_18000E869
0x18000e382  lea     rcx, [rsp+230h+var_1D8]
0x18000e387  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18000e38c  cmp     [rsp+230h+var_200], r12b
0x18000e391  jnz     short loc_18000E3E9
0x18000e393  xor     edx, edx; length
0x18000e395  mov     rcx, r13; string
0x18000e398  call    cs:__imp_WindowsGetStringRawBuffer
0x18000e39e  mov     rbx, rax
0x18000e3a1  call    ?IsEnabled@AAMTraceProvider@@SA_NE_K@Z; AAMTraceProvider::IsEnabled(uchar,unsigned __int64)
0x18000e3a6  test    al, al
0x18000e3a8  jz      short loc_18000E3C7
0x18000e3aa  call    ?Instance@AAMTraceProvider@@KAPEAV1@XZ; AAMTraceProvider::Instance(void)
0x18000e3af  mov     r9d, 2; unsigned int
0x18000e3b5  mov     r8, rbx; unsigned __int16 *
0x18000e3b8  mov     rsi, [rsp+230h+var_1E0]
0x18000e3bd  mov     rdx, rsi; unsigned __int64
0x18000e3c0  call    ?BlockUserForActivation_@AAMTraceProvider@@QEAAX_KPEBGK@Z; AAMTraceProvider::BlockUserForActivation_(unsigned __int64,ushort const *,ulong)
0x18000e3c5  jmp     short loc_18000E3CC
0x18000e3c7  mov     rsi, [rsp+230h+var_1E0]
0x18000e3cc  mov     dil, 1
0x18000e3cf  mov     [r15], r12
0x18000e3d2  xor     r8d, r8d
0x18000e3d5  mov     dl, dil
0x18000e3d8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UserSelectionForRA@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UserSelectionForRA@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UserSelectionForRA> `wil::Feature<__WilFeatureTraits_Feature_UserSelectionForRA>::GetImpl(void)'::`2'::impl
0x18000e3df  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_UserSelectionForRA@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UserSelectionForRA>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18000e3e4  jmp     short loc_18000E3EE
0x18000e3e6  xor     r12d, r12d
0x18000e3e9  mov     rsi, [rsp+230h+var_1E0]
0x18000e3ee  mov     rax, cs:Feature_ShellUserSelection__descriptor
0x18000e3f5  mov     ecx, [rax]
0x18000e3f7  test    cl, 4
0x18000e3fa  jnz     short loc_18000E406
0x18000e3fc  lea     rdx, [rsp+230h+var_1C8]
0x18000e401  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ShellUserSelection@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShellUserSelection>::GetCachedFeatureEnabledState(void)
0x18000e406  cmp     [r15], r12
0x18000e409  jz      short loc_18000E416
0x18000e40b  cmp     [rsp+230h+var_1E8], r12b
0x18000e410  jz      loc_18000E867
0x18000e416  xor     edx, edx; length
0x18000e418  mov     rcx, r13; string
0x18000e41b  call    cs:__imp_WindowsGetStringRawBuffer
0x18000e421  mov     rbx, rax
0x18000e424  mov     [rbp+130h+var_188], r12d
0x18000e428  mov     [rbp+130h+var_184], r12b
0x18000e42c  mov     [rbp+130h+var_148], r12b
0x18000e430  mov     [rbp+130h+var_160], r12d
0x18000e434  lea     rax, aUserselectionp; "UserSelectionPromptActivity"
0x18000e43b  mov     [rbp+130h+var_158], rax
0x18000e43f  mov     [rbp+130h+var_150], r12
0x18000e443  mov     [rbp+130h+var_140], r12d
0x18000e447  xorps   xmm0, xmm0
0x18000e44a  movdqa  [rbp+130h+var_A0], xmm0
0x18000e452  xor     edx, edx; Val
0x18000e454  mov     r8d, 98h; Size
0x18000e45a  lea     rcx, [rbp+130h+var_138]; void *
0x18000e45e  call    memset_0
0x18000e463  mov     [rbp+130h+var_90], 1
0x18000e46d  xor     eax, eax
0x18000e46f  mov     [rbp+130h+var_88], rax
0x18000e476  lea     rax, [rbp+130h+var_188]
0x18000e47a  mov     [rbp+130h+var_80], rax
0x18000e481  mov     [rbp+130h+var_78], r12
0x18000e488  mov     [rbp+130h+var_70], r12
0x18000e48f  lea     rax, [rbp+130h+var_190]
0x18000e493  mov     [rbp+130h+var_68], rax
0x18000e49a  mov     [rbp+130h+var_60], r12
0x18000e4a1  mov     [rbp+130h+var_58], r12d
0x18000e4a8  lea     rax, [rbp+130h+var_160]
0x18000e4ac  mov     [rbp+130h+var_50], rax
0x18000e4b3  mov     [rbp+130h+var_48], r12b
0x18000e4ba  lea     r14, ??_7UserSelectionPromptActivity@AAMTraceProvider@@6B@; const AAMTraceProvider::UserSelectionPromptActivity::`vftable'
0x18000e4c1  mov     [rbp+130h+var_190], r14
0x18000e4c5  mov     r9, [r15]; unsigned __int64
0x18000e4c8  mov     r8, rbx; unsigned __int16 *
0x18000e4cb  mov     rdx, rsi; unsigned __int64
0x18000e4ce  lea     rcx, [rbp+130h+var_190]; this
0x18000e4d2  call    ?StartActivity@UserSelectionPromptActivity@AAMTraceProvider@@QEAAX_KPEBG0@Z; AAMTraceProvider::UserSelectionPromptActivity::StartActivity(unsigned __int64,ushort const *,unsigned __int64)
0x18000e4d7  nop
0x18000e4d8  mov     [rsp+230h+var_1E0], r12
0x18000e4dd  mov     [rbp+130h+string], r12
0x18000e4e1  lea     r9, [rbp+130h+string]; string
0x18000e4e5  lea     r8, [rsp+230h+hstringHeader]; hstringHeader
0x18000e4ea  mov     edx, 31h ; '1'; length
0x18000e4ef  lea     rcx, aWindowsInterna_1; "Windows.Internal.PlatformExtensions.Use"...
0x18000e4f6  call    cs:__imp_WindowsCreateStringReference
0x18000e4fc  test    eax, eax
0x18000e4fe  jns     short loc_18000E513
0x18000e500  xor     r9d, r9d; lpArguments
0x18000e503  xor     r8d, r8d; nNumberOfArguments
0x18000e506  lea     edx, [r9+1]; dwExceptionFlags
0x18000e50a  mov     ecx, eax; dwExceptionCode
0x18000e50c  call    cs:__imp_RaiseException
0x18000e512  int     3; Trap to Debugger
0x18000e513  mov     edx, r12d
0x18000e516  lea     r9, [rsp+230h+var_1E0]
0x18000e51b  mov     rcx, [rbp+130h+string]
0x18000e51f  call    ?TryActivateContractExtensionInternal@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@UWindowId@WindowManagement@ApplicationModel@34@AEBU_GUID@@PEAPEAX@Z; Windows::Internal::PlatformExtensions::Details::TryActivateContractExtensionInternal(HSTRING__ *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,_GUID const &,void * *)
0x18000e524  mov     ebx, eax
0x18000e526  test    eax, eax
0x18000e528  jns     short loc_18000E598
  ... truncated ...
```
