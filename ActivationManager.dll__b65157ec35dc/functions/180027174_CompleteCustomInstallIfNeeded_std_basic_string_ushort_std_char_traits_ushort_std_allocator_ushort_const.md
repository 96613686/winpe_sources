# CompleteCustomInstallIfNeeded(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180027174`
- end: `0x180027881`
- name: `?CompleteCustomInstallIfNeeded@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1805`
- prototype: `void __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180026580`

## callees

- `0x18000cbc0`
- `0x1800263e4`
- `0x180027174`
- `0x180027ce8`
- `0x18004361c`
- `0x180044a14`
- `0x1800458dc`
- `0x180045f40`
- `0x18004670c`
- `0x180046a60`
- `0x180054340`
- `0x180056208`
- `0x1800565f0`
- `0x180058d4c`
- `0x18005ae90`
- `0x18005ba40`
- `0x18007638c`
- `0x1800763c8`
- `0x18008ec24`
- `0x18008ee0c`
- `0x18008ef28`
- `0x18008f1e4`
- `0x18008f5b4`
- `0x18008f628`
- `0x18008f76c`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180027775`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180027775`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800273de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800273de`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180027701`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180027701`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800273ce`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800273ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800273b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800273b7`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18002756b`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18002756b`
- `api-ms-win-appmodel-runtime-internal-l1-1-2!GetEffectivePackageStatusForUser` at `0x1800271b8`
- `api-ms-win-appmodel-runtime-internal-l1-1-2!GetEffectivePackageStatusForUser` at `0x1800277ad`
- `api-ms-win-appmodel-runtime-internal-l1-1-2!GetEffectivePackageStatusForUser` at `0x1800271b8`
- `api-ms-win-appmodel-runtime-internal-l1-1-2!GetEffectivePackageStatusForUser` at `0x1800277ad`
- `ext-ms-win-advapi32-safer-l1-1-0!SaferComputeTokenFromLevel` at `0x180027642`
- `ext-ms-win-advapi32-safer-l1-1-0!SaferComputeTokenFromLevel` at `0x180027642`
- `ext-ms-win-advapi32-safer-l1-1-0!SaferCloseLevel` at `0x180027751`
- `ext-ms-win-advapi32-safer-l1-1-0!SaferCloseLevel` at `0x180027751`
- `ext-ms-win-advapi32-safer-l1-1-0!SaferCreateLevel` at `0x1800275f7`
- `ext-ms-win-advapi32-safer-l1-1-0!SaferCreateLevel` at `0x1800275f7`
- `USERENV!CreateEnvironmentBlock` at `0x1800275a6`
- `USERENV!CreateEnvironmentBlock` at `0x1800275a6`
- `ext-ms-win-appmodel-shellexecute-l1-1-0!ShellExecuteExW` at `0x1800274d4`
- `ext-ms-win-appmodel-shellexecute-l1-1-0!ShellExecuteExW` at `0x1800274d4`

## string_xrefs

- `0x1800272c4`: `custominstallexec.exe`
- `0x1800272f7`: `/install`
- `0x180027285`: `onecore\base\appmodel\execmodel\desktopappx\sharedlib\custominstallutil.cpp`
- `0x18002743a`: `onecore\base\appmodel\execmodel\desktopappx\sharedlib\custominstallutil.cpp`
- `0x1800274de`: `onecore\base\appmodel\execmodel\desktopappx\sharedlib\custominstallutil.cpp`
- `0x180027528`: `onecore\base\appmodel\execmodel\desktopappx\sharedlib\custominstallutil.cpp`
- `0x18002757d`: `onecore\base\appmodel\execmodel\desktopappx\sharedlib\custominstallutil.cpp`
- `0x1800275b8`: `onecore\base\appmodel\execmodel\desktopappx\sharedlib\custominstallutil.cpp`
- `0x180027609`: `onecore\base\appmodel\execmodel\desktopappx\sharedlib\custominstallutil.cpp`
- `0x180027654`: `onecore\base\appmodel\execmodel\desktopappx\sharedlib\custominstallutil.cpp`
- `0x180027713`: `onecore\base\appmodel\execmodel\desktopappx\sharedlib\custominstallutil.cpp`
- `0x180027785`: `onecore\base\appmodel\execmodel\desktopappx\sharedlib\custominstallutil.cpp`
- `0x1800277c2`: `onecore\base\appmodel\execmodel\desktopappx\sharedlib\custominstallutil.cpp`
- `0x1800277eb`: `onecore\base\appmodel\execmodel\desktopappx\sharedlib\custominstallutil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
void __fastcall CompleteCustomInstallIfNeeded(unsigned __int16 *a1)
{
  unsigned __int16 *v1; // rbx
  unsigned __int16 *v2; // rdx
  int EffectivePackageStatusForUser; // eax
  const char *v4; // r9
  const unsigned __int16 *v5; // rdi
  const unsigned __int16 *v6; // rcx
  int v7; // eax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  HANDLE CurrentThread; // rax
  BOOL v13; // edi
  const char *v14; // r9
  __int64 v15; // rax
  const char *v16; // r9
  SAFER_LEVEL_HANDLE v17; // rcx
  HINSTANCE v18; // rdi
  const WCHAR *v19; // rax
  const WCHAR *v20; // rax
  const char *v21; // r9
  const char *v22; // r9
  const char *v23; // r9
  const char *v24; // r9
  const char *v25; // r9
  void *lpEnvironment; // rdi
  __int64 v27; // rax
  __int64 v28; // rax
  const WCHAR *v29; // rdx
  const char *v30; // r9
  int v31; // eax
  struct _PROCESS_INFORMATION *v32; // rdx
  int TokenType; // [rsp+20h] [rbp-3E8h]
  unsigned int v34; // [rsp+60h] [rbp-3A8h] BYREF
  void *OutAccessToken; // [rsp+68h] [rbp-3A0h] BYREF
  SAFER_LEVEL_HANDLE pLevelHandle; // [rsp+70h] [rbp-398h] BYREF
  HANDLE hToken; // [rsp+78h] [rbp-390h] BYREF
  void *TokenHandle; // [rsp+80h] [rbp-388h] BYREF
  LPVOID Environment; // [rsp+88h] [rbp-380h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+90h] [rbp-378h] BYREF
  SHELLEXECUTEINFOW pExecInfo; // [rsp+B0h] [rbp-358h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+120h] [rbp-2E8h] BYREF
  LPCWSTR lpApplicationName[3]; // [rsp+190h] [rbp-278h] BYREF
  unsigned __int64 v44; // [rsp+1A8h] [rbp-260h]
  _QWORD v45[4]; // [rsp+1B0h] [rbp-258h] BYREF
  SAFER_LEVEL_HANDLE *p_pLevelHandle; // [rsp+1D0h] [rbp-238h] BYREF
  char v47; // [rsp+1D8h] [rbp-230h]
  _BYTE v48[32]; // [rsp+1F0h] [rbp-218h] BYREF
  _BYTE v49[32]; // [rsp+210h] [rbp-1F8h] BYREF
  _BYTE v50[32]; // [rsp+230h] [rbp-1D8h] BYREF
  _BYTE v51[32]; // [rsp+250h] [rbp-1B8h] BYREF
  _QWORD v52[42]; // [rsp+270h] [rbp-198h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+408h] [rbp+0h]

  v1 = a1;
  v34 = 0;
  if ( *((_QWORD *)a1 + 3) <= 7u )
    v2 = a1;
  else
    v2 = *(unsigned __int16 **)a1;
  EffectivePackageStatusForUser = GetEffectivePackageStatusForUser(0, v2, &v34);
  try
  {
    if ( EffectivePackageStatusForUser >= 0 && (v34 & 0x1800000) != 0 )
    {
      if ( *((_QWORD *)v1 + 3) <= 7u )
        v5 = v1;
      else
        v5 = *(const unsigned __int16 **)v1;
      wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopAppXProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v52);
      v52[0] = &DesktopAppXProvider::PreActivationCustomInstallCompletion::`vftable';
      DesktopAppXProvider::PreActivationCustomInstallCompletion::StartActivity(
        (DesktopAppXProvider::PreActivationCustomInstallCompletion *)v52,
        v5,
        v34);
      if ( *((_QWORD *)v1 + 3) <= 7u )
        v6 = v1;
      else
        v6 = *(const unsigned __int16 **)v1;
      if ( IsPackagePreOrderAndNotAvailable(v6) )
      {
        DesktopAppXProvider::PreActivationCustomInstallCompletion::PreDownloadLicenseNotYetAvailable((DesktopAppXProvider::PreActivationCustomInstallCompletion *)v52);
        wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v52);
        DesktopAppXProvider::PreActivationCustomInstallCompletion::~PreActivationCustomInstallCompletion((DesktopAppXProvider::PreActivationCustomInstallCompletion *)v52);
      }
      else
      {
        std::wstring::wstring(v48);
        v7 = wil::GetSystemDirectoryW<std::wstring,256>(v48);
        if ( v7 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x83,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\custominstallutil.cpp",
            (const char *)(unsigned int)v7,
            TokenType);
        v8 = std::wstring::wstring(v51, v48);
        v9 = std::operator+<unsigned short>(&p_pLevelHandle, v8, L"\\");
        std::operator+<unsigned short>(lpApplicationName, v9, L"custominstallexec.exe");
        std::wstring::_Tidy_deallocate(&p_pLevelHandle);
        std::wstring::_Tidy_deallocate(v51);
        v10 = std::wstring::wstring(v50, L"/install");
        v11 = std::operator+<unsigned short>(v49, v10, L" ");
        std::operator+<unsigned short>(v45, v11, v1);
        std::wstring::_Tidy_deallocate(v49);
        std::wstring::_Tidy_deallocate(v50);
        memset_0(&StartupInfo, 0, 0x70u);
        StartupInfo.cb = 112;
        StartupInfo.dwFlags = 1;
        StartupInfo.wShowWindow = 5;
        memset(&ProcessInformation, 0, sizeof(ProcessInformation));
        TokenHandle = 0;
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          &TokenHandle,
          0);
        CurrentThread = GetCurrentThread();
        v13 = OpenThreadToken(CurrentThread, 2u, 1, &TokenHandle);
        if ( v13 || GetLastError() != 1008 )
        {
          if ( !v13 )
            wil::details::in1diag3::_Throw_GetLastError(
              retaddr,
              (void *)0xA7,
              (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\custominstallutil.cpp",
              v14);
          hToken = 0;
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
            &hToken,
            0);
          if ( !DuplicateTokenEx(TokenHandle, 0x2000000u, 0, SecurityAnonymous, TokenPrimary, &hToken) )
            wil::details::in1diag3::_Throw_GetLastError(
              retaddr,
              (void *)0xAA,
              (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\custominstallutil.cpp",
              v22);
          Environment = 0;
          if ( !CreateEnvironmentBlock(&Environment, hToken, 0) )
            wil::details::in1diag3::_Throw_GetLastError(
              retaddr,
              (void *)0xAC,
              (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\custominstallutil.cpp",
              v23);
          pLevelHandle = 0;
          p_pLevelHandle = &pLevelHandle;
          v47 = 1;
          if ( !SaferCreateLevel(1u, 0x20000u, 1u, &pLevelHandle, 0) )
            wil::details::in1diag3::_Throw_GetLastError(
              retaddr,
              (void *)0xB5,
              (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\custominstallutil.cpp",
              v24);
          OutAccessToken = 0;
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
            &OutAccessToken,
            0);
          if ( !SaferComputeTokenFromLevel(pLevelHandle, hToken, &OutAccessToken, 0, 0) )
            wil::details::in1diag3::_Throw_GetLastError(
              retaddr,
              (void *)0xB8,
              (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\custominstallutil.cpp",
              v25);
          lpEnvironment = Environment;
          v27 = std::operator+<unsigned short>(v49, lpApplicationName);
          v28 = std::operator+<unsigned short>(v50, v27, v45);
          if ( *(_QWORD *)(v28 + 24) > 7u )
            v28 = *(_QWORD *)v28;
          v29 = (const WCHAR *)lpApplicationName;
          if ( v44 > 7 )
            v29 = lpApplicationName[0];
          if ( !CreateProcessAsUserW(
                  OutAccessToken,
                  v29,
                  (LPWSTR)v28,
                  0,
                  0,
                  0,
                  0x80400u,
                  lpEnvironment,
                  0,
                  &StartupInfo,
                  &ProcessInformation) )
            wil::details::in1diag3::_Throw_GetLastError(
              retaddr,
              (void *)0xBA,
              (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\custominstallutil.cpp",
              v30);
          std::wstring::_Tidy_deallocate(v50);
          std::wstring::_Tidy_deallocate(v49);
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&OutAccessToken);
          SaferCloseLevel(pLevelHandle);
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
        }
        else
        {
          OutAccessToken = 0;
          v15 = Microsoft::WRL::Details::Make<SwitchToDesktopImpl,>(&pLevelHandle);
          Microsoft::WRL::ComPtr<SwitchToDesktopImpl>::operator=(&OutAccessToken, v15);
          v17 = pLevelHandle;
          if ( pLevelHandle )
          {
            pLevelHandle = 0;
            (*(void (__fastcall **)(SAFER_LEVEL_HANDLE))(*(_QWORD *)v17 + 16LL))(v17);
          }
          v18 = (HINSTANCE)OutAccessToken;
          if ( !OutAccessToken )
            wil::details::in1diag3::_Throw_NullAlloc(
              retaddr,
              (void *)0x98,
              (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\custominstallutil.cpp",
              v16);
          memset_0(&pExecInfo, 0, sizeof(pExecInfo));
          pExecInfo.cbSize = 112;
          pExecInfo.nShow = 5;
          pExecInfo.fMask = 142606400;
          v19 = (const WCHAR *)lpApplicationName;
          if ( v44 > 7 )
            v19 = lpApplicationName[0];
          pExecInfo.lpFile = v19;
          v20 = (const WCHAR *)v45;
          if ( v45[3] > 7u )
            v20 = (const WCHAR *)v45[0];
          pExecInfo.lpParameters = v20;
          pExecInfo.hInstApp = v18;
          if ( !ShellExecuteExW(&pExecInfo) )
            wil::details::in1diag3::_Throw_GetLastError(
              retaddr,
              (void *)0xA1,
              (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\custominstallutil.cpp",
              v21);
          ProcessInformation.hProcess = pExecInfo.hProcess;
          if ( v18 )
            (*(void (__fastcall **)(HINSTANCE))(*(_QWORD *)v18 + 16LL))(v18);
        }
        if ( WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF) )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xBD,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\custominstallutil.cpp",
            (const char *)0x80004005LL,
            TokenType);
        if ( *((_QWORD *)v1 + 3) > 7u )
          v1 = *(unsigned __int16 **)v1;
        v31 = GetEffectivePackageStatusForUser(0, v1, &v34);
        if ( v31 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xC0,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\custominstallutil.cpp",
            (const char *)(unsigned int)v31,
            TokenType);
        if ( (v34 & 0x1800000) != 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xC1,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\custominstallutil.cpp",
            (const char *)0x80004005LL,
            TokenType);
        wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v52);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
        wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v32);
        std::wstring::_Tidy_deallocate(v45);
        std::wstring::_Tidy_deallocate(lpApplicationName);
        std::wstring::_Tidy_deallocate(v48);
        DesktopAppXProvider::PreActivationCustomInstallCompletion::~PreActivationCustomInstallCompletion((DesktopAppXProvider::PreActivationCustomInstallCompletion *)v52);
      }
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xC7,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\custominstallutil.cpp",
      v4);
  }
}

```

## disassembly

```asm
0x180027174  push    rbx
0x180027176  push    rsi
0x180027177  push    rdi
0x180027178  push    r13
0x18002717a  push    r14
0x18002717c  push    r15
0x18002717e  sub     rsp, 3D8h
0x180027185  mov     rax, cs:__security_cookie
0x18002718c  xor     rax, rsp
0x18002718f  mov     [rsp+408h+var_48], rax
0x180027197  mov     rbx, rcx
0x18002719a  xor     r14d, r14d
0x18002719d  mov     [rsp+408h+var_3A8], r14d
0x1800271a2  cmp     qword ptr [rcx+18h], 7
0x1800271a7  jbe     short loc_1800271AE
0x1800271a9  mov     rdx, [rcx]
0x1800271ac  jmp     short loc_1800271B1
0x1800271ae  mov     rdx, rbx
0x1800271b1  lea     r8, [rsp+408h+var_3A8]
0x1800271b6  xor     ecx, ecx
0x1800271b8  call    cs:__imp_GetEffectivePackageStatusForUser
0x1800271be  test    eax, eax
0x1800271c0  js      loc_18002785E
0x1800271c6  test    [rsp+408h+var_3A8], 1800000h
0x1800271ce  jz      loc_18002785E
0x1800271d4  cmp     qword ptr [rbx+18h], 7
0x1800271d9  jbe     short loc_1800271E0
0x1800271db  mov     rdi, [rbx]
0x1800271de  jmp     short loc_1800271E3
0x1800271e0  mov     rdi, rbx
0x1800271e3  lea     rcx, [rsp+408h+var_198]; struct wil::details::IFailureCallback *
0x1800271eb  call    ??0?$ActivityBase@VDesktopAppXProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopAppXProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800271f0  lea     rax, ??_7PreActivationCustomInstallCompletion@DesktopAppXProvider@@6B@; const DesktopAppXProvider::PreActivationCustomInstallCompletion::`vftable'
0x1800271f7  mov     [rsp+408h+var_198], rax
0x1800271ff  mov     r8d, [rsp+408h+var_3A8]; unsigned int
0x180027204  mov     rdx, rdi; unsigned __int16 *
0x180027207  lea     rcx, [rsp+408h+var_198]; this
0x18002720f  call    ?StartActivity@PreActivationCustomInstallCompletion@DesktopAppXProvider@@QEAAXPEBGI@Z; DesktopAppXProvider::PreActivationCustomInstallCompletion::StartActivity(ushort const *,uint)
0x180027214  nop
0x180027215  cmp     qword ptr [rbx+18h], 7
0x18002721a  jbe     short loc_180027221
0x18002721c  mov     rcx, [rbx]
0x18002721f  jmp     short loc_180027224
0x180027221  mov     rcx, rbx; unsigned __int16 *
0x180027224  call    ?IsPackagePreOrderAndNotAvailable@@YA_NPEBG@Z; IsPackagePreOrderAndNotAvailable(ushort const *)
0x180027229  test    al, al
0x18002722b  jz      short loc_18002725B
0x18002722d  lea     rcx, [rsp+408h+var_198]; this
0x180027235  call    ?PreDownloadLicenseNotYetAvailable@PreActivationCustomInstallCompletion@DesktopAppXProvider@@QEAAXXZ; DesktopAppXProvider::PreActivationCustomInstallCompletion::PreDownloadLicenseNotYetAvailable(void)
0x18002723a  lea     rcx, [rsp+408h+var_198]
0x180027242  call    ?Stop@?$ActivityBase@VDesktopAppXProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180027247  nop
0x180027248  lea     rcx, [rsp+408h+var_198]; this
0x180027250  call    ??1PreActivationCustomInstallCompletion@DesktopAppXProvider@@QEAA@XZ; DesktopAppXProvider::PreActivationCustomInstallCompletion::~PreActivationCustomInstallCompletion(void)
0x180027255  nop
0x180027256  jmp     loc_180027860
0x18002725b  lea     rcx, [rsp+408h+var_218]; void *
0x180027263  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180027268  nop
0x180027269  lea     rcx, [rsp+408h+var_218]
0x180027271  call    ??$GetSystemDirectoryW@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0BAA@@wil@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; wil::GetSystemDirectoryW<std::wstring,256>(std::wstring &)
0x180027276  mov     rcx, [rsp+408h]; this
0x18002727e  test    eax, eax
0x180027280  jns     short loc_180027296
0x180027282  mov     r9d, eax; char *
0x180027285  lea     r8, aOnecoreBaseApp_2; "onecore\\base\\appmodel\\execmodel\\des"...
0x18002728c  mov     edx, 83h; void *
0x180027291  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180027296  lea     rdx, [rsp+408h+var_218]
0x18002729e  lea     rcx, [rsp+408h+var_1B8]
0x1800272a6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800272ab  nop
0x1800272ac  lea     r8, asc_1800AC0E4; "\\"
0x1800272b3  mov     rdx, rax
0x1800272b6  lea     rcx, [rsp+408h+var_238]
0x1800272be  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800272c3  nop
0x1800272c4  lea     r8, aCustominstalle; "custominstallexec.exe"
0x1800272cb  mov     rdx, rax
0x1800272ce  lea     rcx, [rsp+408h+lpApplicationName]
0x1800272d6  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800272db  nop
0x1800272dc  lea     rcx, [rsp+408h+var_238]
0x1800272e4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800272e9  nop
0x1800272ea  lea     rcx, [rsp+408h+var_1B8]
0x1800272f2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800272f7  lea     rdx, aInstall; "/install"
0x1800272fe  lea     rcx, [rsp+408h+var_1D8]
0x180027306  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002730b  nop
0x18002730c  lea     r8, asc_1800AC0B0; " "
0x180027313  mov     rdx, rax
0x180027316  lea     rcx, [rsp+408h+var_1F8]
0x18002731e  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180027323  nop
0x180027324  mov     r8, rbx
0x180027327  mov     rdx, rax
0x18002732a  lea     rcx, [rsp+408h+var_258]
0x180027332  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x180027337  nop
0x180027338  lea     rcx, [rsp+408h+var_1F8]
0x180027340  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180027345  nop
0x180027346  lea     rcx, [rsp+408h+var_1D8]
0x18002734e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180027353  mov     r15d, 70h ; 'p'
0x180027359  mov     r8d, r15d; Size
0x18002735c  xor     edx, edx; Val
0x18002735e  lea     rcx, [rsp+408h+StartupInfo]; void *
0x180027366  call    memset_0
0x18002736b  mov     [rsp+408h+StartupInfo.cb], r15d
0x180027373  lea     esi, [r15-6Fh]
0x180027377  mov     [rsp+408h+StartupInfo.dwFlags], esi
0x18002737e  lea     r13d, [r15-6Bh]
0x180027382  mov     [rsp+408h+StartupInfo.wShowWindow], r13w
0x18002738b  xorps   xmm0, xmm0
0x18002738e  xor     eax, eax
0x180027390  movups  xmmword ptr [rsp+408h+ProcessInformation.hProcess], xmm0
0x180027398  mov     qword ptr [rsp+408h+ProcessInformation.dwProcessId], rax
0x1800273a0  mov     [rsp+408h+TokenHandle], r14
0x1800273a8  xor     edx, edx
0x1800273aa  lea     rcx, [rsp+408h+TokenHandle]
0x1800273b2  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800273b7  call    cs:__imp_GetCurrentThread
0x1800273bd  lea     r9, [rsp+408h+TokenHandle]; TokenHandle
0x1800273c5  mov     r8d, esi; OpenAsSelf
0x1800273c8  lea     edx, [rsi+1]; DesiredAccess
0x1800273cb  mov     rcx, rax; ThreadHandle
0x1800273ce  call    cs:__imp_OpenThreadToken
0x1800273d4  mov     edi, eax
0x1800273d6  test    eax, eax
0x1800273d8  jnz     loc_18002751C
0x1800273de  call    cs:__imp_GetLastError
0x1800273e4  cmp     eax, 3F0h
0x1800273e9  jnz     loc_18002751C
0x1800273ef  mov     [rsp+408h+OutAccessToken], r14
0x1800273f4  lea     rcx, [rsp+408h+pLevelHandle]
0x1800273f9  call    ??$Make@VSwitchToDesktopImpl@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VSwitchToDesktopImpl@@@12@XZ; Microsoft::WRL::Details::Make<SwitchToDesktopImpl,>(void)
0x1800273fe  mov     rdx, rax
0x180027401  lea     rcx, [rsp+408h+OutAccessToken]
0x180027406  call    ??4?$ComPtr@VSwitchToDesktopImpl@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<SwitchToDesktopImpl>::operator=(Microsoft::WRL::ComPtr<SwitchToDesktopImpl> &&)
0x18002740b  nop
0x18002740c  mov     rcx, [rsp+408h+pLevelHandle]
0x180027411  test    rcx, rcx
0x180027414  jz      short loc_180027428
0x180027416  mov     [rsp+408h+pLevelHandle], r14
0x18002741b  mov     rax, [rcx]
0x18002741e  mov     rax, [rax+10h]
0x180027422  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027427  nop
0x180027428  mov     rcx, [rsp+408h]; this
0x180027430  mov     rdi, [rsp+408h+OutAccessToken]
0x180027435  test    rdi, rdi
0x180027438  jnz     short loc_18002744B
0x18002743a  lea     r8, aOnecoreBaseApp_2; "onecore\\base\\appmodel\\execmodel\\des"...
0x180027441  mov     edx, 98h; void *
0x180027446  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18002744b  mov     r8, r15; Size
0x18002744e  xor     edx, edx; Val
0x180027450  lea     rcx, [rsp+408h+pExecInfo]; void *
0x180027458  call    memset_0
0x18002745d  mov     [rsp+408h+pExecInfo.cbSize], r15d
0x180027465  mov     [rsp+408h+pExecInfo.nShow], r13d
0x18002746d  mov     [rsp+408h+pExecInfo.fMask], 8800040h
0x180027478  lea     rax, [rsp+408h+lpApplicationName]
0x180027480  cmp     [rsp+408h+var_260], 7
0x180027489  cmova   rax, [rsp+408h+lpApplicationName]
0x180027492  mov     [rsp+408h+pExecInfo.lpFile], rax
0x18002749a  lea     rax, [rsp+408h+var_258]
0x1800274a2  cmp     [rsp+408h+var_240], 7
0x1800274ab  cmova   rax, [rsp+408h+var_258]
0x1800274b4  mov     [rsp+408h+pExecInfo.lpParameters], rax
0x1800274bc  mov     [rsp+408h+pExecInfo.hInstApp], rdi
0x1800274c4  mov     rsi, [rsp+408h]
0x1800274cc  lea     rcx, [rsp+408h+pExecInfo]; pExecInfo
0x1800274d4  call    cs:__imp_ShellExecuteExW
0x1800274da  test    eax, eax
0x1800274dc  jnz     short loc_1800274F2
0x1800274de  lea     r8, aOnecoreBaseApp_2; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800274e5  mov     edx, 0A1h; void *
0x1800274ea  mov     rcx, rsi; this
0x1800274ed  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800274f2  mov     rax, [rsp+408h+pExecInfo.hProcess]
0x1800274fa  mov     [rsp+408h+ProcessInformation.hProcess], rax
0x180027502  test    rdi, rdi
0x180027505  jz      short loc_180027517
0x180027507  mov     rax, [rdi]
0x18002750a  mov     rcx, rdi
0x18002750d  mov     rax, [rax+10h]
0x180027511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027516  nop
0x180027517  jmp     loc_180027762
0x18002751c  mov     rcx, [rsp+408h]; this
0x180027524  test    edi, edi
0x180027526  jnz     short loc_180027539
0x180027528  lea     r8, aOnecoreBaseApp_2; "onecore\\base\\appmodel\\execmodel\\des"...
0x18002752f  mov     edx, 0A7h; void *
0x180027534  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180027539  mov     [rsp+408h+hToken], r14
0x18002753e  xor     edx, edx
0x180027540  lea     rcx, [rsp+408h+hToken]
0x180027545  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18002754a  lea     rax, [rsp+408h+hToken]
0x18002754f  mov     [rsp+408h+phNewToken], rax; phNewToken
0x180027554  mov     [rsp+408h+TokenType], esi; TokenType
0x180027558  xor     r9d, r9d; ImpersonationLevel
0x18002755b  xor     r8d, r8d; lpTokenAttributes
0x18002755e  mov     edx, 2000000h; dwDesiredAccess
0x180027563  mov     rcx, [rsp+408h+TokenHandle]; hExistingToken
0x18002756b  call    cs:__imp_DuplicateTokenEx
0x180027571  mov     rcx, [rsp+408h]; this
0x180027579  test    eax, eax
0x18002757b  jnz     short loc_18002758E
0x18002757d  lea     r8, aOnecoreBaseApp_2; "onecore\\base\\appmodel\\execmodel\\des"...
0x180027584  mov     edx, 0AAh; void *
0x180027589  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18002758e  mov     [rsp+408h+Environment], r14
0x180027596  xor     r8d, r8d; bInherit
0x180027599  mov     rdx, [rsp+408h+hToken]; hToken
0x18002759e  lea     rcx, [rsp+408h+Environment]; lpEnvironment
0x1800275a6  call    cs:__imp_CreateEnvironmentBlock
0x1800275ac  mov     rcx, [rsp+408h]; this
0x1800275b4  test    eax, eax
0x1800275b6  jnz     short loc_1800275C9
0x1800275b8  lea     r8, aOnecoreBaseApp_2; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800275bf  mov     edx, 0ACh; void *
0x1800275c4  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800275c9  mov     [rsp+408h+pLevelHandle], r14
0x1800275ce  lea     rax, [rsp+408h+pLevelHandle]
0x1800275d3  mov     [rsp+408h+var_238], rax
0x1800275db  mov     [rsp+408h+var_230], sil
0x1800275e3  mov     qword ptr [rsp+408h+TokenType], r14; lpReserved
0x1800275e8  lea     r9, [rsp+408h+pLevelHandle]; pLevelHandle
0x1800275ed  mov     r8d, esi; OpenFlags
0x1800275f0  mov     edx, 20000h; dwLevelId
0x1800275f5  mov     ecx, esi; dwScopeId
0x1800275f7  call    cs:__imp_SaferCreateLevel
0x1800275fd  mov     rcx, [rsp+408h]; this
0x180027605  test    eax, eax
0x180027607  jnz     short loc_18002761A
0x180027609  lea     r8, aOnecoreBaseApp_2; "onecore\\base\\appmodel\\execmodel\\des"...
0x180027610  mov     edx, 0B5h; void *
0x180027615  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18002761a  mov     [rsp+408h+OutAccessToken], r14
0x18002761f  xor     edx, edx
0x180027621  lea     rcx, [rsp+408h+OutAccessToken]
0x180027626  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18002762b  mov     qword ptr [rsp+408h+TokenType], r14; lpReserved
0x180027630  xor     r9d, r9d; dwFlags
0x180027633  lea     r8, [rsp+408h+OutAccessToken]; OutAccessToken
0x180027638  mov     rdx, [rsp+408h+hToken]; InAccessToken
0x18002763d  mov     rcx, [rsp+408h+pLevelHandle]; LevelHandle
0x180027642  call    cs:__imp_SaferComputeTokenFromLevel
0x180027648  mov     rcx, [rsp+408h]; this
0x180027650  test    eax, eax
0x180027652  jnz     short loc_180027665
0x180027654  lea     r8, aOnecoreBaseApp_2; "onecore\\base\\appmodel\\execmodel\\des"...
0x18002765b  mov     edx, 0B8h; void *
0x180027660  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180027665  mov     rdi, [rsp+408h+Environment]
0x18002766d  lea     rdx, [rsp+408h+lpApplicationName]
0x180027675  lea     rcx, [rsp+408h+var_1F8]
0x18002767d  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x180027682  nop
0x180027683  lea     r8, [rsp+408h+var_258]
0x18002768b  mov     rdx, rax
0x18002768e  lea     rcx, [rsp+408h+var_1D8]
0x180027696  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x18002769b  nop
0x18002769c  cmp     qword ptr [rax+18h], 7
0x1800276a1  jbe     short loc_1800276A6
0x1800276a3  mov     rax, [rax]
0x1800276a6  lea     rdx, [rsp+408h+lpApplicationName]
0x1800276ae  cmp     [rsp+408h+var_260], 7
0x1800276b7  cmova   rdx, [rsp+408h+lpApplicationName]; lpApplicationName
0x1800276c0  lea     rcx, [rsp+408h+ProcessInformation]
0x1800276c8  mov     [rsp+408h+lpProcessInformation], rcx; lpProcessInformation
0x1800276cd  lea     rcx, [rsp+408h+StartupInfo]
0x1800276d5  mov     [rsp+408h+lpStartupInfo], rcx; lpStartupInfo
0x1800276da  mov     [rsp+408h+lpCurrentDirectory], r14; lpCurrentDirectory
0x1800276df  mov     [rsp+408h+lpEnvironment], rdi; lpEnvironment
0x1800276e4  mov     [rsp+408h+dwCreationFlags], 80400h; dwCreationFlags
0x1800276ec  mov     dword ptr [rsp+408h+phNewToken], r14d; bInheritHandles
0x1800276f1  mov     qword ptr [rsp+408h+TokenType], r14; int
0x1800276f6  xor     r9d, r9d; lpProcessAttributes
0x1800276f9  mov     r8, rax; lpCommandLine
0x1800276fc  mov     rcx, [rsp+408h+OutAccessToken]; hToken
0x180027701  call    cs:__imp_CreateProcessAsUserW
0x180027707  mov     rcx, [rsp+408h]; this
0x18002770f  test    eax, eax
0x180027711  jnz     short loc_180027725
0x180027713  lea     r8, aOnecoreBaseApp_2; "onecore\\base\\appmodel\\execmodel\\des"...
0x18002771a  mov     edx, 0BAh; void *
0x18002771f  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180027725  lea     rcx, [rsp+408h+var_1D8]
0x18002772d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180027732  nop
0x180027733  lea     rcx, [rsp+408h+var_1F8]
0x18002773b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
  ... truncated ...
```
