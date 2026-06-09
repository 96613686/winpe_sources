# DcaMgr::DeviceCredentialMgr::UpdateAuthenticationStage(_DeviceCredentialAuthenticationStage)

- ea: `0x180034114`
- end: `0x180034957`
- name: `?UpdateAuthenticationStage@DeviceCredentialMgr@DcaMgr@@QEAAJW4_DeviceCredentialAuthenticationStage@@@Z`
- size: `2115`
- prototype: ``
- caller_count: `2`
- callee_count: `38`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180033ff0`
- `0x1800493c0`

## callees

- `0x1800028a8`
- `0x18000293c`
- `0x18000782c`
- `0x18000926c`
- `0x1800281e0`
- `0x180028200`
- `0x18002832c`
- `0x1800288a0`
- `0x180029940`
- `0x180029f0c`
- `0x180031184`
- `0x18003175c`
- `0x1800323d0`
- `0x180032c20`
- `0x180034114`
- `0x180047228`
- `0x180048304`
- `0x180048434`
- `0x18004884c`
- `0x180049a54`
- `0x18004e338`
- `0x1800524a0`
- `0x180053144`
- `0x1800531ac`
- `0x1800535f4`
- `0x1800596ec`
- `0x18005bce8`
- `0x180081438`
- `0x180097c6c`
- `0x180097c90`
- `0x180097cb4`
- `0x180097d30`
- `0x180098cfc`
- `0x18009969c`
- `0x18009982c`
- `0x18009b3c0`
- `0x1800a7bd4`
- `0x1800c40f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__difftime64` at `0x180034307`
- `api-ms-win-crt-private-l1-1-0!_o__difftime64` at `0x180034307`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800341bc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800341bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034846`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034846`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180034888`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180034888`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003482d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003482d`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x180034756`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1800347e0`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1800347f3`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x180034756`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1800347e0`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1800347f3`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x1800342f9`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x180034546`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x180034600`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x1800342f9`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x180034546`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x180034600`
- `RPCRT4!RpcImpersonateClient` at `0x180034334`
- `RPCRT4!RpcImpersonateClient` at `0x180034334`
- `SystemEventsBrokerClient!SebQueryEventPackage` at `0x18003441d`
- `SystemEventsBrokerClient!SebQueryEventPackage` at `0x18003441d`
- `SystemEventsBrokerClient!SebEnumerateEventsByType` at `0x1800343a1`
- `SystemEventsBrokerClient!SebEnumerateEventsByType` at `0x1800343a1`
- `SystemEventsBrokerClient!SebSignalEvent` at `0x1800344a4`
- `SystemEventsBrokerClient!SebSignalEvent` at `0x1800344a4`

## string_xrefs

