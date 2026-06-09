# AppReadiness::Groups::UserLogon::OnStarted(void)

- ea: `0x180063d50`
- end: `0x180064172`
- name: `?OnStarted@UserLogon@Groups@AppReadiness@@MEAAXXZ`
- size: `1058`
- prototype: `void __fastcall(AppReadiness::Groups::UserLogon *__hidden this)`
- caller_count: `0`
- callee_count: `20`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x18001abb0`
- `0x18001b7b0`
- `0x18001bc04`
- `0x18001e95c`
- `0x180024130`
- `0x1800246e8`
- `0x180026954`
- `0x180027a4c`
- `0x18002a970`
- `0x18002bfbc`
- `0x1800325b4`
- `0x1800327fc`
- `0x18003293c`
- `0x1800397cc`
- `0x18003e210`
- `0x18003ecb4`
- `0x1800473d8`
- `0x180063d50`
- `0x18006558c`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180063edb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180063fc6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180063edb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180063fc6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180063eab`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180063f96`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180063eab`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180063f96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006407d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064118`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006407d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064118`

## string_xrefs

- `0x1800640a0`: `onecoreuap\shell\appreadiness\src\groups\userlogon.cpp`
- `0x1800640e0`: `onecoreuap\shell\appreadiness\src\groups\userlogon.cpp`
- `0x18006413a`: `onecoreuap\shell\appreadiness\src\groups\userlogon.cpp`
- `0x1800640b3`: `SHQueryToken(GetUser()->GetToken().Get(), TokenUser, false, &userToken)`
- `0x180063ea4`: `AppxDeploymentClient.dll`
- `0x180063f8f`: `AppxDeploymentClient.dll`
- `0x1800640ac`: `AppReadiness::Groups::UserLogon::OnStarted`
- `0x1800640ec`: `AppReadiness::Groups::UserLogon::OnStarted`
- `0x180064146`: `AppReadiness::Groups::UserLogon::OnStarted`
- `0x18006414d`: `ResultFromWin32HandleMaybenull( LoadLibraryEx(L"AppxDeploymentClient.dll", nullptr, LOAD_LIBRARY_SEARCH_SYSTEM32), reinterpret_cast<HANDLE*>(module.GetAddressOf()))`
- `0x180063fbf`: `RemoveDeferredPackages`
- `0x1800640f3`: `ResultFromWin32HandleMaybenull(LoadLibraryEx(L"AppxDeploymentClient.dll", nullptr, LOAD_LIBRARY_SEARCH_SYSTEM32), reinterpret_cast<HANDLE*>(module.GetAddressOf()))`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall AppReadiness::Groups::UserLogon::OnStarted(AppReadiness::Groups::UserLogon *this)
{
  char *v2; // rdi
  __int64 v3; // rax
  const unsigned __int16 *v4; // rcx
  __int64 v5; // rax
  int v6; // eax
  HMODULE Library; // rcx
  int Error; // eax
  __int64 v9; // rax
  _QWORD *v10; // rdx
  AppReadiness::TileStoreMigrationRecovery *v11; // rax
  struct AppReadiness::User *v12; // rdx
  HMODULE v13; // rcx
  int v14; // eax
  __int64 v15; // rax
  _QWORD *v16; // rdx
  signed int v17; // eax
  int v18; // edx
  unsigned int v19; // r8d
  signed int LastError; // eax
  int v21; // edx
  unsigned int v22; // r8d
  PSID *ProcAddress; // [rsp+30h] [rbp-D0h] BYREF
  const int *v24; // [rsp+38h] [rbp-C8h] BYREF
  HMODULE v25; // [rsp+40h] [rbp-C0h]
  const int *v26; // [rsp+48h] [rbp-B8h] BYREF
  HMODULE v27; // [rsp+50h] [rbp-B0h]
  FARPROC v28; // [rsp+58h] [rbp-A8h] BYREF
  PSID *v29; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v31[7]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD *v32; // [rsp+C8h] [rbp-38h]
  _QWORD v33[7]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD *v34; // [rsp+108h] [rbp+8h]

  v2 = (char *)this + 320;
  tip2::tip_test<tip2::details::merged_data<_tip_UserLogonTasksTest,_tip_UserLogonTasksTest>>::start(
    (char *)this + 320,
    &v26);
  v3 = (*(__int64 (__fastcall **)(AppReadiness::Groups::UserLogon *))(*(_QWORD *)this + 112LL))(this);
  v4 = (const unsigned __int16 *)(v3 + 64);
  if ( *(_QWORD *)(v3 + 88) > 7u )
    v4 = *(const unsigned __int16 **)v4;
  if ( IsWizardOnlyAccount(v4) )
    *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_UserLogonTasksTest,_tip_UserLogonTasksTest>>::operator->(
                             v2,
                             &ProcAddress)
              + 288LL) = 2;
  else
    *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_UserLogonTasksTest,_tip_UserLogonTasksTest>>::operator->(
                             v2,
                             &ProcAddress)
              + 288LL) = 4;
  tip2::test_data_control<tip2::details::merged_data<_tip_UserLogonTasksTest,_tip_UserLogonTasksTest>>::~test_data_control<tip2::details::merged_data<_tip_UserLogonTasksTest,_tip_UserLogonTasksTest>>(&ProcAddress);
  AppReadiness::Groups::UserLogon::AddPreRegisterTaskIfFound((AppReadiness::Groups::UserLogon *)((char *)this - 8));
  ProcAddress = 0;
  v5 = (*(__int64 (__fastcall **)(AppReadiness::Groups::UserLogon *))(*(_QWORD *)this + 112LL))(this);
  v6 = SHQueryToken<_TOKEN_USER>(*(HANDLE *)(v5 + 112));
  if ( v6 < 0 )
    goto LABEL_34;
  v29 = ProcAddress;
  if ( (int)RDSAppXIsRecoveryNeededForUser(*ProcAddress) >= 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      (*(void (__fastcall **)(AppReadiness::Groups::UserLogon *))(*(_QWORD *)this + 112LL))(this);
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_3e341c78579f3d12fd42feaf7fd435d9_Traceguids);
    }
    v26 = &Microsoft::WRL::Wrappers::HandleT<AppReadiness::HandleTraits::ModuleHandleTraits>::`vftable';
    v27 = 0;
    Library = LoadLibraryExW(L"AppxDeploymentClient.dll", 0, 0x800u);
    v27 = Library;
    if ( Library )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      Library = v27;
    }
    if ( Error < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)pExceptionObject,
        Error,
        "ResultFromWin32HandleMaybenull(LoadLibraryEx(L\"AppxDeploymentClient.dll\", nullptr, LOAD_LIBRARY_SEARCH_SYSTEM3"
        "2), reinterpret_cast<HANDLE*>(module.GetAddressOf()))",
        "AppReadiness::Groups::UserLogon::OnStarted",
        "onecoreuap\\shell\\appreadiness\\src\\groups\\userlogon.cpp",
        172);
      throw (Windows::HResultException *)pExceptionObject;
    }
    ProcAddress = (PSID *)GetProcAddress(Library, "RDSRecoverRequests");
    if ( ProcAddress )
    {
      v9 = (*(__int64 (__fastcall **)(AppReadiness::Groups::UserLogon *))(*(_QWORD *)this + 112LL))(this);
      v31[0] = off_18007DF08;
      v31[1] = &ProcAddress;
      v32 = v31;
      AppReadiness::User::ExecuteUnderContext(v9, (__int64)v31);
      if ( v32 )
      {
        v10 = v31;
        LOBYTE(v10) = v32 != v31;
        (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v32 + 32LL))(v32, v10);
      }
    }
    v26 = &Microsoft::WRL::Wrappers::HandleT<AppReadiness::HandleTraits::ModuleHandleTraits>::`vftable';
    if ( v27 )
    {
      if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<AppReadiness::HandleTraits::ModuleHandleTraits>::InternalClose(&v26) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v21, v22);
