# CInvokeCreateProcessVerb::CallCreateProcess(void)

- ea: `0x18019e44c`
- end: `0x18019ef65`
- name: `?CallCreateProcess@CInvokeCreateProcessVerb@@AEAAJXZ`
- size: `2841`
- prototype: `__int64 __fastcall(CInvokeCreateProcessVerb *__hidden this)`
- caller_count: `1`
- callee_count: `33`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18019d454`

## callees

- `0x18000d6cc`
- `0x18000ee68`
- `0x18001a000`
- `0x1800432f0`
- `0x180060a10`
- `0x1800a5580`
- `0x1800b2f80`
- `0x1800c39dc`
- `0x1800c4068`
- `0x1800dd190`
- `0x18014d4e0`
- `0x180152ad4`
- `0x180152b54`
- `0x18019e090`
- `0x18019e44c`
- `0x18019ef6c`
- `0x18019ef8c`
- `0x18019f080`
- `0x180234d00`
- `0x1802c2e9c`
- `0x1802c71e8`
- `0x1802c72b0`
- `0x1802eae74`
- `0x18032c6b4`
- `0x18033b5a8`
- `0x18034f504`
- `0x18035841c`
- `0x1803a4cb0`
- `0x1803a57e0`
- `0x1803a7b60`
- `0x1803a96d9`
- `0x1805ea504`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019e8d1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019e8d1`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18064bdd2`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18064bdd2`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18019e9a2`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18019ef4f`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18019e9a2`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18019ef4f`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18019e941`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18019e941`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18019e5da`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18019e5da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019eddf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019edea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019ee66`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019ef06`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019ef5a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019eddf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019edea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019ee66`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019ef06`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019ef5a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18019e4a4`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18019e4a4`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathMatchSpecW` at `0x18019e4b4`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathMatchSpecW` at `0x18019e4b4`
- `api-ms-win-core-psm-key-l1-1-1!PsmCreateKeyWithDynamicId` at `0x18064be68`
- `api-ms-win-core-psm-key-l1-1-1!PsmCreateKeyWithDynamicId` at `0x18064be68`
- `api-ms-win-core-psm-key-l1-1-0!PsmCreateKey` at `0x18064bf9c`
- `api-ms-win-core-psm-key-l1-1-0!PsmCreateKey` at `0x18064bf9c`
- `KERNELBASE!ParseApplicationUserModelId` at `0x18019ea75`
- `KERNELBASE!ParseApplicationUserModelId` at `0x18019ea75`
- `KERNELBASE!GetCurrentPackageFamilyName` at `0x18064c220`
- `KERNELBASE!GetCurrentPackageFamilyName` at `0x18064c220`
- `KERNELBASE!GetCurrentApplicationUserModelId` at `0x18064c231`
- `KERNELBASE!GetCurrentApplicationUserModelId` at `0x18064c231`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18019eb84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18019eb84`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18064be3e`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18064be3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019e7ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019e92f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019e9f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019eaee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019ec4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019e7ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019e92f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019e9f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019eaee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019ec4f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18019e81f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18064c0e5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18019e81f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18064c0e5`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18019ee12`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18019ee12`
- `ext-ms-win-rtcore-ntuser-iam-l1-1-2!SetProcessLaunchForegroundPolicy` at `0x18019ef2f`
- `ext-ms-win-rtcore-ntuser-iam-l1-1-2!SetProcessLaunchForegroundPolicy` at `0x18019ef2f`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18019e57d`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18019e57d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18064bee3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18064bee3`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x18064c16f`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x18064c16f`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_ZoneCheckUrlExW` at `0x18064c1ad`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_ZoneCheckUrlExW` at `0x18064c1ad`
- `ext-ms-win-appcompat-pcacli-l1-1-0!PcaMonitorProcess2` at `0x18019eefb`
- `ext-ms-win-appcompat-pcacli-l1-1-0!PcaMonitorProcess2` at `0x18019eefb`
- `ext-ms-win-hostactivitymanager-hostidstore-l1-1-0!HamHostIdInitializeKey` at `0x18064bf3b`
- `ext-ms-win-hostactivitymanager-hostidstore-l1-1-0!HamHostIdInitializeKey` at `0x18064bf3b`
- `ext-ms-win-hostactivitymanager-hostidstore-l1-1-0!HamHostIdFindOrCreate` at `0x18064bf77`
- `ext-ms-win-hostactivitymanager-hostidstore-l1-1-0!HamHostIdFindOrCreate` at `0x18064bf77`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall CInvokeCreateProcessVerb::CallCreateProcess(CInvokeCreateProcessVerb *this)
{
  UINT32 v2; // r12d
  const WCHAR *FileNameW; // rax
  const WCHAR *v4; // rbx
  DWORD v5; // edi
  HRESULT v6; // eax
  signed int v7; // r15d
  BOOL ProcessAsUserW; // eax
  int v9; // eax
  char v10; // di
  void *v11; // rbx
  char v12; // r13
  const unsigned __int16 *v13; // rsi
  int v14; // ecx
  char v15; // di
  DWORD v16; // ecx
  int v17; // eax
  unsigned int v18; // ebx
  void *v19; // rcx
  void *v21; // rcx
  HRESULT v22; // edi
  LPVOID v23; // rcx
  __int64 v24; // rcx
  void *v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  int v28; // eax
  __int64 v29; // rcx
  __int64 v30; // rcx
  void *v31; // rcx
  unsigned int v32; // eax
  void *v33; // rcx
  HRESULT v34; // esi
  int v35; // eax
  LPVOID v36; // rax
  unsigned int AicLaunchFlags; // eax
  unsigned __int64 v38; // r9
  int v39; // eax
  __int64 v40; // rdx
  unsigned __int64 i; // rcx
  int v42; // eax
  HRESULT v43; // eax
  __int64 v44; // rdx
  LPVOID v45; // rsi
  __int64 (__fastcall *v46)(LPVOID, GUID *, GUID *, __int64 *); // rdi
  __int64 v47; // rax
  _DWORD *v48; // rcx
  unsigned int v49; // r12d
  int v50; // eax
  __int64 v51; // rdx
  int token_information; // eax
  void *v53; // rdi
  __int64 v54; // rsi
  const char *v55; // r9
  int LastError; // eax
  int v57; // eax
  __int64 v58; // rdx
  __int64 v59; // r9
  int v60; // eax
  __int64 v61; // rcx
  unsigned int v62; // edi
  BOOL v63; // eax
  __int64 v64; // rsi
  int (__fastcall *v65)(__int64, GUID *, GUID *, LPVOID *); // rdi
  WCHAR *v66; // rdi
  unsigned int v67; // eax
  unsigned __int64 v68; // r10
  void *v69; // r11
  WCHAR *v70; // r8
  WCHAR *v71; // rdx
  void *bInheritHandles; // [rsp+20h] [rbp-E0h]
  _BYTE *dwCreationFlags; // [rsp+28h] [rbp-D8h]
  unsigned __int64 v74; // [rsp+70h] [rbp-90h]
  char v75; // [rsp+80h] [rbp-80h]
  unsigned int v76; // [rsp+84h] [rbp-7Ch]
  const unsigned __int16 *pszPath; // [rsp+88h] [rbp-78h]
  GUID *p_pguid; // [rsp+90h] [rbp-70h]
  unsigned __int64 *v79; // [rsp+98h] [rbp-68h]
  LPVOID pv; // [rsp+A0h] [rbp-60h] BYREF
  UINT32 packageRelativeApplicationIdLength; // [rsp+A8h] [rbp-58h] BYREF
  HANDLE hObject; // [rsp+B0h] [rbp-50h] BYREF
  void *ppvOut; // [rsp+B8h] [rbp-48h] BYREF
  LPVOID ppv; // [rsp+C0h] [rbp-40h] BYREF
  DWORD ReturnLength[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v86; // [rsp+D0h] [rbp-30h] BYREF
  unsigned int TokenInformation; // [rsp+D8h] [rbp-28h] BYREF
  unsigned int v88; // [rsp+DCh] [rbp-24h] BYREF
  int v89[2]; // [rsp+E0h] [rbp-20h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int64 v91; // [rsp+F0h] [rbp-10h] BYREF
  GUID pguid; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v93; // [rsp+108h] [rbp+8h] BYREF
  char Parameter; // [rsp+110h] [rbp+10h] BYREF
  int v95; // [rsp+111h] [rbp+11h]
  __int16 v96; // [rsp+115h] [rbp+15h]
  char Data3_high; // [rsp+117h] [rbp+17h]
  CInvokeCreateProcessVerb *v98; // [rsp+118h] [rbp+18h]
  char v99; // [rsp+120h] [rbp+20h]
  _BYTE v100[1056]; // [rsp+130h] [rbp+30h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+550h] [rbp+450h] BYREF
  WCHAR packageRelativeApplicationId[136]; // [rsp+5E0h] [rbp+4E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+748h] [rbp+648h]

  if ( *((_DWORD *)this + 106) == 2 && SHTestTokenMembership(0, 0x220u) )
    v2 = 0;
  else
    v2 = *((_DWORD *)this + 106);
  packageRelativeApplicationIdLength = v2;
  LauncherAppLaunchTelemetry::CallCreateProcess<unsigned int>(&packageRelativeApplicationIdLength);
  FileNameW = PathFindFileNameW(*((LPCWSTR *)this + 73));
  if ( PathMatchSpecW(FileNameW, L"*.CMD;*.BAT") )
    v4 = 0;
  else
    v4 = (const WCHAR *)*((_QWORD *)this + 73);
  pszPath = v4;
  *((_DWORD *)this + 58) = 112;
  *((_QWORD *)this + 42) = *((_QWORD *)this + 47);
  v5 = *((_DWORD *)this + 57) | 0x80004;
  v76 = v5;
  v91 = 0;
  ppvOut = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppvOut);
  if ( !memcmp_0(&SID_ApplicationUserContextTokenInfo, &Buf2, 0x10u) )
    v6 = CInvokeCreateProcessVerb::QueryInterface(this, &GUID_cb738c08_8b2d_4349_a14d_b969e62e964c, &ppvOut);
  else
    v6 = IUnknown_QueryService(
           *((IUnknown **)this + 1),
           (const GUID *const)&SID_ApplicationUserContextTokenInfo,
           &GUID_cb738c08_8b2d_4349_a14d_b969e62e964c,
           &ppvOut);
  if ( v6 >= 0 && ppvOut )
    (*(void (__fastcall **)(void *, unsigned __int64 *))(*(_QWORD *)ppvOut + 24LL))(ppvOut, &v91);
  v7 = 0;
  if ( CInvokeCreateProcessVerb::IsLaunchingWithPackageIdentity(this) )
    goto LABEL_9;
  if ( v2 )
  {
    if ( v2 != 1 )
    {
LABEL_9:
      CInvokeCreateProcessVerb::DelegateSwitchToDesktopIfNeeded(this);
      goto LABEL_16;
    }
    ProcessAsUserW = CreateProcessAsUserW(
                       *((HANDLE *)this + 51),
                       v4,
                       *((LPWSTR *)this + 64),
                       0,
                       0,
                       *((_DWORD *)this + 118),
                       v5 | 0x2000000,
                       *((LPVOID *)this + 54),
                       *((LPCWSTR *)this + 10),
                       (LPSTARTUPINFOW)((char *)this + 232),
                       (LPPROCESS_INFORMATION)this + 16);
  }
  else
  {
    ProcessAsUserW = CreateProcessW(
                       v4,
                       *((LPWSTR *)this + 64),
                       0,
                       0,
                       *((_DWORD *)this + 118),
                       v5,
                       *((LPVOID *)this + 54),
                       *((LPCWSTR *)this + 10),
                       (LPSTARTUPINFOW)((char *)this + 232),
                       (LPPROCESS_INFORMATION)this + 16);
  }
  v9 = ResultFromWin32Bool(ProcessAsUserW);
  v7 = v9;
  if ( v9 >= 0 || v9 == -2147024156 )
    goto LABEL_9;
LABEL_16:
  v10 = 0;
  v75 = 0;
  v11 = 0;
  pv = 0;
  v79 = 0;
  p_pguid = 0;
  v93 = 0;
  pguid = 0;
  hObject = 0;
  v12 = 1;
  if ( CInvokeCreateProcessVerb::IsLaunchingWithPackageIdentity(this) && (*((_DWORD *)this + 138) & 0x800) != 0 )
  {
    v17 = CInvokeCreateProcessVerb::ResolvePackageFullNameIfNecessary(this, v91);
    v18 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7A0,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\execassoc.cpp",
        (const char *)(unsigned int)v17,
        (int)bInheritHandles);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      v19 = ppvOut;
      if ( ppvOut )
      {
        ppvOut = 0;
        (*(void (__fastcall **)(void *))(*(_QWORD *)v19 + 16LL))(v19);
      }
      return v18;
    }
    memset_0(packageRelativeApplicationId, 0, 0x84u);
    packageRelativeApplicationIdLength = 66;
    memset_0(packageFamilyName, 0, 0x82u);
    packageFamilyNameLength = 65;
    v32 = ParseApplicationUserModelId(
            *((PCWSTR *)this + 66),
            &packageFamilyNameLength,
            packageFamilyName,
            &packageRelativeApplicationIdLength,
            packageRelativeApplicationId);
    if ( v32 )
    {
      v18 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x7A7,
              (unsigned int)"onecoreuap\\shell\\windows.storage\\execassoc.cpp",
              (const char *)v32,
              (unsigned int)bInheritHandles);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      v33 = ppvOut;
      if ( ppvOut )
      {
        ppvOut = 0;
        (*(void (__fastcall **)(void *))(*(_QWORD *)v33 + 16LL))(v33);
      }
      return v18;
    }
    v88 = 464;
    v36 = CoTaskMemAlloc(0x1D0u);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &pv,
      v36);
    v11 = pv;
    if ( !pv )
    {
      v22 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7AB,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\execassoc.cpp",
        (const char *)0x8007000ELL,
        (int)bInheritHandles);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