- `0x180034195`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x18003425c`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x1800342a1`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x1800342d4`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x180034901`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x1800347d3`: `LastDataReadyEvent`

## pseudocode

```c
__int64 __fastcall DcaMgr::DeviceCredentialMgr::UpdateAuthenticationStage(__int64 a1, int a2)
{
  int v4; // ebx
  unsigned __int64 v5; // r9
  __int64 v6; // rdx
  int SessionIdFromToken; // eax
  bool HasAdminPermission; // r14
  unsigned int CallerProcessId; // ebx
  const char *v10; // r9
  int v11; // edx
  const char *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // r9
  int v16; // eax
  double v17; // xmm0_8
  unsigned int v18; // eax
  int v19; // ebx
  unsigned int v20; // ebx
  HKEY v21; // r13
  __int64 v22; // r14
  int v23; // r15d
  const struct _tlgProvider_t *v24; // rax
  int v25; // r15d
  const struct _tlgProvider_t *v26; // rax
  __int64 v27; // r8
  __int64 v28; // r9
  void *v29; // rdx
  wil::details *v30; // rcx
  int v31; // eax
  char *v32; // rbx
  const char *v33; // r9
  int v34; // eax
  int RegStringValue; // ebx
  HKEY *v36; // r8
  const WCHAR *v37; // rcx
  unsigned __int16 *v38; // rax
  int v39; // ecx
  int v40; // edx
  unsigned int v41; // eax
  struct _TP_TIMER **v42; // rbx
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v44; // rcx
  DWORD LastError; // eax
  const struct _tlgProvider_t *v46; // rax
  __int64 *v48; // [rsp+20h] [rbp-B9h]
  char *v49; // [rsp+28h] [rbp-B1h]
  unsigned int *v50; // [rsp+30h] [rbp-A9h]
  unsigned int v51; // [rsp+30h] [rbp-A9h]
  _QWORD *v52; // [rsp+38h] [rbp-A1h]
  __int64 *v53; // [rsp+40h] [rbp-99h]
  HKEY hkey; // [rsp+50h] [rbp-89h] BYREF
  __int64 v55; // [rsp+58h] [rbp-81h] BYREF
  __int64 v56; // [rsp+60h] [rbp-79h] BYREF
  wil::details *v57; // [rsp+68h] [rbp-71h] BYREF
  unsigned int v58[2]; // [rsp+70h] [rbp-69h] BYREF
  HANDLE TokenHandle; // [rsp+78h] [rbp-61h] BYREF
  __int64 *p_hkey; // [rsp+80h] [rbp-59h] BYREF
  unsigned __int16 v61[4]; // [rsp+88h] [rbp-51h] BYREF
  char v62; // [rsp+90h] [rbp-49h]
  int TokenInformation; // [rsp+98h] [rbp-41h] BYREF
  _QWORD v64[2]; // [rsp+A0h] [rbp-39h] BYREF
  __int128 v65; // [rsp+B0h] [rbp-29h] BYREF
  char v66; // [rsp+C0h] [rbp-19h]
  void *p_TokenHandle; // [rsp+D0h] [rbp-9h] BYREF
  __int64 v68; // [rsp+D8h] [rbp-1h] BYREF
  char v69; // [rsp+E0h] [rbp+7h]
  __time64_t Time; // [rsp+E8h] [rbp+Fh] BYREF
  HKEY v71[8]; // [rsp+F0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+5Fh]
  struct _FILETIME pftDueTime; // [rsp+150h] [rbp+77h] BYREF
  unsigned int v74; // [rsp+158h] [rbp+7Fh] BYREF

  v69 = 1;
  TokenHandle = 0;
  p_TokenHandle = &TokenHandle;
  v68 = 0;
  v4 = OpenCallerImpersonationToken(a1, &v68);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&p_TokenHandle);
  if ( v4 < 0 )
  {
    v5 = (unsigned int)v4;
    v6 = 469;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
      (const char *)v5,
      (int)v48);
LABEL_93:
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    return (unsigned int)v4;
  }
  TokenInformation = -1;
  SessionIdFromToken = GetSessionIdFromToken(TokenHandle, &TokenInformation);
  v4 = SessionIdFromToken;
  if ( SessionIdFromToken < 0 )
  {
    v5 = (unsigned int)SessionIdFromToken;
    v6 = 474;
    goto LABEL_5;
  }
  HasAdminPermission = DcaMgr::DeviceCredentialMgr::HasAdminPermission(TokenHandle);
  CallerProcessId = DcaMgr::DeviceCredentialMgr::GetCallerProcessId();
  AcquireSRWLockExclusive((PSRWLOCK)a1);
  v11 = *(_DWORD *)(a1 + 48);
  v55 = a1;
  if ( v11 == -1 )
  {
    if ( a2 != 6 )
    {
      *(_DWORD *)(a1 + 48) = CallerProcessId;
      goto LABEL_11;
    }
    v11 = -1;
  }
  if ( v11 != CallerProcessId )
  {
    v51 = CallerProcessId;
    v4 = -2147024891;
    LODWORD(v49) = v11;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x1ED,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
      (const char *)0x80070005LL,
      (int)"Mismatched process Ids, current process Id=%d, new caller process Id=%d, newStage=%d.",
      v49,
      v51,
      a2);
    goto LABEL_92;
  }
LABEL_11:
  if ( TokenInformation != *(_DWORD *)(a1 + 44) )
  {
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v55);
    v4 = 1;
    goto LABEL_93;
  }
  if ( a2 != 9 )
  {
    if ( *(_DWORD *)(a1 + 24) != 4 )
    {
      if ( *(_DWORD *)(a1 + 24) == 5 )
      {
        if ( a2 != 6 && a2 )
        {
          v12 = "Only expect StoppingAuthentication or NotStarted, newStage=%d.";
          v13 = 538;
LABEL_28:
          LODWORD(v49) = a2;
          v4 = wil::details::in1diag3::Return_Win32Msg(
                 retaddr,
                 (void *)v13,
                 (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
                 (const char *)0x139F,
                 (unsigned int)v12,
                 v49);
          goto LABEL_92;
        }
        if ( !*(_QWORD *)(a1 + 96) )
        {
          wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            &pftDueTime,
            (char *)L"_00000-@@@@@-00000-@@@@@_",
            0xFFFFFFFFFFFFFFFFuLL,
            v10);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
            a1 + 96,
            &pftDueTime);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pftDueTime);
          if ( !*(_QWORD *)(a1 + 96) )
          {
            v14 = 547;
LABEL_21:
            v4 = -2147024882;
            v15 = 2147942414LL;
LABEL_22:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v14,
              (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
              (const char *)v15,
              (int)v48);
LABEL_92:
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v55);
            goto LABEL_93;
          }
        }
      }
      goto LABEL_30;
    }
    if ( a2 != 3 )
    {
      if ( a2 == 5 )
      {
LABEL_30:
        *(_DWORD *)(a1 + 24) = a2;
        goto LABEL_31;
      }
      if ( a2 && a2 != 6 )
      {
        v12 = "Authentication is not finished, newStage=%d.";
        v13 = 517;
        goto LABEL_28;
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      a1 + 96,
      0);
    goto LABEL_30;
  }
