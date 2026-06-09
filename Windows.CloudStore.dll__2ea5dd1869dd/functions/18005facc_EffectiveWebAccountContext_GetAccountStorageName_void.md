# EffectiveWebAccountContext::GetAccountStorageName(void)

- ea: `0x18005facc`
- end: `0x180060104`
- name: `?GetAccountStorageName@EffectiveWebAccountContext@@QEBAPEBGXZ`
- size: `1592`
- prototype: `const unsigned __int16 *__fastcall(EffectiveWebAccountContext *__hidden this)`
- caller_count: `2`
- callee_count: `22`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180010fb0`
- `0x18005f914`

## callees

- `0x18000dfe4`
- `0x18000e828`
- `0x18000e878`
- `0x18000e8d0`
- `0x18000e904`
- `0x18000f8dc`
- `0x180016cf4`
- `0x180032964`
- `0x180032a50`
- `0x18003f11c`
- `0x180042d28`
- `0x180042ec0`
- `0x1800433b0`
- `0x180047904`
- `0x18005facc`
- `0x180062040`
- `0x180065614`
- `0x18009104c`
- `0x1800f9bbc`
- `0x18010d418`
- `0x1801201a0`
- `0x180208010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005fd04`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005ff7c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005fd04`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005ff7c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18005ffc3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18005ffc3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005fb05`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005fb05`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005fbf8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005fbf8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005fb2b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005fc73`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005fb2b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005fc73`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005fc3c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005fc3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005fbbc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005fbbc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005fb1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005fbdd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005fc2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005fb1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005fbdd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005fc2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005fc65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005fc65`

## string_xrefs

- `0x18005fc91`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.cpp`
- `0x18005fe8a`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.cpp`
- `0x18005fe9f`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.cpp`
- `0x18005feb4`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.cpp`
- `0x18005fec9`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.cpp`
- `0x18005fede`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.cpp`
- `0x18005fef3`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.cpp`
- `0x18005ffe3`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.cpp`
- `0x180060095`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.cpp`
- `0x1800600aa`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.cpp`
- `0x1800600bf`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.cpp`
- `0x1800600d7`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.cpp`
- `0x1800600f2`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=25
PCWSTR __fastcall EffectiveWebAccountContext::GetAccountStorageName(EffectiveWebAccountContext *this)
{
  RTL_SRWLOCK *v2; // rbx
  HSTRING v3; // rcx
  PCWSTR StringRawBuffer; // rdi
  struct Windows::Security::Credentials::IWebAccount *WebAccount; // rbx
  HRESULT v7; // eax
  RTL_SRWLOCK *v8; // rsi
  HSTRING *v9; // rcx
  __int64 **v10; // rax
  __int64 *v11; // rcx
  __int64 v12; // rax
  int v13; // eax
  HANDLE CurrentProcess; // rax
  bool *v15; // r8
  int IsProcessAppContainer; // eax
  __int64 v17; // rax
  __int64 **v18; // rax
  __int64 *v19; // rcx
  __int64 v20; // rax
  int v21; // eax
  __int64 v22; // rax
  int v23; // eax
  __int64 v24; // rsi
  __int64 (__fastcall *v25)(__int64, __int64, PVOID, _QWORD *); // r15
  _QWORD *v26; // r14
  const WCHAR *v27; // rax
  HSTRING_HEADER *v28; // rax
  int v29; // eax
  __int64 **v30; // rax
  __int64 *v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  __int64 *v34; // rcx
  HANDLE v35; // rax
  unsigned __int16 **v36; // r8
  int PackageFamilyNameFromProcess; // eax
  const WCHAR *v38; // rcx
  __int64 **v39; // rax
  __int64 *v40; // rcx
  __int64 v41; // rax
  int v42; // eax
  CloudStoreUtilities *v43; // rcx
  int v44; // eax
  __int64 v45; // rax
  int v46; // eax
  HSTRING *bIgnoreCase; // [rsp+20h] [rbp-59h]
  _BYTE v48[8]; // [rsp+30h] [rbp-49h] BYREF
  __int64 *p_lpString2; // [rsp+38h] [rbp-41h] BYREF
  HSTRING string; // [rsp+40h] [rbp-39h] BYREF
  char v51; // [rsp+48h] [rbp-31h]
  HSTRING v52; // [rsp+50h] [rbp-29h] BYREF
  LPCWCH lpString2; // [rsp+58h] [rbp-21h] BYREF
  __int64 v54; // [rsp+60h] [rbp-19h] BYREF
  _QWORD *v55; // [rsp+68h] [rbp-11h] BYREF
  __int64 v56; // [rsp+70h] [rbp-9h] BYREF
  const WCHAR *v57; // [rsp+78h] [rbp-1h] BYREF
  struct Windows::Security::Credentials::IWebAccount *v58; // [rsp+80h] [rbp+7h] BYREF
  HSTRING_HEADER v59; // [rsp+88h] [rbp+Fh] BYREF
  __int64 v60; // [rsp+A0h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v2 = (RTL_SRWLOCK *)*((_QWORD *)this + 8);
  AcquireSRWLockShared(v2);
  v3 = *(HSTRING *)(*((_QWORD *)this + 8) + 32LL);
  if ( v3 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(v3, 0);
    if ( v2 )
      ReleaseSRWLockShared(v2);
    return StringRawBuffer;
  }
  if ( v2 )
    ReleaseSRWLockShared(v2);
  v52 = 0;
  if ( EffectiveWebAccountContext::GetIsDefault(this) )
    WebAccount = 0;
  else
    WebAccount = EffectiveWebAccountContext::GetWebAccount(this);
  v58 = WebAccount;
  if ( !WebAccount )
  {
    p_lpString2 = (__int64 *)&v52;
    string = 0;
    v51 = 1;
    v7 = WindowsCreateString(L"DefaultAccount", 0xEu, &string);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1B9,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\effectivecontext.cpp",
        (const char *)(unsigned int)v7,
        (int)bIgnoreCase);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(&p_lpString2);
    goto LABEL_13;
  }
  (*(void (__fastcall **)(struct Windows::Security::Credentials::IWebAccount *))(*(_QWORD *)WebAccount + 8LL))(WebAccount);
  v10 = (__int64 **)wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::query<Windows::Security::Credentials::IWebAccount2>(
                      &v58,
                      &v56);
  v11 = *v10;
  v12 = **v10;
  p_lpString2 = (__int64 *)&v52;
  string = 0;
  v51 = 1;
  v13 = (*(__int64 (__fastcall **)(__int64 *, HSTRING *))(v12 + 48))(v11, &string);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x171,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\effectivecontext.cpp",
      (const char *)(unsigned int)v13,
      (int)bIgnoreCase);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(&p_lpString2);
  if ( v56 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
  v48[0] = 0;
  CurrentProcess = GetCurrentProcess();
  IsProcessAppContainer = CallerIdentity::IsProcessAppContainer(CurrentProcess, v48, v15);
  if ( IsProcessAppContainer < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x174,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\effectivecontext.cpp",
      (const char *)(unsigned int)IsProcessAppContainer,
      (int)bIgnoreCase);
  v17 = *((_QWORD *)this + 6);
  if ( v48[0] )
  {
    if ( v17 )
    {
      lpString2 = 0;
      p_lpString2 = (__int64 *)&lpString2;
      string = 0;
      v51 = 1;
      v35 = GetCurrentProcess();
      PackageFamilyNameFromProcess = CallerIdentity::GetPackageFamilyNameFromProcess(v35, &string, v36);
      if ( PackageFamilyNameFromProcess < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x180,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\effectivecontext.cpp",
          (const char *)(unsigned int)PackageFamilyNameFromProcess,
          (int)bIgnoreCase);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_lpString2);
      v38 = (const WCHAR *)((char *)this + 32);
      if ( *((_QWORD *)this + 7) > 7u )
        v38 = *(const WCHAR **)v38;
      if ( CompareStringOrdinal(v38, -1, lpString2, -1, 1) != 2 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x181,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\effectivecontext.cpp",
          (const char *)0x8007109CLL,
          (int)bIgnoreCase);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpString2);
      goto LABEL_13;
    }
    v54 = 0;
    v39 = (__int64 **)wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::query<Windows::Security::Credentials::IWebAccount2>(
                        &v58,
                        &v56);
    v40 = *v39;
    v41 = **v39;
    p_lpString2 = &v54;
    string = 0;
    v51 = 1;
    v42 = (*(__int64 (__fastcall **)(__int64 *, HSTRING *))(v41 + 48))(v40, &string);
    if ( v42 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x18A,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\effectivecontext.cpp",
        (const char *)(unsigned int)v42,
        (int)bIgnoreCase);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(&p_lpString2);
    wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v56);
    v44 = CloudStoreUtilities::VerifyStoreAccessPermissions(v43);
    if ( v44 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x18F,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\effectivecontext.cpp",
        (const char *)(unsigned int)v44,
        (int)bIgnoreCase);
    EffectiveUserContext::ActivateInstance<Windows::Internal::Storage::Cloud::Broker::ICloudStoreBroker>(
      (__int64)this,
      (__int64)&v55);
    v45 = *v55;
    p_lpString2 = (__int64 *)&v52;
    string = 0;
    v51 = 1;
    v46 = (*(__int64 (__fastcall **)(_QWORD *, struct Windows::Security::Credentials::IWebAccount *, HSTRING *))(v45 + 48))(
            v55,
            WebAccount,
            &string);
    if ( v46 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x191,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\effectivecontext.cpp",
        (const char *)(unsigned int)v46,
        (int)bIgnoreCase);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(&p_lpString2);
    wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v55);
    v34 = &v54;
    goto LABEL_45;
  }
  if ( v17 )
  {
    v55 = 0;
    v18 = (__int64 **)wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::query<Windows::Security::Credentials::IWebAccount2>(
                        &v58,
                        &v57);
    v19 = *v18;
    v20 = **v18;
    p_lpString2 = (__int64 *)&v55;
    string = 0;
    v51 = 1;
    v21 = (*(__int64 (__fastcall **)(__int64 *, HSTRING *))(v20 + 48))(v19, &string);
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1A0,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\effectivecontext.cpp",
        (const char *)(unsigned int)v21,
        (int)bIgnoreCase);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(&p_lpString2);
    wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v57);
    v54 = 0;
    v22 = *(_QWORD *)WebAccount;
    p_lpString2 = &v54;
    string = 0;
    v51 = 1;
    v23 = (*(__int64 (__fastcall **)(struct Windows::Security::Credentials::IWebAccount *, HSTRING *))(v22 + 48))(
            WebAccount,
            &string);
    if ( v23 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1A3,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\effectivecontext.cpp",
        (const char *)(unsigned int)v23,
        (int)bIgnoreCase);
    wil::details::out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>(&p_lpString2);
    EffectiveWebAccountContext::GetTokenBrokerInternalStatics(&v56);
    lpString2 = 0;
    v24 = v56;
    v25 = *(__int64 (__fastcall **)(__int64, __int64, PVOID, _QWORD *))(*(_QWORD *)v56 + 80LL);
    p_lpString2 = (__int64 *)&lpString2;
    string = 0;
    v51 = 1;
    v26 = v55;
    v27 = (const WCHAR *)((char *)this + 32);
    if ( *((_QWORD *)this + 7) > 7u )
      v27 = *(const WCHAR **)v27;
    v57 = v27;
    v28 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v59, &v57);
    bIgnoreCase = &string;
    v29 = v25(v24, v54, v28[1].Reserved.Reserved1, v26);
    if ( v29 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1A8,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\effectivecontext.cpp",
        (const char *)(unsigned int)v29,
        (int)&string);
    v60 = 0;
    wil::details::out_param_t<wil::com_ptr_t<IMarshal,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<IMarshal,wil::err_exception_policy>>(&p_lpString2);
    v30 = (__int64 **)wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::query<Windows::Security::Credentials::IWebAccount2>(
                        &lpString2,
                        &v57);
    v31 = *v30;
    v32 = **v30;
    p_lpString2 = (__int64 *)&v52;
    string = 0;
    v51 = 1;
    v33 = (*(__int64 (__fastcall **)(__int64 *, HSTRING *))(v32 + 48))(v31, &string);
    if ( v33 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1A9,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\effectivecontext.cpp",
        (const char *)(unsigned int)v33,
        (int)&string);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(&p_lpString2);
    wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v57);
    wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&lpString2);
    wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v56);
    wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v54);
    v34 = (__int64 *)&v55;
LABEL_45:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(v34);
  }
LABEL_13:
  if ( !*WindowsGetStringRawBuffer(v52, 0) )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x1BD,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\effectivecontext.cpp",
      (const char *)0x80070005LL,
      (int)bIgnoreCase);
  v8 = (RTL_SRWLOCK *)*((_QWORD *)this + 8);
  AcquireSRWLockExclusive(v8);
  v9 = (HSTRING *)(*((_QWORD *)this + 8) + 32LL);
  if ( !*v9 && v9 != &v52 )
  {
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
      v9,
      v52);
    v52 = 0;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)(*((_QWORD *)this + 8) + 32LL), 0);
  if ( v8 )
    ReleaseSRWLockExclusive(v8);
  if ( WebAccount )
    (*(void (__fastcall **)(struct Windows::Security::Credentials::IWebAccount *))(*(_QWORD *)WebAccount + 16LL))(WebAccount);
  if ( v52 )
    WindowsDeleteString(v52);
  return StringRawBuffer;
}

```