LABEL_94:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppvOut);
      return (unsigned int)v22;
    }
    if ( v91 )
    {
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &hObject,
        0);
      v43 = UMgrQueryUserToken(v91, &hObject);
      v22 = v43;
      if ( v43 < 0 )
      {
        v44 = 1969;
LABEL_141:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v44,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\execassoc.cpp",
          (const char *)(unsigned int)v43,
          (int)bInheritHandles);
LABEL_106:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
        goto LABEL_107;
      }
    }
    else
    {
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &hObject,
        0);
      v43 = wil::open_current_access_token_nothrow(&hObject, 8, 1);
      v22 = v43;
      if ( v43 < 0 )
      {
        v44 = 1975;
        goto LABEL_141;
      }
    }
    v10 = 1;
    v75 = 1;
    if ( (*((_DWORD *)this + 138) & 0x1000) != 0 )
    {
      v43 = CoCreateGuid(&pguid);
      v22 = v43;
      if ( v43 < 0 )
      {
        v44 = 1987;
        goto LABEL_141;
      }
      bInheritHandles = &v88;
      v50 = PsmCreateKeyWithDynamicId(*((_QWORD *)this + 68), packageRelativeApplicationId, &pguid, v11);
      if ( v50 < 0 )
      {
        v51 = 1989;
LABEL_148:
        v22 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)v51,
                (unsigned int)"onecoreuap\\shell\\windows.storage\\execassoc.cpp",
                (const char *)(unsigned int)v50,
                (int)bInheritHandles);
        goto LABEL_106;
      }
      ppv = 0;
      token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&ppv, hObject);
      v22 = token_information;
      if ( token_information < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7C8,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\execassoc.cpp",
          (const char *)(unsigned int)token_information,
          (int)&v88);
        if ( ppv )
          CZeroInitNew::operator delete(ppv);
        goto LABEL_106;
      }
      v53 = ppv;
      v54 = *(_QWORD *)ppv;
      TokenInformation = 0;
      ReturnLength[0] = 4;
      if ( !GetTokenInformation(hObject, TokenSessionId, &TokenInformation, 4u, ReturnLength) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x7CE,
                      (unsigned int)"onecoreuap\\shell\\windows.storage\\execassoc.cpp",
                      v55);
