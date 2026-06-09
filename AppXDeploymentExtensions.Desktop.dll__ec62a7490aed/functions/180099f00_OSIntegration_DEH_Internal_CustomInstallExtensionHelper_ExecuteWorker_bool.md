# OSIntegration::DEH::Internal::CustomInstallExtensionHelper::ExecuteWorker(bool)

- ea: `0x180099f00`
- end: `0x18009a571`
- name: `?ExecuteWorker@CustomInstallExtensionHelper@Internal@DEH@OSIntegration@@IEAAX_N@Z`
- size: `1649`
- prototype: `void __fastcall(OSIntegration::DEH::Internal::CustomInstallExtensionHelper *this, char)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180097618`
- `0x1800eedc0`

## callees

- `0x18003d9b0`
- `0x18004ce78`
- `0x18004e96c`
- `0x18005174c`
- `0x1800529ec`
- `0x180064a88`
- `0x180072114`
- `0x180099f00`
- `0x18009a578`
- `0x18009a59c`
- `0x18009a5e0`
- `0x18009a72c`
- `0x1800af1bc`
- `0x1800af918`
- `0x1800ef2ec`
- `0x1800ef318`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009a416`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009a416`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18009a1a5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18009a1a5`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18009a486`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18009a486`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18009a3e2`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18009a3e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18009a18b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18009a18b`
- `USERENV!CreateEnvironmentBlock` at `0x18009a286`
- `USERENV!CreateEnvironmentBlock` at `0x18009a286`
- `ext-ms-win-advapi32-safer-l1-1-0!SaferComputeTokenFromLevel` at `0x18009a330`
- `ext-ms-win-advapi32-safer-l1-1-0!SaferComputeTokenFromLevel` at `0x18009a330`
- `ext-ms-win-advapi32-safer-l1-1-0!SaferCloseLevel` at `0x18009a4f4`
- `ext-ms-win-advapi32-safer-l1-1-0!SaferCloseLevel` at `0x18009a4f4`
- `ext-ms-win-advapi32-safer-l1-1-0!SaferCreateLevel` at `0x18009a2dc`
- `ext-ms-win-advapi32-safer-l1-1-0!SaferCreateLevel` at `0x18009a2dc`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18009a244`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18009a244`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18009a1f9`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18009a1f9`

## string_xrefs

- `0x18009a455`: `Wait For Custom Install Worker Process failed!`
- `0x180099fad`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\dehlib\custominstallextensionhelper.cpp`
- `0x180099fe2`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\dehlib\custominstallextensionhelper.cpp`
- `0x18009a016`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\dehlib\custominstallextensionhelper.cpp`
- `0x18009a058`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\dehlib\custominstallextensionhelper.cpp`
- `0x18009a08c`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\dehlib\custominstallextensionhelper.cpp`
- `0x18009a0c4`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\dehlib\custominstallextensionhelper.cpp`
- `0x18009a0f8`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\dehlib\custominstallextensionhelper.cpp`
- `0x18009a137`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\dehlib\custominstallextensionhelper.cpp`
- `0x18009a1bd`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\dehlib\custominstallextensionhelper.cpp`
- `0x18009a214`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\dehlib\custominstallextensionhelper.cpp`
- `0x18009a25f`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\dehlib\custominstallextensionhelper.cpp`
- `0x18009a29e`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\dehlib\custominstallextensionhelper.cpp`
- `0x18009a2f4`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\dehlib\custominstallextensionhelper.cpp`
- `0x18009a348`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\dehlib\custominstallextensionhelper.cpp`
- `0x18009a3fa`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\dehlib\custominstallextensionhelper.cpp`
- `0x18009a42a`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\dehlib\custominstallextensionhelper.cpp`
- `0x18009a49e`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\dehlib\custominstallextensionhelper.cpp`
- `0x18009a4c4`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\dehlib\custominstallextensionhelper.cpp`
- `0x18009a027`: `/uninstall`
- `0x18009a02e`: `/install`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall OSIntegration::DEH::Internal::CustomInstallExtensionHelper::ExecuteWorker(
        OSIntegration::DEH::Internal::CustomInstallExtensionHelper *this,
        char a2)
{
  const unsigned __int16 *CustomInstallExecPath; // rax
  int appended; // eax
  const unsigned __int16 *v6; // rax
  int v7; // eax
  int v8; // eax
  const unsigned __int16 *v9; // rdx
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int inserted; // eax
  HANDLE CurrentThread; // rax
  const char *v16; // r9
  int v17; // eax
  int v18; // eax
  const char *v19; // r9
  const char *v20; // r9
  struct _PROCESS_INFORMATION *v21; // rdx
  const char *v22; // r9
  const char *v23; // r9
  DWORD v24; // eax
  struct _PROCESS_INFORMATION *v25; // rdx
  const char *v26; // r9
  const struct std::nothrow_t *v27; // rdx
  const char *v28; // r9
  int lpReserved; // [rsp+20h] [rbp-178h]
  int lpReserveda; // [rsp+20h] [rbp-178h]
  unsigned int lpReservedb; // [rsp+20h] [rbp-178h]
  const char *bInheritHandles; // [rsp+28h] [rbp-170h]
  void *OutAccessToken; // [rsp+60h] [rbp-138h] BYREF
  SAFER_LEVEL_HANDLE pLevelHandle; // [rsp+68h] [rbp-130h] BYREF
  void *TokenHandle; // [rsp+70h] [rbp-128h] BYREF
  LPVOID Environment; // [rsp+78h] [rbp-120h] BYREF
  void **v37; // [rsp+80h] [rbp-118h] BYREF
  unsigned int *v38; // [rsp+88h] [rbp-110h]
  LPWSTR *v39; // [rsp+90h] [rbp-108h]
  __int64 v40; // [rsp+98h] [rbp-100h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+A0h] [rbp-F8h] BYREF
  LPWSTR lpCommandLine[2]; // [rsp+B8h] [rbp-E0h] BYREF
  int v43; // [rsp+C8h] [rbp-D0h]
  LPCWSTR lpApplicationName[2]; // [rsp+D0h] [rbp-C8h] BYREF
  int v45; // [rsp+E0h] [rbp-B8h]
  _BYTE v46[8]; // [rsp+E8h] [rbp-B0h] BYREF
  _QWORD v47[4]; // [rsp+F0h] [rbp-A8h] BYREF
  char v48; // [rsp+110h] [rbp-88h]
  struct _STARTUPINFOW StartupInfo; // [rsp+120h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+0h]
  DWORD ExitCode; // [rsp+1B0h] [rbp+18h] BYREF
  HANDLE hToken; // [rsp+1B8h] [rbp+20h] BYREF

  *(_OWORD *)lpApplicationName = 0;
  v45 = 0;
  *(_OWORD *)lpCommandLine = 0;
  v43 = 0;
  v47[1] = lpApplicationName;
  v47[0] = &Common::StringBufferBuilder::`vftable';
  v47[2] = lpApplicationName;
  v38 = (unsigned int *)lpCommandLine;
  v37 = &Common::StringBufferBuilder::`vftable';
  v39 = lpCommandLine;
  try
  {
    CustomInstallExecPath = OSIntegration::DEH::Internal::CustomInstallExtensionHelper::GetCustomInstallExecPath();
    appended = Common::StringBuilder::AppendString((Common::StringBuilder *)v47, CustomInstallExecPath);
    if ( appended < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x165,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\dehlib\\custominstallextensionhelper.cpp",
        (const char *)(unsigned int)appended,
        lpReserved);
    v6 = OSIntegration::DEH::Internal::CustomInstallExtensionHelper::GetCustomInstallExecPath();
    v7 = Common::StringBuilder::AppendString((Common::StringBuilder *)&v37, v6);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x167,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\dehlib\\custominstallextensionhelper.cpp",
        (const char *)(unsigned int)v7,
        lpReserved);
    v8 = Common::StringBuilder::AppendString((Common::StringBuilder *)&v37, L" ");
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x168,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\dehlib\\custominstallextensionhelper.cpp",
        (const char *)(unsigned int)v8,
        lpReserved);
    v9 = L"/install";
    if ( !a2 )
      v9 = L"/uninstall";
    v10 = Common::StringBuilder::AppendString((Common::StringBuilder *)&v37, v9);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x169,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\dehlib\\custominstallextensionhelper.cpp",
        (const char *)(unsigned int)v10,
        lpReserved);
    v11 = Common::StringBuilder::AppendString((Common::StringBuilder *)&v37, L" ");
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x16A,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\dehlib\\custominstallextensionhelper.cpp",
        (const char *)(unsigned int)v11,
        lpReserved);
    v12 = Common::StringBuilder::AppendString(
            (Common::StringBuilder *)&v37,
            *(const unsigned __int16 **)(*((_QWORD *)this + 2) + 224LL));
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x16B,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\dehlib\\custominstallextensionhelper.cpp",
        (const char *)(unsigned int)v12,
        lpReserved);
    v13 = Common::StringBuilder::AppendString((Common::StringBuilder *)&v37, L" ");
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x16D,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\dehlib\\custominstallextensionhelper.cpp",
        (const char *)(unsigned int)v13,
        lpReserved);
    inserted = Common::StringBuilder::InsertInt64(
                 (Common::StringBuilder *)&v37,
                 *v38,
                 *(_QWORD *)(*((_QWORD *)this + 1) + 8LL));
    if ( inserted < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x16E,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\dehlib\\custominstallextensionhelper.cpp",
        (const char *)(unsigned int)inserted,
        lpReserved);
    memset_0(&StartupInfo, 0, 0x70u);
    StartupInfo.cb = 112;
    StartupInfo.dwFlags = 1;
    StartupInfo.wShowWindow = 0;
    TokenHandle = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &TokenHandle,
      0);
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 0xAu, 1, &TokenHandle) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x17C,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\dehlib\\custominstallextensionhelper.cpp",
        v16);
    wil::impersonate_token(v46);
    v40 = 0;
    hToken = 0;
    v17 = UMgrQueryUserContext(TokenHandle, &v40);
    if ( v17 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x185,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\dehlib\\custominstallextensionhelper.cpp",
        (const char *)(unsigned int)v17,
        lpReserved);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &hToken,
      0);
    v18 = UMgrQueryUserToken(v40, &hToken);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x186,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\dehlib\\custominstallextensionhelper.cpp",
        (const char *)(unsigned int)v18,
        lpReserved);
    Environment = 0;
    if ( !CreateEnvironmentBlock(&Environment, hToken, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x189,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\dehlib\\custominstallextensionhelper.cpp",
        v19);
    pLevelHandle = 0;
    v47[3] = &pLevelHandle;
    v48 = 1;
    if ( !SaferCreateLevel(1u, 0x20000u, 1u, &pLevelHandle, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x192,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\dehlib\\custominstallextensionhelper.cpp",
        v20);
    OutAccessToken = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &OutAccessToken,
      0);
    if ( !SaferComputeTokenFromLevel(pLevelHandle, hToken, &OutAccessToken, 0, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x195,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\dehlib\\custominstallextensionhelper.cpp",
        v22);
    memset(&ProcessInformation, 0, sizeof(ProcessInformation));
    wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v21);
    memset(&ProcessInformation, 0, sizeof(ProcessInformation));
    if ( !CreateProcessAsUserW(
            OutAccessToken,
            lpApplicationName[1],
            lpCommandLine[1],
            0,
            0,
            0,
            0x80400u,
            Environment,
            0,
            &StartupInfo,
            &ProcessInformation) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x199,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\dehlib\\custominstallextensionhelper.cpp",
        v23);
    v24 = WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF);
    if ( v24 == 128 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x19C,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\dehlib\\custominstallextensionhelper.cpp",
        (const char *)0x800703E3LL,
        lpReserveda);
    wil::details::in1diag3::Throw_GetLastErrorIfMsg(
      retaddr,
      (void *)0x19D,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\dehlib\\custominstallextensionhelper.cpp",
      (const char *)(v24 != 0),
      (bool)"Wait For Custom Install Worker Process failed!",
      bInheritHandles);
    ExitCode = 0;
    if ( !GetExitCodeProcess(ProcessInformation.hProcess, &ExitCode) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x1A0,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\dehlib\\custominstallextensionhelper.cpp",
        v26);
    if ( ExitCode )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x1A1,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\dehlib\\custominstallextensionhelper.cpp",
        (const char *)ExitCode,
        lpReservedb);
    wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v25);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&OutAccessToken);
    SaferCloseLevel(pLevelHandle);
    wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int DestroyEnvironmentBlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int DestroyEnvironmentBlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Environment);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v46);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    if ( lpCommandLine[1] )
      operator delete(lpCommandLine[1], v27);
    if ( lpApplicationName[1] )
      operator delete((void *)lpApplicationName[1], v27);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x1A3,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\dehlib\\custominstallextensionhelper.cpp",
      v28);
  }
}

```

