# AppReadiness::Tasks::PackageChanges::OnExecute(void)

- ea: `0x180026c10`
- end: `0x180027062`
- name: `?OnExecute@PackageChanges@Tasks@AppReadiness@@MEAAXXZ`
- size: `1106`
- prototype: `void __fastcall(AppReadiness::Tasks::PackageChanges *__hidden this)`
- caller_count: `0`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180002958`
- `0x180002a60`
- `0x1800041e0`
- `0x18000d17c`
- `0x18000e4a0`
- `0x18000e5b4`
- `0x18001009c`
- `0x180012784`
- `0x180016f34`
- `0x180026c10`
- `0x180027068`
- `0x180027158`
- `0x180027340`
- `0x180027390`
- `0x180027a4c`
- `0x18003235c`
- `0x18003e210`
- `0x18003ecb4`
- `0x18003eec0`
- `0x18003f110`
- `0x1800473d8`
- `0x180059fb4`
- `0x180065b9c`
- `0x180079010`

## import_xrefs

- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x180026ec5`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x180026ec5`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180026f52`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180026f52`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x180026e22`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x180026e22`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x180026c7d`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x180026c7d`

## string_xrefs

- `0x180026c98`: `onecoreuap\shell\appreadiness\src\tasks\packagechanges.cpp`
- `0x180026ed7`: `onecoreuap\shell\appreadiness\src\tasks\packagechanges.cpp`
- `0x180026ff1`: `onecoreuap\shell\appreadiness\src\tasks\packagechanges.cpp`
- `0x180026ca4`: `AppReadiness::Tasks::PackageChanges::OnExecute`
- `0x180026ee3`: `AppReadiness::Tasks::PackageChanges::OnExecute`
- `0x180026ffd`: `AppReadiness::Tasks::PackageChanges::OnExecute`
- `0x180027004`: `UMgrQueryUserToken(sessionUserContext.ContextToken, userToken.GetAddressOf())`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall AppReadiness::Tasks::PackageChanges::OnExecute(AppReadiness::Tasks::PackageChanges *this)
{
  RTL_SRWLOCK *v2; // rsi
  __int64 v3; // rcx
  int Error; // eax
  PWTS_SESSION_INFOW v5; // rbx
  __int64 v6; // rdi
  DWORD i; // ecx
  __int64 SessionId; // r8
  WTS_CONNECTSTATE_CLASS State; // eax
  AppReadiness::User *v10; // rcx
  AppReadiness::User **v11; // rax
  AppReadiness::User *v12; // rdx
  AppReadiness::User *v13; // rcx
  AppReadiness::User *v14; // rcx
  AppReadiness::User *v15; // rcx
  _QWORD *DefaultAccountSid; // rax
  int v17; // eax
  DWORD j; // ebx
  __int64 v19; // rdi
  AppReadiness::User *v20; // rcx
  int v21; // eax
  AppReadiness::User **v22; // rax
  AppReadiness::User *v23; // [rsp+30h] [rbp-49h] BYREF
  DWORD pCount; // [rsp+38h] [rbp-41h] BYREF
  PWTS_SESSION_INFOW ppSessionInfo; // [rsp+40h] [rbp-39h] BYREF
  AppReadiness::User *v26; // [rsp+48h] [rbp-31h] BYREF
  _QWORD v27[2]; // [rsp+50h] [rbp-29h] BYREF
  PWTS_SESSION_INFOW v28; // [rsp+60h] [rbp-19h] BYREF
  __int64 v29; // [rsp+68h] [rbp-11h] BYREF
  char v30; // [rsp+70h] [rbp-9h] BYREF
  _QWORD pExceptionObject[3]; // [rsp+78h] [rbp-1h] BYREF
  unsigned __int64 v32; // [rsp+90h] [rbp+17h]

  v2 = (RTL_SRWLOCK *)AppReadiness::Service::Get();
  AppReadiness::Storage::PackageList::MarkAllUsersAs();
  if ( (unsigned __int8)IsWTSEnumerateSessionsWPresent() )
  {
    ppSessionInfo = 0;
    pCount = 0;
    if ( !WTSEnumerateSessionsW(0, 0, 1u, &ppSessionInfo, &pCount) )
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
      {
        Windows::HResultException::HResultException(
          (Windows::HResultException *)pExceptionObject,
          Error,
          "WTSEnumerateSessions(WTS_CURRENT_SERVER_HANDLE, 0, 1, &sessionPtr, &numSessions)",
          "AppReadiness::Tasks::PackageChanges::OnExecute",
          "onecoreuap\\shell\\appreadiness\\src\\tasks\\packagechanges.cpp",
          50);
        throw (Windows::HResultException *)pExceptionObject;
      }
    }
    v5 = ppSessionInfo;
    v28 = ppSessionInfo;
    v6 = 0;
    for ( i = pCount; (unsigned int)v6 < i; v6 = (unsigned int)(v6 + 1) )
    {
      SessionId = v5[v6].SessionId;
      if ( (_DWORD)SessionId )
      {
        State = v5[v6].State;
        if ( State == WTSActive || (unsigned int)(State - 3) <= 1 )
        {
          AppReadiness::Service::FindUserBySessionIdAndUserContext(v2, &v23, SessionId, 0);
          v10 = v23;
          if ( !v23 )
          {
            AppReadiness::Service::GetSessionUserToken(v27, v5[v6].SessionId);
            AppReadiness::Service::GetTokenSid(pExceptionObject, v27);
            v11 = AppReadiness::Service::CreateUser((__int64)v2, &v26, pExceptionObject, (__int64)v27);
            v12 = 0;
            if ( &v30 != (char *)v11 )
            {
              v12 = *v11;
              *v11 = 0;
            }
            v13 = v23;
            v23 = v12;
            if ( v13 )
              (*(void (__fastcall **)(AppReadiness::User *))(*(_QWORD *)v13 + 16LL))(v13);
            v14 = v26;
            if ( v26 )
            {
              v26 = 0;
              (*(void (__fastcall **)(AppReadiness::User *))(*(_QWORD *)v14 + 16LL))(v14);
            }
            if ( v32 > 7 )
              std::_Deallocate<16>(pExceptionObject[0], 2 * v32 + 2);
            v27[0] = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
            Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(v27);
            v10 = v23;
          }
          AppReadiness::User::SetShouldQueryAppx(v10, 1);
          AppReadiness::Service::ProcessUserTasks(v2, v23);
          v15 = v23;
          if ( v23 )
          {
            v23 = 0;
            (*(void (__fastcall **)(AppReadiness::User *))(*(_QWORD *)v15 + 16LL))(v15);
          }
          i = pCount;
        }
      }
    }
    if ( v5 )
      WTSFreeMemory(v5);
  }
  else if ( (unsigned __int8)IsUMgrEnumerateSessionUsersPresent(v3) )
  {
    if ( *((_DWORD *)this + 60) != 3 )
    {
      v27[0] = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
      v27[1] = 0;
      DefaultAccountSid = (_QWORD *)AppReadiness::User::GetDefaultAccountSid(pExceptionObject);
      AppReadiness::Service::CreateUser((__int64)v2, &v23, DefaultAccountSid, (__int64)v27);
      std::pair<std::wstring,enum AppReadiness::Storage::PackageOperation>::~pair<std::wstring,enum AppReadiness::Storage::PackageOperation>(pExceptionObject);
      AppReadiness::User::SetShouldQueryAppx(v23, 1);
      AppReadiness::Service::ProcessUserTasks(v2, v23);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
      v27[0] = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
      Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(v27);
    }
    pCount = 0;
    ppSessionInfo = 0;
    v17 = UMgrEnumerateSessionUsers(&pCount, &ppSessionInfo);
    if ( v17 < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)pExceptionObject,
        v17,
        "UMgrEnumerateSessionUsers(&usersCount, &sessionUsers)",
        "AppReadiness::Tasks::PackageChanges::OnExecute",
        "onecoreuap\\shell\\appreadiness\\src\\tasks\\packagechanges.cpp",
        91);
      throw (Windows::HResultException *)pExceptionObject;
    }
    for ( j = 0; j < pCount; ++j )
    {
      v19 = *((_QWORD *)&ppSessionInfo->SessionId + 2 * j);
      AppReadiness::Service::FindUserBySessionIdAndUserContext(
        v2,
        &v23,
        *((unsigned int *)&ppSessionInfo->pWinStationName + 4 * j),
        v19);
      v20 = v23;
      if ( !v23 )
      {
        v28 = (PWTS_SESSION_INFOW)&Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
        v29 = 0;
        v21 = UMgrQueryUserToken(v19, &v29);
        if ( v21 < 0 )
        {
          Windows::HResultException::HResultException(
            (Windows::HResultException *)pExceptionObject,
            v21,
            "UMgrQueryUserToken(sessionUserContext.ContextToken, userToken.GetAddressOf())",
            "AppReadiness::Tasks::PackageChanges::OnExecute",
            "onecoreuap\\shell\\appreadiness\\src\\tasks\\packagechanges.cpp",
            101);
          throw (Windows::HResultException *)pExceptionObject;
        }
        AppReadiness::Service::GetTokenSid(pExceptionObject, &v28);
        v22 = AppReadiness::Service::CreateUser((__int64)v2, &v26, pExceptionObject, (__int64)&v28);
        Microsoft::WRL::ComPtr<IWindowsStoreUserApps>::operator=(&v23, v22);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
        std::pair<std::wstring,enum AppReadiness::Storage::PackageOperation>::~pair<std::wstring,enum AppReadiness::Storage::PackageOperation>(pExceptionObject);
        v28 = (PWTS_SESSION_INFOW)&Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
        Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(&v28);
        v20 = v23;
      }
      if ( !*((_BYTE *)v20 + 177) && !*((_BYTE *)v20 + 176) )
      {
        AppReadiness::User::SetShouldQueryAppx(v20, 1);
        AppReadiness::Service::ProcessUserTasks(v2, v23);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
    }
    wil::details::unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>(&ppSessionInfo);
  }
  AppReadiness::Impl::BaseTask::CompleteTask(this, 0);
}

```