## disassembly

```asm
0x18005facc  mov     [rsp-8+arg_8], rbx
0x18005fad1  mov     [rsp-8+arg_10], rsi
0x18005fad6  push    rbp
0x18005fad7  push    rdi
0x18005fad8  push    r12
0x18005fada  push    r14
0x18005fadc  push    r15
0x18005fade  lea     rbp, [rsp-37h]
0x18005fae3  sub     rsp, 0B0h
0x18005faea  mov     rax, cs:__security_cookie
0x18005faf1  xor     rax, rsp
0x18005faf4  mov     [rbp+57h+var_28], rax
0x18005faf8  mov     rdi, rcx
0x18005fafb  xor     r12d, r12d
0x18005fafe  mov     rbx, [rcx+40h]
0x18005fb02  mov     rcx, rbx; SRWLock
0x18005fb05  call    cs:__imp_AcquireSRWLockShared
0x18005fb0b  mov     rax, [rdi+40h]
0x18005fb0f  mov     rcx, [rax+20h]; string
0x18005fb13  test    rcx, rcx
0x18005fb16  jz      short loc_18005FB5C
0x18005fb18  xor     edx, edx; length
0x18005fb1a  call    cs:__imp_WindowsGetStringRawBuffer
0x18005fb20  mov     rdi, rax
0x18005fb23  test    rbx, rbx
0x18005fb26  jz      short loc_18005FB31
0x18005fb28  mov     rcx, rbx; SRWLock
0x18005fb2b  call    cs:__imp_ReleaseSRWLockShared
0x18005fb31  mov     rax, rdi
0x18005fb34  mov     rcx, [rbp+57h+var_28]
0x18005fb38  xor     rcx, rsp; StackCookie
0x18005fb3b  call    __security_check_cookie
0x18005fb40  lea     r11, [rsp+0D0h+var_20]
0x18005fb48  mov     rbx, [r11+38h]
0x18005fb4c  mov     rsi, [r11+40h]
0x18005fb50  mov     rsp, r11
0x18005fb53  pop     r15
0x18005fb55  pop     r14
0x18005fb57  pop     r12
0x18005fb59  pop     rdi
0x18005fb5a  pop     rbp
0x18005fb5b  retn
0x18005fb5c  test    rbx, rbx
0x18005fb5f  jnz     loc_18005FC70
0x18005fb65  mov     [rbp+57h+var_80], r12
0x18005fb69  mov     rcx, rdi; this
0x18005fb6c  call    ?GetIsDefault@EffectiveWebAccountContext@@QEBA_NXZ; EffectiveWebAccountContext::GetIsDefault(void)
0x18005fb71  test    al, al
0x18005fb73  jz      loc_18005FC7E
0x18005fb79  mov     rbx, r12
0x18005fb7c  mov     [rbp+57h+var_50], rbx
0x18005fb80  test    rbx, rbx
0x18005fb83  jz      short loc_18005FB95
0x18005fb85  mov     rcx, [rbx]
0x18005fb88  mov     rax, [rcx+8]
0x18005fb8c  mov     rcx, rbx
0x18005fb8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fb94  nop
0x18005fb95  test    rbx, rbx
0x18005fb98  jnz     loc_18005FCA3
0x18005fb9e  lea     rax, [rbp+57h+var_80]
0x18005fba2  mov     [rbp+57h+var_98], rax
0x18005fba6  mov     [rbp+57h+string], r12
0x18005fbaa  mov     [rbp+57h+var_88], 1
0x18005fbae  lea     r8, [rbp+57h+string]; string
0x18005fbb2  lea     edx, [rbx+0Eh]; length
0x18005fbb5  lea     rcx, String1; "DefaultAccount"
0x18005fbbc  call    cs:__imp_WindowsCreateString
0x18005fbc2  mov     rcx, [rbp+5Fh]; this
0x18005fbc6  test    eax, eax
0x18005fbc8  js      loc_18005FC8E
0x18005fbce  lea     rcx, [rbp+57h+var_98]
0x18005fbd2  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(void)
0x18005fbd7  xor     edx, edx; length
0x18005fbd9  mov     rcx, [rbp+57h+var_80]; string
0x18005fbdd  call    cs:__imp_WindowsGetStringRawBuffer
0x18005fbe3  mov     rcx, [rbp+5Fh]; this
0x18005fbe7  cmp     [rax], r12w
0x18005fbeb  jz      loc_1800600EC
0x18005fbf1  mov     rsi, [rdi+40h]
0x18005fbf5  mov     rcx, rsi; SRWLock
0x18005fbf8  call    cs:__imp_AcquireSRWLockExclusive
0x18005fbfe  mov     rcx, [rdi+40h]
0x18005fc02  add     rcx, 20h ; ' '
0x18005fc06  cmp     [rcx], r12
0x18005fc09  jnz     short loc_18005FC21
0x18005fc0b  lea     rax, [rbp+57h+var_80]
0x18005fc0f  cmp     rcx, rax
0x18005fc12  jz      short loc_18005FC21
0x18005fc14  mov     rdx, [rbp+57h+var_80]
0x18005fc18  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x18005fc1d  mov     [rbp+57h+var_80], r12
0x18005fc21  mov     rcx, [rdi+40h]
0x18005fc25  xor     edx, edx; length
0x18005fc27  mov     rcx, [rcx+20h]; string
0x18005fc2b  call    cs:__imp_WindowsGetStringRawBuffer
0x18005fc31  mov     rdi, rax
0x18005fc34  test    rsi, rsi
0x18005fc37  jz      short loc_18005FC43
0x18005fc39  mov     rcx, rsi; SRWLock
0x18005fc3c  call    cs:__imp_ReleaseSRWLockExclusive
0x18005fc42  nop
0x18005fc43  test    rbx, rbx
0x18005fc46  jz      short loc_18005FC58
0x18005fc48  mov     rcx, [rbx]
0x18005fc4b  mov     rax, [rcx+10h]
0x18005fc4f  mov     rcx, rbx
0x18005fc52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fc57  nop
0x18005fc58  mov     rcx, [rbp+57h+var_80]; string
0x18005fc5c  test    rcx, rcx
0x18005fc5f  jz      loc_18005FB31
0x18005fc65  call    cs:__imp_WindowsDeleteString
0x18005fc6b  jmp     loc_18005FB31
0x18005fc70  mov     rcx, rbx; SRWLock
0x18005fc73  call    cs:__imp_ReleaseSRWLockShared
0x18005fc79  jmp     loc_18005FB65
0x18005fc7e  mov     rcx, rdi; this
0x18005fc81  call    ?GetWebAccount@EffectiveWebAccountContext@@QEBAPEAUIWebAccount@Credentials@Security@Windows@@XZ; EffectiveWebAccountContext::GetWebAccount(void)
0x18005fc86  mov     rbx, rax
0x18005fc89  jmp     loc_18005FB7C
0x18005fc8e  mov     r9d, eax; char *
0x18005fc91  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18005fc98  mov     edx, 1B9h; void *
0x18005fc9d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005fca3  lea     rdx, [rbp+57h+var_60]
0x18005fca7  lea     rcx, [rbp+57h+var_50]
0x18005fcab  call    ??$query@UIWebAccount2@Credentials@Security@Windows@@@?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIWebAccount2@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::query<Windows::Security::Credentials::IWebAccount2>(void)
0x18005fcb0  nop
0x18005fcb1  mov     rcx, [rax]
0x18005fcb4  mov     rax, [rcx]
0x18005fcb7  lea     rdx, [rbp+57h+var_80]
0x18005fcbb  mov     [rbp+57h+var_98], rdx
0x18005fcbf  mov     [rbp+57h+string], r12
0x18005fcc3  mov     [rbp+57h+var_88], 1
0x18005fcc7  lea     rdx, [rbp+57h+string]
0x18005fccb  mov     rax, [rax+30h]
0x18005fccf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fcd4  mov     rcx, [rbp+5Fh]; this
0x18005fcd8  test    eax, eax
0x18005fcda  js      loc_18005FE9C
0x18005fce0  lea     rcx, [rbp+57h+var_98]
0x18005fce4  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(void)
0x18005fce9  nop
0x18005fcea  mov     rcx, [rbp+57h+var_60]
0x18005fcee  test    rcx, rcx
0x18005fcf1  jz      short loc_18005FD00
0x18005fcf3  mov     rax, [rcx]
0x18005fcf6  mov     rax, [rax+10h]
0x18005fcfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fcff  nop
0x18005fd00  mov     [rbp+57h+var_A0], r12b
0x18005fd04  call    cs:__imp_GetCurrentProcess
0x18005fd0a  mov     rcx, rax; ProcessHandle
0x18005fd0d  lea     rdx, [rbp+57h+var_A0]; void *
0x18005fd11  call    ?IsProcessAppContainer@CallerIdentity@@YAJPEAXPEA_N@Z; CallerIdentity::IsProcessAppContainer(void *,bool *)
0x18005fd16  mov     rcx, [rbp+5Fh]; this
0x18005fd1a  test    eax, eax
0x18005fd1c  js      loc_18005FEB1
0x18005fd22  mov     rax, [rdi+30h]
0x18005fd26  cmp     [rbp+57h+var_A0], r12b
0x18005fd2a  jnz     loc_18005FF5F
0x18005fd30  test    rax, rax
0x18005fd33  jz      loc_18005FBD7
0x18005fd39  mov     [rbp+57h+var_68], r12
0x18005fd3d  lea     rdx, [rbp+57h+var_58]
0x18005fd41  lea     rcx, [rbp+57h+var_50]
0x18005fd45  call    ??$query@UIWebAccount2@Credentials@Security@Windows@@@?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIWebAccount2@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::query<Windows::Security::Credentials::IWebAccount2>(void)
0x18005fd4a  nop
0x18005fd4b  mov     rcx, [rax]
0x18005fd4e  mov     rax, [rcx]
0x18005fd51  lea     rdx, [rbp+57h+var_68]
0x18005fd55  mov     [rbp+57h+var_98], rdx
0x18005fd59  mov     [rbp+57h+string], r12
0x18005fd5d  mov     [rbp+57h+var_88], 1
0x18005fd61  lea     rdx, [rbp+57h+string]
0x18005fd65  mov     rax, [rax+30h]
0x18005fd69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fd6e  mov     rcx, [rbp+5Fh]; this
0x18005fd72  test    eax, eax
0x18005fd74  js      loc_18005FEC6
0x18005fd7a  lea     rcx, [rbp+57h+var_98]
0x18005fd7e  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(void)
0x18005fd83  nop
0x18005fd84  lea     rcx, [rbp+57h+var_58]
0x18005fd88  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x18005fd8d  mov     [rbp+57h+var_70], r12
0x18005fd91  mov     rax, [rbx]
0x18005fd94  lea     rcx, [rbp+57h+var_70]
0x18005fd98  mov     [rbp+57h+var_98], rcx
0x18005fd9c  mov     [rbp+57h+string], r12
0x18005fda0  mov     [rbp+57h+var_88], 1
0x18005fda4  lea     rdx, [rbp+57h+string]
0x18005fda8  mov     rcx, rbx
0x18005fdab  mov     rax, [rax+30h]
0x18005fdaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fdb4  mov     rcx, [rbp+5Fh]; this
0x18005fdb8  test    eax, eax
0x18005fdba  js      loc_18005FEDB
0x18005fdc0  lea     rcx, [rbp+57h+var_98]
0x18005fdc4  call    ??1?$out_param_t@V?$com_ptr_t@U?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>(void)
0x18005fdc9  lea     rcx, [rbp+57h+var_60]
0x18005fdcd  call    ?GetTokenBrokerInternalStatics@EffectiveWebAccountContext@@SA?AV?$com_ptr_t@UITokenBrokerInternalStatics@Web@Authentication@Security@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@XZ; EffectiveWebAccountContext::GetTokenBrokerInternalStatics(void)
0x18005fdd2  nop
0x18005fdd3  mov     [rbp+57h+lpString2], r12
0x18005fdd7  mov     rsi, [rbp+57h+var_60]
0x18005fddb  mov     rax, [rsi]
0x18005fdde  mov     r15, [rax+50h]
0x18005fde2  lea     rax, [rbp+57h+lpString2]
0x18005fde6  mov     [rbp+57h+var_98], rax
0x18005fdea  mov     [rbp+57h+string], r12
0x18005fdee  mov     [rbp+57h+var_88], 1
0x18005fdf2  mov     r14, [rbp+57h+var_68]
0x18005fdf6  lea     rax, [rdi+20h]
0x18005fdfa  cmp     qword ptr [rax+18h], 7
0x18005fdff  jbe     short loc_18005FE04
0x18005fe01  mov     rax, [rax]
0x18005fe04  mov     [rbp+57h+var_58], rax
0x18005fe08  lea     rdx, [rbp+57h+var_58]
0x18005fe0c  lea     rcx, [rbp+57h+var_48]
0x18005fe10  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18005fe15  nop
0x18005fe16  lea     rcx, [rbp+57h+string]
0x18005fe1a  mov     qword ptr [rsp+0D0h+bIgnoreCase], rcx; int
0x18005fe1f  mov     r9, r14
0x18005fe22  mov     r8, [rax+18h]
0x18005fe26  mov     rdx, [rbp+57h+var_70]
0x18005fe2a  mov     rcx, rsi
0x18005fe2d  mov     rax, r15
0x18005fe30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fe35  mov     rcx, [rbp+5Fh]; this
0x18005fe39  test    eax, eax
0x18005fe3b  js      loc_18005FEF0
0x18005fe41  mov     [rbp+57h+var_30], r12
0x18005fe45  lea     rcx, [rbp+57h+var_98]
0x18005fe49  call    ??1?$out_param_t@V?$com_ptr_t@UIMarshal@@Uerr_exception_policy@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::com_ptr_t<IMarshal,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<IMarshal,wil::err_exception_policy>>(void)
0x18005fe4e  lea     rdx, [rbp+57h+var_58]
0x18005fe52  lea     rcx, [rbp+57h+lpString2]
0x18005fe56  call    ??$query@UIWebAccount2@Credentials@Security@Windows@@@?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIWebAccount2@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::query<Windows::Security::Credentials::IWebAccount2>(void)
0x18005fe5b  nop
0x18005fe5c  mov     rcx, [rax]
0x18005fe5f  mov     rax, [rcx]
0x18005fe62  lea     rdx, [rbp+57h+var_80]
0x18005fe66  mov     [rbp+57h+var_98], rdx
0x18005fe6a  mov     [rbp+57h+string], r12
0x18005fe6e  mov     [rbp+57h+var_88], 1
0x18005fe72  lea     rdx, [rbp+57h+string]
0x18005fe76  mov     rax, [rax+30h]
0x18005fe7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fe7f  mov     rcx, [rbp+5Fh]; this
0x18005fe83  test    eax, eax
0x18005fe85  jns     short loc_18005FF05
0x18005fe87  mov     r9d, eax; char *
0x18005fe8a  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18005fe91  mov     edx, 1A9h; void *
0x18005fe96  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005fe9c  mov     r9d, eax; char *
0x18005fe9f  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18005fea6  mov     edx, 171h; void *
0x18005feab  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005feb1  mov     r9d, eax; char *
0x18005feb4  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18005febb  mov     edx, 174h; void *
0x18005fec0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005fec6  mov     r9d, eax; char *
0x18005fec9  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18005fed0  mov     edx, 1A0h; void *
0x18005fed5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005fedb  mov     r9d, eax; char *
0x18005fede  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18005fee5  mov     edx, 1A3h; void *
0x18005feea  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005fef0  mov     r9d, eax; char *
0x18005fef3  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\cloudstore\\common\\"...
0x18005fefa  mov     edx, 1A8h; void *
0x18005feff  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005ff05  lea     rcx, [rbp+57h+var_98]
0x18005ff09  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(void)
0x18005ff0e  nop
0x18005ff0f  lea     rcx, [rbp+57h+var_58]
0x18005ff13  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x18005ff18  nop
0x18005ff19  lea     rcx, [rbp+57h+lpString2]
0x18005ff1d  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x18005ff22  nop
0x18005ff23  lea     rcx, [rbp+57h+var_60]
0x18005ff27  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x18005ff2c  nop
0x18005ff2d  lea     rcx, [rbp+57h+var_70]
0x18005ff31  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x18005ff36  nop
0x18005ff37  lea     rcx, [rbp+57h+var_68]
0x18005ff3b  jmp     short loc_18005FF55
0x18005ff3d  lea     rcx, [rbp+57h+var_98]
0x18005ff41  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(void)
0x18005ff46  nop
0x18005ff47  lea     rcx, [rbp+57h+var_68]
0x18005ff4b  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x18005ff50  nop
0x18005ff51  lea     rcx, [rbp+57h+var_70]
  ... truncated ...
```