LABEL_91:
        v34 = LastError;
        if ( v53 )
          CZeroInitNew::operator delete(v53);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
        CoTaskMemFree(v11);
        v22 = v34;
        goto LABEL_94;
      }
      memset_0(v100, 0, 0x418u);
      dwCreationFlags = v100;
      bInheritHandles = 0;
      v57 = HamHostIdInitializeKey(v11, v54, TokenInformation, 0);
      if ( v57 < 0 )
      {
        v58 = 2002;
LABEL_154:
        LastError = wil::details::in1diag3::Return_NtStatus(
                      retaddr,
                      (void *)v58,
                      (unsigned int)"onecoreuap\\shell\\windows.storage\\execassoc.cpp",
                      (const char *)(unsigned int)v57,
                      0);
        goto LABEL_91;
      }
      v57 = HamHostIdFindOrCreate(v100, &v93);
      if ( v57 < 0 )
      {
        v58 = 2004;
        goto LABEL_154;
      }
      v79 = (unsigned __int64 *)&v93;
      p_pguid = &pguid;
      if ( v53 )
        CZeroInitNew::operator delete(v53);
      v10 = 1;
    }
    else
    {
      v50 = PsmCreateKey(*((_QWORD *)this + 68), packageRelativeApplicationId, v11, &v88);
      if ( v50 < 0 )
      {
        v51 = 2011;
        goto LABEL_148;
      }
    }
  }
  v86 = 0;
  if ( *((_QWORD *)this + 70) || v10 )
  {
    ppv = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
    v22 = CoCreateInstance(&CLSID_ShellServiceHost, 0, 4u, &GUID_6d5140c1_7436_11ce_8034_00aa006009fa, &ppv);
    if ( v22 >= 0 )
    {
      v45 = ppv;
      v46 = *(__int64 (__fastcall **)(LPVOID, GUID *, GUID *, __int64 *))(*(_QWORD *)ppv + 24LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
      v22 = v46(v45, &IID_IApplicationInstanceManager, &GUID_62a9407f_345a_4300_8cdd_4847dee60f48, &v86);
    }
    if ( v75 && v22 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7EE,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\execassoc.cpp",
        (const char *)(unsigned int)v22,
        (int)bInheritHandles);
      v23 = ppv;
      if ( ppv )
      {
        ppv = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v23 + 16LL))(v23);
      }
      v24 = v86;
      if ( v86 )
      {
        v86 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      }
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      if ( v11 )
        CoTaskMemFree(v11);
      v25 = ppvOut;
      if ( ppvOut )
      {
        ppvOut = 0;
        (*(void (__fastcall **)(void *))(*(_QWORD *)v25 + 16LL))(v25);
      }
      return (unsigned int)v22;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
    v10 = v75;
  }
  *(_QWORD *)v89 = 0;
  if ( v10 )
  {
    v59 = (*((_DWORD *)this + 138) >> 14) & 1 | 2u;
    if ( (*((_DWORD *)this + 138) & 0x8000) == 0 )
      v59 = (*((_DWORD *)this + 138) >> 14) & 1;
    bInheritHandles = v89;
    v60 = (*(__int64 (__fastcall **)(__int64, HANDLE, void *, __int64))(*(_QWORD *)v86 + 104LL))(v86, hObject, v11, v59);
    v22 = v60;
    if ( v60 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x800,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\execassoc.cpp",
        (const char *)(unsigned int)v60,
        (int)v89);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v89);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v86);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
      if ( !v11 )
        goto LABEL_94;