LABEL_31:
  v16 = *(_DWORD *)(a1 + 24);
  if ( v16 == 5 )
  {
    *(_DWORD *)(a1 + 40) = 0;
  }
  else if ( (unsigned int)(v16 - 1) > 1 )
  {
    goto LABEL_51;
  }
  Time = 0;
  _time64(&Time);
  v17 = _o__difftime64(Time, *(_QWORD *)(a1 + 32));
  v74 = 0;
  p_TokenHandle = &pftDueTime;
  hkey = *(HKEY *)&v17;
  v57 = 0;
  LOBYTE(pftDueTime.dwLowDateTime) = 0;
  LOWORD(v68) = 256;
  if ( !HasAdminPermission )
  {
    v18 = RpcImpersonateClient(0);
    if ( v18 )
    {
      v4 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x256,
             (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
             (const char *)v18,
             (unsigned int)v48);
      wil::details::ScopeExitFnGuard__lambda_7f3d40de85dbd45b8cf192816ff9c04c___::operator()(&p_TokenHandle);
      v57 = 0;
      goto LABEL_92;
    }
    LOBYTE(pftDueTime.dwLowDateTime) = 1;
  }
  *((_QWORD *)&v65 + 1) = 0;
  *(_QWORD *)&v65 = &v57;
  v66 = 1;
  v19 = SebEnumerateEventsByType(&v74, (char *)&v65 + 8, L"*.*", 66);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>(&v65);
  wil::details::ScopeExitFnGuard__lambda_7f3d40de85dbd45b8cf192816ff9c04c___::operator()(&p_TokenHandle);
  if ( v19 >= 0 )
  {
    v20 = 0;
    if ( v74 )
    {
      v21 = hkey;
      do
      {
        hkey = 0;
        p_hkey = (__int64 *)&hkey;
        *(_QWORD *)v61 = 0;
        v62 = 1;
        v22 = 16LL * v20;
        v65 = *(_OWORD *)((char *)v57 + v22);
        v23 = SebQueryEventPackage(&v65, v61);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_hkey);
        if ( v23 >= 0 )
        {
          v65 = *(_OWORD *)((char *)v57 + v22);
          v25 = SebSignalEvent(&v65, 0, 0, hkey, v48, v49, v50, v52, v53);
          v26 = DevCredSvcTraceLoggingProvider::Provider();
          if ( *(_DWORD *)v26 > 4u )
          {
            v71[0] = hkey;
            v58[0] = *(_DWORD *)(a1 + 24);
            v53 = &v56;
            v52 = v64;
            *(_QWORD *)&v65 = (char *)v57 + v22;
            LODWORD(v56) = v25;
            v64[0] = v21;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
              (__int64)v26,
              (__int64)byte_180108DA3,
              v27,
              v28,
              (__int64)v58,
              (__int64)&v65,
              v71);
          }
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            &hkey,
            0);
        }
        else
        {
          v24 = DevCredSvcTraceLoggingProvider::Provider();
          if ( *(_DWORD *)v24 > 4u )
          {
            LODWORD(v56) = *(_DWORD *)(a1 + 24);
            v64[0] = (char *)v57 + v22;
            v50 = v58;
            v58[0] = v23;
            v49 = (char *)v64;
            v48 = &v56;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
              (__int64)v24,
              (__int64)byte_180108DF3);
          }
        }
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hkey);
        ++v20;
      }
      while ( v20 < v74 );
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x262,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
      (const char *)(unsigned int)v19,
      (int)v48);
  }
  _time64((__time64_t *)(a1 + 32));
  wil::details::ScopeExitFnGuard__lambda_7f3d40de85dbd45b8cf192816ff9c04c___::operator()(&p_TokenHandle);
  v30 = v57;
  v57 = 0;
  if ( v30 )
    wil::details::FreeProcessHeap(v30, v29);
