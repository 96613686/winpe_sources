# BitsHelper::HandleError(IBackgroundCopyJob *)

- ea: `0x1400100e0`
- end: `0x140010ab9`
- name: `?HandleError@BitsHelper@@AEAAJPEAUIBackgroundCopyJob@@@Z`
- size: `2521`
- prototype: `__int64 __fastcall(BitsHelper *__hidden this, struct IBackgroundCopyJob *)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140010ac0`

## callees

- `0x140002f40`
- `0x140005320`
- `0x140005cac`
- `0x140006150`
- `0x14000a49c`
- `0x14000a4bc`
- `0x14000df28`
- `0x14000f5b0`
- `0x14000fa20`
- `0x14000fa44`
- `0x14000ff7c`
- `0x1400100e0`
- `0x1400115ec`
- `0x140011674`
- `0x1400136f0`
- `0x140013d10`
- `0x140013f5c`
- `0x1400184b4`
- `0x14001a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1400106e8`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1400106e8`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x140010947`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x140010947`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1400103fd`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1400103fd`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x14001049a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x14001051f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1400105a9`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1400105fe`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x14001049a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x14001051f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1400105a9`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1400105fe`

## string_xrefs

- `0x140010144`: `onecore\windows\directx\database\updater\exe\bitshelper.cpp`
- `0x1400101a7`: `onecore\windows\directx\database\updater\exe\bitshelper.cpp`
- `0x140010213`: `onecore\windows\directx\database\updater\exe\bitshelper.cpp`
- `0x14001027e`: `onecore\windows\directx\database\updater\exe\bitshelper.cpp`
- `0x1400102fb`: `onecore\windows\directx\database\updater\exe\bitshelper.cpp`
- `0x14001038a`: `onecore\windows\directx\database\updater\exe\bitshelper.cpp`
- `0x14001040b`: `onecore\windows\directx\database\updater\exe\bitshelper.cpp`
- `0x140010488`: `onecore\windows\directx\database\updater\exe\bitshelper.cpp`
- `0x14001050d`: `onecore\windows\directx\database\updater\exe\bitshelper.cpp`
- `0x140010597`: `onecore\windows\directx\database\updater\exe\bitshelper.cpp`
- `0x14001067e`: `onecore\windows\directx\database\updater\exe\bitshelper.cpp`
- `0x14001074b`: `onecore\windows\directx\database\updater\exe\bitshelper.cpp`
- `0x1400107dc`: `onecore\windows\directx\database\updater\exe\bitshelper.cpp`
- `0x1400108e8`: `onecore\windows\directx\database\updater\exe\bitshelper.cpp`
- `0x140010987`: `onecore\windows\directx\database\updater\exe\bitshelper.cpp`
- `0x1400109b0`: `onecore\windows\directx\database\updater\exe\bitshelper.cpp`
- `0x140010a24`: `onecore\windows\directx\database\updater\exe\bitshelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall BitsHelper::HandleError(BitsHelper *this, struct IBackgroundCopyJob *a2)
{
  int v2; // eax
  unsigned int LastError; // ebx
  struct IBackgroundCopyJobVtbl *lpVtbl; // rax
  int v6; // eax
  int v7; // eax
  BitsHelper *v8; // rcx
  int v9; // ebx
  int ActiveUserToken; // eax
  struct IBackgroundCopyJobVtbl *v11; // rax
  int v12; // eax
  int IsLogonTriggerEnabled; // eax
  BitsHelper *v14; // rcx
  const char *v15; // r9
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  wchar_t *v20; // rbx
  __int64 v21; // rax
  _QWORD *v22; // rdx
  int v23; // eax
  int v24; // eax
  int v25; // ecx
  int v26; // eax
  __int64 v27; // rdi
  void (__fastcall *v28)(__int64, _QWORD, HANDLE *); // rbx
  unsigned __int16 ThreadLocale; // ax
  int v30; // eax
  int v31; // eax
  int v32; // [rsp+20h] [rbp-E0h]
  char *v33; // [rsp+28h] [rbp-D8h]
  bool v34; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *Str; // [rsp+48h] [rbp-B8h] BYREF
  struct IBackgroundCopyJob *v36; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v37; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE hToken; // [rsp+60h] [rbp-A0h] BYREF
  struct IBitsTokenOptions *v39; // [rsp+68h] [rbp-98h] BYREF
  char *v40; // [rsp+70h] [rbp-90h] BYREF
  _OWORD v41[2]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v42; // [rsp+98h] [rbp-68h]
  char v43; // [rsp+A0h] [rbp-60h]
  _OWORD v44[2]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v45; // [rsp+C8h] [rbp-38h]
  char v46; // [rsp+D0h] [rbp-30h]
  struct IBackgroundCopyJob **v47; // [rsp+D8h] [rbp-28h]
  char v48; // [rsp+E0h] [rbp-20h]
  _QWORD v49[4]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v50[32]; // [rsp+108h] [rbp+8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v36 = a2;
  v47 = &v36;
  v48 = 1;
  Str = 0;
  v2 = ((__int64 (__fastcall *)(struct IBackgroundCopyJob *, wchar_t **))a2->lpVtbl->GetDisplayName)(a2, &Str);
  LastError = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x15B,
      (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\bitshelper.cpp",
      (const char *)(unsigned int)v2,
      v32);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Str);
    ((void (__fastcall *)(struct IBackgroundCopyJob *))v36->lpVtbl->Cancel)(v36);
    return LastError;
  }
  v37 = 0;
  lpVtbl = v36->lpVtbl;
  v37 = 0;
  v6 = ((__int64 (__fastcall *)(struct IBackgroundCopyJob *, __int64 *))lpVtbl->GetError)(v36, &v37);
  LastError = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x15E,
      (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\bitshelper.cpp",
      (const char *)(unsigned int)v6,
      v32);
    wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v37);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Str);
    ((void (__fastcall *)(struct IBackgroundCopyJob *))v36->lpVtbl->Cancel)(v36);
    return LastError;
  }
  v40 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, char *, char **))(*(_QWORD *)v37 + 24LL))(v37, (char *)&v40 + 4, &v40);
  LastError = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x164,
      (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\bitshelper.cpp",
      (const char *)(unsigned int)v7,
      v32);
    wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v37);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Str);
    ((void (__fastcall *)(struct IBackgroundCopyJob *))v36->lpVtbl->Cancel)(v36);
    return LastError;
  }
  v9 = (int)v40;
  if ( (_DWORD)v40 == -2145386410 )
  {
    hToken = 0;
    ActiveUserToken = BitsHelper::GetActiveUserToken(v8, &hToken);
    LastError = ActiveUserToken;
    if ( ActiveUserToken < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x16A,
        (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\bitshelper.cpp",
        (const char *)(unsigned int)ActiveUserToken,
        v32);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
      wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v37);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Str);
      ((void (__fastcall *)(struct IBackgroundCopyJob *))v36->lpVtbl->Cancel)(v36);
      return LastError;
    }
    v39 = 0;
    v11 = v36->lpVtbl;
    v39 = 0;
    v12 = ((__int64 (__fastcall *)(struct IBackgroundCopyJob *, GUID *, struct IBitsTokenOptions **))v11->QueryInterface)(
            v36,
            &GUID_9a2584c3_f7d2_457a_9a5e_22b67bffc7d2,
            &v39);
    LastError = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x16D,
        (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\bitshelper.cpp",
        (const char *)(unsigned int)v12,
        v32);
      wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v39);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
      wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v37);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Str);
      ((void (__fastcall *)(struct IBackgroundCopyJob *))v36->lpVtbl->Cancel)(v36);
      return LastError;
    }
    memset(v41, 0, sizeof(v41));
    v42 = 0;
    v43 = 0;
    v34 = 0;
    IsLogonTriggerEnabled = TaskHelper::GetIsLogonTriggerEnabled((TaskHelper *)v41, &v34);
    LastError = IsLogonTriggerEnabled;
    if ( IsLogonTriggerEnabled < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x171,
        (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\bitshelper.cpp",
        (const char *)(unsigned int)IsLogonTriggerEnabled,
        v32);
      TaskHelper::~TaskHelper((TaskHelper *)v41);
      wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v39);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
      wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v37);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Str);
      ((void (__fastcall *)(struct IBackgroundCopyJob *))v36->lpVtbl->Cancel)(v36);
      return LastError;
    }
    if ( (char *)hToken - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      if ( v34 )
      {
        TaskHelper::~TaskHelper((TaskHelper *)v41);
        wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v39);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
        wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v37);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Str);
        ((void (__fastcall *)(struct IBackgroundCopyJob *))v36->lpVtbl->Cancel)(v36);
        return 0;
      }
      v19 = ((__int64 (__fastcall *)(struct IBitsTokenOptions *, _QWORD))v39->lpVtbl->SetHelperTokenFlags)(v39, 0);
      LastError = v19;
      if ( v19 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x189,
          (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\bitshelper.cpp",
          (const char *)(unsigned int)v19,
          v32);
        TaskHelper::~TaskHelper((TaskHelper *)v41);
        wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v39);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
        wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v37);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Str);
        ((void (__fastcall *)(struct IBackgroundCopyJob *))v36->lpVtbl->Cancel)(v36);
        return LastError;
      }
      v20 = wcsrchr(Str, 0x5Fu);
      v21 = std::wstring::wstring(v50, L"DirectX_Database_Download_");
      std::operator+<unsigned short>(v49, v21, v20 + 1);
      std::wstring::_Tidy_deallocate(v50);
      v22 = v49;
      if ( v49[3] > 7u )
        v22 = (_QWORD *)v49[0];
      v23 = ((__int64 (__fastcall *)(struct IBackgroundCopyJob *, _QWORD *))v36->lpVtbl->SetDisplayName)(v36, v22);
      LastError = v23;
      if ( v23 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x18E,
          (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\bitshelper.cpp",
          (const char *)(unsigned int)v23,
          v32);
        std::wstring::_Tidy_deallocate(v49);
        TaskHelper::~TaskHelper((TaskHelper *)v41);
        wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v39);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
        wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v37);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Str);
        ((void (__fastcall *)(struct IBackgroundCopyJob *))v36->lpVtbl->Cancel)(v36);
        return LastError;
      }
      std::wstring::_Tidy_deallocate(v49);
    }
    else
    {
      if ( !ImpersonateLoggedOnUser(hToken) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x176,
                      (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\bitshelper.cpp",
                      v15);
        TaskHelper::~TaskHelper((TaskHelper *)v41);
        wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v39);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
        wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v37);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Str);
        ((void (__fastcall *)(struct IBackgroundCopyJob *))v36->lpVtbl->Cancel)(v36);
        return LastError;
      }
      v34 = 1;
      v16 = BitsHelper::SetBITSProxyBlanketImpersonationLevelAndDynamicCloaking(v14, v39);
      LastError = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x179,
          (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\bitshelper.cpp",
          (const char *)(unsigned int)v16,
          v32);
        RevertToSelf();
        TaskHelper::~TaskHelper((TaskHelper *)v41);
        wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v39);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
        wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v37);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Str);
        ((void (__fastcall *)(struct IBackgroundCopyJob *))v36->lpVtbl->Cancel)(v36);
        return LastError;
      }
      v17 = ((__int64 (__fastcall *)(struct IBitsTokenOptions *))v39->lpVtbl->SetHelperToken)(v39);
      LastError = v17;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x17B,
          (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\bitshelper.cpp",
          (const char *)(unsigned int)v17,
          v32);
        RevertToSelf();
        TaskHelper::~TaskHelper((TaskHelper *)v41);
        wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v39);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
        wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v37);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Str);
        ((void (__fastcall *)(struct IBackgroundCopyJob *))v36->lpVtbl->Cancel)(v36);
        return LastError;
      }
      v18 = ((__int64 (__fastcall *)(struct IBitsTokenOptions *, __int64))v39->lpVtbl->SetHelperTokenFlags)(v39, 2);
      LastError = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x17C,
          (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\bitshelper.cpp",
          (const char *)(unsigned int)v18,
          v32);
        RevertToSelf();
        TaskHelper::~TaskHelper((TaskHelper *)v41);
        wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v39);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
        wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v37);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Str);
        ((void (__fastcall *)(struct IBackgroundCopyJob *))v36->lpVtbl->Cancel)(v36);
        return LastError;
      }
      RevertToSelf();
    }
    v24 = ((__int64 (__fastcall *)(struct IBackgroundCopyJob *))v36->lpVtbl->Resume)(v36);
    LastError = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x192,
        (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\bitshelper.cpp",
        (const char *)(unsigned int)v24,
        v32);
      TaskHelper::~TaskHelper((TaskHelper *)v41);
      wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v39);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
      wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v37);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Str);
      ((void (__fastcall *)(struct IBackgroundCopyJob *))v36->lpVtbl->Cancel)(v36);
      return LastError;
    }
    TaskHelper::~TaskHelper((TaskHelper *)v41);
    wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v39);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
    wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v37);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Str);
  }
  else
  {
    memset(v44, 0, sizeof(v44));
    v45 = 0;
    v46 = 0;
    if ( wcsncmp_0(L"DirectX_Database_Download_AsUser_", Str, 0x21u)
      && ((unsigned int)(v9 + 2147012894) <= 0x1C && (v25 = 402685985, _bittest(&v25, v9 + 2147012894))
       || v9 == -2145844841) )
    {
      v26 = TaskHelper::SetIsLogonTriggerEnabled((TaskHelper *)v44, 1);
      LastError = v26;
      if ( v26 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1AC,
          (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\bitshelper.cpp",
          (const char *)(unsigned int)v26,
          v32);
        TaskHelper::~TaskHelper((TaskHelper *)v44);
        wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v37);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Str);
        ((void (__fastcall *)(struct IBackgroundCopyJob *))v36->lpVtbl->Cancel)(v36);
        return LastError;
      }
    }
    else
    {
      hToken = 0;
      v27 = v37;
      v28 = *(void (__fastcall **)(__int64, _QWORD, HANDLE *))(*(_QWORD *)v37 + 40LL);
      hToken = 0;
      ThreadLocale = GetThreadLocale();
      v28(v27, ThreadLocale, &hToken);
      LODWORD(v33) = HIDWORD(v40);
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0x1A4,
        (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\bitshelper.cpp",
        (const char *)(unsigned int)v40,
        (int)"Context:%d, Desc:%ws\n",
        v33);
      v30 = TaskHelper::SetIsLogonTriggerEnabled((TaskHelper *)v44, 0);
      LastError = v30;
      if ( v30 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1A7,
          (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\bitshelper.cpp",
          (const char *)(unsigned int)v30,
          v32);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hToken);
        TaskHelper::~TaskHelper((TaskHelper *)v44);
        wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v37);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Str);
        ((void (__fastcall *)(struct IBackgroundCopyJob *))v36->lpVtbl->Cancel)(v36);
        return LastError;
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hToken);
    }
    v31 = TaskHelper::SaveLogonTriggerChange((TaskHelper *)v44);
    LastError = v31;
    if ( v31 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1AF,
        (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\bitshelper.cpp",
        (const char *)(unsigned int)v31,
        v32);
      TaskHelper::~TaskHelper((TaskHelper *)v44);
      wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v37);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Str);
      ((void (__fastcall *)(struct IBackgroundCopyJob *))v36->lpVtbl->Cancel)(v36);
      return LastError;
    }
    TaskHelper::~TaskHelper((TaskHelper *)v44);
    wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v37);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Str);
    ((void (__fastcall *)(struct IBackgroundCopyJob *))v36->lpVtbl->Cancel)(v36);
  }
  return 0;
}