## disassembly

```asm
0x180026c10  mov     [rsp-8+arg_8], rbx
0x180026c15  mov     [rsp-8+arg_10], rsi
0x180026c1a  push    rbp
0x180026c1b  push    rdi
0x180026c1c  push    r12
0x180026c1e  push    r14
0x180026c20  push    r15
0x180026c22  lea     rbp, [rsp-37h]
0x180026c27  sub     rsp, 0B0h
0x180026c2e  mov     rax, cs:__security_cookie
0x180026c35  xor     rax, rsp
0x180026c38  mov     [rbp+57h+var_30], rax
0x180026c3c  mov     r12, rcx
0x180026c3f  call    ?Get@Service@AppReadiness@@SAAEAV12@XZ; AppReadiness::Service::Get(void)
0x180026c44  mov     rsi, rax
0x180026c47  call    ?MarkAllUsersAs@PackageList@Storage@AppReadiness@@SAXW4UserState@23@@Z; AppReadiness::Storage::PackageList::MarkAllUsersAs(AppReadiness::Storage::UserState)
0x180026c4c  call    IsWTSEnumerateSessionsWPresent
0x180026c51  test    al, al
0x180026c53  jz      loc_180026E2D
0x180026c59  mov     [rbp+57h+ppSessionInfo], 0
0x180026c61  mov     [rbp+57h+var_98], 0
0x180026c68  lea     rax, [rbp+57h+var_98]
0x180026c6c  mov     [rsp+0D0h+pCount], rax; pCount
0x180026c71  lea     r9, [rbp+57h+ppSessionInfo]; ppSessionInfo
0x180026c75  xor     edx, edx; Reserved
0x180026c77  xor     ecx, ecx; hServer
0x180026c79  lea     r8d, [rdx+1]; Version
0x180026c7d  call    cs:__imp_WTSEnumerateSessionsW
0x180026c83  test    eax, eax
0x180026c85  jnz     short loc_180026CCE
0x180026c87  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180026c8c  test    eax, eax
0x180026c8e  jns     short loc_180026CCE
0x180026c90  mov     [rsp+0D0h+var_A8], 32h ; '2'; int
0x180026c98  lea     rcx, aOnecoreuapShel_27; "onecoreuap\\shell\\appreadiness\\src\\t"...
0x180026c9f  mov     [rsp+0D0h+pCount], rcx; char *
0x180026ca4  lea     r9, aAppreadinessTa_18; "AppReadiness::Tasks::PackageChanges::On"...
0x180026cab  lea     r8, aWtsenumeratese_0; "WTSEnumerateSessions(WTS_CURRENT_SERVER"...
0x180026cb2  mov     edx, eax; int
0x180026cb4  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180026cb8  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180026cbd  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180026cc4  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180026cc8  call    _CxxThrowException_0
0x180026cce  mov     rbx, [rbp+57h+ppSessionInfo]
0x180026cd2  mov     [rbp+57h+var_70], rbx
0x180026cd6  xor     edi, edi
0x180026cd8  mov     ecx, [rbp+57h+var_98]
0x180026cdb  test    ecx, ecx
0x180026cdd  jz      loc_180026E16
0x180026ce3  lea     r14, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x180026cea  lea     r15, [rdi+rdi*2]
0x180026cee  mov     r8d, [rbx+r15*8]
0x180026cf2  test    r8d, r8d
0x180026cf5  jz      loc_180026E0C
0x180026cfb  mov     eax, [rbx+r15*8+10h]
0x180026d00  test    eax, eax
0x180026d02  jz      short loc_180026D10
0x180026d04  add     eax, 0FFFFFFFDh
0x180026d07  cmp     eax, 1
0x180026d0a  ja      loc_180026E0C
0x180026d10  xor     r9d, r9d
0x180026d13  lea     rdx, [rbp+57h+var_A0]
0x180026d17  mov     rcx, rsi
0x180026d1a  call    ?FindUserBySessionIdAndUserContext@Service@AppReadiness@@QEAA?AV?$ComPtr@VUser@AppReadiness@@@WRL@Microsoft@@K_K@Z; AppReadiness::Service::FindUserBySessionIdAndUserContext(ulong,unsigned __int64)
0x180026d1f  nop
0x180026d20  mov     rcx, [rbp+57h+var_A0]
0x180026d24  test    rcx, rcx
0x180026d27  jnz     loc_180026DD7
0x180026d2d  mov     edx, [rbx+r15*8]
0x180026d31  lea     rcx, [rbp+57h+var_80]
0x180026d35  call    ?GetSessionUserToken@Service@AppReadiness@@SA?AV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@K@Z; AppReadiness::Service::GetSessionUserToken(ulong)
0x180026d3a  nop
0x180026d3b  lea     rdx, [rbp+57h+var_80]
0x180026d3f  lea     rcx, [rbp+57h+pExceptionObject]
0x180026d43  call    ?GetTokenSid@Service@AppReadiness@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@@Z; AppReadiness::Service::GetTokenSid(Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> const &)
0x180026d48  nop
0x180026d49  lea     r9, [rbp+57h+var_80]
0x180026d4d  lea     r8, [rbp+57h+pExceptionObject]
0x180026d51  lea     rdx, [rbp+57h+var_88]
0x180026d55  mov     rcx, rsi
0x180026d58  call    ?CreateUser@Service@AppReadiness@@QEAA?AV?$ComPtr@VUser@AppReadiness@@@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@45@@Z; AppReadiness::Service::CreateUser(std::wstring const &,Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> const &)
0x180026d5d  xor     edx, edx
0x180026d5f  lea     rcx, [rbp+57h+var_60]
0x180026d63  cmp     rcx, rax
0x180026d66  jz      short loc_180026D72
0x180026d68  mov     rdx, [rax]
0x180026d6b  mov     qword ptr [rax], 0
0x180026d72  mov     rcx, [rbp+57h+var_A0]
0x180026d76  mov     [rbp+57h+var_A0], rdx
0x180026d7a  test    rcx, rcx
0x180026d7d  jz      short loc_180026D8C
0x180026d7f  mov     rax, [rcx]
0x180026d82  mov     rax, [rax+10h]
0x180026d86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026d8b  nop
0x180026d8c  mov     rcx, [rbp+57h+var_88]
0x180026d90  test    rcx, rcx
0x180026d93  jz      short loc_180026DAA
0x180026d95  mov     [rbp+57h+var_88], 0
0x180026d9d  mov     rax, [rcx]
0x180026da0  mov     rax, [rax+10h]
0x180026da4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026da9  nop
0x180026daa  mov     rdx, [rbp+57h+var_40]
0x180026dae  cmp     rdx, 7
0x180026db2  jbe     short loc_180026DC6
0x180026db4  lea     rdx, ds:2[rdx*2]
0x180026dbc  mov     rcx, [rbp+57h+pExceptionObject]
0x180026dc0  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180026dc5  nop
0x180026dc6  mov     [rbp+57h+var_80], r14
0x180026dca  lea     rcx, [rbp+57h+var_80]
0x180026dce  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x180026dd3  mov     rcx, [rbp+57h+var_A0]; this
0x180026dd7  mov     dl, 1; bool
0x180026dd9  call    ?SetShouldQueryAppx@User@AppReadiness@@QEAAX_N@Z; AppReadiness::User::SetShouldQueryAppx(bool)
0x180026dde  mov     rdx, [rbp+57h+var_A0]; struct AppReadiness::User *
0x180026de2  mov     rcx, rsi; this
0x180026de5  call    ?ProcessUserTasks@Service@AppReadiness@@QEAAXPEAVUser@2@@Z; AppReadiness::Service::ProcessUserTasks(AppReadiness::User *)
0x180026dea  nop
0x180026deb  mov     rcx, [rbp+57h+var_A0]
0x180026def  test    rcx, rcx
0x180026df2  jz      short loc_180026E09
0x180026df4  mov     [rbp+57h+var_A0], 0
0x180026dfc  mov     rax, [rcx]
0x180026dff  mov     rax, [rax+10h]
0x180026e03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e08  nop
0x180026e09  mov     ecx, [rbp+57h+var_98]
0x180026e0c  inc     edi
0x180026e0e  cmp     edi, ecx
0x180026e10  jb      loc_180026CEA
0x180026e16  test    rbx, rbx
0x180026e19  jz      loc_180027030
0x180026e1f  mov     rcx, rbx; pMemory
0x180026e22  call    cs:__imp_WTSFreeMemory
0x180026e28  jmp     loc_180027030
0x180026e2d  call    IsUMgrEnumerateSessionUsersPresent
0x180026e32  test    al, al
0x180026e34  jz      loc_180027030
0x180026e3a  lea     r14, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x180026e41  cmp     dword ptr [r12+0F0h], 3
0x180026e4a  jz      short loc_180026EAE
0x180026e4c  mov     [rbp+57h+var_80], r14
0x180026e50  mov     [rbp+57h+var_78], 0
0x180026e58  lea     rcx, [rbp+57h+pExceptionObject]
0x180026e5c  call    ?GetDefaultAccountSid@User@AppReadiness@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; AppReadiness::User::GetDefaultAccountSid(void)
0x180026e61  nop
0x180026e62  lea     r9, [rbp+57h+var_80]
0x180026e66  mov     r8, rax
0x180026e69  lea     rdx, [rbp+57h+var_A0]
0x180026e6d  mov     rcx, rsi
0x180026e70  call    ?CreateUser@Service@AppReadiness@@QEAA?AV?$ComPtr@VUser@AppReadiness@@@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@45@@Z; AppReadiness::Service::CreateUser(std::wstring const &,Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> const &)
0x180026e75  nop
0x180026e76  lea     rcx, [rbp+57h+pExceptionObject]
0x180026e7a  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4PackageOperation@Storage@AppReadiness@@@std@@QEAA@XZ; std::pair<std::wstring,AppReadiness::Storage::PackageOperation>::~pair<std::wstring,AppReadiness::Storage::PackageOperation>(void)
0x180026e7f  mov     dl, 1; bool
0x180026e81  mov     rcx, [rbp+57h+var_A0]; this
0x180026e85  call    ?SetShouldQueryAppx@User@AppReadiness@@QEAAX_N@Z; AppReadiness::User::SetShouldQueryAppx(bool)
0x180026e8a  mov     rdx, [rbp+57h+var_A0]; struct AppReadiness::User *
0x180026e8e  mov     rcx, rsi; this
0x180026e91  call    ?ProcessUserTasks@Service@AppReadiness@@QEAAXPEAVUser@2@@Z; AppReadiness::Service::ProcessUserTasks(AppReadiness::User *)
0x180026e96  nop
0x180026e97  lea     rcx, [rbp+57h+var_A0]
0x180026e9b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180026ea0  nop
0x180026ea1  mov     [rbp+57h+var_80], r14
0x180026ea5  lea     rcx, [rbp+57h+var_80]
0x180026ea9  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x180026eae  mov     [rbp+57h+var_98], 0
0x180026eb5  mov     [rbp+57h+ppSessionInfo], 0
0x180026ebd  lea     rdx, [rbp+57h+ppSessionInfo]
0x180026ec1  lea     rcx, [rbp+57h+var_98]
0x180026ec5  call    cs:__imp_UMgrEnumerateSessionUsers
0x180026ecb  test    eax, eax
0x180026ecd  jns     short loc_180026F0D
0x180026ecf  mov     [rsp+0D0h+var_A8], 5Bh ; '['; int
0x180026ed7  lea     rcx, aOnecoreuapShel_27; "onecoreuap\\shell\\appreadiness\\src\\t"...
0x180026ede  mov     [rsp+0D0h+pCount], rcx; char *
0x180026ee3  lea     r9, aAppreadinessTa_18; "AppReadiness::Tasks::PackageChanges::On"...
0x180026eea  lea     r8, aUmgrenumerates_0; "UMgrEnumerateSessionUsers(&usersCount, "...
0x180026ef1  mov     edx, eax; int
0x180026ef3  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180026ef7  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180026efc  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180026f03  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180026f07  call    _CxxThrowException_0
0x180026f0d  xor     ebx, ebx
0x180026f0f  cmp     ebx, [rbp+57h+var_98]
0x180026f12  jnb     loc_180027027
0x180026f18  mov     eax, ebx
0x180026f1a  add     rax, rax
0x180026f1d  mov     r8, [rbp+57h+ppSessionInfo]
0x180026f21  mov     rdi, [r8+rax*8]
0x180026f25  mov     r9, rdi
0x180026f28  mov     r8d, [r8+rax*8+8]
0x180026f2d  lea     rdx, [rbp+57h+var_A0]
0x180026f31  mov     rcx, rsi
0x180026f34  call    ?FindUserBySessionIdAndUserContext@Service@AppReadiness@@QEAA?AV?$ComPtr@VUser@AppReadiness@@@WRL@Microsoft@@K_K@Z; AppReadiness::Service::FindUserBySessionIdAndUserContext(ulong,unsigned __int64)
0x180026f39  nop
0x180026f3a  mov     rcx, [rbp+57h+var_A0]
0x180026f3e  test    rcx, rcx
0x180026f41  jnz     short loc_180026FB3
0x180026f43  mov     [rbp+57h+var_70], r14
0x180026f47  mov     [rbp+57h+var_68], rcx
0x180026f4b  lea     rdx, [rbp+57h+var_68]
0x180026f4f  mov     rcx, rdi
0x180026f52  call    cs:__imp_UMgrQueryUserToken
0x180026f58  test    eax, eax
0x180026f5a  js      loc_180026FE9
0x180026f60  lea     rdx, [rbp+57h+var_70]
0x180026f64  lea     rcx, [rbp+57h+pExceptionObject]
0x180026f68  call    ?GetTokenSid@Service@AppReadiness@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@@Z; AppReadiness::Service::GetTokenSid(Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> const &)
0x180026f6d  nop
0x180026f6e  lea     r9, [rbp+57h+var_70]
0x180026f72  lea     r8, [rbp+57h+pExceptionObject]
0x180026f76  lea     rdx, [rbp+57h+var_88]
0x180026f7a  mov     rcx, rsi
0x180026f7d  call    ?CreateUser@Service@AppReadiness@@QEAA?AV?$ComPtr@VUser@AppReadiness@@@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@45@@Z; AppReadiness::Service::CreateUser(std::wstring const &,Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> const &)
0x180026f82  mov     rdx, rax
0x180026f85  lea     rcx, [rbp+57h+var_A0]
0x180026f89  call    ??4?$ComPtr@UIWindowsStoreUserApps@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<IWindowsStoreUserApps>::operator=(Microsoft::WRL::ComPtr<IWindowsStoreUserApps> &&)
0x180026f8e  lea     rcx, [rbp+57h+var_88]
0x180026f92  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180026f97  nop
0x180026f98  lea     rcx, [rbp+57h+pExceptionObject]
0x180026f9c  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4PackageOperation@Storage@AppReadiness@@@std@@QEAA@XZ; std::pair<std::wstring,AppReadiness::Storage::PackageOperation>::~pair<std::wstring,AppReadiness::Storage::PackageOperation>(void)
0x180026fa1  nop
0x180026fa2  mov     [rbp+57h+var_70], r14
0x180026fa6  lea     rcx, [rbp+57h+var_70]
0x180026faa  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x180026faf  mov     rcx, [rbp+57h+var_A0]; this
0x180026fb3  cmp     byte ptr [rcx+0B1h], 0
0x180026fba  jnz     short loc_180026FD9
0x180026fbc  cmp     byte ptr [rcx+0B0h], 0
0x180026fc3  jnz     short loc_180026FD9
0x180026fc5  mov     dl, 1; bool
0x180026fc7  call    ?SetShouldQueryAppx@User@AppReadiness@@QEAAX_N@Z; AppReadiness::User::SetShouldQueryAppx(bool)
0x180026fcc  mov     rdx, [rbp+57h+var_A0]; struct AppReadiness::User *
0x180026fd0  mov     rcx, rsi; this
0x180026fd3  call    ?ProcessUserTasks@Service@AppReadiness@@QEAAXPEAVUser@2@@Z; AppReadiness::Service::ProcessUserTasks(AppReadiness::User *)
0x180026fd8  nop
0x180026fd9  lea     rcx, [rbp+57h+var_A0]
0x180026fdd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180026fe2  inc     ebx
0x180026fe4  jmp     loc_180026F0F
0x180026fe9  mov     [rsp+0D0h+var_A8], 65h ; 'e'; int
0x180026ff1  lea     rcx, aOnecoreuapShel_27; "onecoreuap\\shell\\appreadiness\\src\\t"...
0x180026ff8  mov     [rsp+0D0h+pCount], rcx; char *
0x180026ffd  lea     r9, aAppreadinessTa_18; "AppReadiness::Tasks::PackageChanges::On"...
0x180027004  lea     r8, aUmgrqueryusert_1; "UMgrQueryUserToken(sessionUserContext.C"...
0x18002700b  mov     edx, eax; int
0x18002700d  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180027011  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180027016  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18002701d  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180027021  call    _CxxThrowException_0
0x180027027  lea     rcx, [rbp+57h+ppSessionInfo]
0x18002702b  call    ??1?$unique_storage@U?$resource_policy@PEAU_SESSION_USER_CONTEXT@@P6AXPEAU1@@Z$1?UMgrFreeSessionUsers@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>(void)
0x180027030  xor     edx, edx; int
0x180027032  mov     rcx, r12; this
0x180027035  call    ?CompleteTask@BaseTask@Impl@AppReadiness@@IEAA_NJ@Z; AppReadiness::Impl::BaseTask::CompleteTask(long)
0x18002703a  mov     rcx, [rbp+57h+var_30]
0x18002703e  xor     rcx, rsp; StackCookie
0x180027041  call    __security_check_cookie
0x180027046  lea     r11, [rsp+0D0h+var_20]
0x18002704e  mov     rbx, [r11+38h]
0x180027052  mov     rsi, [r11+40h]
0x180027056  mov     rsp, r11
0x180027059  pop     r15
0x18002705b  pop     r14
0x18002705d  pop     r12
0x18002705f  pop     rdi
0x180027060  pop     rbp
0x180027061  retn
```
