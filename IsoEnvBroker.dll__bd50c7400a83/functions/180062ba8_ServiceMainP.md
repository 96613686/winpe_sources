# ServiceMainP

- ea: `0x180062ba8`
- end: `0x180063240`
- name: `ServiceMainP`
- size: `1688`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `33`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000e560`

## callees

- `0x180002520`
- `0x1800030d0`
- `0x1800030e8`
- `0x180005c78`
- `0x18000a444`
- `0x18000bb10`
- `0x18000bd98`
- `0x18000e4ec`
- `0x180011e18`
- `0x1800134e8`
- `0x180023170`
- `0x18003dce4`
- `0x1800472d8`
- `0x18004f6f8`
- `0x180056060`
- `0x18005fa0c`
- `0x18005facc`
- `0x18005fbc4`
- `0x18005fdf4`
- `0x180060218`
- `0x1800607fc`
- `0x1800617e8`
- `0x180061944`
- `0x180061d58`
- `0x1800628cc`
- `0x1800629b0`
- `0x1800629d4`
- `0x1800629f4`
- `0x180062ba8`
- `0x180063248`
- `0x180063310`
- `0x180063568`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180062efd`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180062efd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180062e9c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006316c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180062e9c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006316c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062cdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062d12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062e5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062f0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062f21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062f70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062cdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062d12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062e5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062f0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062f21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062f70`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180062f44`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180062f83`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180062f44`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180062f83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180062f2c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180062f2c`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180063097`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180063097`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180062d82`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180062db9`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180062d82`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180062db9`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180062ec6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180062ec6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180062e49`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180062e49`
- `AUTHZ!AuthzRegisterSecurityEventSource` at `0x180062d08`
- `AUTHZ!AuthzRegisterSecurityEventSource` at `0x180062d08`
- `AUTHZ!AuthzInstallSecurityEventSource` at `0x180062cd1`
- `AUTHZ!AuthzInstallSecurityEventSource` at `0x180062cd1`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180062c54`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800630f3`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180062c54`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800630f3`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180062c0d`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180062c0d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180062e1a`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180062e1a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x180062f7b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x180062f7b`

## string_xrefs

- `0x1800631f0`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x180062dcb`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\clientidentity.cpp`
- `0x180062d94`: `onecoreuap\windows\core\isoenvbroker\lib\v2\clientidentity.cpp`
- `0x180062bd4`: `ServiceStartActivity`
- `0x18006320d`: `onecoreuap\windows\core\isoenvbroker\lib\common\isoenvbrokersvc.cpp`
- `0x180063222`: `onecoreuap\windows\core\isoenvbroker\lib\common\isoenvbrokersvc.cpp`
- `0x180062c06`: `IsoEnvBroker`
- `0x180062faf`: `IsoEnvBroker`
- `0x180062fdc`: `SYSTEM\CurrentControlSet\Services\IsoEnvBroker\Data`
- `0x180062e13`: `%SystemRoot%\Logs\IsoEnvBroker.log`
- `0x180062e64`: `Error: Could not open log file. Error code: %#x`
- `0x1800630c0`: `Ready.`
- `0x180062c8f`: `IsoEnvBrokerSvc`
- `0x180062c81`: `IsoEnvBrokerSvc Audit Source`

## pseudocode

