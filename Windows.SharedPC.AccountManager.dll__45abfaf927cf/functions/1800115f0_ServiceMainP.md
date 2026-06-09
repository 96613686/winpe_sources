# ServiceMainP

- ea: `0x1800115f0`
- end: `0x180011a0e`
- name: `ServiceMainP`
- size: `1054`
- prototype: `void __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `27`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180009710`

## callees

- `0x180003530`
- `0x180005120`
- `0x180009534`
- `0x180009664`
- `0x18000a1bc`
- `0x18000ccd4`
- `0x18000ccf4`
- `0x18000cd50`
- `0x18000d73c`
- `0x18000e808`
- `0x18000edd4`
- `0x18000eee0`
- `0x18000f03c`
- `0x18000f734`
- `0x18000f760`
- `0x18000fa84`
- `0x18000fbc4`
- `0x1800101c0`
- `0x180010458`
- `0x180010504`
- `0x1800112ac`
- `0x1800112f0`
- `0x18001138c`
- `0x180011474`
- `0x1800115f0`
- `0x18002297c`
- `0x180026010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180011867`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180011867`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011879`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011879`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18001182a`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18001182a`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180011651`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180011651`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800116a4`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180011990`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800116a4`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180011990`

## string_xrefs

- `0x18001160f`: `ServiceStartActivity`
- `0x18001166b`: `shellcommon\shell\sharedpc\accountmanager\lib\service\service.cpp`
- `0x1800116b6`: `shellcommon\shell\sharedpc\accountmanager\lib\service\service.cpp`
- `0x180011776`: `shellcommon\shell\sharedpc\accountmanager\lib\service\service.cpp`
- `0x1800117bf`: `shellcommon\shell\sharedpc\accountmanager\lib\service\service.cpp`
- `0x180011819`: `shellcommon\shell\sharedpc\accountmanager\lib\service\service.cpp`
- `0x180011848`: `shellcommon\shell\sharedpc\accountmanager\lib\service\service.cpp`
- `0x1800118f1`: `shellcommon\shell\sharedpc\accountmanager\lib\service\service.cpp`
- `0x180011950`: `shellcommon\shell\sharedpc\accountmanager\lib\service\service.cpp`
- `0x1800119a2`: `shellcommon\shell\sharedpc\accountmanager\lib\service\service.cpp`

## pseudocode

```c
void __fastcall ServiceMainP(__int64 a1, __int64 a2, __int64 a3)
{
  SERVICE_STATUS_HANDLE v3; // rax
  const char *v4; // r9
  const char *v5; // r9
  int SharedPCRegistryValue; // ebx
  const char *v7; // r9
  int v8; // eax
  int v9; // eax
  int v10; // eax
  bool v11; // cl
  int v12; // eax
  void *v13; // rdx
  HANDLE Event; // rbx
  unsigned int v15; // r8d
  const char *v16; // r9
  __int64 (__fastcall *v17)(__int64 *, const WCHAR *, wil::details *, void (__fastcall *)(void *, unsigned __int8)); // rdi
  wil::details *v18; // rbx
  unsigned int v19; // eax
  __int64 v20; // r8
  __int64 v21; // rcx
  int v22; // eax
  const char *v23; // r9
  wil *v24; // rcx
  int v25; // eax
  int v26; // [rsp+20h] [rbp-328h]
  void *v27; // [rsp+40h] [rbp-308h] BYREF
  void *v28; // [rsp+48h] [rbp-300h] BYREF
  _BYTE v29[32]; // [rsp+50h] [rbp-2F8h] BYREF
  _BYTE v30[32]; // [rsp+70h] [rbp-2D8h] BYREF
  _QWORD v31[42]; // [rsp+90h] [rbp-2B8h] BYREF
  _QWORD v32[42]; // [rsp+1E0h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+348h] [rbp+0h]

  wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v31,
    "ServiceStartActivity",
    a3);
  v31[0] = &SharedPCAccountManagerTelemetry::ServiceStartActivity::`vftable';
  SharedPCAccountManagerTelemetry::ServiceStartActivity::StartActivity((SharedPCAccountManagerTelemetry::ServiceStartActivity *)v31);
  v3 = RegisterServiceCtrlHandlerExW(L"shpamsvc", ServiceHandler, 0);
  try
  {
    g_serviceState = v3;
    if ( !v3 )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xBF,
        (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\service\\service.cpp",
        v4);
    ServiceStatus.dwServiceType = 32;
    ServiceStatus.dwCurrentState = 2;
    ServiceStatus.dwWaitHint = 5000;
    if ( !SetServiceStatus(v3, &ServiceStatus) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xC6,
        (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\service\\service.cpp",
        v5);
    std::wstring::wstring(v30, L"EnableAccountManager");
    std::wstring::wstring(v29, L"AccountManagement");
    SharedPCRegistryValue = GetSharedPCRegistryValue(v29, v30, 0);
    std::wstring::_Tidy_deallocate(v29);
    std::wstring::_Tidy_deallocate(v30);
    if ( SharedPCRegistryValue )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&qword_180036BF0);
      v8 = Microsoft::WRL::Details::MakeAndInitialize<UserAccountStore,IUserAccountStore,>(&qword_180036BF0);
      if ( v8 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xD5,
          (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\service\\service.cpp",
          (const char *)(unsigned int)v8,
          v26);
      v27 = qword_180036BF0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&qword_180036BF8);
      v9 = Microsoft::WRL::Details::MakeAndInitialize<PolicyEngineController,IPolicyEngineController,IUserAccountStore *>(&qword_180036BF8);
      if ( v9 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xD6,
          (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\service\\service.cpp",
          (const char *)(unsigned int)v9,
          v26);
      v27 = qword_180036BF8;
      v28 = qword_180036BF0;
      Microsoft::WRL::ComPtr<LogonTrigger>::InternalRelease(&qword_180036C00);
      v10 = Microsoft::WRL::Details::MakeAndInitialize<LogonTrigger,LogonTrigger,IUserAccountStore *,IPolicyEngineController *>(
              &qword_180036C00,
              &v28,
              &v27);
      if ( v10 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xD7,
          (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\service\\service.cpp",
          (const char *)(unsigned int)v10,
          v26);
      if ( (unsigned __int8)RtlIsStateSeparationEnabled(retaddr) )
      {
        v12 = SetScheduledTaskEnabledState(v11);
        if ( v12 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xDE,
            (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\service\\service.cpp",
            (const char *)(unsigned int)v12,
            v26);
      }
      Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
      if ( !Event )
        wil::details::in1diag3::Throw_GetLastError(retaddr, v13, v15, v16);
      GetLastError();
      _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
        &qword_180036BD8,
        Event);
      v17 = *(__int64 (__fastcall **)(__int64 *, const WCHAR *, wil::details *, void (__fastcall *)(void *, unsigned __int8)))(qword_180036BE8 + 192);
      v18 = qword_180036BD8;
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int UnregisterWait(void *)>>::reset(
        &qword_180036BE0,
        0);
      v19 = v17(&qword_180036BE0, L"shpamsvc", v18, ServiceStopCallback);
      if ( v19 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0xEB,
          (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\service\\service.cpp",
          (const char *)v19,
          0);
      wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
        v32,
        "RegisterObjectsActivity",
        v20);
      v32[0] = &SharedPCAccountManagerTelemetry::RegisterObjectsActivity::`vftable';
      SharedPCAccountManagerTelemetry::RegisterObjectsActivity::StartActivity((SharedPCAccountManagerTelemetry::RegisterObjectsActivity *)v32);
      LOBYTE(v21) = 1;
      v22 = ((__int64 (__fastcall *)(__int64))qword_180036C08)(v21);
      if ( v22 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xEE,
          (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\service\\service.cpp",
          (const char *)(unsigned int)v22,
          0);
      wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v32);
      ServiceStatus.dwCurrentState = 4;
      ServiceStatus.dwControlsAccepted = 4225;
      if ( !SetServiceStatus(g_serviceState, &ServiceStatus) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0xF7,
          (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\service\\service.cpp",
          v23);
      wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v31);
      SharedPCAccountManagerTelemetry::RegisterObjectsActivity::~RegisterObjectsActivity((SharedPCAccountManagerTelemetry::RegisterObjectsActivity *)v32);
      SharedPCAccountManagerTelemetry::ServiceStartActivity::~ServiceStartActivity((SharedPCAccountManagerTelemetry::ServiceStartActivity *)v31);
    }
    else
    {
      SharedPCAccountManagerTelemetry::DisabledUsageDetected();
      ServiceState::StopServiceWithExitCode((ServiceState *)&g_serviceState, -2147418113);
      wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v31);
      SharedPCAccountManagerTelemetry::ServiceStartActivity::~ServiceStartActivity((SharedPCAccountManagerTelemetry::ServiceStartActivity *)v31);
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xFD,
      (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\service\\service.cpp",
      v7);
    v25 = wil::ResultFromCaughtException(v24);
    ServiceState::StopServiceWithExitCode((ServiceState *)&g_serviceState, v25);
  }
}