LABEL_107:
      CoTaskMemFree(v11);
      goto LABEL_94;
    }
  }
  if ( !CInvokeCreateProcessVerb::IsLaunchingWithPackageIdentity(this) || v2 )
  {
    v13 = pszPath;
  }
  else
  {
    AicLaunchFlags = CInvokeCreateProcessVerb::GetAicLaunchFlags(this, 0);
    v13 = pszPath;
    v39 = AicLaunchProcessWithIdentity(
            pszPath,
            *((unsigned __int16 **)this + 64),
            0,
            v76,
            *((const unsigned __int16 **)this + 10),
            (struct _STARTUPINFOW *)((char *)this + 232),
            *((const unsigned __int16 **)this + 67),
            *((const unsigned __int16 **)this + 66),
            *((HWND *)this + 24),
            AicLaunchFlags,
            *((void **)this + 52),
            v38,
            v79,
            p_pguid,
            v74,
            (struct _PROCESS_INFORMATION *)this + 16);
    v7 = v39;
    if ( v39 > 0 )
      v7 = (unsigned __int16)v39 | 0x80070000;
  }
  if ( v7 != -2147024156 )
  {
    v14 = 0;
    if ( v2 != 2 )
      goto LABEL_24;
  }
  if ( (*((_BYTE *)this + 504) & 2) != 0 )
  {
    v88 = 0;
    ReturnLength[0] = 0;
    if ( AicCheckAdminApp(v13, *((unsigned __int16 **)this + 64), &v88, (enum ELEVATION_REASON *)ReturnLength) )
      goto LABEL_171;
    v62 = v88;
    if ( v88 - 16 > 2 )
      goto LABEL_171;
    packageRelativeApplicationIdLength = 0;
    if ( v88 >= 3 )
      v62 = v88 - 16;
    TokenInformation = 0;
    if ( (int)LUAGetUserType(v61, &TokenInformation) < 0
      || (int)LUAShouldElevate(TokenInformation, v62, &packageRelativeApplicationIdLength) < 0
      || packageRelativeApplicationIdLength )
    {
LABEL_171:
      v7 = -2147024156;
      goto LABEL_62;
    }
  }
  v63 = v7 != -2147024156;
  v49 = v63 | *((_DWORD *)this + 126) & 0x10;
  if ( !(v63 & 0x10 | *((_BYTE *)this + 504) & 0x10) )
  {
    CRPCTimeout::CRPCTimeout(&Parameter, 0x1388u);
    *(_QWORD *)ReturnLength = 0;
    ppv = 0;
    packageRelativeApplicationIdLength = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(ReturnLength);
    if ( CoCreateInstance(
           &CLSID_ImmersiveShell,
           0,
           4u,
           &GUID_6d5140c1_7436_11ce_8034_00aa006009fa,
           (LPVOID *)ReturnLength) >= 0 )
    {
      v64 = *(_QWORD *)ReturnLength;
      v65 = *(int (__fastcall **)(__int64, GUID *, GUID *, LPVOID *))(**(_QWORD **)ReturnLength + 24LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
      if ( v65(v64, &IID_IImmersiveSystemMode, &GUID_ea9aac7d_0cac_4ceb_981c_4545a28bada2, &ppv) >= 0
        && (*(int (__fastcall **)(LPVOID, UINT32 *))(*(_QWORD *)ppv + 24LL))(ppv, &packageRelativeApplicationIdLength) >= 0
        && packageRelativeApplicationIdLength == -1 )
      {
        v49 |= 0x40u;
      }
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(ReturnLength);
    CBaseRPCTimeout::Disarm((CBaseRPCTimeout *)&Parameter);
    v13 = pszPath;
  }
  if ( PathIsNetworkPathW(v13) )
  {
    packageRelativeApplicationIdLength = 0;
    ReturnLength[0] = 0;
    LODWORD(dwCreationFlags) = 6162;
    LODWORD(bInheritHandles) = 4;
    if ( (int)ZoneCheckUrlExW(
                v13,
                &packageRelativeApplicationIdLength,
                4,
                ReturnLength,
                bInheritHandles,
                dwCreationFlags,
                4611,
                0) >= 0
      && (packageRelativeApplicationIdLength & 0xF) != 0 )
    {
      v49 |= 0x80u;
    }
  }
  if ( CInvokeCreateProcessVerb::IsLaunchingWithPackageIdentity(this) )
  {
    memset_0(packageFamilyName, 0, 0x82u);
    memset_0(packageRelativeApplicationId, 0, 0x104u);
    v66 = (WCHAR *)*((_QWORD *)this + 67);
    if ( !v66 )
    {
      ReturnLength[0] = 65;
      packageFamilyNameLength = 130;
      GetCurrentPackageFamilyName(ReturnLength, packageFamilyName);
      GetCurrentApplicationUserModelId(&packageFamilyNameLength, packageRelativeApplicationId);
      v66 = (WCHAR *)*((_QWORD *)this + 67);
    }
    v67 = CInvokeCreateProcessVerb::GetAicLaunchFlags(this, 1);
    v70 = packageRelativeApplicationId;
    if ( *((_QWORD *)this + 66) )
      v70 = (WCHAR *)*((_QWORD *)this + 66);
    v71 = packageFamilyName;
    if ( v66 )
      v71 = v66;
    v35 = AicLaunchProcessWithIdentity(
            v13,
            *((unsigned __int16 **)this + 64),
            v49,
            v76,
            *((const unsigned __int16 **)this + 10),
            (struct _STARTUPINFOW *)((char *)this + 232),
            v71,
            v70,
            *((HWND *)this + 24),
            v67,
            v69,
            v68,
            v79,
            p_pguid,
            v74,
            (struct _PROCESS_INFORMATION *)this + 16);
  }
  else
  {
    for ( i = 0; i < *((_QWORD *)this + 44); ++i )
    {
      v40 = 3 * i;
      if ( *(_QWORD *)(*((_QWORD *)this + 43) + 24 * i) == 131089 )
      {
        _mm_lfence();
        v47 = *((_QWORD *)this + 43);
        v48 = *(_DWORD **)(v47 + 24 * i + 8);
        if ( v48 && *(_QWORD *)(v47 + 8 * v40 + 16) == 524 )
        {
          if ( (*v48 & 0x22) == 2 || (*(_BYTE *)v48 & 0x50) != 0 )
            v49 |= 0x100u;
          else
            v49 |= 0x800u;
        }
        break;
      }
    }
    ReturnLength[0] = 0;
    v35 = AicLaunchAdminProcess(
            v13,
            *((unsigned __int16 **)this + 64),
            v49,
            v76,
            *((const unsigned __int16 **)this + 10),
            *((HWND *)this + 24),
            (struct _STARTUPINFOW *)((char *)this + 232),
            (struct _PROCESS_INFORMATION *)this + 16,
            (enum ELEVATION_REASON *)ReturnLength);
  }
  v7 = v35;
  if ( v35 > 0 )
    v7 = (unsigned __int16)v35 | 0x80070000;
  if ( v7 >= 0 )
  {
    v14 = 2;
LABEL_24:
    if ( v7 >= 0 )
    {
      v15 = v75;
      Parameter = v75;
      v95 = *(unsigned int *)((char *)&pguid.Data1 + 1);
      v96 = *(unsigned __int16 *)((char *)&pguid.Data2 + 1);
      Data3_high = HIBYTE(pguid.Data3);
      v98 = this;
      v99 = 1;
      if ( (*((_BYTE *)this + 504) & 1) != 0 || v14 )
      {
        bInheritHandles = (void *)*((_QWORD *)this + 10);
        PcaMonitorProcess2(*((_QWORD *)this + 48), 1, v13, *((_QWORD *)this + 64));
      }
      if ( *((_QWORD *)this + 70) )
      {
        if ( v86 )
        {
          v42 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v86 + 96LL))(v86, *((_QWORD *)this + 48));
          if ( v42 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x8BD,
              (unsigned int)"onecoreuap\\shell\\windows.storage\\execassoc.cpp",
              (const char *)(unsigned int)v42,
              (int)bInheritHandles);
        }
      }
      if ( v75 )
      {
        v28 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v86 + 112LL))(
                v86,
                *((_QWORD *)this + 48),
                *(_QWORD *)v89);
        v22 = v28;
        if ( v28 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x8C2,
            (unsigned int)"onecoreuap\\shell\\windows.storage\\execassoc.cpp",
            (const char *)(unsigned int)v28,
            (int)bInheritHandles);
          TerminateProcess(*((HANDLE *)this + 48), 0x80004005);
          v29 = *(_QWORD *)v89;
          if ( *(_QWORD *)v89 )
          {
            *(_QWORD *)v89 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
          }
          v30 = v86;
          if ( v86 )
          {
            v86 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
          }
          if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            CloseHandle(hObject);
          if ( v11 )
            CoTaskMemFree(v11);
          v31 = ppvOut;
          if ( ppvOut )
          {
            ppvOut = 0;
            (*(void (__fastcall **)(void *))(*(_QWORD *)v31 + 16LL))(v31);
          }
          return (unsigned int)v22;
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v89);
        v15 = v75;
      }
      if ( (unsigned __int8)IsSetProcessLaunchForegroundPolicyPresent() && (*((_BYTE *)this + 504) & 0x20) != 0 )
        SetProcessLaunchForegroundPolicy(*((unsigned int *)this + 100), 4);
      if ( (*((_BYTE *)this + 228) & 4) != 0 || ResumeThread(*((HANDLE *)this + 49)) != -1 )
        v12 = 0;
      if ( v12 && v15 )
        TerminateProcess(*((HANDLE *)this + 48), 0x80004005);
    }
  }
  if ( (v7 & 0x1FFF0000) == 0x70000 )
  {
LABEL_62:
    v16 = (unsigned __int16)v7;
    goto LABEL_63;
  }
  v16 = v7;