LABEL_39:
        Windows::HResultException::HResultException(
          (Windows::HResultException *)pExceptionObject,
          v14,
          "ResultFromWin32HandleMaybenull( LoadLibraryEx(L\"AppxDeploymentClient.dll\", nullptr, LOAD_LIBRARY_SEARCH_SYST"
          "EM32), reinterpret_cast<HANDLE*>(module.GetAddressOf()))",
          "AppReadiness::Groups::UserLogon::OnStarted",
          "onecoreuap\\shell\\appreadiness\\src\\groups\\userlogon.cpp",
          187);
        throw (Windows::HResultException *)pExceptionObject;
      }
    }
  }
  v11 = (AppReadiness::TileStoreMigrationRecovery *)(*(__int64 (__fastcall **)(AppReadiness::Groups::UserLogon *))(*(_QWORD *)this + 112LL))(this);
  AppReadiness::TileStoreMigrationRecovery::RecoverTileMigration(v11, v12);
  v24 = &Microsoft::WRL::Wrappers::HandleT<AppReadiness::HandleTraits::ModuleHandleTraits>::`vftable';
  v25 = 0;
  v13 = LoadLibraryExW(L"AppxDeploymentClient.dll", 0, 0x800u);
  v25 = v13;
  if ( v13 )
  {
    v14 = 0;
  }
  else
  {
    v14 = ResultFromKnownLastError();
    v13 = v25;
  }
  if ( v14 < 0 )
    goto LABEL_39;
  v28 = GetProcAddress(v13, "RemoveDeferredPackages");
  if ( v28 )
  {
    v15 = (*(__int64 (__fastcall **)(AppReadiness::Groups::UserLogon *))(*(_QWORD *)this + 112LL))(this);
    v33[0] = off_18007DED8;
    v33[1] = &v28;
    v34 = v33;
    AppReadiness::User::ExecuteUnderContext(v15, (__int64)v33);
    if ( v34 )
    {
      v16 = v33;
      LOBYTE(v16) = v34 != v33;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v34 + 32LL))(v34, v16);
    }
  }
  AppReadiness::Groups::UserLogon::CreateTaskList((AppReadiness::Groups::UserLogon *)((char *)this - 8));
  v24 = &Microsoft::WRL::Wrappers::HandleT<AppReadiness::HandleTraits::ModuleHandleTraits>::`vftable';
  if ( v25 )
  {
    if ( (unsigned __int8)Microsoft::WRL::Wrappers::HandleT<AppReadiness::HandleTraits::ModuleHandleTraits>::InternalClose(&v24) )
    {
      v25 = 0;
      goto LABEL_30;
    }
    v17 = GetLastError();
    if ( v17 > 0 )
      v17 = (unsigned __int16)v17 | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v17, v18, v19);
