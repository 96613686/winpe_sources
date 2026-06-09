# DcaMgr::DeviceCredentialMgr::BeginAuthentication(_DeviceCredentialAuthenticationScenario,ushort const *)

- ea: `0x1800493c0`
- end: `0x18004979a`
- name: `?BeginAuthentication@DeviceCredentialMgr@DcaMgr@@QEAAJW4_DeviceCredentialAuthenticationScenario@@PEBG@Z`
- size: `986`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18009e800`

## callees

- `0x18000782c`
- `0x18000926c`
- `0x1800281e0`
- `0x180028200`
- `0x1800288a0`
- `0x180031184`
- `0x18003175c`
- `0x1800323d0`
- `0x180034114`
- `0x180047228`
- `0x180048304`
- `0x180048434`
- `0x1800493c0`
- `0x1800497a0`
- `0x1800499b8`
- `0x1800499d4`
- `0x180049a54`
- `0x18004e338`
- `0x1800524a0`
- `0x1800535f4`
- `0x1800997f0`
- `0x18009b414`
- `0x1800a7bd4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800494b3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800494b3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18004973c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18004973c`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180049684`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180049684`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x1800493e5`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x1800493e5`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x180049598`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x180049598`
- `RPCRT4!RpcImpersonateClient` at `0x18004951b`
- `RPCRT4!RpcImpersonateClient` at `0x18004951b`

## string_xrefs

- `0x180049451`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x180049471`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x1800494e0`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x180049544`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x18004956c`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x18004963e`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x1800496bb`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x180049754`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x18004953d`: `OpenEvent %ws`
- `0x18004969b`: `LastDataReadyEvent`

## pseudocode

```c
__int64 __fastcall DcaMgr::DeviceCredentialMgr::BeginAuthentication(__int64 a1, int a2, char *a3)
{
  DWORD active; // edi
  int v7; // ecx
  int v8; // ebx
  unsigned __int64 v9; // r9
  __int64 v10; // rdx
  int SessionIdFromToken; // eax
  struct _TP_TIMER *v12; // rbx
  unsigned int CallerProcessId; // edi
  unsigned int v14; // eax
  int LastErrorMsg; // eax
  __int64 v16; // rdx
  int v17; // r9d
  char *v18; // rax
  signed __int64 v19; // r8
  int v20; // edx
  int v21; // ecx
  const char *v22; // r9
  __int64 v23; // rdx
  int v24; // eax
  int v25; // edi
  struct _TP_TIMER **v26; // rdi
  __int64 v27; // rdx
  int updated; // eax
  unsigned int lpData; // [rsp+20h] [rbp-60h]
  const char *cbData; // [rsp+28h] [rbp-58h]
  int TokenInformation; // [rsp+40h] [rbp-40h] BYREF
  struct _TP_TIMER *v33; // [rsp+48h] [rbp-38h] BYREF
  __int64 v34; // [rsp+50h] [rbp-30h] BYREF
  __int64 v35; // [rsp+58h] [rbp-28h] BYREF
  HANDLE TokenHandle; // [rsp+60h] [rbp-20h] BYREF
  HANDLE *p_TokenHandle; // [rsp+68h] [rbp-18h] BYREF
  HANDLE v38; // [rsp+70h] [rbp-10h] BYREF
  char v39; // [rsp+78h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]
  char v41; // [rsp+C8h] [rbp+48h] BYREF

  TokenHandle = 0;
  active = WTSGetActiveConsoleSessionId();
  v38 = 0;
  v39 = 1;
  p_TokenHandle = &TokenHandle;
  v8 = OpenCallerImpersonationToken(v7, &v38);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&p_TokenHandle);
  if ( v8 < 0 )
  {
    v9 = (unsigned int)v8;
    v10 = 342;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
      (const char *)v9,
      lpData);
    goto LABEL_44;
  }
  TokenInformation = -1;
  SessionIdFromToken = GetSessionIdFromToken(TokenHandle, &TokenInformation);
  v8 = SessionIdFromToken;
  if ( SessionIdFromToken < 0 )
  {
    v9 = (unsigned int)SessionIdFromToken;
    v10 = 347;
    goto LABEL_5;
  }
  if ( TokenInformation != active && TokenInformation )
  {
    v8 = -2147019873;
    LODWORD(cbData) = active;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x163,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
      (const char *)0x8007139FLL,
      (int)"The call is not from console session, console sessionId=%d, new sessionId=%d.",
      cbData,
      TokenInformation);
    goto LABEL_44;
  }
  v12 = 0;
  v33 = 0;
  CallerProcessId = DcaMgr::DeviceCredentialMgr::GetCallerProcessId();
  AcquireSRWLockExclusive((PSRWLOCK)a1);
  v34 = a1;
  if ( a2 == 1 && !*(_DWORD *)(a1 + 40) )
  {
    v8 = -2147418113;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x16F,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
      (const char *)0x8000FFFFLL,
      (int)"The machine is waiting for unlock",
      cbData);