LABEL_63:
  SetLastError(v16);
  v26 = *(_QWORD *)v89;
  if ( *(_QWORD *)v89 )
  {
    *(_QWORD *)v89 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  }
  v27 = v86;
  if ( v86 )
  {
    v86 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  }
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  if ( v11 )
    CoTaskMemFree(v11);
  v21 = ppvOut;
  if ( ppvOut )
  {
    ppvOut = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v21 + 16LL))(v21);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18019e44c  push    rbp
0x18019e44e  push    rbx
0x18019e44f  push    rsi
0x18019e450  push    rdi
0x18019e451  push    r12
0x18019e453  push    r13
0x18019e455  push    r14
0x18019e457  push    r15
0x18019e459  lea     rbp, [rsp-608h]
0x18019e461  sub     rsp, 708h
0x18019e468  mov     rax, cs:__security_cookie
0x18019e46f  xor     rax, rsp
0x18019e472  mov     [rbp+640h+var_50], rax
0x18019e479  mov     r14, rcx
0x18019e47c  cmp     dword ptr [rcx+1A8h], 2
0x18019e483  jz      loc_18019EDA1
0x18019e489  mov     r12d, [r14+1A8h]
0x18019e490  mov     [rbp+640h+packageRelativeApplicationIdLength], r12d
0x18019e494  lea     rcx, [rbp+640h+packageRelativeApplicationIdLength]
0x18019e498  call    ??$CallCreateProcess@I@LauncherAppLaunchTelemetry@@SAX$$QEAI@Z; LauncherAppLaunchTelemetry::CallCreateProcess<uint>(uint &&)
0x18019e49d  mov     rcx, [r14+248h]; pszPath
0x18019e4a4  call    cs:__imp_PathFindFileNameW
0x18019e4aa  lea     rdx, aCmdBat; "*.CMD;*.BAT"
0x18019e4b1  mov     rcx, rax; pszFile
0x18019e4b4  call    cs:__imp_PathMatchSpecW
0x18019e4ba  test    eax, eax
0x18019e4bc  jnz     loc_18019E585
0x18019e4c2  mov     rbx, [r14+248h]
0x18019e4c9  mov     [rbp+640h+pszPath], rbx
0x18019e4cd  lea     rsi, [r14+0E8h]
0x18019e4d4  mov     dword ptr [rsi], 70h ; 'p'
0x18019e4da  mov     rax, [r14+178h]
0x18019e4e1  mov     [r14+150h], rax
0x18019e4e8  mov     edi, [r14+0E4h]
0x18019e4ef  or      edi, 80004h
0x18019e4f5  mov     [rbp+640h+var_6BC], edi
0x18019e4f8  mov     [rbp+640h+var_650], 0
0x18019e500  mov     [rbp+640h+ppvOut], 0
0x18019e508  lea     rcx, [rbp+640h+ppvOut]
0x18019e50c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019e511  mov     r8d, 10h; Size
0x18019e517  lea     rdx, Buf2; Buf2
0x18019e51e  lea     rcx, SID_ApplicationUserContextTokenInfo; Buf1
0x18019e525  call    memcmp_0
0x18019e52a  test    eax, eax
0x18019e52c  jnz     short loc_18019E567
0x18019e52e  lea     r8, [rbp+640h+ppvOut]; ppv
0x18019e532  lea     rdx, _GUID_cb738c08_8b2d_4349_a14d_b969e62e964c; riid
0x18019e539  mov     rcx, r14; this
0x18019e53c  call    ?QueryInterface@CInvokeCreateProcessVerb@@UEAAJAEBU_GUID@@PEAPEAX@Z; CInvokeCreateProcessVerb::QueryInterface(_GUID const &,void * *)
0x18019e541  test    eax, eax
0x18019e543  jns     loc_18019EDBD
0x18019e549  xor     r15d, r15d
0x18019e54c  mov     rcx, r14; this
0x18019e54f  call    ?IsLaunchingWithPackageIdentity@CInvokeCreateProcessVerb@@AEBA_NXZ; CInvokeCreateProcessVerb::IsLaunchingWithPackageIdentity(void)
0x18019e554  test    al, al
0x18019e556  jz      short loc_18019E58C
0x18019e558  xor     esi, esi
0x18019e55a  mov     rcx, r14; this
0x18019e55d  call    ?DelegateSwitchToDesktopIfNeeded@CInvokeCreateProcessVerb@@AEAAXXZ; CInvokeCreateProcessVerb::DelegateSwitchToDesktopIfNeeded(void)
0x18019e562  jmp     loc_18019E5FF
0x18019e567  lea     r9, [rbp+640h+ppvOut]; ppvOut
0x18019e56b  lea     r8, _GUID_cb738c08_8b2d_4349_a14d_b969e62e964c; riid
0x18019e572  lea     rdx, SID_ApplicationUserContextTokenInfo; guidService
0x18019e579  mov     rcx, [r14+8]; punk
0x18019e57d  call    cs:__imp_IUnknown_QueryService
0x18019e583  jmp     short loc_18019E541
0x18019e585  xor     ebx, ebx
0x18019e587  jmp     loc_18019E4C9
0x18019e58c  test    r12d, r12d
0x18019e58f  jnz     loc_18064BD72
0x18019e595  lea     rax, [r14+180h]
0x18019e59c  mov     [rsp+740h+lpProcessInformation], rax; lpProcessInformation
0x18019e5a1  mov     [rsp+740h+lpStartupInfo], rsi; lpStartupInfo
0x18019e5a6  mov     rax, [r14+50h]
0x18019e5aa  mov     [rsp+740h+lpCurrentDirectory], rax; lpCurrentDirectory
0x18019e5af  mov     rax, [r14+1B0h]
0x18019e5b6  mov     [rsp+740h+lpEnvironment], rax; lpEnvironment
0x18019e5bb  mov     [rsp+740h+dwCreationFlags], edi; dwCreationFlags
0x18019e5bf  mov     eax, [r14+1D8h]
0x18019e5c6  mov     [rsp+740h+bInheritHandles], eax; int
0x18019e5ca  xor     r9d, r9d; lpThreadAttributes
0x18019e5cd  xor     r8d, r8d; lpProcessAttributes
0x18019e5d0  mov     rdx, [r14+200h]; lpCommandLine
0x18019e5d7  mov     rcx, rbx; lpApplicationName
0x18019e5da  call    cs:__imp_CreateProcessW
0x18019e5e0  xor     esi, esi
0x18019e5e2  mov     ecx, eax; int
0x18019e5e4  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x18019e5e9  mov     r15d, eax
0x18019e5ec  test    eax, eax
0x18019e5ee  jns     loc_18019E55A
0x18019e5f4  cmp     eax, 800702E4h
0x18019e5f9  jz      loc_18019E55A
0x18019e5ff  mov     dil, sil
0x18019e602  mov     [rbp+640h+var_6C0], sil
0x18019e606  mov     rbx, rsi
0x18019e609  mov     [rbp+640h+pv], rbx
0x18019e60d  mov     [rbp+640h+var_6A8], rsi
0x18019e611  mov     [rbp+640h+var_6B0], rsi
0x18019e615  mov     [rbp+640h+var_638], rsi
0x18019e619  xorps   xmm0, xmm0
0x18019e61c  movups  xmmword ptr [rbp+640h+pguid.Data1], xmm0
0x18019e620  mov     [rbp+640h+hObject], rsi
0x18019e624  mov     rcx, r14; this
0x18019e627  call    ?IsLaunchingWithPackageIdentity@CInvokeCreateProcessVerb@@AEBA_NXZ; CInvokeCreateProcessVerb::IsLaunchingWithPackageIdentity(void)
0x18019e62c  mov     r13d, 1
0x18019e632  test    al, al
0x18019e634  jnz     loc_18019E738
0x18019e63a  mov     [rbp+640h+var_670], rsi
0x18019e63e  cmp     [r14+230h], rsi
0x18019e645  jnz     loc_18019E7F5
0x18019e64b  test    dil, dil
0x18019e64e  jnz     loc_18019E7F5
0x18019e654  mov     qword ptr [rbp+640h+var_660], rsi
0x18019e658  test    dil, dil
0x18019e65b  jnz     loc_18064BFAF
0x18019e661  mov     rcx, r14; this
0x18019e664  call    ?IsLaunchingWithPackageIdentity@CInvokeCreateProcessVerb@@AEBA_NXZ; CInvokeCreateProcessVerb::IsLaunchingWithPackageIdentity(void)
0x18019e669  test    al, al
0x18019e66b  jnz     loc_18019EE83
0x18019e671  mov     rsi, [rbp+640h+pszPath]
0x18019e675  cmp     r15d, 800702E4h
0x18019e67c  jz      loc_18064C002
0x18019e682  xor     ecx, ecx
0x18019e684  cmp     r12d, 2
0x18019e688  jz      loc_18064C002
0x18019e68e  xor     r12d, r12d
0x18019e691  test    r15d, r15d
0x18019e694  js      loc_18019E71D
0x18019e69a  mov     dil, [rbp+640h+var_6C0]
0x18019e69e  mov     [rbp+640h+Parameter], dil
0x18019e6a2  mov     eax, [rbp+640h+pguid.Data1+1]
0x18019e6a5  mov     [rbp+640h+var_62F], eax
0x18019e6a8  movzx   eax, [rbp+640h+pguid.Data2+1]
0x18019e6ac  mov     [rbp+640h+var_62B], ax
0x18019e6b0  mov     al, byte ptr [rbp+640h+pguid.Data3+1]
0x18019e6b3  mov     [rbp+640h+var_629], al
0x18019e6b6  mov     [rbp+640h+var_628], r14
0x18019e6ba  mov     [rbp+640h+var_620], r13b
0x18019e6be  test    [r14+1F8h], r13b
0x18019e6c5  jnz     loc_18019EEDA
0x18019e6cb  test    ecx, ecx
0x18019e6cd  jnz     loc_18019EED7
0x18019e6d3  mov     r8, [r14+230h]
0x18019e6da  test    r8, r8
0x18019e6dd  jnz     loc_18019ED34
0x18019e6e3  test    dil, dil
0x18019e6e6  jnz     loc_18019E955
0x18019e6ec  call    IsSetProcessLaunchForegroundPolicyPresent
0x18019e6f1  test    al, al
0x18019e6f3  jz      short loc_18019E703
0x18019e6f5  test    byte ptr [r14+1F8h], 20h
0x18019e6fd  jnz     loc_18019EF23
0x18019e703  test    byte ptr [r14+0E4h], 4
0x18019e70b  jz      loc_18019E93A
0x18019e711  mov     r13b, r12b
0x18019e714  test    r13b, r13b
0x18019e717  jnz     loc_18019EF3A
0x18019e71d  mov     eax, r15d
0x18019e720  and     eax, 1FFF0000h
0x18019e725  cmp     eax, 70000h
0x18019e72a  jz      loc_18019E8CD
0x18019e730  mov     ecx, r15d
0x18019e733  jmp     loc_18019E8D1
0x18019e738  test    dword ptr [r14+228h], 800h
0x18019e743  jz      loc_18019E63A
0x18019e749  mov     rdx, [rbp+640h+var_650]; unsigned __int64
0x18019e74d  mov     rcx, r14; this
0x18019e750  call    ?ResolvePackageFullNameIfNecessary@CInvokeCreateProcessVerb@@AEAAJ_K@Z; CInvokeCreateProcessVerb::ResolvePackageFullNameIfNecessary(unsigned __int64)
0x18019e755  mov     ebx, eax
0x18019e757  test    eax, eax
0x18019e759  jns     loc_18019EA1D
0x18019e75f  mov     rcx, [rbp+648h]; this
0x18019e766  mov     r9d, eax; char *
0x18019e769  lea     r8, aOnecoreuapShel_58; "onecoreuap\\shell\\windows.storage\\exe"...
0x18019e770  mov     edx, 7A0h; void *
0x18019e775  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019e77a  nop
0x18019e77b  mov     rcx, [rbp+640h+hObject]; hObject
0x18019e77f  lea     rdx, [rcx-1]
0x18019e783  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18019e787  jbe     loc_18019EDDF
0x18019e78d  mov     rcx, [rbp+640h+ppvOut]
0x18019e791  test    rcx, rcx
0x18019e794  jz      short loc_18019E7A7
0x18019e796  mov     [rbp+640h+ppvOut], rsi
0x18019e79a  mov     rax, [rcx]
0x18019e79d  mov     rax, [rax+10h]
0x18019e7a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019e7a6  nop
0x18019e7a7  mov     eax, ebx
0x18019e7a9  jmp     short loc_18019E7D2
0x18019e7ab  mov     rcx, rbx; pv
0x18019e7ae  call    cs:__imp_CoTaskMemFree
0x18019e7b4  nop
0x18019e7b5  mov     rcx, [rbp+640h+ppvOut]
0x18019e7b9  test    rcx, rcx
0x18019e7bc  jz      short loc_18019E7CF
0x18019e7be  mov     [rbp+640h+ppvOut], r12
0x18019e7c2  mov     rdx, [rcx]
0x18019e7c5  mov     rax, [rdx+10h]
0x18019e7c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019e7ce  nop
0x18019e7cf  mov     eax, r15d
0x18019e7d2  mov     rcx, [rbp+640h+var_50]
0x18019e7d9  xor     rcx, rsp; StackCookie
0x18019e7dc  call    __security_check_cookie
0x18019e7e1  add     rsp, 708h
0x18019e7e8  pop     r15
0x18019e7ea  pop     r14
0x18019e7ec  pop     r13
0x18019e7ee  pop     r12
0x18019e7f0  pop     rdi
0x18019e7f1  pop     rsi
0x18019e7f2  pop     rbx
0x18019e7f3  pop     rbp
0x18019e7f4  retn
0x18019e7f5  mov     [rbp+640h+ppv], rsi
0x18019e7f9  lea     rcx, [rbp+640h+ppv]
0x18019e7fd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019e802  lea     rax, [rbp+640h+ppv]
0x18019e806  mov     qword ptr [rsp+740h+bInheritHandles], rax; int
0x18019e80b  lea     r9, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa; riid
0x18019e812  xor     edx, edx; pUnkOuter
0x18019e814  lea     r8d, [rdx+4]; dwClsContext
0x18019e818  lea     rcx, CLSID_ShellServiceHost; rclsid
0x18019e81f  call    cs:__imp_CoCreateInstance
0x18019e825  mov     edi, eax
0x18019e827  test    eax, eax
0x18019e829  jns     loc_18019EE2C
0x18019e82f  cmp     [rbp+640h+var_6C0], sil
0x18019e833  jz      loc_18019EE71
0x18019e839  test    edi, edi
0x18019e83b  jns     loc_18019EE71
0x18019e841  mov     rcx, [rbp+648h]; this
0x18019e848  mov     r9d, edi; char *
0x18019e84b  lea     r8, aOnecoreuapShel_58; "onecoreuap\\shell\\windows.storage\\exe"...
0x18019e852  mov     edx, 7EEh; void *
0x18019e857  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019e85c  nop
0x18019e85d  mov     rcx, [rbp+640h+ppv]
0x18019e861  test    rcx, rcx
0x18019e864  jz      short loc_18019E877
0x18019e866  mov     [rbp+640h+ppv], rsi
0x18019e86a  mov     rax, [rcx]
0x18019e86d  mov     rax, [rax+10h]
0x18019e871  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019e876  nop
0x18019e877  mov     rcx, [rbp+640h+var_670]
0x18019e87b  test    rcx, rcx
0x18019e87e  jz      short loc_18019E891
0x18019e880  mov     [rbp+640h+var_670], rsi
0x18019e884  mov     rax, [rcx]
0x18019e887  mov     rax, [rax+10h]
0x18019e88b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019e890  nop
0x18019e891  mov     rcx, [rbp+640h+hObject]; hObject
0x18019e895  lea     rax, [rcx-1]
0x18019e899  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18019e89d  jbe     loc_18019EE66
0x18019e8a3  test    rbx, rbx
0x18019e8a6  jnz     loc_18019E92C
0x18019e8ac  mov     rcx, [rbp+640h+ppvOut]
0x18019e8b0  test    rcx, rcx
0x18019e8b3  jz      short loc_18019E8C6
0x18019e8b5  mov     [rbp+640h+ppvOut], rsi
0x18019e8b9  mov     rax, [rcx]
0x18019e8bc  mov     rax, [rax+10h]
0x18019e8c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019e8c5  nop
0x18019e8c6  mov     eax, edi
0x18019e8c8  jmp     loc_18019E7D2
0x18019e8cd  movzx   ecx, r15w; dwErrCode
0x18019e8d1  call    cs:__imp_SetLastError
0x18019e8d7  nop
0x18019e8d8  mov     rcx, qword ptr [rbp+640h+var_660]
0x18019e8dc  test    rcx, rcx
0x18019e8df  jz      short loc_18019E8F2
0x18019e8e1  mov     qword ptr [rbp+640h+var_660], r12
0x18019e8e5  mov     rax, [rcx]
0x18019e8e8  mov     rax, [rax+10h]
0x18019e8ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019e8f1  nop
0x18019e8f2  mov     rcx, [rbp+640h+var_670]
0x18019e8f6  test    rcx, rcx
0x18019e8f9  jz      short loc_18019E90C
0x18019e8fb  mov     [rbp+640h+var_670], r12
0x18019e8ff  mov     rax, [rcx]
0x18019e902  mov     rax, [rax+10h]
0x18019e906  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019e90b  nop
0x18019e90c  mov     rcx, [rbp+640h+hObject]; hObject
0x18019e910  lea     rax, [rcx-1]
0x18019e914  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18019e918  jbe     loc_18019EF5A
0x18019e91e  test    rbx, rbx
0x18019e921  jz      loc_18019E7B5
0x18019e927  jmp     loc_18019E7AB
0x18019e92c  mov     rcx, rbx; pv
  ... truncated ...
```