LABEL_51:
  if ( *(_DWORD *)(a1 + 24) )
  {
    v31 = DcaMgr::DeviceCredentialMgr::PublishStageChangeEvent((DcaMgr::DeviceCredentialMgr *)a1);
    if ( v31 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x28E,
        (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
        (const char *)(unsigned int)v31,
        (int)v48);
  }
  if ( *(_DWORD *)(a1 + 24) == 5 )
  {
    v32 = *(char **)(a1 + 96);
    if ( v32 )
    {
      if ( wcscmp_0(L"_00000-@@@@@-00000-@@@@@_", *(const wchar_t **)(a1 + 96)) )
      {
        wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          &hkey,
          v32,
          0xFFFFFFFFFFFFFFFFuLL,
          v33);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
          a1 + 120,
          &hkey);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&hkey);
        if ( !*(_QWORD *)(a1 + 120) )
        {
          v14 = 664;
          goto LABEL_21;
        }
        _time64((__time64_t *)(a1 + 112));
        v34 = WriteRegStringValue(
                HKEY_LOCAL_MACHINE,
                L"Software\\Microsoft\\Windows\\CurrentVersion\\SecondaryAuthFactor",
                (char *)L"LastUnlockDeviceId",
                *(LPCVOID *)(a1 + 96));
        v4 = v34;
        if ( v34 < 0 )
        {
          v15 = (unsigned int)v34;
          v14 = 671;
          goto LABEL_22;
        }
        v56 = 0;
        p_hkey = &v56;
        *(_QWORD *)v61 = 0;
        v62 = 1;
        RegStringValue = ReadRegStringValue(
                           HKEY_LOCAL_MACHINE,
                           L"Software\\Microsoft\\Windows\\CurrentVersion\\SecondaryAuthFactor",
                           L"LastProvisionedAppId");
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_hkey);
        if ( RegStringValue < 0 )
        {
          if ( RegStringValue != -2147024894 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x2BD,
              (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
              (const char *)(unsigned int)RegStringValue,
              (int)v48);
        }
        else
        {
          v37 = *(const WCHAR **)(a1 + 96);
          p_hkey = (__int64 *)&hkey;
          hkey = 0;
          *(_QWORD *)v61 = 0;
          v62 = 1;
          v4 = DcaMgr::OpenDeviceRegKey(v37, v61, v36);
          wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hkey);
          if ( v4 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2AB,
              (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
              (const char *)(unsigned int)v4,
              (int)v48);
LABEL_63:
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v56);
            goto LABEL_92;
          }
          p_hkey = (__int64 *)v58;
          *(_QWORD *)v58 = 0;
          *(_QWORD *)v61 = 0;
          v62 = 1;
          v4 = ReadRegStringValue(hkey, 0, L"AppId");
          wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_hkey);
          if ( v4 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2B1,
              (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
              (const char *)(unsigned int)v4,
              (int)v48);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(v58);
            goto LABEL_63;
          }
          v38 = *(unsigned __int16 **)v58;
          do
          {
            v39 = *(unsigned __int16 *)((char *)v38 + v56 - *(_QWORD *)v58);
            v40 = *v38 - v39;
            if ( v40 )
              break;
            ++v38;
          }
          while ( v39 );
          if ( !v40 )
          {
            v41 = RegDeleteKeyValueW(
                    HKEY_LOCAL_MACHINE,
                    L"Software\\Microsoft\\Windows\\CurrentVersion\\SecondaryAuthFactor",
                    L"LastProvisionedAppId");
            if ( v41 )
              wil::details::in1diag3::_Log_Win32(
                retaddr,
                (void *)0x2B8,
                (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
                (const char *)v41,
                (unsigned int)v48);
          }
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(v58);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
        }
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v56);
      }
    }
  }
  if ( (unsigned int)(*(_DWORD *)(a1 + 24) - 5) <= 1 )
  {
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      a1 + 16,
      0);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      a1 + 56,
      0);
    RegDeleteKeyValueW(
      HKEY_LOCAL_MACHINE,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\SecondaryAuthFactor",
      L"LastDataReadyEvent");
    RegDeleteKeyValueW(
      HKEY_LOCAL_MACHINE,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\SecondaryAuthFactor",
      L"LastSessionId");
    if ( *(_DWORD *)(a1 + 24) == 6 )
    {
      if ( !*(_DWORD *)(a1 + 40) && !*(_BYTE *)(a1 + 80) )
      {
        v42 = (struct _TP_TIMER **)(a1 + 72);
        if ( !*(_QWORD *)(a1 + 72) )
        {
          ThreadpoolTimer = CreateThreadpoolTimer(DcaMgr::DeviceCredentialMgr::PresenceCheckTimerCallback, (PVOID)a1, 0);
          wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
            a1 + 72,
            ThreadpoolTimer);
        }
        v44 = *v42;
        if ( *v42 )
        {
          pftDueTime.dwLowDateTime = -100000000;
          pftDueTime.dwHighDateTime = -1;
          SetThreadpoolTimer(v44, &pftDueTime, 0, 0);
          *(_BYTE *)(a1 + 80) = 1;
          v46 = DevCredSvcTraceLoggingProvider::Provider();
          if ( *(_DWORD *)v46 > 4u )
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
              (__int64)v46,
              (unsigned __int8 *)&dword_180108D7C,
              0);
        }
        else
        {
          LastError = GetLastError();
          if ( LastError )
            wil::details::in1diag3::_Log_Win32(
              retaddr,
              (void *)0x2E1,
              (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
              (const char *)LastError,
              (unsigned int)v48);
        }
      }
      *(_DWORD *)(a1 + 44) = -1;
      *(_DWORD *)(a1 + 48) = -1;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        a1 + 96,
        0);
      *(_DWORD *)(a1 + 40) = 1;
    }
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v55);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return 0;
}