LABEL_34:
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      v6,
      "SHQueryToken(GetUser()->GetToken().Get(), TokenUser, false, &userToken)",
      "AppReadiness::Groups::UserLogon::OnStarted",
      "onecoreuap\\shell\\appreadiness\\src\\groups\\userlogon.cpp",
      166);
    throw (Windows::HResultException *)pExceptionObject;
  }
LABEL_30:
  std::unique_ptr<_USER_INFO_24,LocalMem_Deleter<_USER_INFO_24>>::~unique_ptr<_USER_INFO_24,LocalMem_Deleter<_USER_INFO_24>>(&v29);
}

```

## disassembly

```asm
0x180063d50  push    rbp
0x180063d52  push    rbx
0x180063d53  push    rsi
0x180063d54  push    rdi
0x180063d55  lea     rbp, [rsp-28h]
0x180063d5a  sub     rsp, 128h
0x180063d61  mov     rax, cs:__security_cookie
0x180063d68  xor     rax, rsp
0x180063d6b  mov     [rbp+40h+var_30], rax
0x180063d6f  mov     rbx, rcx
0x180063d72  lea     rdi, [rcx+140h]
0x180063d79  lea     rdx, [rsp+140h+var_F8]
0x180063d7e  mov     rcx, rdi
0x180063d81  call    ?start@?$tip_test@V?$merged_data@U_tip_UserLogonTasksTest@@U1@@details@tip2@@@tip2@@QEAA?AU_GUID@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_UserLogonTasksTest,_tip_UserLogonTasksTest>>::start(void)
0x180063d86  mov     rax, [rbx]
0x180063d89  mov     rcx, rbx
0x180063d8c  mov     rax, [rax+70h]
0x180063d90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063d95  lea     rcx, [rax+40h]
0x180063d99  cmp     qword ptr [rcx+18h], 7
0x180063d9e  jbe     short loc_180063DA3
0x180063da0  mov     rcx, [rcx]; unsigned __int16 *
0x180063da3  call    ?IsWizardOnlyAccount@@YA_NPEBG@Z; IsWizardOnlyAccount(ushort const *)
0x180063da8  lea     rdx, [rsp+140h+var_110]
0x180063dad  mov     rcx, rdi
0x180063db0  test    al, al
0x180063db2  jz      short loc_180063DC8
0x180063db4  call    ??C?$tip_test@V?$merged_data@U_tip_UserLogonTasksTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_UserLogonTasksTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_UserLogonTasksTest,_tip_UserLogonTasksTest>>::operator->(void)
0x180063db9  mov     rcx, [rax]
0x180063dbc  mov     dword ptr [rcx+120h], 2
0x180063dc6  jmp     short loc_180063DDA
0x180063dc8  call    ??C?$tip_test@V?$merged_data@U_tip_UserLogonTasksTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_UserLogonTasksTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_UserLogonTasksTest,_tip_UserLogonTasksTest>>::operator->(void)
0x180063dcd  mov     rcx, [rax]
0x180063dd0  mov     dword ptr [rcx+120h], 4
0x180063dda  lea     rcx, [rsp+140h+var_110]
0x180063ddf  call    ??1?$test_data_control@V?$merged_data@U_tip_UserLogonTasksTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_UserLogonTasksTest,_tip_UserLogonTasksTest>>::~test_data_control<tip2::details::merged_data<_tip_UserLogonTasksTest,_tip_UserLogonTasksTest>>(void)
0x180063de4  lea     rcx, [rbx-8]; this
0x180063de8  call    ?AddPreRegisterTaskIfFound@UserLogon@Groups@AppReadiness@@AEAAXXZ; AppReadiness::Groups::UserLogon::AddPreRegisterTaskIfFound(void)
0x180063ded  mov     [rsp+140h+var_110], 0
0x180063df6  mov     rax, [rbx]
0x180063df9  mov     rcx, rbx
0x180063dfc  mov     rax, [rax+70h]
0x180063e00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063e05  lea     r9, [rsp+140h+var_110]
0x180063e0a  mov     rcx, [rax+70h]; TokenHandle
0x180063e0e  call    ??$SHQueryToken@U_TOKEN_USER@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@HPEAPEAU_TOKEN_USER@@@Z; SHQueryToken<_TOKEN_USER>(void *,_TOKEN_INFORMATION_CLASS,int,_TOKEN_USER * *)
0x180063e13  test    eax, eax
0x180063e15  js      loc_180064098
0x180063e1b  mov     rcx, [rsp+140h+var_110]
0x180063e20  mov     [rsp+140h+var_E0], rcx
0x180063e25  mov     rcx, [rcx]; Sid
0x180063e28  call    RDSAppXIsRecoveryNeededForUser
0x180063e2d  lea     rdi, ??_7?$HandleT@UModuleHandleTraits@HandleTraits@AppReadiness@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<AppReadiness::HandleTraits::ModuleHandleTraits>::`vftable'
0x180063e34  test    eax, eax
0x180063e36  js      loc_180063F62
0x180063e3c  lea     rcx, WPP_GLOBAL_Control
0x180063e43  mov     rax, cs:WPP_GLOBAL_Control
0x180063e4a  cmp     rax, rcx
0x180063e4d  jz      short loc_180063E8E
0x180063e4f  test    byte ptr [rax+1Ch], 2
0x180063e53  jz      short loc_180063E8E
0x180063e55  mov     rax, [rbx]
0x180063e58  mov     rcx, rbx
0x180063e5b  mov     rax, [rax+70h]
0x180063e5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063e64  lea     r9, [rax+40h]
0x180063e68  cmp     qword ptr [r9+18h], 7
0x180063e6d  jbe     short loc_180063E72
0x180063e6f  mov     r9, [r9]
0x180063e72  mov     edx, 0Fh
0x180063e77  lea     r8, WPP_3e341c78579f3d12fd42feaf7fd435d9_Traceguids
0x180063e7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180063e85  mov     rcx, [rcx+10h]
0x180063e89  call    WPP_SF_S
0x180063e8e  mov     [rsp+140h+var_F8], rdi
0x180063e93  mov     [rsp+140h+var_F0], 0
0x180063e9c  xor     edx, edx; hFile
0x180063e9e  mov     r8d, 800h; dwFlags
0x180063ea4  lea     rcx, aAppxdeployment_0; "AppxDeploymentClient.dll"
0x180063eab  call    cs:__imp_LoadLibraryExW
0x180063eb1  mov     rcx, rax; hModule
0x180063eb4  mov     [rsp+140h+var_F0], rax
0x180063eb9  test    rax, rax
0x180063ebc  jnz     short loc_180063ECA
0x180063ebe  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180063ec3  mov     rcx, [rsp+140h+var_F0]
0x180063ec8  jmp     short loc_180063ECC
0x180063eca  xor     eax, eax
0x180063ecc  test    eax, eax
0x180063ece  js      loc_1800640D8
0x180063ed4  lea     rdx, aRdsrecoverrequ; "RDSRecoverRequests"
0x180063edb  call    cs:__imp_GetProcAddress
0x180063ee1  mov     [rsp+140h+var_110], rax
0x180063ee6  test    rax, rax
0x180063ee9  jz      short loc_180063F43
0x180063eeb  mov     rax, [rbx]
0x180063eee  mov     rcx, rbx
0x180063ef1  mov     rax, [rax+70h]
0x180063ef5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063efa  lea     rcx, off_18007DF08
0x180063f01  mov     [rbp+40h+var_B0], rcx
0x180063f05  lea     rcx, [rsp+140h+var_110]
0x180063f0a  mov     [rbp+40h+var_A8], rcx
0x180063f0e  lea     rcx, [rbp+40h+var_B0]
0x180063f12  mov     [rbp+40h+var_78], rcx
0x180063f16  lea     rdx, [rbp+40h+var_B0]
0x180063f1a  mov     rcx, rax
0x180063f1d  call    ?ExecuteUnderContext@User@AppReadiness@@QEAAJAEBV?$function@$$A6AXXZ@std@@@Z; AppReadiness::User::ExecuteUnderContext(std::function<void (void)> const &)
0x180063f22  nop
0x180063f23  mov     rcx, [rbp+40h+var_78]
0x180063f27  test    rcx, rcx
0x180063f2a  jz      short loc_180063F43
0x180063f2c  mov     rax, [rcx]
0x180063f2f  lea     rdx, [rbp+40h+var_B0]
0x180063f33  cmp     rcx, rdx
0x180063f36  setnz   dl
0x180063f39  mov     rax, [rax+20h]
0x180063f3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063f42  nop
0x180063f43  mov     [rsp+140h+var_F8], rdi
0x180063f48  cmp     [rsp+140h+var_F0], 0
0x180063f4e  jz      short loc_180063F62
0x180063f50  lea     rcx, [rsp+140h+var_F8]
0x180063f55  call    ?InternalClose@?$HandleT@UModuleHandleTraits@HandleTraits@AppReadiness@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<AppReadiness::HandleTraits::ModuleHandleTraits>::InternalClose(void)
0x180063f5a  test    al, al
0x180063f5c  jz      loc_180064118
0x180063f62  mov     rax, [rbx]
0x180063f65  mov     rcx, rbx
0x180063f68  mov     rax, [rax+70h]
0x180063f6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063f71  mov     rcx, rax; this
0x180063f74  call    ?RecoverTileMigration@TileStoreMigrationRecovery@AppReadiness@@YAXPEAVUser@2@@Z; AppReadiness::TileStoreMigrationRecovery::RecoverTileMigration(AppReadiness::User *)
0x180063f79  mov     [rsp+140h+var_108], rdi
0x180063f7e  mov     [rsp+140h+var_100], 0
0x180063f87  xor     edx, edx; hFile
0x180063f89  mov     r8d, 800h; dwFlags
0x180063f8f  lea     rcx, aAppxdeployment_0; "AppxDeploymentClient.dll"
0x180063f96  call    cs:__imp_LoadLibraryExW
0x180063f9c  mov     rcx, rax; hModule
0x180063f9f  mov     [rsp+140h+var_100], rax
0x180063fa4  test    rax, rax
0x180063fa7  jnz     short loc_180063FB5
0x180063fa9  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180063fae  mov     rcx, [rsp+140h+var_100]
0x180063fb3  jmp     short loc_180063FB7
0x180063fb5  xor     eax, eax
0x180063fb7  test    eax, eax
0x180063fb9  js      loc_180064132
0x180063fbf  lea     rdx, aRemovedeferred; "RemoveDeferredPackages"
0x180063fc6  call    cs:__imp_GetProcAddress
0x180063fcc  mov     [rsp+140h+var_E8], rax
0x180063fd1  test    rax, rax
0x180063fd4  jz      short loc_18006402D
0x180063fd6  mov     rax, [rbx]
0x180063fd9  mov     rcx, rbx
0x180063fdc  mov     rax, [rax+70h]
0x180063fe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063fe5  lea     rcx, off_18007DED8
0x180063fec  mov     [rbp+40h+var_70], rcx
0x180063ff0  lea     rcx, [rsp+140h+var_E8]
0x180063ff5  mov     [rbp+40h+var_68], rcx
0x180063ff9  lea     rcx, [rbp+40h+var_70]
0x180063ffd  mov     [rbp+40h+var_38], rcx
0x180064001  lea     rdx, [rbp+40h+var_70]
0x180064005  mov     rcx, rax
0x180064008  call    ?ExecuteUnderContext@User@AppReadiness@@QEAAJAEBV?$function@$$A6AXXZ@std@@@Z; AppReadiness::User::ExecuteUnderContext(std::function<void (void)> const &)
0x18006400d  nop
0x18006400e  mov     rcx, [rbp+40h+var_38]
0x180064012  test    rcx, rcx
0x180064015  jz      short loc_18006402D
0x180064017  mov     rax, [rcx]
0x18006401a  lea     rdx, [rbp+40h+var_70]
0x18006401e  cmp     rcx, rdx
0x180064021  setnz   dl
0x180064024  mov     rax, [rax+20h]
0x180064028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006402d  lea     rcx, [rbx-8]; this
0x180064031  call    ?CreateTaskList@UserLogon@Groups@AppReadiness@@AEAAXXZ; AppReadiness::Groups::UserLogon::CreateTaskList(void)
0x180064036  nop
0x180064037  mov     [rsp+140h+var_108], rdi
0x18006403c  cmp     [rsp+140h+var_100], 0
0x180064042  jz      short loc_18006405B
0x180064044  lea     rcx, [rsp+140h+var_108]
0x180064049  call    ?InternalClose@?$HandleT@UModuleHandleTraits@HandleTraits@AppReadiness@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<AppReadiness::HandleTraits::ModuleHandleTraits>::InternalClose(void)
0x18006404e  test    al, al
0x180064050  jz      short loc_18006407D
0x180064052  mov     [rsp+140h+var_100], 0
0x18006405b  lea     rcx, [rsp+140h+var_E0]
0x180064060  call    ??1?$unique_ptr@U_USER_INFO_24@@U?$LocalMem_Deleter@U_USER_INFO_24@@@@@std@@QEAA@XZ; std::unique_ptr<_USER_INFO_24,LocalMem_Deleter<_USER_INFO_24>>::~unique_ptr<_USER_INFO_24,LocalMem_Deleter<_USER_INFO_24>>(void)
0x180064065  mov     rcx, [rbp+40h+var_30]
0x180064069  xor     rcx, rsp; StackCookie
0x18006406c  call    __security_check_cookie
0x180064071  add     rsp, 128h
0x180064078  pop     rdi
0x180064079  pop     rsi
0x18006407a  pop     rbx
0x18006407b  pop     rbp
0x18006407c  retn
0x18006407d  call    cs:__imp_GetLastError
0x180064083  nop
0x180064084  test    eax, eax
0x180064086  jle     short loc_180064090
0x180064088  movzx   eax, ax
0x18006408b  or      eax, 80070000h
0x180064090  mov     ecx, eax; this
0x180064092  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180064097  nop
0x180064098  mov     [rsp+140h+var_118], 0A6h; int
0x1800640a0  lea     rcx, aOnecoreuapShel_17; "onecoreuap\\shell\\appreadiness\\src\\g"...
0x1800640a7  mov     [rsp+140h+var_120], rcx; char *
0x1800640ac  lea     r9, aAppreadinessGr_3; "AppReadiness::Groups::UserLogon::OnStar"...
0x1800640b3  lea     r8, aShquerytokenGe; "SHQueryToken(GetUser()->GetToken().Get("...
0x1800640ba  mov     edx, eax; int
0x1800640bc  lea     rcx, [rsp+140h+pExceptionObject]; this
0x1800640c1  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x1800640c6  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x1800640cd  lea     rcx, [rsp+140h+pExceptionObject]; pExceptionObject
0x1800640d2  call    _CxxThrowException_0
0x1800640d8  mov     [rsp+140h+var_118], 0ACh; int
0x1800640e0  lea     rcx, aOnecoreuapShel_17; "onecoreuap\\shell\\appreadiness\\src\\g"...
0x1800640e7  mov     [rsp+140h+var_120], rcx; char *
0x1800640ec  lea     r9, aAppreadinessGr_3; "AppReadiness::Groups::UserLogon::OnStar"...
0x1800640f3  lea     r8, aResultfromwin3_10; "ResultFromWin32HandleMaybenull(LoadLibr"...
0x1800640fa  mov     edx, eax; int
0x1800640fc  lea     rcx, [rsp+140h+pExceptionObject]; this
0x180064101  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180064106  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18006410d  lea     rcx, [rsp+140h+pExceptionObject]; pExceptionObject
0x180064112  call    _CxxThrowException_0
0x180064118  call    cs:__imp_GetLastError
0x18006411e  test    eax, eax
0x180064120  jle     short loc_18006412A
0x180064122  movzx   eax, ax
0x180064125  or      eax, 80070000h
0x18006412a  mov     ecx, eax; this
0x18006412c  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180064131  nop
0x180064132  mov     [rsp+140h+var_118], 0BBh; int
0x18006413a  lea     rcx, aOnecoreuapShel_17; "onecoreuap\\shell\\appreadiness\\src\\g"...
0x180064141  mov     [rsp+140h+var_120], rcx; char *
0x180064146  lea     r9, aAppreadinessGr_3; "AppReadiness::Groups::UserLogon::OnStar"...
0x18006414d  lea     r8, aResultfromwin3_6; "ResultFromWin32HandleMaybenull( LoadLib"...
0x180064154  mov     edx, eax; int
0x180064156  lea     rcx, [rsp+140h+pExceptionObject]; this
0x18006415b  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180064160  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180064167  lea     rcx, [rsp+140h+pExceptionObject]; pExceptionObject
0x18006416c  call    _CxxThrowException_0
```