```

## disassembly

```asm
0x1800115f0  mov     [rsp+arg_0], rbx
0x1800115f5  push    rdi
0x1800115f6  sub     rsp, 340h
0x1800115fd  mov     rax, cs:__security_cookie
0x180011604  xor     rax, rsp
0x180011607  mov     [rsp+348h+var_18], rax
0x18001160f  lea     rdx, aServicestartac; "ServiceStartActivity"
0x180011616  lea     rcx, [rsp+348h+var_2B8]
0x18001161e  call    ??0?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180011623  lea     rax, ??_7ServiceStartActivity@SharedPCAccountManagerTelemetry@@6B@; const SharedPCAccountManagerTelemetry::ServiceStartActivity::`vftable'
0x18001162a  mov     [rsp+348h+var_2B8], rax
0x180011632  lea     rcx, [rsp+348h+var_2B8]; this
0x18001163a  call    ?StartActivity@ServiceStartActivity@SharedPCAccountManagerTelemetry@@QEAAXXZ; SharedPCAccountManagerTelemetry::ServiceStartActivity::StartActivity(void)
0x18001163f  nop
0x180011640  xor     r8d, r8d; lpContext
0x180011643  lea     rdx, ServiceHandler; lpHandlerProc
0x18001164a  lea     rcx, ServiceName; "shpamsvc"
0x180011651  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180011657  mov     cs:?g_serviceState@@3VServiceState@@A, rax; ServiceState g_serviceState
0x18001165e  mov     rcx, [rsp+348h]; this
0x180011666  test    rax, rax
0x180011669  jnz     short loc_18001167C
0x18001166b  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\sharedpc\\accountma"...
0x180011672  mov     edx, 0BFh; void *
0x180011677  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18001167c  mov     cs:ServiceStatus.dwServiceType, 20h ; ' '
0x180011686  mov     cs:ServiceStatus.dwCurrentState, 2
0x180011690  mov     cs:ServiceStatus.dwWaitHint, 1388h
0x18001169a  lea     rdx, ServiceStatus; lpServiceStatus
0x1800116a1  mov     rcx, rax; hServiceStatus
0x1800116a4  call    cs:__imp_SetServiceStatus
0x1800116aa  mov     rcx, [rsp+348h]; this
0x1800116b2  test    eax, eax
0x1800116b4  jnz     short loc_1800116C7
0x1800116b6  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\sharedpc\\accountma"...
0x1800116bd  mov     edx, 0C6h; void *
0x1800116c2  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800116c7  lea     rdx, aEnableaccountm; "EnableAccountManager"
0x1800116ce  lea     rcx, [rsp+348h+var_2D8]
0x1800116d3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800116d8  nop
0x1800116d9  lea     rdx, aAccountmanagem; "AccountManagement"
0x1800116e0  lea     rcx, [rsp+348h+var_2F8]
0x1800116e5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800116ea  nop
0x1800116eb  xor     r8d, r8d
0x1800116ee  lea     rdx, [rsp+348h+var_2D8]
0x1800116f3  lea     rcx, [rsp+348h+var_2F8]
0x1800116f8  call    ?GetSharedPCRegistryValue@@YAKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0K@Z; GetSharedPCRegistryValue(std::wstring const &,std::wstring const &,ulong)
0x1800116fd  mov     ebx, eax
0x1800116ff  lea     rcx, [rsp+348h+var_2F8]
0x180011704  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180011709  nop
0x18001170a  lea     rcx, [rsp+348h+var_2D8]
0x18001170f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180011714  test    ebx, ebx
0x180011716  jnz     short loc_18001174F
0x180011718  call    ?DisabledUsageDetected@SharedPCAccountManagerTelemetry@@SAXXZ; SharedPCAccountManagerTelemetry::DisabledUsageDetected(void)
0x18001171d  mov     edx, 8000FFFFh; int
0x180011722  lea     rcx, ?g_serviceState@@3VServiceState@@A; this
0x180011729  call    ?StopServiceWithExitCode@ServiceState@@QEAAXJ@Z; ServiceState::StopServiceWithExitCode(long)
0x18001172e  lea     rcx, [rsp+348h+var_2B8]
0x180011736  call    ?Stop@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001173b  nop
0x18001173c  lea     rcx, [rsp+348h+var_2B8]; this
0x180011744  call    ??1ServiceStartActivity@SharedPCAccountManagerTelemetry@@QEAA@XZ; SharedPCAccountManagerTelemetry::ServiceStartActivity::~ServiceStartActivity(void)
0x180011749  nop
0x18001174a  jmp     loc_1800119ED
0x18001174f  lea     rcx, qword_180036BF0
0x180011756  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001175b  lea     rcx, qword_180036BF0; void **
0x180011762  call    ??$MakeAndInitialize@VUserAccountStore@@UIUserAccountStore@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUserAccountStore@@@Z; Microsoft::WRL::Details::MakeAndInitialize<UserAccountStore,IUserAccountStore,>(IUserAccountStore * *)
0x180011767  mov     rcx, [rsp+348h]; this
0x18001176f  test    eax, eax
0x180011771  jns     short loc_180011787
0x180011773  mov     r9d, eax; char *
0x180011776  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\sharedpc\\accountma"...
0x18001177d  mov     edx, 0D5h; void *
0x180011782  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180011787  mov     rax, cs:qword_180036BF0
0x18001178e  mov     [rsp+348h+var_308], rax
0x180011793  lea     rcx, qword_180036BF8
0x18001179a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001179f  lea     rdx, [rsp+348h+var_308]
0x1800117a4  lea     rcx, qword_180036BF8; void **
0x1800117ab  call    ??$MakeAndInitialize@VPolicyEngineController@@UIPolicyEngineController@@PEAUIUserAccountStore@@@Details@WRL@Microsoft@@YAJPEAPEAUIPolicyEngineController@@$$QEAPEAUIUserAccountStore@@@Z; Microsoft::WRL::Details::MakeAndInitialize<PolicyEngineController,IPolicyEngineController,IUserAccountStore *>(IPolicyEngineController * *,IUserAccountStore * &&)
0x1800117b0  mov     rcx, [rsp+348h]; this
0x1800117b8  test    eax, eax
0x1800117ba  jns     short loc_1800117D0
0x1800117bc  mov     r9d, eax; char *
0x1800117bf  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\sharedpc\\accountma"...
0x1800117c6  mov     edx, 0D6h; void *
0x1800117cb  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800117d0  mov     rax, cs:qword_180036BF8
0x1800117d7  mov     [rsp+348h+var_308], rax
0x1800117dc  mov     rax, cs:qword_180036BF0
0x1800117e3  mov     [rsp+348h+var_300], rax
0x1800117e8  lea     rcx, qword_180036C00
0x1800117ef  call    ?InternalRelease@?$ComPtr@VLogonTrigger@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<LogonTrigger>::InternalRelease(void)
0x1800117f4  lea     r8, [rsp+348h+var_308]
0x1800117f9  lea     rdx, [rsp+348h+var_300]
0x1800117fe  lea     rcx, qword_180036C00
0x180011805  call    ??$MakeAndInitialize@VLogonTrigger@@V1@PEAUIUserAccountStore@@PEAUIPolicyEngineController@@@Details@WRL@Microsoft@@YAJPEAPEAVLogonTrigger@@$$QEAPEAUIUserAccountStore@@$$QEAPEAUIPolicyEngineController@@@Z; Microsoft::WRL::Details::MakeAndInitialize<LogonTrigger,LogonTrigger,IUserAccountStore *,IPolicyEngineController *>(LogonTrigger * *,IUserAccountStore * &&,IPolicyEngineController * &&)
0x18001180a  mov     rcx, [rsp+348h]; this
0x180011812  test    eax, eax
0x180011814  jns     short loc_18001182A
0x180011816  mov     r9d, eax; char *
0x180011819  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\sharedpc\\accountma"...
0x180011820  mov     edx, 0D7h; void *
0x180011825  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001182a  call    cs:__imp_RtlIsStateSeparationEnabled
0x180011830  test    al, al
0x180011832  jz      short loc_180011859
0x180011834  call    ?SetScheduledTaskEnabledState@@YAJ_N@Z; SetScheduledTaskEnabledState(bool)
0x180011839  mov     rcx, [rsp+348h]; this
0x180011841  test    eax, eax
0x180011843  jns     short loc_180011859
0x180011845  mov     r9d, eax; char *
0x180011848  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\sharedpc\\accountma"...
0x18001184f  mov     edx, 0DEh; void *
0x180011854  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180011859  xor     edx, edx; lpName
0x18001185b  xor     ecx, ecx; lpEventAttributes
0x18001185d  mov     r9d, 1F0003h; dwDesiredAccess
0x180011863  lea     r8d, [rdx+1]; dwFlags
0x180011867  call    cs:__imp_CreateEventExW
0x18001186d  mov     rbx, rax
0x180011870  test    rax, rax
0x180011873  jz      loc_1800119DF
0x180011879  call    cs:__imp_GetLastError
0x18001187f  mov     rdx, rbx
0x180011882  lea     rcx, qword_180036BD8
0x180011889  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001188e  mov     rax, cs:qword_180036BE8
0x180011895  mov     rdi, [rax+0C0h]
0x18001189c  mov     rbx, cs:qword_180036BD8
0x1800118a3  xor     edx, edx
0x1800118a5  lea     rcx, qword_180036BE0
0x1800118ac  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?UnregisterWait@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&UnregisterWait(void *)>>::reset(void *)
0x1800118b1  mov     [rsp+348h+var_320], 18h
0x1800118b9  mov     qword ptr [rsp+348h+var_328], 0; int
0x1800118c2  lea     r9, ?ServiceStopCallback@@YAXPEAXE@Z; ServiceStopCallback(void *,uchar)
0x1800118c9  mov     r8, rbx
0x1800118cc  lea     rdx, ServiceName; "shpamsvc"
0x1800118d3  lea     rcx, qword_180036BE0
0x1800118da  mov     rax, rdi
0x1800118dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118e2  mov     rcx, [rsp+348h]; this
0x1800118ea  test    eax, eax
0x1800118ec  jz      short loc_180011902
0x1800118ee  mov     r9d, eax; char *
0x1800118f1  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\sharedpc\\accountma"...
0x1800118f8  mov     edx, 0EBh; void *
0x1800118fd  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180011902  lea     rdx, aRegisterobject; "RegisterObjectsActivity"
0x180011909  lea     rcx, [rsp+348h+var_168]
0x180011911  call    ??0?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180011916  lea     rax, ??_7RegisterObjectsActivity@SharedPCAccountManagerTelemetry@@6B@; const SharedPCAccountManagerTelemetry::RegisterObjectsActivity::`vftable'
0x18001191d  mov     [rsp+348h+var_168], rax
0x180011925  lea     rcx, [rsp+348h+var_168]; this
0x18001192d  call    ?StartActivity@RegisterObjectsActivity@SharedPCAccountManagerTelemetry@@QEAAXXZ; SharedPCAccountManagerTelemetry::RegisterObjectsActivity::StartActivity(void)
0x180011932  nop
0x180011933  mov     cl, 1
0x180011935  mov     rax, cs:qword_180036C08
0x18001193c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011941  mov     rcx, [rsp+348h]; this
0x180011949  test    eax, eax
0x18001194b  jns     short loc_180011961
0x18001194d  mov     r9d, eax; char *
0x180011950  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\sharedpc\\accountma"...
0x180011957  mov     edx, 0EEh; void *
0x18001195c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180011961  lea     rcx, [rsp+348h+var_168]
0x180011969  call    ?Stop@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001196e  mov     cs:ServiceStatus.dwCurrentState, 4
0x180011978  mov     cs:ServiceStatus.dwControlsAccepted, 1081h
0x180011982  lea     rdx, ServiceStatus; lpServiceStatus
0x180011989  mov     rcx, cs:?g_serviceState@@3VServiceState@@A; hServiceStatus
0x180011990  call    cs:__imp_SetServiceStatus
0x180011996  mov     rcx, [rsp+348h]; this
0x18001199e  test    eax, eax
0x1800119a0  jnz     short loc_1800119B3
0x1800119a2  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\sharedpc\\accountma"...
0x1800119a9  mov     edx, 0F7h; void *
0x1800119ae  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800119b3  lea     rcx, [rsp+348h+var_2B8]
0x1800119bb  call    ?Stop@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800119c0  nop
0x1800119c1  lea     rcx, [rsp+348h+var_168]; this
0x1800119c9  call    ??1RegisterObjectsActivity@SharedPCAccountManagerTelemetry@@QEAA@XZ; SharedPCAccountManagerTelemetry::RegisterObjectsActivity::~RegisterObjectsActivity(void)
0x1800119ce  nop
0x1800119cf  lea     rcx, [rsp+348h+var_2B8]; this
0x1800119d7  call    ??1ServiceStartActivity@SharedPCAccountManagerTelemetry@@QEAA@XZ; SharedPCAccountManagerTelemetry::ServiceStartActivity::~ServiceStartActivity(void)
0x1800119dc  nop
0x1800119dd  jmp     short loc_1800119ED
0x1800119df  mov     rcx, [rsp+348h]; this
0x1800119e7  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800119ed  mov     rcx, [rsp+348h+var_18]
0x1800119f5  xor     rcx, rsp; StackCookie
0x1800119f8  call    __security_check_cookie
0x1800119fd  mov     rbx, [rsp+348h+arg_0]
0x180011a05  add     rsp, 340h
0x180011a0c  pop     rdi
0x180011a0d  retn
```