LABEL_12:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v34);
    wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(&v33);
    goto LABEL_44;
  }
  v41 = 0;
  p_TokenHandle = (HANDLE *)&v41;
  LOWORD(v38) = 256;
  v14 = RpcImpersonateClient(0);
  if ( v14 )
  {
    if ( v14 != 1725 )
    {
      v16 = 393;
LABEL_19:
      LastErrorMsg = wil::details::in1diag3::Return_Win32(
                       retaddr,
                       (void *)v16,
                       (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
                       (const char *)v14,
                       lpData);
      goto LABEL_20;
    }
  }
  else
  {
    v41 = 1;
  }
  if ( !(unsigned __int8)_try_open___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAA_NPEBGK_N_Z(
                           a1 + 16,
                           a3) )
  {
    LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                     retaddr,
                     (void *)0x191,
                     (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
                     "OpenEvent %ws",
                     a3);
LABEL_20:
    v8 = LastErrorMsg;
LABEL_21:
    wil::details::ScopeExitFnGuard__lambda_7f3d40de85dbd45b8cf192816ff9c04c___::operator()(&p_TokenHandle);
    goto LABEL_12;
  }
  wil::details::ScopeExitFnGuard__lambda_7f3d40de85dbd45b8cf192816ff9c04c___::operator()(&p_TokenHandle);
  _time64((__time64_t *)(a1 + 32));
  v17 = TokenInformation;
  if ( *(_DWORD *)(a1 + 44) != TokenInformation )
    goto LABEL_30;
  if ( *(_DWORD *)(a1 + 40) != a2 )
    goto LABEL_30;
  if ( *(_DWORD *)(a1 + 48) != CallerProcessId )
    goto LABEL_30;
  v18 = *(char **)(a1 + 56);
  if ( !v18 )
    goto LABEL_30;
  v19 = a3 - v18;
  do
  {
    v20 = *(unsigned __int16 *)&v18[v19];
    v21 = *(unsigned __int16 *)v18 - v20;
    if ( v21 )
      break;
    v18 += 2;
  }
  while ( v20 );
  if ( v21 )
  {
LABEL_30:
    *(_DWORD *)(a1 + 40) = a2;
    *(_DWORD *)(a1 + 44) = v17;
    *(_DWORD *)(a1 + 48) = CallerProcessId;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      a1 + 96,
      0);
    DcaMgr::DeviceCredentialMgrAuthData::Clear(*(DcaMgr::DeviceCredentialMgrAuthData **)(a1 + 88));
    wistd::unique_ptr<DcaMgr::DeviceCredentialHmacBase,wistd::default_delete<DcaMgr::DeviceCredentialHmacBase>>::reset(
      a1 + 104,
      0);
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v35,
      a3,
      0xFFFFFFFFFFFFFFFFuLL,
      v22);
    v23 = v35;
    v35 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      a1 + 56,
      v23);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v35);
    if ( !*(_QWORD *)(a1 + 56) )
    {
      v8 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A7,
        (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
        (const char *)0x8007000ELL,
        lpData);
      goto LABEL_21;
    }
    v14 = RegSetKeyValueW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\SecondaryAuthFactor",
            L"LastSessionId",
            4u,
            (LPCVOID)(a1 + 44),
            4u);
    if ( v14 )
    {
      v16 = 431;
      goto LABEL_19;
    }
    v24 = WriteRegStringValue(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\SecondaryAuthFactor",
            (char *)L"LastDataReadyEvent",
            a3);
    v25 = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B5,
        (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
        (const char *)(unsigned int)v24,
        lpData);
      wil::details::ScopeExitFnGuard__lambda_7f3d40de85dbd45b8cf192816ff9c04c___::operator()(&p_TokenHandle);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v34);
      wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(&v33);
      v8 = v25;
      goto LABEL_44;
    }
  }
  v26 = (struct _TP_TIMER **)(a1 + 72);
  *(_BYTE *)(a1 + 64) = 0;
  v27 = *(_QWORD *)(a1 + 72);
  if ( v27 && &v33 != v26 )
  {
    wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
      &v33,
      v27);
    *v26 = 0;
    v12 = v33;
  }
  *(_BYTE *)(a1 + 80) = 0;
  wil::details::ScopeExitFnGuard__lambda_7f3d40de85dbd45b8cf192816ff9c04c___::operator()(&p_TokenHandle);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v34);
  if ( v12 )
    WaitForThreadpoolTimerCallbacks(v12, 1);
  updated = DcaMgr::DeviceCredentialMgr::UpdateAuthenticationStage(a1, 0);
  if ( updated < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1C6,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
      (const char *)(unsigned int)updated,
      lpData);
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(&v33);
  v8 = 0;