```

## disassembly

```asm
0x180034114  mov     [rsp-8+arg_0], rbx
0x180034119  push    rbp
0x18003411a  push    rsi
0x18003411b  push    rdi
0x18003411c  push    r12
0x18003411e  push    r13
0x180034120  push    r14
0x180034122  push    r15
0x180034124  lea     rbp, [rsp-27h]
0x180034129  sub     rsp, 100h
0x180034130  mov     esi, edx
0x180034132  mov     [rbp+57h+var_50], 1
0x180034136  xor     r15d, r15d
0x180034139  lea     rax, [rbp+57h+TokenHandle]
0x18003413d  lea     rdx, [rbp+57h+var_58]
0x180034141  mov     [rbp+57h+TokenHandle], r15
0x180034145  mov     [rbp+57h+var_60], rax
0x180034149  mov     rdi, rcx
0x18003414c  mov     [rbp+57h+var_58], r15
0x180034150  call    OpenCallerImpersonationToken
0x180034155  lea     rcx, [rbp+57h+var_60]
0x180034159  mov     ebx, eax
0x18003415b  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x180034160  test    ebx, ebx
0x180034162  jns     short loc_18003416E
0x180034164  mov     r9d, ebx
0x180034167  mov     edx, 1D5h
0x18003416c  jmp     short loc_180034191
0x18003416e  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180034172  lea     rdx, [rbp+57h+TokenInformation]; TokenInformation
0x180034176  or      r13d, 0FFFFFFFFh
0x18003417a  mov     [rbp+57h+TokenInformation], r13d
0x18003417e  call    GetSessionIdFromToken
0x180034183  mov     ebx, eax
0x180034185  test    eax, eax
0x180034187  jns     short loc_1800341A6
0x180034189  mov     r9d, eax; char *
0x18003418c  mov     edx, 1DAh; void *
0x180034191  mov     rcx, [rbp+5Fh]; this
0x180034195  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x18003419c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800341a1  jmp     loc_180034931
0x1800341a6  mov     rcx, [rbp+57h+TokenHandle]; void *
0x1800341aa  call    ?HasAdminPermission@DeviceCredentialMgr@DcaMgr@@CA_NPEAX@Z; DcaMgr::DeviceCredentialMgr::HasAdminPermission(void *)
0x1800341af  mov     r14b, al
0x1800341b2  call    ?GetCallerProcessId@DeviceCredentialMgr@DcaMgr@@CAKXZ; DcaMgr::DeviceCredentialMgr::GetCallerProcessId(void)
0x1800341b7  mov     rcx, rdi; SRWLock
0x1800341ba  mov     ebx, eax
0x1800341bc  call    cs:__imp_AcquireSRWLockExclusive
0x1800341c2  mov     edx, [rdi+30h]
0x1800341c5  mov     [rsp+130h+var_D8], rdi
0x1800341ca  cmp     edx, r13d
0x1800341cd  jnz     short loc_1800341DC
0x1800341cf  cmp     esi, 6
0x1800341d2  jz      short loc_1800341D9
0x1800341d4  mov     [rdi+30h], ebx
0x1800341d7  jmp     short loc_1800341E4
0x1800341d9  mov     edx, r13d
0x1800341dc  cmp     edx, ebx
0x1800341de  jnz     loc_1800348F2
0x1800341e4  mov     eax, [rdi+2Ch]
0x1800341e7  cmp     [rbp+57h+TokenInformation], eax
0x1800341ea  jnz     loc_1800348E1
0x1800341f0  cmp     esi, 9
0x1800341f3  jz      loc_1800342D1
0x1800341f9  mov     ecx, [rdi+18h]
0x1800341fc  sub     ecx, 4
0x1800341ff  jz      short loc_18003427E
0x180034201  cmp     ecx, 1
0x180034204  jnz     loc_1800342CE
0x18003420a  cmp     esi, 6
0x18003420d  jz      short loc_180034221
0x18003420f  test    esi, esi
0x180034211  jz      short loc_180034221
0x180034213  lea     rax, aOnlyExpectStop; "Only expect StoppingAuthentication or N"...
0x18003421a  mov     edx, 21Ah
0x18003421f  jmp     short loc_18003429D
0x180034221  lea     rbx, [rdi+60h]
0x180034225  cmp     [rbx], r15
0x180034228  jnz     loc_1800342CE
0x18003422e  or      r8, 0FFFFFFFFFFFFFFFFh
0x180034232  lea     rdx, a0000000000; "_00000-@@@@@-00000-@@@@@_"
0x180034239  lea     rcx, [rbp+57h+pftDueTime]
0x18003423d  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180034242  lea     rdx, [rbp+57h+pftDueTime]
0x180034246  mov     rcx, rbx
0x180034249  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18003424e  lea     rcx, [rbp+57h+pftDueTime]; void *
0x180034252  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180034257  cmp     [rbx], r15
0x18003425a  jnz     short loc_1800342CE
0x18003425c  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x180034263  mov     edx, 223h; void *
0x180034268  mov     ebx, 8007000Eh
0x18003426d  mov     r9d, ebx; char *
0x180034270  mov     rcx, [rbp+5Fh]; this
0x180034274  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034279  jmp     loc_180034927
0x18003427e  cmp     esi, 3
0x180034281  jz      short loc_1800342C3
0x180034283  cmp     esi, 5
0x180034286  jz      short loc_1800342CE
0x180034288  test    esi, esi
0x18003428a  jz      short loc_1800342C3
0x18003428c  cmp     esi, 6
0x18003428f  jz      short loc_1800342C3
0x180034291  lea     rax, aAuthentication; "Authentication is not finished, newStag"...
0x180034298  mov     edx, 205h; void *
0x18003429d  mov     rcx, [rbp+5Fh]; this
0x1800342a1  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x1800342a8  mov     dword ptr [rsp+130h+var_108], esi; char *
0x1800342ac  mov     r9d, 139Fh; char *
0x1800342b2  mov     qword ptr [rsp+130h+var_110], rax; unsigned int
0x1800342b7  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x1800342bc  mov     ebx, eax
0x1800342be  jmp     loc_180034927
0x1800342c3  lea     rcx, [rdi+60h]
0x1800342c7  xor     edx, edx
0x1800342c9  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800342ce  mov     [rdi+18h], esi
0x1800342d1  mov     eax, [rdi+18h]
0x1800342d4  lea     rsi, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x1800342db  cmp     eax, 5
0x1800342de  jnz     short loc_1800342E6
0x1800342e0  mov     [rdi+28h], r15d
0x1800342e4  jmp     short loc_1800342F1
0x1800342e6  dec     eax
0x1800342e8  cmp     eax, 1
0x1800342eb  ja      loc_180034567
0x1800342f1  lea     rcx, [rbp+57h+Time]; Time
0x1800342f5  mov     [rbp+57h+Time], r15
0x1800342f9  call    cs:__imp__time64
0x1800342ff  mov     rdx, [rdi+20h]
0x180034303  mov     rcx, [rbp+57h+Time]
0x180034307  call    cs:__imp__o__difftime64
0x18003430d  mov     [rbp+57h+arg_18], r15d
0x180034311  lea     rax, [rbp+57h+pftDueTime]
0x180034315  mov     [rbp+57h+var_60], rax
0x180034319  movsd   [rsp+130h+hkey], xmm0
0x18003431f  mov     [rbp+57h+var_C8], r15
0x180034323  mov     byte ptr [rbp+57h+pftDueTime.dwLowDateTime], r15b
0x180034327  mov     word ptr [rbp+57h+var_58], 100h
0x18003432d  test    r14b, r14b
0x180034330  jnz     short loc_18003437C
0x180034332  xor     ecx, ecx; BindingHandle
0x180034334  call    cs:__imp_RpcImpersonateClient
0x18003433a  test    eax, eax
0x18003433c  jz      short loc_180034378
0x18003433e  mov     rcx, [rbp+5Fh]; this
0x180034342  mov     r9d, eax; char *
0x180034345  mov     r8, rsi; unsigned int
0x180034348  mov     edx, 256h; void *
0x18003434d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180034352  lea     rcx, [rbp+57h+var_60]
0x180034356  mov     ebx, eax
0x180034358  call    wil__details__ScopeExitFnGuard__lambda_7f3d40de85dbd45b8cf192816ff9c04c_____operator__
0x18003435d  mov     rcx, [rbp+57h+var_C8]; this
0x180034361  mov     [rbp+57h+var_C8], r15
0x180034365  test    rcx, rcx
0x180034368  jz      loc_180034927
0x18003436e  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180034373  jmp     loc_180034927
0x180034378  mov     byte ptr [rbp+57h+pftDueTime.dwLowDateTime], 1
0x18003437c  lea     rax, [rbp+57h+var_C8]
0x180034380  mov     qword ptr [rbp+57h+var_80+8], r15
0x180034384  mov     r9d, 42h ; 'B'
0x18003438a  mov     qword ptr [rbp+57h+var_80], rax
0x18003438e  lea     r8, asc_1800E7080; "*.*"
0x180034395  mov     [rbp+57h+var_70], 1
0x180034399  lea     rdx, [rbp+57h+var_80+8]
0x18003439d  lea     rcx, [rbp+57h+arg_18]
0x1800343a1  call    cs:__imp_SebEnumerateEventsByType
0x1800343a7  lea     rcx, [rbp+57h+var_80]
0x1800343ab  mov     ebx, eax
0x1800343ad  call    ??1?$out_param_t@V?$unique_ptr@GUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>(void)
0x1800343b2  lea     rcx, [rbp+57h+var_60]
0x1800343b6  call    wil__details__ScopeExitFnGuard__lambda_7f3d40de85dbd45b8cf192816ff9c04c_____operator__
0x1800343bb  test    ebx, ebx
0x1800343bd  jns     short loc_1800343D8
0x1800343bf  mov     rcx, [rbp+5Fh]; this
0x1800343c3  mov     r9d, ebx; char *
0x1800343c6  mov     r8, rsi; unsigned int
0x1800343c9  mov     edx, 262h; void *
0x1800343ce  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800343d3  jmp     loc_180034542
0x1800343d8  mov     ebx, r15d
0x1800343db  cmp     [rbp+57h+arg_18], r15d
0x1800343df  jbe     loc_180034542
0x1800343e5  mov     r13, [rsp+130h+hkey]
0x1800343ea  lea     rax, [rsp+130h+hkey]
0x1800343ef  mov     [rsp+130h+hkey], r15
0x1800343f4  mov     [rbp+57h+var_B0], rax
0x1800343f8  lea     rdx, [rbp+57h+var_A8]
0x1800343fc  mov     rax, [rbp+57h+var_C8]
0x180034400  lea     rcx, [rbp+57h+var_80]
0x180034404  mov     qword ptr [rbp+57h+var_A8], r15
0x180034408  mov     [rbp+57h+var_A0], 1
0x18003440c  mov     r14d, ebx
0x18003440f  shl     r14, 4
0x180034413  movups  xmm0, xmmword ptr [r14+rax]
0x180034418  movdqu  [rbp+57h+var_80], xmm0
0x18003441d  call    cs:__imp_SebQueryEventPackage
0x180034423  lea     rcx, [rbp+57h+var_B0]
0x180034427  mov     r15d, eax
0x18003442a  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18003442f  test    r15d, r15d
0x180034432  jns     short loc_180034488
0x180034434  call    ?Provider@DevCredSvcTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; DevCredSvcTraceLoggingProvider::Provider(void)
0x180034439  mov     ecx, [rax]
0x18003443b  cmp     ecx, 4
0x18003443e  jbe     loc_180034523
0x180034444  mov     ecx, [rdi+18h]
0x180034447  mov     rdx, [rbp+57h+var_C8]
0x18003444b  mov     dword ptr [rbp+57h+var_D0], ecx
0x18003444e  add     rdx, r14
0x180034451  lea     rcx, [rbp+57h+var_C0]
0x180034455  mov     [rbp+57h+var_90], rdx
0x180034459  mov     [rsp+130h+var_100], rcx
0x18003445e  lea     rdx, byte_180108DF3
0x180034465  lea     rcx, [rbp+57h+var_90]
0x180034469  mov     [rbp+57h+var_C0], r15d
0x18003446d  mov     [rsp+130h+var_108], rcx
0x180034472  lea     rcx, [rbp+57h+var_D0]
0x180034476  mov     qword ptr [rsp+130h+var_110], rcx
0x18003447b  mov     rcx, rax
0x18003447e  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x180034483  jmp     loc_180034523
0x180034488  mov     rax, [rbp+57h+var_C8]
0x18003448c  lea     rcx, [rbp+57h+var_80]
0x180034490  mov     r9, [rsp+130h+hkey]
0x180034495  xor     r8d, r8d
0x180034498  xor     edx, edx
0x18003449a  movups  xmm0, xmmword ptr [r14+rax]
0x18003449f  movdqu  [rbp+57h+var_80], xmm0
0x1800344a4  call    cs:__imp_SebSignalEvent
0x1800344aa  mov     r15d, eax
0x1800344ad  call    ?Provider@DevCredSvcTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; DevCredSvcTraceLoggingProvider::Provider(void)
0x1800344b2  mov     ecx, [rax]
0x1800344b4  cmp     ecx, 4
0x1800344b7  jbe     short loc_180034517
0x1800344b9  mov     rcx, [rsp+130h+hkey]
0x1800344be  mov     rdx, [rbp+57h+var_C8]
0x1800344c2  mov     [rbp+57h+var_40], rcx
0x1800344c6  add     rdx, r14
0x1800344c9  mov     ecx, [rdi+18h]
0x1800344cc  mov     [rbp+57h+var_C0], ecx
0x1800344cf  lea     rcx, [rbp+57h+var_D0]
0x1800344d3  mov     [rsp+130h+var_F0], rcx
0x1800344d8  lea     rcx, [rbp+57h+var_90]
0x1800344dc  mov     [rsp+130h+var_F8], rcx
0x1800344e1  lea     rcx, [rbp+57h+var_40]
0x1800344e5  mov     [rsp+130h+var_100], rcx
0x1800344ea  lea     rcx, [rbp+57h+var_80]
0x1800344ee  mov     [rsp+130h+var_108], rcx
0x1800344f3  lea     rcx, [rbp+57h+var_C0]
0x1800344f7  mov     qword ptr [rsp+130h+var_110], rcx; unsigned int
0x1800344fc  mov     rcx, rax
0x1800344ff  mov     qword ptr [rbp+57h+var_80], rdx
0x180034503  lea     rdx, byte_180108DA3
0x18003450a  mov     dword ptr [rbp+57h+var_D0], r15d
0x18003450e  mov     [rbp+57h+var_90], r13
0x180034512  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180034517  xor     edx, edx
0x180034519  lea     rcx, [rsp+130h+hkey]
0x18003451e  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180034523  lea     rcx, [rsp+130h+hkey]
0x180034528  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003452d  inc     ebx
0x18003452f  mov     r15d, 0
0x180034535  cmp     ebx, [rbp+57h+arg_18]
0x180034538  jb      loc_1800343EA
0x18003453e  or      r13d, 0FFFFFFFFh
0x180034542  lea     rcx, [rdi+20h]; Time
0x180034546  call    cs:__imp__time64
0x18003454c  lea     rcx, [rbp+57h+var_60]
0x180034550  call    wil__details__ScopeExitFnGuard__lambda_7f3d40de85dbd45b8cf192816ff9c04c_____operator__
0x180034555  mov     rcx, [rbp+57h+var_C8]; this
0x180034559  mov     [rbp+57h+var_C8], r15
0x18003455d  test    rcx, rcx
0x180034560  jz      short loc_180034567
0x180034562  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180034567  cmp     [rdi+18h], r15d
0x18003456b  jz      short loc_18003458D
0x18003456d  mov     rcx, rdi; this
0x180034570  call    ?PublishStageChangeEvent@DeviceCredentialMgr@DcaMgr@@AEAAJXZ; DcaMgr::DeviceCredentialMgr::PublishStageChangeEvent(void)
0x180034575  test    eax, eax
0x180034577  jns     short loc_18003458D
0x180034579  mov     rcx, [rbp+5Fh]; this
0x18003457d  mov     r9d, eax; char *
0x180034580  mov     r8, rsi; unsigned int
0x180034583  mov     edx, 28Eh; void *
0x180034588  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003458d  cmp     dword ptr [rdi+18h], 5
0x180034591  lea     r14, aSoftwareMicros_14; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180034598  mov     r12, 0FFFFFFFF80000002h
0x18003459f  jnz     loc_1800347AE
0x1800345a5  mov     rbx, [rdi+60h]
0x1800345a9  test    rbx, rbx
0x1800345ac  jz      loc_1800347AE
0x1800345b2  mov     rdx, rbx; String2
  ... truncated ...
```