```c
// Hidden C++ exception states: #wind=26
void __fastcall ServiceMainP(__int64 a1)
{
  SERVICE_STATUS_HANDLE v1; // rax
  unsigned int v2; // r8d
  const char *v3; // r9
  unsigned int v4; // r8d
  const char *v5; // r9
  unsigned int v6; // eax
  const char *v7; // r9
  const char *v8; // r9
  HANDLE FileW; // rax
  DWORD LastError; // eax
  const char *v11; // r9
  RTL_SRWLOCK *v12; // rcx
  void *v13; // rdx
  HANDLE Event; // rsi
  unsigned int v15; // r8d
  const char *v16; // r9
  HANDLE v17; // rbx
  DWORD v18; // edi
  const char *v19; // r9
  __int64 (__fastcall *v20)(HANDLE *, const WCHAR *, HANDLE, void (__fastcall *)(void *, unsigned __int8)); // r14
  HANDLE v21; // rdi
  DWORD v22; // ebx
  unsigned int v23; // eax
  void *v24; // rdx
  unsigned int v25; // r8d
  int unique_key_nothrow; // eax
  __int64 v27; // rax
  __int64 v28; // rcx
  __int64 v29; // rcx
  int v30; // eax
  unsigned int v31; // r8d
  const char *v32; // r9
  RTL_SRWLOCK *v33; // rcx
  unsigned int v34; // eax
  void *v35; // rdx
  unsigned int v36; // r8d
  const struct wil::FailureInfo *v37; // rdx
  wil *v38; // rcx
  DWORD v39; // eax
  DWORD v40; // ebx
  int dwCreationDisposition; // [rsp+20h] [rbp-518h]
  DWORD cbSid; // [rsp+40h] [rbp-4F8h] BYREF
  PSRWLOCK SRWLock; // [rsp+48h] [rbp-4F0h] BYREF
  _QWORD v44[42]; // [rsp+50h] [rbp-4E8h] BYREF
  _QWORD v45[42]; // [rsp+1A0h] [rbp-398h] BYREF
  WCHAR Dst[264]; // [rsp+2F0h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+538h] [rbp+0h]

  checked_srwlock::lock_exclusive(a1, &SRWLock);
  wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v44,
    "ServiceStartActivity");
  v44[0] = &IsoEnvBrokerTelemetry::ServiceStartActivity::`vftable';
  IsoEnvBrokerTelemetry::ServiceStartActivity::StartActivity((IsoEnvBrokerTelemetry::ServiceStartActivity *)v44);
  v1 = RegisterServiceCtrlHandlerExW(L"IsoEnvBroker", ServiceHandler, 0);
  try
  {
    g_serviceState = v1;
    if ( !v1 )
      wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x12B, v2, v3);
    ServiceStatus.dwServiceType = 32;
    ServiceStatus.dwCurrentState = 2;
    ServiceStatus.dwWaitHint = 5000;
    if ( !SetServiceStatus(v1, &ServiceStatus) )
      wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x131, v4, v5);
    if ( byte_1800B9248 )
    {
      v34 = wil::verify_hresult<long>(2147549183LL);
      wil::details::in1diag3::FailFast_Hr(retaddr, v35, v36, (const char *)v34, dwCreationDisposition);
    }
    pRegistration.dwFlags = 0;
    pRegistration.szEventSourceName = L"IsoEnvBrokerSvc Audit Source";
    pRegistration.szEventMessageFile = L"IsoEnvBrokerSvc";
    pRegistration.szExecutableImagePath = 0;
    *(_OWORD *)&pRegistration.szEventSourceXmlSchemaFile = 0;
    pRegistration.pReserved = 0;
    pRegistration.dwObjectTypeNameCount = 0;
    if ( AuthzInstallSecurityEventSource(0, &pRegistration) || (cbSid = GetLastError(), cbSid == 5010) )
    {
      if ( AuthzRegisterSecurityEventSource(0, pRegistration.szEventSourceName, &g_securityLog) )
      {
        byte_1800B9248 = 1;
      }
      else
      {
        cbSid = GetLastError();
        IsoEnvBrokerTelemetry::SecurityLogRegisterSecurityEventSourceFailure<unsigned long>(&cbSid);
      }
    }
    else
    {
      IsoEnvBrokerTelemetry::SecurityLogInstallSecurityEventSourceFailure<unsigned long &>(&cbSid);
    }
    v6 = McGenEventRegister_EventRegister();
    if ( v6 )
    {
      Log(3u, L"EventLog::Init - EventRegister failed with error %lu", v6);
    }
    else
    {
      g_eventLog = 1;
      Log(4u, L"Initialized EventLog");
    }
    cbSid = 68;
    if ( !CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, &ClientIdentity2::s_builtinAdministratorBuffer, &cbSid) )
      wil::details::in1diag3::Return_GetLastError(
        retaddr,
        (void *)0x145,
        (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v2\\clientidentity.cpp",
        v7);
    cbSid = 68;
    if ( !CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, &ClientIdentity::s_builtinAdministratorBuffer, &cbSid) )
      wil::details::in1diag3::Return_GetLastError(
        retaddr,
        (void *)0x183,
        (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\clientidentity.cpp",
        v8);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59372856>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID59372856>::GetImpl'::`2'::impl) )
    {
      memset_0(Dst, 0, 0x208u);
      ExpandEnvironmentStringsW(L"%SystemRoot%\\Logs\\IsoEnvBroker.log", Dst, 0x104u);
      FileW = CreateFileW(Dst, 0xC0000000, 7u, 0, 2u, 0x80u, 0);
      g_hLogFile = FileW;
      if ( FileW == (HANDLE)-1LL )
      {
        LastError = GetLastError();
        wprintf(L"Error: Could not open log file. Error code: %#x", LastError);
        v44[0] = &IsoEnvBrokerTelemetry::ServiceStartActivity::`vftable';
        wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v44);
        wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v44);
        v12 = SRWLock;
        if ( SRWLock )
        {
          LODWORD(SRWLock[1].Ptr) = 0;
          ReleaseSRWLockExclusive(v12);
        }
        return;
      }
      LOWORD(cbSid) = -257;
      WriteFile(FileW, &cbSid, 2u, 0, 0);
    }
    if ( wil::details::g_pfnLoggingCallback
      && (__int64 (__fastcall *)())wil::details::g_pfnLoggingCallback != ServiceMainP_::_3_::_lambda_1_::_lambda_invoker_cdecl_ )
    {
      memset_0(Dst, 0, 0x98u);
      wil::details::WilFailFast((wil::details *)Dst, v37);
    }
    wil::details::g_pfnLoggingCallback = (__int64)ServiceMainP_::_3_::_lambda_1_::_lambda_invoker_cdecl_;
    Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
    if ( !Event )
      wil::details::in1diag3::Throw_GetLastError(retaddr, v13, v15, v16);
    GetLastError();
    v17 = g_shutdownEvent;
    if ( g_shutdownEvent )
    {
      v18 = GetLastError();
      if ( !CloseHandle(v17) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
          v19);
      SetLastError(v18);
    }
    g_shutdownEvent = Event;
    v20 = *(__int64 (__fastcall **)(HANDLE *, const WCHAR *, HANDLE, void (__fastcall *)(void *, unsigned __int8)))(qword_1800B91E0 + 192);
    v21 = WaitHandle;
    if ( (char *)WaitHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      v22 = GetLastError();
      UnregisterWait(v21);
      SetLastError(v22);
    }
    WaitHandle = 0;
    v23 = v20(&WaitHandle, L"IsoEnvBroker", Event, ServiceStopCallback);
    if ( v23 )
      wil::details::in1diag3::_Throw_Win32(retaddr, v24, v25, (const char *)v23, 0);
    unique_key_nothrow = wil::reg::create_unique_key_nothrow(
                           retaddr,
                           L"SYSTEM\\CurrentControlSet\\Services\\IsoEnvBroker\\Data",
                           &g_rootKey);
    if ( unique_key_nothrow < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x185,
        (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\common\\isoenvbrokersvc.cpp",
        (const char *)(unsigned int)unique_key_nothrow,
        0);
    v27 = wil::reg::create_unique_key(&cbSid, g_rootKey, L"Users");
    AgentAccountRegistry::Initialize(v28, v27);
    MigrateEnabledRegkeyToPolicy();
    Windows::AI::IsolationEnvironment::Preview::IsolationEnvironmentStatics2::CleanupAllOutstandingAgentUsers_DropsLock();
    Windows::AI::IsolationEnvironment::IsolationEnvironmentStatics::CleanupAllOutstandingAgentUsers_DropsLock();
    wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
      v45,
      "RegisterObjectsActivity");
    v45[0] = &IsoEnvBrokerTelemetry::RegisterObjectsActivity::`vftable';
    IsoEnvBrokerTelemetry::RegisterObjectsActivity::StartActivity((IsoEnvBrokerTelemetry::RegisterObjectsActivity *)v45);
    LOBYTE(v29) = 1;
    v30 = ((__int64 (__fastcall *)(__int64))qword_1800B91E8)(v29);
    if ( v30 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x196,
        (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\common\\isoenvbrokersvc.cpp",
        (const char *)(unsigned int)v30,
        0);
    wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v45);
    InitOnceExecuteOnce(
      &Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::initOnceOutOfProc_,
      `Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::Create'::`2'::_lambda_1_::_lambda_invoker_cdecl_,
      0,
      0);
    byte_1800B92C0 = 1;
    (*(void (__fastcall **)(void *))(Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int>::instance_
                                   + 16LL))(&Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int>::instance_);
    BYTE1(cbSid) = 1;
    Log(4u, L"Ready.");
    ServiceStatus.dwCurrentState = 4;
    ServiceStatus.dwControlsAccepted = 4225;
    if ( !SetServiceStatus(g_serviceState, &ServiceStatus) )
      wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x1B4, v31, v32);
    wil::details::lambda_call__ServiceMainP_::_10_::_lambda_2___::_lambda_call__ServiceMainP_::_10_::_lambda_2___(&cbSid);
    wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v44);
    v45[0] = &IsoEnvBrokerTelemetry::RegisterObjectsActivity::`vftable';
    wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v45);
    wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v45);
    v44[0] = &IsoEnvBrokerTelemetry::ServiceStartActivity::`vftable';
    wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v44);
    wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v44);
    v33 = SRWLock;
    if ( SRWLock )
    {
      LODWORD(SRWLock[1].Ptr) = 0;
      ReleaseSRWLockExclusive(v33);
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x1BB,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\common\\isoenvbrokersvc.cpp",
      v11);
    v39 = wil::ResultFromCaughtException(v38);
    v40 = v39;
    if ( g_serviceState )
    {
      if ( v39 )
        Log(2u, L"Service stopping with error code 0x%08X.", v39);
      else
        Log(4u, L"Service stopping with exit code 0.");
      *(_QWORD *)&ServiceStatus.dwCurrentState = 1;
      ServiceStatus.dwWin32ExitCode = v40;
      SetServiceStatus(g_serviceState, &ServiceStatus);
      ServiceState::Reset((ServiceState *)&g_serviceState);
    }
  }
}