## disassembly

```asm
0x180099f00  mov     r11, rsp
0x180099f03  mov     [r11+8], rbx
0x180099f07  mov     [r11+10h], rsi
0x180099f0b  push    rdi
0x180099f0c  sub     rsp, 190h
0x180099f13  mov     dil, dl
0x180099f16  mov     rbx, rcx
0x180099f19  xor     esi, esi
0x180099f1b  xorps   xmm0, xmm0
0x180099f1e  movups  xmmword ptr [rsp+198h+lpApplicationName], xmm0
0x180099f26  mov     [rsp+198h+var_B8], esi
0x180099f2d  movups  xmmword ptr [rsp+198h+lpCommandLine], xmm0
0x180099f35  mov     [rsp+198h+var_D0], esi
0x180099f3c  lea     rax, [r11-0C8h]
0x180099f43  mov     [r11-0A0h], rax
0x180099f4a  lea     rcx, ??_7StringBufferBuilder@Common@@6B@; const Common::StringBufferBuilder::`vftable'
0x180099f51  mov     [r11-0A8h], rcx
0x180099f58  lea     rax, [r11-0C8h]
0x180099f5f  mov     [r11-98h], rax
0x180099f66  lea     rax, [r11-0E0h]
0x180099f6d  mov     [r11-110h], rax
0x180099f74  mov     [r11-118h], rcx
0x180099f7b  lea     rax, [r11-0E0h]
0x180099f82  mov     [r11-108h], rax
0x180099f89  call    ?GetCustomInstallExecPath@CustomInstallExtensionHelper@Internal@DEH@OSIntegration@@KAPEBGXZ; OSIntegration::DEH::Internal::CustomInstallExtensionHelper::GetCustomInstallExecPath(void)
0x180099f8e  mov     rdx, rax; unsigned __int16 *
0x180099f91  lea     rcx, [rsp+198h+var_A8]; this
0x180099f99  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x180099f9e  mov     rcx, [rsp+198h]; this
0x180099fa6  test    eax, eax
0x180099fa8  jns     short loc_180099FBE
0x180099faa  mov     r9d, eax; char *
0x180099fad  lea     r8, aOnecoreAdminAp_71; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180099fb4  mov     edx, 165h; void *
0x180099fb9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180099fbe  call    ?GetCustomInstallExecPath@CustomInstallExtensionHelper@Internal@DEH@OSIntegration@@KAPEBGXZ; OSIntegration::DEH::Internal::CustomInstallExtensionHelper::GetCustomInstallExecPath(void)
0x180099fc3  mov     rdx, rax; unsigned __int16 *
0x180099fc6  lea     rcx, [rsp+198h+var_118]; this
0x180099fce  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x180099fd3  mov     rcx, [rsp+198h]; this
0x180099fdb  test    eax, eax
0x180099fdd  jns     short loc_180099FF3
0x180099fdf  mov     r9d, eax; char *
0x180099fe2  lea     r8, aOnecoreAdminAp_71; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180099fe9  mov     edx, 167h; void *
0x180099fee  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180099ff3  lea     rdx, asc_1801D0E40; " "
0x180099ffa  lea     rcx, [rsp+198h+var_118]; this
0x18009a002  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x18009a007  mov     rcx, [rsp+198h]; this
0x18009a00f  test    eax, eax
0x18009a011  jns     short loc_18009A027
0x18009a013  mov     r9d, eax; char *
0x18009a016  lea     r8, aOnecoreAdminAp_71; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18009a01d  mov     edx, 168h; void *
0x18009a022  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009a027  lea     rax, aUninstall_0; "/uninstall"
0x18009a02e  lea     rdx, aInstall_0; "/install"
0x18009a035  test    dil, dil
0x18009a038  cmovz   rdx, rax; unsigned __int16 *
0x18009a03c  lea     rcx, [rsp+198h+var_118]; this
0x18009a044  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x18009a049  mov     rcx, [rsp+198h]; this
0x18009a051  test    eax, eax
0x18009a053  jns     short loc_18009A069
0x18009a055  mov     r9d, eax; char *
0x18009a058  lea     r8, aOnecoreAdminAp_71; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18009a05f  mov     edx, 169h; void *
0x18009a064  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009a069  lea     rdx, asc_1801D0E40; " "
0x18009a070  lea     rcx, [rsp+198h+var_118]; this
0x18009a078  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x18009a07d  mov     rcx, [rsp+198h]; this
0x18009a085  test    eax, eax
0x18009a087  jns     short loc_18009A09D
0x18009a089  mov     r9d, eax; char *
0x18009a08c  lea     r8, aOnecoreAdminAp_71; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18009a093  mov     edx, 16Ah; void *
0x18009a098  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009a09d  mov     rdx, [rbx+10h]
0x18009a0a1  mov     rdx, [rdx+0E0h]; unsigned __int16 *
0x18009a0a8  lea     rcx, [rsp+198h+var_118]; this
0x18009a0b0  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x18009a0b5  mov     rcx, [rsp+198h]; this
0x18009a0bd  test    eax, eax
0x18009a0bf  jns     short loc_18009A0D5
0x18009a0c1  mov     r9d, eax; char *
0x18009a0c4  lea     r8, aOnecoreAdminAp_71; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18009a0cb  mov     edx, 16Bh; void *
0x18009a0d0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009a0d5  lea     rdx, asc_1801D0E40; " "
0x18009a0dc  lea     rcx, [rsp+198h+var_118]; this
0x18009a0e4  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x18009a0e9  mov     rcx, [rsp+198h]; this
0x18009a0f1  test    eax, eax
0x18009a0f3  jns     short loc_18009A109
0x18009a0f5  mov     r9d, eax; char *
0x18009a0f8  lea     r8, aOnecoreAdminAp_71; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18009a0ff  mov     edx, 16Dh; void *
0x18009a104  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009a109  mov     r8, [rbx+8]
0x18009a10d  mov     r8, [r8+8]; __int64
0x18009a111  mov     rdx, [rsp+198h+var_110]
0x18009a119  mov     edx, [rdx]; unsigned int
0x18009a11b  lea     rcx, [rsp+198h+var_118]; this
0x18009a123  call    ?InsertInt64@StringBuilder@Common@@QEAAJK_J@Z; Common::StringBuilder::InsertInt64(ulong,__int64)
0x18009a128  mov     rcx, [rsp+198h]; this
0x18009a130  test    eax, eax
0x18009a132  jns     short loc_18009A148
0x18009a134  mov     r9d, eax; char *
0x18009a137  lea     r8, aOnecoreAdminAp_71; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18009a13e  mov     edx, 16Eh; void *
0x18009a143  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009a148  mov     ebx, 70h ; 'p'
0x18009a14d  mov     r8d, ebx; Size
0x18009a150  xor     edx, edx; Val
0x18009a152  lea     rcx, [rsp+198h+StartupInfo]; void *
0x18009a15a  call    memset_0
0x18009a15f  mov     [rsp+198h+StartupInfo.cb], ebx
0x18009a166  mov     ebx, 1
0x18009a16b  mov     [rsp+198h+StartupInfo.dwFlags], ebx
0x18009a172  mov     [rsp+198h+StartupInfo.wShowWindow], si
0x18009a17a  mov     [rsp+198h+TokenHandle], rsi
0x18009a17f  xor     edx, edx
0x18009a181  lea     rcx, [rsp+198h+TokenHandle]
0x18009a186  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18009a18b  call    cs:__imp_GetCurrentThread
0x18009a192  nop     dword ptr [rax+rax+00h]
0x18009a197  lea     r9, [rsp+198h+TokenHandle]; TokenHandle
0x18009a19c  mov     r8d, ebx; OpenAsSelf
0x18009a19f  lea     edx, [rbx+9]; DesiredAccess
0x18009a1a2  mov     rcx, rax; ThreadHandle
0x18009a1a5  call    cs:__imp_OpenThreadToken
0x18009a1ac  nop     dword ptr [rax+rax+00h]
0x18009a1b1  mov     rcx, [rsp+198h]; this
0x18009a1b9  test    eax, eax
0x18009a1bb  jnz     short loc_18009A1CE
0x18009a1bd  lea     r8, aOnecoreAdminAp_71; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18009a1c4  mov     edx, 17Ch; void *
0x18009a1c9  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18009a1ce  lea     rcx, [rsp+198h+var_B0]
0x18009a1d6  call    ?impersonate_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@PEAX@Z; wil::impersonate_token(void *)
0x18009a1db  nop
0x18009a1dc  mov     [rsp+198h+var_100], rsi
0x18009a1e4  mov     [rsp+198h+hToken], rsi
0x18009a1ec  lea     rdx, [rsp+198h+var_100]
0x18009a1f4  mov     rcx, [rsp+198h+TokenHandle]
0x18009a1f9  call    cs:__imp_UMgrQueryUserContext
0x18009a200  nop     dword ptr [rax+rax+00h]
0x18009a205  mov     rcx, [rsp+198h]; this
0x18009a20d  test    eax, eax
0x18009a20f  jns     short loc_18009A225
0x18009a211  mov     r9d, eax; char *
0x18009a214  lea     r8, aOnecoreAdminAp_71; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18009a21b  mov     edx, 185h; void *
0x18009a220  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009a225  xor     edx, edx
0x18009a227  lea     rcx, [rsp+198h+hToken]
0x18009a22f  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18009a234  lea     rdx, [rsp+198h+hToken]
0x18009a23c  mov     rcx, [rsp+198h+var_100]
0x18009a244  call    cs:__imp_UMgrQueryUserToken
0x18009a24b  nop     dword ptr [rax+rax+00h]
0x18009a250  mov     rcx, [rsp+198h]; this
0x18009a258  test    eax, eax
0x18009a25a  jns     short loc_18009A271
0x18009a25c  mov     r9d, eax; char *
0x18009a25f  lea     r8, aOnecoreAdminAp_71; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18009a266  mov     edx, 186h; void *
0x18009a26b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009a271  mov     [rsp+198h+Environment], rsi
0x18009a276  xor     r8d, r8d; bInherit
0x18009a279  mov     rdx, [rsp+198h+hToken]; hToken
0x18009a281  lea     rcx, [rsp+198h+Environment]; lpEnvironment
0x18009a286  call    cs:__imp_CreateEnvironmentBlock
0x18009a28d  nop     dword ptr [rax+rax+00h]
0x18009a292  mov     rcx, [rsp+198h]; this
0x18009a29a  test    eax, eax
0x18009a29c  jnz     short loc_18009A2AF
0x18009a29e  lea     r8, aOnecoreAdminAp_71; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18009a2a5  mov     edx, 189h; void *
0x18009a2aa  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18009a2af  mov     [rsp+198h+pLevelHandle], rsi
0x18009a2b4  lea     rax, [rsp+198h+pLevelHandle]
0x18009a2b9  mov     [rsp+198h+var_90], rax
0x18009a2c1  mov     [rsp+198h+var_88], bl
0x18009a2c8  mov     [rsp+198h+lpReserved], rsi; lpReserved
0x18009a2cd  lea     r9, [rsp+198h+pLevelHandle]; pLevelHandle
0x18009a2d2  mov     r8d, ebx; OpenFlags
0x18009a2d5  mov     edx, 20000h; dwLevelId
0x18009a2da  mov     ecx, ebx; dwScopeId
0x18009a2dc  call    cs:__imp_SaferCreateLevel
0x18009a2e3  nop     dword ptr [rax+rax+00h]
0x18009a2e8  mov     rcx, [rsp+198h]; this
0x18009a2f0  test    eax, eax
0x18009a2f2  jnz     short loc_18009A305
0x18009a2f4  lea     r8, aOnecoreAdminAp_71; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18009a2fb  mov     edx, 192h; void *
0x18009a300  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18009a305  mov     [rsp+198h+OutAccessToken], rsi
0x18009a30a  xor     edx, edx
0x18009a30c  lea     rcx, [rsp+198h+OutAccessToken]
0x18009a311  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18009a316  mov     [rsp+198h+lpReserved], rsi; lpReserved
0x18009a31b  xor     r9d, r9d; dwFlags
0x18009a31e  lea     r8, [rsp+198h+OutAccessToken]; OutAccessToken
0x18009a323  mov     rdx, [rsp+198h+hToken]; InAccessToken
0x18009a32b  mov     rcx, [rsp+198h+pLevelHandle]; LevelHandle
0x18009a330  call    cs:__imp_SaferComputeTokenFromLevel
0x18009a337  nop     dword ptr [rax+rax+00h]
0x18009a33c  mov     rcx, [rsp+198h]; this
0x18009a344  test    eax, eax
0x18009a346  jnz     short loc_18009A359
0x18009a348  lea     r8, aOnecoreAdminAp_71; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18009a34f  mov     edx, 195h; void *
0x18009a354  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18009a359  xorps   xmm0, xmm0
0x18009a35c  xor     eax, eax
0x18009a35e  movups  xmmword ptr [rsp+198h+ProcessInformation.hProcess], xmm0
0x18009a366  mov     qword ptr [rsp+198h+ProcessInformation.dwProcessId], rax
0x18009a36e  lea     rcx, [rsp+198h+ProcessInformation]; this
0x18009a376  call    ?CloseProcessInformation@details@wil@@YAXPEAU_PROCESS_INFORMATION@@@Z; wil::details::CloseProcessInformation(_PROCESS_INFORMATION *)
0x18009a37b  xorps   xmm0, xmm0
0x18009a37e  xor     eax, eax
0x18009a380  movups  xmmword ptr [rsp+198h+ProcessInformation.hProcess], xmm0
0x18009a388  mov     qword ptr [rsp+198h+ProcessInformation.dwProcessId], rax
0x18009a390  mov     rax, [rsp+198h+Environment]
0x18009a395  lea     rcx, [rsp+198h+ProcessInformation]
0x18009a39d  mov     [rsp+198h+lpProcessInformation], rcx; lpProcessInformation
0x18009a3a2  lea     rcx, [rsp+198h+StartupInfo]
0x18009a3aa  mov     [rsp+198h+lpStartupInfo], rcx; lpStartupInfo
0x18009a3af  mov     [rsp+198h+lpCurrentDirectory], rsi; lpCurrentDirectory
0x18009a3b4  mov     [rsp+198h+lpEnvironment], rax; lpEnvironment
0x18009a3b9  mov     [rsp+198h+dwCreationFlags], 80400h; dwCreationFlags
0x18009a3c1  mov     dword ptr [rsp+198h+bInheritHandles], esi; char *
0x18009a3c5  mov     [rsp+198h+lpReserved], rsi; int
0x18009a3ca  xor     r9d, r9d; lpProcessAttributes
0x18009a3cd  mov     r8, [rsp+198h+lpCommandLine+8]; lpCommandLine
0x18009a3d5  mov     rdx, [rsp+198h+lpApplicationName+8]; lpApplicationName
0x18009a3dd  mov     rcx, [rsp+198h+OutAccessToken]; hToken
0x18009a3e2  call    cs:__imp_CreateProcessAsUserW
0x18009a3e9  nop     dword ptr [rax+rax+00h]
0x18009a3ee  mov     rcx, [rsp+198h]; this
0x18009a3f6  test    eax, eax
0x18009a3f8  jnz     short loc_18009A40B
0x18009a3fa  lea     r8, aOnecoreAdminAp_71; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18009a401  mov     edx, 199h; void *
0x18009a406  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18009a40b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18009a40e  mov     rcx, [rsp+198h+ProcessInformation.hProcess]; hHandle
0x18009a416  call    cs:__imp_WaitForSingleObject
0x18009a41d  nop     dword ptr [rax+rax+00h]
0x18009a422  mov     rcx, [rsp+198h]; this
0x18009a42a  lea     r8, aOnecoreAdminAp_71; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18009a431  cmp     eax, 80h
0x18009a436  jnz     short loc_18009A448
0x18009a438  mov     r9d, 800703E3h; char *
0x18009a43e  mov     edx, 19Ch; void *
0x18009a443  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009a448  test    eax, eax
0x18009a44a  setnz   al
0x18009a44d  mov     rcx, [rsp+198h]; this
0x18009a455  lea     rdx, aWaitForCustomI; "Wait For Custom Install Worker Process "...
0x18009a45c  mov     [rsp+198h+lpReserved], rdx; unsigned int
0x18009a461  movzx   r9d, al; char *
0x18009a465  mov     edx, 19Dh; void *
0x18009a46a  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x18009a46f  mov     [rsp+198h+ExitCode], esi
0x18009a476  lea     rdx, [rsp+198h+ExitCode]; lpExitCode
0x18009a47e  mov     rcx, [rsp+198h+ProcessInformation.hProcess]; hProcess
0x18009a486  call    cs:__imp_GetExitCodeProcess
0x18009a48d  nop     dword ptr [rax+rax+00h]
0x18009a492  mov     rcx, [rsp+198h]; this
0x18009a49a  test    eax, eax
0x18009a49c  jnz     short loc_18009A4AF
0x18009a49e  lea     r8, aOnecoreAdminAp_71; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18009a4a5  mov     edx, 1A0h; void *
0x18009a4aa  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18009a4af  mov     r9d, [rsp+198h+ExitCode]; char *
0x18009a4b7  mov     rcx, [rsp+198h]; this
0x18009a4bf  test    r9d, r9d
0x18009a4c2  jz      short loc_18009A4D6
0x18009a4c4  lea     r8, aOnecoreAdminAp_71; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18009a4cb  mov     edx, 1A1h; void *
0x18009a4d0  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18009a4d6  lea     rcx, [rsp+198h+ProcessInformation]; this
0x18009a4de  call    ?CloseProcessInformation@details@wil@@YAXPEAU_PROCESS_INFORMATION@@@Z; wil::details::CloseProcessInformation(_PROCESS_INFORMATION *)
0x18009a4e3  nop
0x18009a4e4  lea     rcx, [rsp+198h+OutAccessToken]
0x18009a4e9  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18009a4ee  nop
0x18009a4ef  mov     rcx, [rsp+198h+pLevelHandle]; hLevelHandle
0x18009a4f4  call    cs:__imp_SaferCloseLevel
0x18009a4fb  nop     dword ptr [rax+rax+00h]
0x18009a500  nop
0x18009a501  lea     rcx, [rsp+198h+Environment]
0x18009a506  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?DestroyEnvironmentBlock@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&DestroyEnvironmentBlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&DestroyEnvironmentBlock(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18009a50b  nop
0x18009a50c  lea     rcx, [rsp+198h+hToken]
0x18009a514  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
  ... truncated ...
```