```

## disassembly

```asm
0x1400100e0  push    rbp
0x1400100e2  push    rbx
0x1400100e3  push    rsi
0x1400100e4  push    rdi
0x1400100e5  lea     rbp, [rsp-38h]
0x1400100ea  sub     rsp, 138h
0x1400100f1  mov     rax, cs:__security_cookie
0x1400100f8  xor     rax, rsp
0x1400100fb  mov     [rbp+50h+var_28], rax
0x1400100ff  mov     r8, rdx
0x140010102  mov     [rsp+150h+var_100], rdx
0x140010107  lea     rax, [rsp+150h+var_100]
0x14001010c  mov     [rbp+50h+var_78], rax
0x140010110  mov     [rbp+50h+var_70], 1
0x140010114  xor     esi, esi
0x140010116  mov     [rsp+150h+Str], rsi
0x14001011b  mov     rax, [rdx]
0x14001011e  mov     [rsp+150h+Str], rsi
0x140010123  lea     rdx, [rsp+150h+Str]
0x140010128  mov     rcx, r8
0x14001012b  mov     rax, [rax+90h]
0x140010132  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010137  mov     ebx, eax
0x140010139  test    eax, eax
0x14001013b  jns     short loc_14001017A
0x14001013d  mov     rcx, [rbp+58h]; this
0x140010141  mov     r9d, eax; char *
0x140010144  lea     r8, aOnecoreWindows; "onecore\\windows\\directx\\database\\up"...
0x14001014b  mov     edx, 15Bh; void *
0x140010150  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140010155  nop
0x140010156  lea     rcx, [rsp+150h+Str]
0x14001015b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140010160  nop
0x140010161  mov     rcx, [rsp+150h+var_100]
0x140010166  mov     rax, [rcx]
0x140010169  mov     rax, [rax+40h]
0x14001016d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010172  nop
0x140010173  mov     eax, ebx
0x140010175  jmp     loc_140010AA1
0x14001017a  mov     [rsp+150h+var_F8], rsi
0x14001017f  mov     rcx, [rsp+150h+var_100]
0x140010184  mov     rax, [rcx]
0x140010187  mov     [rsp+150h+var_F8], rsi
0x14001018c  lea     rdx, [rsp+150h+var_F8]
0x140010191  mov     rax, [rax+78h]
0x140010195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001019a  mov     ebx, eax
0x14001019c  test    eax, eax
0x14001019e  jns     short loc_1400101E3
0x1400101a0  mov     rcx, [rbp+58h]; this
0x1400101a4  mov     r9d, eax; char *
0x1400101a7  lea     r8, aOnecoreWindows; "onecore\\windows\\directx\\database\\up"...
0x1400101ae  mov     edx, 15Eh; void *
0x1400101b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400101b8  nop
0x1400101b9  lea     rcx, [rsp+150h+var_F8]
0x1400101be  call    ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
0x1400101c3  nop
0x1400101c4  lea     rcx, [rsp+150h+Str]
0x1400101c9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1400101ce  nop
0x1400101cf  mov     rcx, [rsp+150h+var_100]
0x1400101d4  mov     rax, [rcx]
0x1400101d7  mov     rax, [rax+40h]
0x1400101db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400101e0  nop
0x1400101e1  jmp     short loc_140010173
0x1400101e3  mov     dword ptr [rsp+150h+var_E0+4], esi
0x1400101e7  mov     dword ptr [rsp+150h+var_E0], esi
0x1400101eb  mov     rcx, [rsp+150h+var_F8]
0x1400101f0  mov     rax, [rcx]
0x1400101f3  lea     r8, [rsp+150h+var_E0]
0x1400101f8  lea     rdx, [rsp+150h+var_E0+4]
0x1400101fd  mov     rax, [rax+18h]
0x140010201  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010206  mov     ebx, eax
0x140010208  test    eax, eax
0x14001020a  jns     short loc_140010252
0x14001020c  mov     rcx, [rbp+58h]; this
0x140010210  mov     r9d, eax; char *
0x140010213  lea     r8, aOnecoreWindows; "onecore\\windows\\directx\\database\\up"...
0x14001021a  mov     edx, 164h; void *
0x14001021f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140010224  nop
0x140010225  lea     rcx, [rsp+150h+var_F8]
0x14001022a  call    ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
0x14001022f  nop
0x140010230  lea     rcx, [rsp+150h+Str]
0x140010235  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14001023a  nop
0x14001023b  mov     rcx, [rsp+150h+var_100]
0x140010240  mov     rax, [rcx]
0x140010243  mov     rax, [rax+40h]
0x140010247  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001024c  nop
0x14001024d  jmp     loc_140010173
0x140010252  mov     ebx, dword ptr [rsp+150h+var_E0]
0x140010256  cmp     ebx, 80200056h
0x14001025c  jnz     loc_140010878
0x140010262  mov     [rsp+150h+hToken], rsi
0x140010267  lea     rdx, [rsp+150h+hToken]; void **
0x14001026c  call    ?GetActiveUserToken@BitsHelper@@AEAAJPEAPEAX@Z; BitsHelper::GetActiveUserToken(void * *)
0x140010271  mov     ebx, eax
0x140010273  test    eax, eax
0x140010275  jns     short loc_1400102C8
0x140010277  mov     rcx, [rbp+58h]; this
0x14001027b  mov     r9d, eax; char *
0x14001027e  lea     r8, aOnecoreWindows; "onecore\\windows\\directx\\database\\up"...
0x140010285  mov     edx, 16Ah; void *
0x14001028a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001028f  nop
0x140010290  lea     rcx, [rsp+150h+hToken]
0x140010295  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14001029a  nop
0x14001029b  lea     rcx, [rsp+150h+var_F8]
0x1400102a0  call    ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
0x1400102a5  nop
0x1400102a6  lea     rcx, [rsp+150h+Str]
0x1400102ab  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1400102b0  nop
0x1400102b1  mov     rcx, [rsp+150h+var_100]
0x1400102b6  mov     rax, [rcx]
0x1400102b9  mov     rax, [rax+40h]
0x1400102bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400102c2  nop
0x1400102c3  jmp     loc_140010173
0x1400102c8  mov     [rsp+150h+var_E8], rsi
0x1400102cd  mov     rcx, [rsp+150h+var_100]
0x1400102d2  mov     rax, [rcx]
0x1400102d5  mov     [rsp+150h+var_E8], rsi
0x1400102da  lea     r8, [rsp+150h+var_E8]
0x1400102df  lea     rdx, _GUID_9a2584c3_f7d2_457a_9a5e_22b67bffc7d2
0x1400102e6  mov     rax, [rax]
0x1400102e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400102ee  mov     ebx, eax
0x1400102f0  test    eax, eax
0x1400102f2  jns     short loc_140010350
0x1400102f4  mov     rcx, [rbp+58h]; this
0x1400102f8  mov     r9d, eax; char *
0x1400102fb  lea     r8, aOnecoreWindows; "onecore\\windows\\directx\\database\\up"...
0x140010302  mov     edx, 16Dh; void *
0x140010307  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001030c  nop
0x14001030d  lea     rcx, [rsp+150h+var_E8]
0x140010312  call    ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
0x140010317  nop
0x140010318  lea     rcx, [rsp+150h+hToken]
0x14001031d  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140010322  nop
0x140010323  lea     rcx, [rsp+150h+var_F8]
0x140010328  call    ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
0x14001032d  nop
0x14001032e  lea     rcx, [rsp+150h+Str]
0x140010333  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140010338  nop
0x140010339  mov     rcx, [rsp+150h+var_100]
0x14001033e  mov     rax, [rcx]
0x140010341  mov     rax, [rax+40h]
0x140010345  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001034a  nop
0x14001034b  jmp     loc_140010173
0x140010350  xorps   xmm0, xmm0
0x140010353  movdqu  [rsp+150h+var_D8], xmm0
0x140010359  xorps   xmm1, xmm1
0x14001035c  movdqu  [rbp+50h+var_C8], xmm1
0x140010361  mov     [rbp+50h+var_B8], rsi
0x140010365  mov     [rbp+50h+var_B0], sil
0x140010369  mov     [rsp+150h+var_110], sil
0x14001036e  lea     rdx, [rsp+150h+var_110]; bool *
0x140010373  lea     rcx, [rsp+150h+var_D8]; this
0x140010378  call    ?GetIsLogonTriggerEnabled@TaskHelper@@QEAAJAEA_N@Z; TaskHelper::GetIsLogonTriggerEnabled(bool &)
0x14001037d  mov     ebx, eax
0x14001037f  test    eax, eax
0x140010381  jns     short loc_1400103EA
0x140010383  mov     rcx, [rbp+58h]; this
0x140010387  mov     r9d, eax; char *
0x14001038a  lea     r8, aOnecoreWindows; "onecore\\windows\\directx\\database\\up"...
0x140010391  mov     edx, 171h; void *
0x140010396  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001039b  nop
0x14001039c  lea     rcx, [rsp+150h+var_D8]; this
0x1400103a1  call    ??1TaskHelper@@QEAA@XZ; TaskHelper::~TaskHelper(void)
0x1400103a6  nop
0x1400103a7  lea     rcx, [rsp+150h+var_E8]
0x1400103ac  call    ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
0x1400103b1  nop
0x1400103b2  lea     rcx, [rsp+150h+hToken]
0x1400103b7  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400103bc  nop
0x1400103bd  lea     rcx, [rsp+150h+var_F8]
0x1400103c2  call    ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
0x1400103c7  nop
0x1400103c8  lea     rcx, [rsp+150h+Str]
0x1400103cd  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1400103d2  nop
0x1400103d3  mov     rcx, [rsp+150h+var_100]
0x1400103d8  mov     rax, [rcx]
0x1400103db  mov     rax, [rax+40h]
0x1400103df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400103e4  nop
0x1400103e5  jmp     loc_140010173
0x1400103ea  mov     rcx, [rsp+150h+hToken]; hToken
0x1400103ef  lea     rax, [rcx-1]
0x1400103f3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400103f7  ja      loc_140010609
0x1400103fd  call    cs:__imp_ImpersonateLoggedOnUser
0x140010403  test    eax, eax
0x140010405  jnz     short loc_14001046C
0x140010407  mov     rcx, [rbp+58h]; this
0x14001040b  lea     r8, aOnecoreWindows; "onecore\\windows\\directx\\database\\up"...
0x140010412  mov     edx, 176h; void *
0x140010417  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14001041c  mov     ebx, eax
0x14001041e  lea     rcx, [rsp+150h+var_D8]; this
0x140010423  call    ??1TaskHelper@@QEAA@XZ; TaskHelper::~TaskHelper(void)
0x140010428  nop
0x140010429  lea     rcx, [rsp+150h+var_E8]
0x14001042e  call    ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
0x140010433  nop
0x140010434  lea     rcx, [rsp+150h+hToken]
0x140010439  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14001043e  nop
0x14001043f  lea     rcx, [rsp+150h+var_F8]
0x140010444  call    ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
0x140010449  nop
0x14001044a  lea     rcx, [rsp+150h+Str]
0x14001044f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140010454  nop
0x140010455  mov     rcx, [rsp+150h+var_100]
0x14001045a  mov     rax, [rcx]
0x14001045d  mov     rax, [rax+40h]
0x140010461  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010466  nop
0x140010467  jmp     loc_140010173
0x14001046c  mov     [rsp+150h+var_110], 1
0x140010471  mov     rdx, [rsp+150h+var_E8]; struct IBitsTokenOptions *
0x140010476  call    ?SetBITSProxyBlanketImpersonationLevelAndDynamicCloaking@BitsHelper@@AEAAJPEAUIBitsTokenOptions@@@Z; BitsHelper::SetBITSProxyBlanketImpersonationLevelAndDynamicCloaking(IBitsTokenOptions *)
0x14001047b  mov     ebx, eax
0x14001047d  test    eax, eax
0x14001047f  jns     short loc_1400104EF
0x140010481  mov     rcx, [rbp+58h]; this
0x140010485  mov     r9d, eax; char *
0x140010488  lea     r8, aOnecoreWindows; "onecore\\windows\\directx\\database\\up"...
0x14001048f  mov     edx, 179h; void *
0x140010494  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140010499  nop
0x14001049a  call    cs:__imp_RevertToSelf
0x1400104a0  nop
0x1400104a1  lea     rcx, [rsp+150h+var_D8]; this
0x1400104a6  call    ??1TaskHelper@@QEAA@XZ; TaskHelper::~TaskHelper(void)
0x1400104ab  nop
0x1400104ac  lea     rcx, [rsp+150h+var_E8]
0x1400104b1  call    ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
0x1400104b6  nop
0x1400104b7  lea     rcx, [rsp+150h+hToken]
0x1400104bc  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400104c1  nop
0x1400104c2  lea     rcx, [rsp+150h+var_F8]
0x1400104c7  call    ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
0x1400104cc  nop
0x1400104cd  lea     rcx, [rsp+150h+Str]
0x1400104d2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1400104d7  nop
0x1400104d8  mov     rcx, [rsp+150h+var_100]
0x1400104dd  mov     rax, [rcx]
0x1400104e0  mov     rax, [rax+40h]
0x1400104e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400104e9  nop
0x1400104ea  jmp     loc_140010173
0x1400104ef  mov     rcx, [rsp+150h+var_E8]
0x1400104f4  mov     rax, [rcx]
0x1400104f7  mov     rax, [rax+28h]
0x1400104fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010500  mov     ebx, eax
0x140010502  test    eax, eax
0x140010504  jns     short loc_140010574
0x140010506  mov     rcx, [rbp+58h]; this
0x14001050a  mov     r9d, eax; char *
0x14001050d  lea     r8, aOnecoreWindows; "onecore\\windows\\directx\\database\\up"...
0x140010514  mov     edx, 17Bh; void *
0x140010519  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001051e  nop
0x14001051f  call    cs:__imp_RevertToSelf
0x140010525  nop
0x140010526  lea     rcx, [rsp+150h+var_D8]; this
0x14001052b  call    ??1TaskHelper@@QEAA@XZ; TaskHelper::~TaskHelper(void)
0x140010530  nop
0x140010531  lea     rcx, [rsp+150h+var_E8]
0x140010536  call    ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
0x14001053b  nop
0x14001053c  lea     rcx, [rsp+150h+hToken]
0x140010541  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140010546  nop
0x140010547  lea     rcx, [rsp+150h+var_F8]
0x14001054c  call    ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
0x140010551  nop
0x140010552  lea     rcx, [rsp+150h+Str]
0x140010557  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
  ... truncated ...
```