```

## disassembly

```asm
0x180062ba8  push    rbx
0x180062baa  push    rsi
0x180062bab  push    rdi
0x180062bac  push    r12
0x180062bae  push    r14
0x180062bb0  sub     rsp, 510h
0x180062bb7  mov     rax, cs:__security_cookie
0x180062bbe  xor     rax, rsp
0x180062bc1  mov     [rsp+538h+var_38], rax
0x180062bc9  lea     rdx, [rsp+538h+SRWLock]
0x180062bce  call    ?lock_exclusive@checked_srwlock@@QEAA?AV?$holder@UExclusiveTag@checked_srwlock@@UAcquireTag@2@$0A@@1@XZ; checked_srwlock::lock_exclusive(void)
0x180062bd3  nop
0x180062bd4  lea     rdx, aServicestartac; "ServiceStartActivity"
0x180062bdb  lea     rcx, [rsp+538h+var_4E8]
0x180062be0  call    ??0?$ActivityBase@VIsoEnvBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180062be5  lea     r12, ??_7ServiceStartActivity@IsoEnvBrokerTelemetry@@6B@; const IsoEnvBrokerTelemetry::ServiceStartActivity::`vftable'
0x180062bec  mov     [rsp+538h+var_4E8], r12
0x180062bf1  lea     rcx, [rsp+538h+var_4E8]; this
0x180062bf6  call    ?StartActivity@ServiceStartActivity@IsoEnvBrokerTelemetry@@QEAAXXZ; IsoEnvBrokerTelemetry::ServiceStartActivity::StartActivity(void)
0x180062bfb  nop
0x180062bfc  xor     r8d, r8d; lpContext
0x180062bff  lea     rdx, ServiceHandler; lpHandlerProc
0x180062c06  lea     rcx, ServiceName; "IsoEnvBroker"
0x180062c0d  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180062c13  mov     cs:?g_serviceState@@3UServiceState@@A, rax; ServiceState g_serviceState
0x180062c1a  mov     rcx, [rsp+538h]; this
0x180062c22  test    rax, rax
0x180062c25  jz      loc_18006319F
0x180062c2b  mov     cs:ServiceStatus.dwServiceType, 20h ; ' '
0x180062c35  mov     esi, 2
0x180062c3a  mov     cs:ServiceStatus.dwCurrentState, esi
0x180062c40  mov     cs:ServiceStatus.dwWaitHint, 1388h
0x180062c4a  lea     rdx, ServiceStatus; lpServiceStatus
0x180062c51  mov     rcx, rax; hServiceStatus
0x180062c54  call    cs:__imp_SetServiceStatus
0x180062c5a  mov     rcx, [rsp+538h]; this
0x180062c62  test    eax, eax
0x180062c64  jz      loc_1800631A9
0x180062c6a  cmp     cs:byte_1800B9248, 0
0x180062c71  jnz     loc_1800631B3
0x180062c77  mov     cs:pRegistration.dwFlags, 0
0x180062c81  lea     rax, aIsoenvbrokersv_0; "IsoEnvBrokerSvc Audit Source"
0x180062c88  mov     cs:pRegistration.szEventSourceName, rax
0x180062c8f  lea     rax, aIsoenvbrokersv; "IsoEnvBrokerSvc"
0x180062c96  mov     cs:pRegistration.szEventMessageFile, rax
0x180062c9d  mov     cs:pRegistration.szExecutableImagePath, 0
0x180062ca8  xorps   xmm0, xmm0
0x180062cab  movdqa  xmmword ptr cs:pRegistration.szEventSourceXmlSchemaFile, xmm0
0x180062cb3  mov     qword ptr cs:pRegistration.30h, 0
0x180062cbe  mov     cs:pRegistration.dwObjectTypeNameCount, 0
0x180062cc8  lea     rdx, pRegistration; pRegistration
0x180062ccf  xor     ecx, ecx; dwFlags
0x180062cd1  call    cs:__imp_AuthzInstallSecurityEventSource
0x180062cd7  test    eax, eax
0x180062cd9  jnz     short loc_180062CF8
0x180062cdb  call    cs:__imp_GetLastError
0x180062ce1  mov     [rsp+538h+cbSid], eax
0x180062ce5  cmp     eax, 1392h
0x180062cea  jz      short loc_180062CF8
0x180062cec  lea     rcx, [rsp+538h+cbSid]
0x180062cf1  call    ??$SecurityLogInstallSecurityEventSourceFailure@AEAK@IsoEnvBrokerTelemetry@@SAXAEAK@Z; IsoEnvBrokerTelemetry::SecurityLogInstallSecurityEventSourceFailure<ulong &>(ulong &)
0x180062cf6  jmp     short loc_180062D2F
0x180062cf8  lea     r8, ?g_securityLog@@3VSecurityLog@@A; phEventProvider
0x180062cff  mov     rdx, cs:pRegistration.szEventSourceName; szEventSourceName
0x180062d06  xor     ecx, ecx; dwFlags
0x180062d08  call    cs:__imp_AuthzRegisterSecurityEventSource
0x180062d0e  test    eax, eax
0x180062d10  jnz     short loc_180062D28
0x180062d12  call    cs:__imp_GetLastError
0x180062d18  mov     [rsp+538h+cbSid], eax
0x180062d1c  lea     rcx, [rsp+538h+cbSid]
0x180062d21  call    ??$SecurityLogRegisterSecurityEventSourceFailure@K@IsoEnvBrokerTelemetry@@SAX$$QEAK@Z; IsoEnvBrokerTelemetry::SecurityLogRegisterSecurityEventSourceFailure<ulong>(ulong &&)
0x180062d26  jmp     short loc_180062D2F
0x180062d28  mov     cs:byte_1800B9248, 1
0x180062d2f  call    McGenEventRegister_EventRegister
0x180062d34  test    eax, eax
0x180062d36  jz      short loc_180062D4E
0x180062d38  mov     r8d, eax
0x180062d3b  lea     rdx, aEventlogInitEv; "EventLog::Init - EventRegister failed w"...
0x180062d42  mov     ecx, 3; unsigned __int8
0x180062d47  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180062d4c  jmp     short loc_180062D66
0x180062d4e  mov     cs:?g_eventLog@@3VEventLog@@A, 1; EventLog g_eventLog
0x180062d55  lea     rdx, aInitializedEve; "Initialized EventLog"
0x180062d5c  mov     ecx, 4; unsigned __int8
0x180062d61  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180062d66  mov     ebx, 44h ; 'D'
0x180062d6b  mov     [rsp+538h+cbSid], ebx
0x180062d6f  lea     r9, [rsp+538h+cbSid]; cbSid
0x180062d74  lea     r8, ?s_builtinAdministratorBuffer@ClientIdentity2@@0PAEA; pSid
0x180062d7b  xor     edx, edx; DomainSid
0x180062d7d  lea     edi, [rbx-2Ah]
0x180062d80  mov     ecx, edi; WellKnownSidType
0x180062d82  call    cs:__imp_CreateWellKnownSid
0x180062d88  test    eax, eax
0x180062d8a  jnz     short loc_180062DA5
0x180062d8c  mov     rcx, [rsp+538h]; this
0x180062d94  lea     r8, aOnecoreuapWind_29; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180062d9b  mov     edx, 145h; void *
0x180062da0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180062da5  mov     [rsp+538h+cbSid], ebx
0x180062da9  lea     r9, [rsp+538h+cbSid]; cbSid
0x180062dae  lea     r8, ?s_builtinAdministratorBuffer@ClientIdentity@@0PAEA; pSid
0x180062db5  xor     edx, edx; DomainSid
0x180062db7  mov     ecx, edi; WellKnownSidType
0x180062db9  call    cs:__imp_CreateWellKnownSid
0x180062dbf  test    eax, eax
0x180062dc1  jnz     short loc_180062DDC
0x180062dc3  mov     rcx, [rsp+538h]; this
0x180062dcb  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180062dd2  mov     edx, 183h; void *
0x180062dd7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180062ddc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID59372856@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID59372856@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59372856> `wil::Feature<__WilFeatureTraits_Feature_ID59372856>::GetImpl(void)'::`2'::impl
0x180062de3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID59372856@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59372856>::__private_IsEnabled(void)
0x180062de8  test    al, al
0x180062dea  jz      loc_180062ECC
0x180062df0  xor     edx, edx; Val
0x180062df2  mov     r8d, 208h; Size
0x180062df8  lea     rcx, [rsp+538h+Dst]; void *
0x180062e00  call    memset_0
0x180062e05  mov     r8d, 104h; nSize
0x180062e0b  lea     rdx, [rsp+538h+Dst]; lpDst
0x180062e13  lea     rcx, Src; "%SystemRoot%\\Logs\\IsoEnvBroker.log"
0x180062e1a  call    cs:__imp_ExpandEnvironmentStringsW
0x180062e20  mov     [rsp+538h+hTemplateFile], 0; hTemplateFile
0x180062e29  mov     [rsp+538h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180062e31  mov     [rsp+538h+dwCreationDisposition], esi; dwCreationDisposition
0x180062e35  xor     r9d, r9d; lpSecurityAttributes
0x180062e38  mov     edx, 0C0000000h; dwDesiredAccess
0x180062e3d  lea     r8d, [r9+7]; dwShareMode
0x180062e41  lea     rcx, [rsp+538h+Dst]; lpFileName
0x180062e49  call    cs:__imp_CreateFileW
0x180062e4f  mov     cs:?g_hLogFile@@3PEAXEA, rax; void * g_hLogFile
0x180062e56  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180062e5a  jnz     short loc_180062EA8
0x180062e5c  call    cs:__imp_GetLastError
0x180062e62  mov     edx, eax
0x180062e64  lea     rcx, aErrorCouldNotO_0; "Error: Could not open log file. Error c"...
0x180062e6b  call    wprintf
0x180062e70  nop
0x180062e71  mov     [rsp+538h+var_4E8], r12
0x180062e76  lea     rcx, [rsp+538h+var_4E8]
0x180062e7b  call    ?Destroy@?$ActivityBase@VIsoEnvBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180062e80  lea     rcx, [rsp+538h+var_4E8]
0x180062e85  call    ??1?$ActivityBase@VIsoEnvBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x180062e8a  nop
0x180062e8b  mov     rcx, [rsp+538h+SRWLock]; SRWLock
0x180062e90  test    rcx, rcx
0x180062e93  jz      short loc_180062EA3
0x180062e95  mov     dword ptr [rcx+8], 0
0x180062e9c  call    cs:__imp_ReleaseSRWLockExclusive
0x180062ea2  nop
0x180062ea3  jmp     loc_180063173
0x180062ea8  mov     word ptr [rsp+538h+cbSid], 0FEFFh
0x180062eaf  mov     qword ptr [rsp+538h+dwCreationDisposition], 0; lpOverlapped
0x180062eb8  xor     r9d, r9d; lpNumberOfBytesWritten
0x180062ebb  mov     r8d, esi; nNumberOfBytesToWrite
0x180062ebe  lea     rdx, [rsp+538h+cbSid]; lpBuffer
0x180062ec3  mov     rcx, rax; hFile
0x180062ec6  call    cs:__imp_WriteFile
0x180062ecc  mov     rcx, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180062ed3  lea     rax, _ServiceMainP____3____lambda_1____lambda_invoker_cdecl_
0x180062eda  test    rcx, rcx
0x180062edd  jz      short loc_180062EE8
0x180062edf  cmp     rcx, rax
0x180062ee2  jnz     loc_1800631CE
0x180062ee8  mov     cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA, rax
0x180062eef  xor     edx, edx; lpName
0x180062ef1  xor     ecx, ecx; lpEventAttributes
0x180062ef3  mov     r9d, 1F0003h; dwDesiredAccess
0x180062ef9  lea     r8d, [rdx+1]; dwFlags
0x180062efd  call    cs:__imp_CreateEventExW
0x180062f03  mov     rsi, rax
0x180062f06  test    rax, rax
0x180062f09  jz      loc_180063192
0x180062f0f  call    cs:__imp_GetLastError
0x180062f15  mov     rbx, cs:?g_shutdownEvent@@3V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A
0x180062f1c  test    rbx, rbx
0x180062f1f  jz      short loc_180062F4A
0x180062f21  call    cs:__imp_GetLastError
0x180062f27  mov     edi, eax
0x180062f29  mov     rcx, rbx; hObject
0x180062f2c  call    cs:__imp_CloseHandle
0x180062f32  mov     rcx, [rsp+538h]; this
0x180062f3a  test    eax, eax
0x180062f3c  jz      loc_1800631F0
0x180062f42  mov     ecx, edi; dwErrCode
0x180062f44  call    cs:__imp_SetLastError
0x180062f4a  mov     cs:?g_shutdownEvent@@3V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A, rsi
0x180062f51  mov     rax, cs:qword_1800B91E0
0x180062f58  mov     r14, [rax+0C0h]
0x180062f5f  mov     rdi, cs:WaitHandle
0x180062f66  lea     rax, [rdi-1]
0x180062f6a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180062f6e  ja      short loc_180062F89
0x180062f70  call    cs:__imp_GetLastError
0x180062f76  mov     ebx, eax
0x180062f78  mov     rcx, rdi; WaitHandle
0x180062f7b  call    cs:__imp_UnregisterWait
0x180062f81  mov     ecx, ebx; dwErrCode
0x180062f83  call    cs:__imp_SetLastError
0x180062f89  mov     cs:WaitHandle, 0
0x180062f94  mov     [rsp+538h+dwFlagsAndAttributes], 18h
0x180062f9c  mov     qword ptr [rsp+538h+dwCreationDisposition], 0; int
0x180062fa5  lea     r9, ?ServiceStopCallback@@YAXPEAXE@Z; ServiceStopCallback(void *,uchar)
0x180062fac  mov     r8, rsi
0x180062faf  lea     rdx, ServiceName; "IsoEnvBroker"
0x180062fb6  lea     rcx, WaitHandle
0x180062fbd  mov     rax, r14
0x180062fc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062fc5  mov     rcx, [rsp+538h]; this
0x180062fcd  test    eax, eax
0x180062fcf  jnz     loc_180063202
0x180062fd5  lea     r8, ?g_rootKey@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> g_rootKey
0x180062fdc  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Is"...
0x180062fe3  call    ?create_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEB_WAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::create_unique_key_nothrow(HKEY__ *,wchar_t const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x180062fe8  mov     rcx, [rsp+538h]; this
0x180062ff0  test    eax, eax
0x180062ff2  js      loc_18006320A
0x180062ff8  lea     r8, aUsers; "Users"
0x180062fff  mov     rdx, cs:?g_rootKey@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> g_rootKey
0x180063006  lea     rcx, [rsp+538h+cbSid]
0x18006300b  call    ?create_unique_key@reg@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@PEAUHKEY__@@PEB_WW4key_access@12@@Z; wil::reg::create_unique_key(HKEY__ *,wchar_t const *,wil::reg::key_access)
0x180063010  mov     rdx, rax
0x180063013  call    ?Initialize@AgentAccountRegistry@@QEAAXV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; AgentAccountRegistry::Initialize(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>)
0x180063018  call    ?MigrateEnabledRegkeyToPolicy@@YAXXZ; MigrateEnabledRegkeyToPolicy(void)
0x18006301d  call    ?CleanupAllOutstandingAgentUsers_DropsLock@IsolationEnvironmentStatics2@Preview@IsolationEnvironment@AI@Windows@@SAXXZ; Windows::AI::IsolationEnvironment::Preview::IsolationEnvironmentStatics2::CleanupAllOutstandingAgentUsers_DropsLock(void)
0x180063022  call    ?CleanupAllOutstandingAgentUsers_DropsLock@IsolationEnvironmentStatics@IsolationEnvironment@AI@Windows@@SAXXZ; Windows::AI::IsolationEnvironment::IsolationEnvironmentStatics::CleanupAllOutstandingAgentUsers_DropsLock(void)
0x180063027  lea     rdx, aRegisterobject; "RegisterObjectsActivity"
0x18006302e  lea     rcx, [rsp+538h+var_398]
0x180063036  call    ??0?$ActivityBase@VIsoEnvBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18006303b  lea     rbx, ??_7RegisterObjectsActivity@IsoEnvBrokerTelemetry@@6B@; const IsoEnvBrokerTelemetry::RegisterObjectsActivity::`vftable'
0x180063042  mov     [rsp+538h+var_398], rbx
0x18006304a  lea     rcx, [rsp+538h+var_398]; this
0x180063052  call    ?StartActivity@RegisterObjectsActivity@IsoEnvBrokerTelemetry@@QEAAXXZ; IsoEnvBrokerTelemetry::RegisterObjectsActivity::StartActivity(void)
0x180063057  nop
0x180063058  mov     cl, 1
0x18006305a  mov     rax, cs:qword_1800B91E8
0x180063061  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063066  mov     rcx, [rsp+538h]; this
0x18006306e  test    eax, eax
0x180063070  js      loc_18006321F
0x180063076  lea     rcx, [rsp+538h+var_398]
0x18006307e  call    ?Stop@?$ActivityBase@VIsoEnvBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180063083  xor     r9d, r9d; Context
0x180063086  xor     r8d, r8d; Parameter
0x180063089  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Create@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@SAAEAVSvcHostModule@Internal@Windows@@XZ@SAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180063090  lea     rcx, ?initOnceOutOfProc_@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x180063097  call    cs:__imp_InitOnceExecuteOnce
0x18006309d  mov     cs:byte_1800B92C0, 1
0x1800630a4  mov     rax, cs:?instance_@?$StaticStorage@VSvcHostModule@Internal@Windows@@$00H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int> Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int>::instance_
0x1800630ab  lea     rcx, ?instance_@?$StaticStorage@VSvcHostModule@Internal@Windows@@$00H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int> Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int>::instance_
0x1800630b2  mov     rax, [rax+10h]
0x1800630b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800630bb  mov     byte ptr [rsp+538h+cbSid+1], 1
0x1800630c0  lea     rdx, aReady; "Ready."
0x1800630c7  mov     ecx, 4; unsigned __int8
0x1800630cc  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x1800630d1  mov     cs:ServiceStatus.dwCurrentState, 4
0x1800630db  mov     cs:ServiceStatus.dwControlsAccepted, 1081h
0x1800630e5  lea     rdx, ServiceStatus; lpServiceStatus
0x1800630ec  mov     rcx, cs:?g_serviceState@@3UServiceState@@A; hServiceStatus
0x1800630f3  call    cs:__imp_SetServiceStatus
0x1800630f9  mov     rcx, [rsp+538h]; this
0x180063101  test    eax, eax
0x180063103  jz      loc_180063234
0x180063109  lea     rcx, [rsp+538h+cbSid]
0x18006310e  call    wil__details__lambda_call__ServiceMainP____10____lambda_2______lambda_call__ServiceMainP____10____lambda_2___
0x180063113  lea     rcx, [rsp+538h+var_4E8]
0x180063118  call    ?Stop@?$ActivityBase@VIsoEnvBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18006311d  nop
0x18006311e  mov     [rsp+538h+var_398], rbx
0x180063126  lea     rcx, [rsp+538h+var_398]
0x18006312e  call    ?Destroy@?$ActivityBase@VIsoEnvBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180063133  lea     rcx, [rsp+538h+var_398]
0x18006313b  call    ??1?$ActivityBase@VIsoEnvBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x180063140  nop
0x180063141  mov     [rsp+538h+var_4E8], r12
0x180063146  lea     rcx, [rsp+538h+var_4E8]
0x18006314b  call    ?Destroy@?$ActivityBase@VIsoEnvBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180063150  lea     rcx, [rsp+538h+var_4E8]
0x180063155  call    ??1?$ActivityBase@VIsoEnvBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18006315a  nop
0x18006315b  mov     rcx, [rsp+538h+SRWLock]; SRWLock
0x180063160  test    rcx, rcx
0x180063163  jz      short loc_180063173
0x180063165  mov     dword ptr [rcx+8], 0
0x18006316c  call    cs:__imp_ReleaseSRWLockExclusive
0x180063172  nop
0x180063173  mov     rcx, [rsp+538h+var_38]
0x18006317b  xor     rcx, rsp; StackCookie
0x18006317e  call    __security_check_cookie
0x180063183  add     rsp, 510h
0x18006318a  pop     r14
0x18006318c  pop     r12
0x18006318e  pop     rdi
0x18006318f  pop     rsi
0x180063190  pop     rbx
0x180063191  retn
0x180063192  mov     rcx, [rsp+538h]; this
  ... truncated ...
```