LABEL_44:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800493c0  mov     [rsp-28h+arg_0], rbx
0x1800493c5  mov     [rsp-28h+arg_8], rsi
0x1800493ca  push    rbp
0x1800493cb  push    rdi
0x1800493cc  push    r12
0x1800493ce  push    r14
0x1800493d0  push    r15
0x1800493d2  mov     rbp, rsp
0x1800493d5  sub     rsp, 80h
0x1800493dc  mov     r14, r8
0x1800493df  mov     r12d, edx
0x1800493e2  mov     rsi, rcx
0x1800493e5  call    cs:__imp_WTSGetActiveConsoleSessionId
0x1800493eb  lea     rdx, [rbp+var_10]
0x1800493ef  mov     [rbp+TokenHandle], 0
0x1800493f7  mov     edi, eax
0x1800493f9  mov     [rbp+var_10], 0
0x180049401  lea     rax, [rbp+TokenHandle]
0x180049405  mov     [rbp+var_8], 1
0x180049409  mov     [rbp+var_18], rax
0x18004940d  call    OpenCallerImpersonationToken
0x180049412  lea     rcx, [rbp+var_18]
0x180049416  mov     ebx, eax
0x180049418  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x18004941d  test    ebx, ebx
0x18004941f  jns     short loc_18004942B
0x180049421  mov     r9d, ebx
0x180049424  mov     edx, 156h
0x180049429  jmp     short loc_18004944D
0x18004942b  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18004942f  lea     rdx, [rbp+TokenInformation]; TokenInformation
0x180049433  mov     [rbp+TokenInformation], 0FFFFFFFFh
0x18004943a  call    GetSessionIdFromToken
0x18004943f  mov     ebx, eax
0x180049441  test    eax, eax
0x180049443  jns     short loc_180049462
0x180049445  mov     r9d, eax; char *
0x180049448  mov     edx, 15Bh; void *
0x18004944d  mov     rcx, [rbp+28h]; this
0x180049451  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x180049458  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004945d  jmp     loc_180049773
0x180049462  mov     eax, [rbp+TokenInformation]
0x180049465  cmp     eax, edi
0x180049467  jz      short loc_1800494A3
0x180049469  test    eax, eax
0x18004946b  jz      short loc_1800494A3
0x18004946d  mov     rcx, [rbp+28h]; this
0x180049471  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x180049478  mov     [rsp+80h+var_50], eax
0x18004947c  mov     ebx, 8007139Fh
0x180049481  lea     rax, aTheCallIsNotFr; "The call is not from console session, c"...
0x180049488  mov     dword ptr [rsp+80h+cbData], edi; char *
0x18004948c  mov     r9d, ebx; char *
0x18004948f  mov     [rsp+80h+lpData], rax; int
0x180049494  mov     edx, 163h; void *
0x180049499  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004949e  jmp     loc_180049773
0x1800494a3  xor     ebx, ebx
0x1800494a5  mov     [rbp+var_38], rbx
0x1800494a9  call    ?GetCallerProcessId@DeviceCredentialMgr@DcaMgr@@CAKXZ; DcaMgr::DeviceCredentialMgr::GetCallerProcessId(void)
0x1800494ae  mov     rcx, rsi; SRWLock
0x1800494b1  mov     edi, eax
0x1800494b3  call    cs:__imp_AcquireSRWLockExclusive
0x1800494b9  mov     [rbp+var_30], rsi
0x1800494bd  cmp     r12d, 1
0x1800494c1  jnz     short loc_180049508
0x1800494c3  cmp     [rsi+28h], ebx
0x1800494c6  jnz     short loc_180049508
0x1800494c8  mov     rcx, [rbp+28h]; this
0x1800494cc  lea     rax, aTheMachineIsWa; "The machine is waiting for unlock"
0x1800494d3  mov     ebx, 8000FFFFh
0x1800494d8  mov     [rsp+80h+lpData], rax; int
0x1800494dd  mov     r9d, ebx; char *
0x1800494e0  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x1800494e7  mov     edx, 16Fh; void *
0x1800494ec  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800494f1  lea     rcx, [rbp+var_30]
0x1800494f5  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1800494fa  lea     rcx, [rbp+var_38]
0x1800494fe  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(void)
0x180049503  jmp     loc_180049773
0x180049508  lea     rax, [rbp+arg_18]
0x18004950c  mov     [rbp+arg_18], bl
0x18004950f  xor     ecx, ecx; BindingHandle
0x180049511  mov     [rbp+var_18], rax
0x180049515  mov     word ptr [rbp+var_10], 100h
0x18004951b  call    cs:__imp_RpcImpersonateClient
0x180049521  test    eax, eax
0x180049523  jnz     short loc_18004955C
0x180049525  mov     [rbp+arg_18], 1
0x180049529  lea     rcx, [rsi+10h]
0x18004952d  mov     rdx, r14
0x180049530  call    ?try_open@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAA_NPEBGK_N@Z
0x180049535  test    al, al
0x180049537  jnz     short loc_18004958B
0x180049539  mov     rcx, [rbp+28h]; this
0x18004953d  lea     r9, aOpeneventWs; "OpenEvent %ws"
0x180049544  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x18004954b  mov     [rsp+80h+lpData], r14; char *
0x180049550  mov     edx, 191h; void *
0x180049555  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18004955a  jmp     short loc_18004957B
0x18004955c  cmp     eax, 6BDh
0x180049561  jz      short loc_180049529
0x180049563  mov     edx, 189h; void *
0x180049568  mov     rcx, [rbp+28h]; this
0x18004956c  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x180049573  mov     r9d, eax; char *
0x180049576  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004957b  mov     ebx, eax
0x18004957d  lea     rcx, [rbp+var_18]
0x180049581  call    wil__details__ScopeExitFnGuard__lambda_7f3d40de85dbd45b8cf192816ff9c04c_____operator__
0x180049586  jmp     loc_1800494F1
0x18004958b  lea     rcx, [rbp+var_18]
0x18004958f  call    wil__details__ScopeExitFnGuard__lambda_7f3d40de85dbd45b8cf192816ff9c04c_____operator__
0x180049594  lea     rcx, [rsi+20h]; Time
0x180049598  call    cs:__imp__time64
0x18004959e  mov     r9d, [rbp+TokenInformation]
0x1800495a2  lea     r15, [rsi+2Ch]
0x1800495a6  cmp     [r15], r9d
0x1800495a9  jnz     short loc_1800495E1
0x1800495ab  cmp     [rsi+28h], r12d
0x1800495af  jnz     short loc_1800495E1
0x1800495b1  cmp     [rsi+30h], edi
0x1800495b4  jnz     short loc_1800495E1
0x1800495b6  mov     rax, [rsi+38h]
0x1800495ba  test    rax, rax
0x1800495bd  jz      short loc_1800495E1
0x1800495bf  mov     r8, r14
0x1800495c2  sub     r8, rax
0x1800495c5  movzx   ecx, word ptr [rax]
0x1800495c8  movzx   edx, word ptr [rax+r8]
0x1800495cd  sub     ecx, edx
0x1800495cf  jnz     short loc_1800495D9
0x1800495d1  add     rax, 2
0x1800495d5  test    edx, edx
0x1800495d7  jnz     short loc_1800495C5
0x1800495d9  test    ecx, ecx
0x1800495db  jz      loc_1800496F1
0x1800495e1  lea     rcx, [rsi+60h]
0x1800495e5  mov     [rsi+28h], r12d
0x1800495e9  xor     edx, edx
0x1800495eb  mov     [r15], r9d
0x1800495ee  mov     [rsi+30h], edi
0x1800495f1  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800495f6  mov     rcx, [rsi+58h]; this
0x1800495fa  call    ?Clear@DeviceCredentialMgrAuthData@DcaMgr@@QEAAXXZ; DcaMgr::DeviceCredentialMgrAuthData::Clear(void)
0x1800495ff  lea     rcx, [rsi+68h]
0x180049603  xor     edx, edx
0x180049605  call    ?reset@?$unique_ptr@VDeviceCredentialHmacBase@DcaMgr@@U?$default_delete@VDeviceCredentialHmacBase@DcaMgr@@@wistd@@@wistd@@QEAAXPEAVDeviceCredentialHmacBase@DcaMgr@@@Z; wistd::unique_ptr<DcaMgr::DeviceCredentialHmacBase,wistd::default_delete<DcaMgr::DeviceCredentialHmacBase>>::reset(DcaMgr::DeviceCredentialHmacBase *)
0x18004960a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004960e  lea     rcx, [rbp+var_28]
0x180049612  mov     rdx, r14
0x180049615  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18004961a  mov     rdx, [rbp+var_28]
0x18004961e  lea     rcx, [rsi+38h]
0x180049622  mov     [rbp+var_28], rbx
0x180049626  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18004962b  lea     rcx, [rbp+var_28]; void *
0x18004962f  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180049634  cmp     [rsi+38h], rbx
0x180049638  jnz     short loc_18004965C
0x18004963a  mov     rcx, [rbp+28h]; this
0x18004963e  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x180049645  mov     ebx, 8007000Eh
0x18004964a  mov     edx, 1A7h; void *
0x18004964f  mov     r9d, ebx; char *
0x180049652  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049657  jmp     loc_18004957D
0x18004965c  mov     r9d, 4; dwType
0x180049662  lea     r8, aLastsessionid; "LastSessionId"
0x180049669  mov     dword ptr [rsp+80h+cbData], r9d; cbData
0x18004966e  lea     rdx, aSoftwareMicros_14; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180049675  mov     rdi, 0FFFFFFFF80000002h
0x18004967c  mov     [rsp+80h+lpData], r15; int
0x180049681  mov     rcx, rdi; hKey
0x180049684  call    cs:__imp_RegSetKeyValueW
0x18004968a  test    eax, eax
0x18004968c  jz      short loc_180049698
0x18004968e  mov     edx, 1AFh
0x180049693  jmp     loc_180049568
0x180049698  mov     r9, r14; lpData
0x18004969b  lea     r8, aLastdatareadye; "LastDataReadyEvent"
0x1800496a2  lea     rdx, aSoftwareMicros_14; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800496a9  mov     rcx, rdi; hKey
0x1800496ac  call    WriteRegStringValue
0x1800496b1  mov     edi, eax
0x1800496b3  test    eax, eax
0x1800496b5  jns     short loc_1800496F1
0x1800496b7  mov     rcx, [rbp+28h]; this
0x1800496bb  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x1800496c2  mov     r9d, eax; char *
0x1800496c5  mov     edx, 1B5h; void *
0x1800496ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800496cf  lea     rcx, [rbp+var_18]
0x1800496d3  call    wil__details__ScopeExitFnGuard__lambda_7f3d40de85dbd45b8cf192816ff9c04c_____operator__
0x1800496d8  lea     rcx, [rbp+var_30]
0x1800496dc  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1800496e1  lea     rcx, [rbp+var_38]
0x1800496e5  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(void)
0x1800496ea  mov     ebx, edi
0x1800496ec  jmp     loc_180049773
0x1800496f1  lea     rdi, [rsi+48h]
0x1800496f5  mov     [rsi+40h], bl
0x1800496f8  mov     rdx, [rdi]
0x1800496fb  test    rdx, rdx
0x1800496fe  jz      short loc_180049719
0x180049700  lea     rax, [rbp+var_38]
0x180049704  cmp     rax, rdi
0x180049707  jz      short loc_180049719
0x180049709  lea     rcx, [rbp+var_38]
0x18004970d  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180049712  mov     [rdi], rbx
0x180049715  mov     rbx, [rbp+var_38]
0x180049719  lea     rcx, [rbp+var_18]
0x18004971d  mov     byte ptr [rsi+50h], 0
0x180049721  call    wil__details__ScopeExitFnGuard__lambda_7f3d40de85dbd45b8cf192816ff9c04c_____operator__
0x180049726  lea     rcx, [rbp+var_30]
0x18004972a  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x18004972f  test    rbx, rbx
0x180049732  jz      short loc_180049742
0x180049734  mov     edx, 1; fCancelPendingCallbacks
0x180049739  mov     rcx, rbx; pti
0x18004973c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180049742  xor     edx, edx
0x180049744  mov     rcx, rsi
0x180049747  call    ?UpdateAuthenticationStage@DeviceCredentialMgr@DcaMgr@@QEAAJW4_DeviceCredentialAuthenticationStage@@@Z; DcaMgr::DeviceCredentialMgr::UpdateAuthenticationStage(_DeviceCredentialAuthenticationStage)
0x18004974c  test    eax, eax
0x18004974e  jns     short loc_180049768
0x180049750  mov     rcx, [rbp+28h]; this
0x180049754  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x18004975b  mov     r9d, eax; char *
0x18004975e  mov     edx, 1C6h; void *
0x180049763  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180049768  lea     rcx, [rbp+var_38]
0x18004976c  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(void)
0x180049771  xor     ebx, ebx
0x180049773  lea     rcx, [rbp+TokenHandle]
0x180049777  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004977c  lea     r11, [rsp+80h+var_s0]
0x180049784  mov     eax, ebx
0x180049786  mov     rbx, [r11+30h]
0x18004978a  mov     rsi, [r11+38h]
0x18004978e  mov     rsp, r11
0x180049791  pop     r15
0x180049793  pop     r14
0x180049795  pop     r12
0x180049797  pop     rdi
0x180049798  pop     rbp
0x180049799  retn
```
