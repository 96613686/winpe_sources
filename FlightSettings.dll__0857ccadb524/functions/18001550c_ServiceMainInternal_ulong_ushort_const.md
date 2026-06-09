# ServiceMainInternal(ulong,ushort * * const)

- ea: `0x18001550c`
- end: `0x18001597d`
- name: `?ServiceMainInternal@@YAJKQEAPEAG@Z`
- size: `1137`
- prototype: `__int64 __fastcall(ULONG, LPCWSTR *)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180015420`

## callees

- `0x18000aa48`
- `0x18000cc8c`
- `0x18000e528`
- `0x18001105c`
- `0x180013d20`
- `0x180013da0`
- `0x180013f3c`
- `0x180014230`
- `0x180014348`
- `0x180014fd4`
- `0x18001550c`
- `0x180015c54`
- `0x180015cec`
- `0x180015d7c`
- `0x1800162b4`
- `0x1800177bc`
- `0x1800178a8`
- `0x180017900`
- `0x18006dc84`
- `0x1800859a4`
- `0x180086944`
- `0x18008f55c`
- `0x1800c8010`

## import_xrefs

- `combase!__imp_CoGetSharedServiceId` at `0x1800156f7`
- `combase!__imp_CoGetSharedServiceId` at `0x1800156f7`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x18001573e`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x18001573e`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180015586`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180015586`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015594`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800155c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800156a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015594`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800155c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800156a8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800157be`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800157be`
- `ntdll!RtlNtStatusToDosError` at `0x1800158f2`
- `ntdll!RtlNtStatusToDosError` at `0x1800158f2`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800158e8`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800158e8`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800155b6`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800155b6`

## string_xrefs

- `0x1800155eb`: `onecore\base\flighting\flightsettings\broker\dll\service.cpp`
- `0x180015622`: `onecore\base\flighting\flightsettings\broker\dll\service.cpp`
- `0x1800156cb`: `onecore\base\flighting\flightsettings\broker\dll\service.cpp`
- `0x18001570d`: `onecore\base\flighting\flightsettings\broker\dll\service.cpp`
- `0x180015754`: `onecore\base\flighting\flightsettings\broker\dll\service.cpp`
- `0x18001578b`: `onecore\base\flighting\flightsettings\broker\dll\service.cpp`
- `0x18001593f`: `onecore\base\flighting\flightsettings\broker\dll\service.cpp`
- `0x18001583e`: `##DELETE##`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ServiceMainInternal(ULONG a1, LPCWSTR *a2)
{
  wil::details *v3; // rcx
  HANDLE Event; // rbx
  __int64 v5; // rcx
  signed int LastError; // eax
  signed int v7; // ebx
  int LastErrorFailHr; // eax
  struct _SVCHOST_GLOBAL_DATA *v9; // rdi
  __int64 (__fastcall *v10)(HANDLE *, const wchar_t *, wil::details *, void (__fastcall *)(void *, unsigned __int8)); // rdi
  wil::details *v11; // rbx
  signed int v12; // eax
  int SharedServiceId; // eax
  int v14; // eax
  ServiceComContextRegistrar *v15; // rcx
  int v16; // eax
  __int64 v17; // rcx
  unsigned __int64 v18; // rdx
  wil *v19; // rcx
  int FlightingRegDWORD; // edi
  struct wil::WNF_CHANGE_STAMP_STRUCT *v21; // r9
  unsigned int v22; // edi
  int v23; // edi
  unsigned __int64 v24; // rdx
  unsigned __int8 v25; // cl
  FlightSettingsAPITelemetryClass *v26; // rax
  FlightSettingsAPITelemetryClass *v27; // rax
  __int64 v28; // rcx
  FlightSettingsAPITelemetryClass *v29; // rax
  NTSTATUS v30; // edi
  signed int v31; // eax
  unsigned __int64 v32; // rdx
  unsigned __int8 v33; // cl
  unsigned int v34; // ebx
  __int64 v35; // rcx
  FlightSettingsAPITelemetryClass *v36; // rax
  int v38; // [rsp+20h] [rbp-60h]
  unsigned int v39; // [rsp+40h] [rbp-40h] BYREF
  bool v40[8]; // [rsp+48h] [rbp-38h] BYREF
  _BYTE v41[16]; // [rsp+50h] [rbp-30h] BYREF
  _QWORD v42[2]; // [rsp+60h] [rbp-20h] BYREF
  char v43; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]
  _WNF_STATE_NAME v45; // [rsp+A0h] [rbp+20h] BYREF
  char *v46; // [rsp+B0h] [rbp+30h] BYREF
  int v47; // [rsp+B8h] [rbp+38h] BYREF

  v45.Data[0] = a1;
  v47 = 0;
  LODWORD(v46) = 0;
  Microsoft::WRL::Wrappers::Mutex::Lock(&g_serviceLock, v41, 0xFFFFFFFFLL);
  v42[0] = &v47;
  v42[1] = &v46;
  v43 = 1;
  g_serviceStatus.dwServiceType = 32;
  *(_QWORD *)&g_serviceStatus.dwCurrentState = 2;
  *(_QWORD *)&g_serviceStatus.dwWin32ExitCode = 0;
  *(_QWORD *)&g_serviceStatus.dwCheckPoint = 0;
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( Event )
  {
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      &qword_18011D728,
      Event);
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v3);
    v7 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x212,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\dll\\service.cpp",
        (const char *)(unsigned int)LastErrorFailHr,
        v38);
      v43 = 0;
      lambda_9d15a0f67537066254c22d3eb2f8431c_::operator()(v42);
      goto LABEL_46;
    }
  }
  g_serviceStatusHandle = RegisterServiceCtrlHandlerExW(*a2, ServiceCtrlHandler, 0);
  if ( !g_serviceStatusHandle )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    LODWORD(v46) = v7;
    if ( v7 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x219,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\dll\\service.cpp",
        (const char *)(unsigned int)v7,
        v38);
LABEL_8:
    v43 = 0;
    lambda_9d15a0f67537066254c22d3eb2f8431c_::operator()(v42);
    goto LABEL_46;
  }
  v9 = g_svchostSharedGlobals;
  if ( !g_svchostSharedGlobals )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    v9 = g_svchostSharedGlobals;
  }
  v10 = (__int64 (__fastcall *)(HANDLE *, const wchar_t *, wil::details *, void (__fastcall *)(void *, unsigned __int8)))*((_QWORD *)v9 + 24);
  v11 = qword_18011D728;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<void (*)(void *),&void UnregisterWaitNoCheck(void *)>>::reset(
    v5,
    0);
  v47 = v10(&WaitHandle, L"wisvc", v11, ServiceStopCallback);
  if ( v47 )
  {
    v12 = GetLastError();
    v7 = v12;
    if ( v12 > 0 )
      v7 = (unsigned __int16)v12 | 0x80070000;
    LODWORD(v46) = v7;
    if ( v7 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x22A,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\dll\\service.cpp",
        (const char *)(unsigned int)v7,
        0);
    goto LABEL_8;
  }
  SharedServiceId = CoGetSharedServiceId(&dword_18011D65C);
  v7 = SharedServiceId;
  LODWORD(v46) = SharedServiceId;
  if ( SharedServiceId < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22D,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\dll\\service.cpp",
      (const char *)(unsigned int)SharedServiceId,
      0);
    v43 = 0;
    lambda_9d15a0f67537066254c22d3eb2f8431c_::operator()(v42);
    goto LABEL_46;
  }
  v14 = CoRegisterServerShutdownDelay(qword_18011D728, 60000);
  v7 = v14;
  LODWORD(v46) = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22E,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\dll\\service.cpp",
      (const char *)(unsigned int)v14,
      0);
    v43 = 0;
    lambda_9d15a0f67537066254c22d3eb2f8431c_::operator()(v42);
    goto LABEL_46;
  }
  v16 = ServiceComContextRegistrar::Register(v15);
  v7 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x230,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\dll\\service.cpp",
      (const char *)(unsigned int)v16,
      0);
    v43 = 0;
    lambda_9d15a0f67537066254c22d3eb2f8431c_::operator()(v42);
    goto LABEL_46;
  }
  LOBYTE(v17) = 1;
  SvcAllowAsyncActions(v17);
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  g_serviceStatus.dwControlsAccepted = 5;
  g_serviceStatus.dwCurrentState = 4;
  RegisterForWNSIfNeeded();
  RequestNewChannelUriIfNeeded();
  v39 = 0;
  *(_QWORD *)v40 = -2147483646;
  FlightingRegDWORD = FSRegUtils::GetFlightingRegDWORD((HKEY *)v40, 0, L"WNFEventChangeStamp", &v39);
  if ( FlightingRegDWORD < 0 )
  {
    if ( FlightingRegDWORD != -2147024894 && FlightSettingsAPITelemetryClass::IsEnabled((unsigned __int8)v19, v18) )
    {
      v27 = (FlightSettingsAPITelemetryClass *)wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(
                                                 v19,
                                                 _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_);
      FlightSettingsAPITelemetryClass::ServiceWNSChangeStampReadFromRegFailed_(v27, FlightingRegDWORD);
    }
  }
  else
  {
    *(_DWORD *)v40 = 0;
    LOBYTE(v45.Data[0]) = 0;
    if ( (int)wil::wnf_is_published_nothrow(v19, &v45, v40, v21) >= 0 )
    {
      if ( LOBYTE(v45.Data[0]) )
      {
        v22 = v39;
        if ( *(_DWORD *)v40 == v39 )
          goto LABEL_35;
      }
    }
    *(_QWORD *)v40 = -2147483646;
    v23 = FSRegUtils::SetFlightingRegString((HKEY *)v40, 0, L"WNFEventChangeStamp", L"##DELETE##");
    if ( FlightSettingsAPITelemetryClass::IsEnabled(v25, v24) )
    {
      v26 = (FlightSettingsAPITelemetryClass *)wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(
                                                 v19,
                                                 _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_);
      FlightSettingsAPITelemetryClass::ServiceWNSChangeStampDelete_(v26, v23);
    }
  }
  v22 = 0;
LABEL_35:
  if ( FlightSettingsAPITelemetryClass::IsEnabled((unsigned __int8)v19, v18) )
  {
    v29 = (FlightSettingsAPITelemetryClass *)wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(
                                               v28,
                                               _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_);
    FlightSettingsAPITelemetryClass::ServiceWNSChangeStamp_(v29, v22);
  }
  v30 = RtlSubscribeWnfStateChangeNotification(&g_WNFSubscription, WNF_FLTN_WNF_ARRIVED, v22, TriggerCallback);
  v31 = RtlNtStatusToDosError(v30);
  v34 = v31;
  if ( v31 > 0 )
    v34 = (unsigned __int16)v31 | 0x80070000;
  if ( FlightSettingsAPITelemetryClass::IsEnabled(v33, v32) )
  {
    v36 = (FlightSettingsAPITelemetryClass *)wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(
                                               v35,
                                               _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_);
    FlightSettingsAPITelemetryClass::ServiceWNSRegister_(v36, v34);
  }
  if ( v30 < 0 )
    g_WNFSubscription = 0;
  v7 = (int)v46;
  if ( (int)v46 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x284,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\dll\\service.cpp",
      (const char *)(unsigned int)v46,
      0);
  v43 = 0;
  lambda_9d15a0f67537066254c22d3eb2f8431c_::operator()(v42);
LABEL_46:
  Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT<Microsoft::WRL::Wrappers::HandleTraits::MutexTraits>::InternalUnlock(v41);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001550c  mov     [rsp-18h+arg_8], rbx
0x180015511  mov     [rsp-18h+arg_0.Data], ecx
0x180015515  push    rbp
0x180015516  push    rsi
0x180015517  push    rdi
0x180015518  mov     rbp, rsp
0x18001551b  sub     rsp, 80h
0x180015522  mov     rdi, rdx
0x180015525  xor     esi, esi
0x180015527  mov     [rbp+arg_18], esi
0x18001552a  mov     dword ptr [rbp+arg_10], esi
0x18001552d  or      r8d, 0FFFFFFFFh
0x180015531  lea     rdx, [rbp+var_30]
0x180015535  lea     rcx, ?g_serviceLock@@3VMutex@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::Mutex g_serviceLock
0x18001553c  call    ?Lock@Mutex@Wrappers@WRL@Microsoft@@QEAA?AV?$SyncLockWithStatusT@UMutexTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Details@234@K@Z; Microsoft::WRL::Wrappers::Mutex::Lock(ulong)
0x180015541  nop
0x180015542  lea     rax, [rbp+arg_18]
0x180015546  mov     [rbp+var_20], rax
0x18001554a  lea     rax, [rbp+arg_10]
0x18001554e  mov     [rbp+var_18], rax
0x180015552  mov     [rbp+var_10], 1
0x180015556  mov     cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwServiceType, 20h ; ' '; _SERVICE_STATUS g_serviceStatus ...
0x180015560  mov     qword ptr cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 2; _SERVICE_STATUS g_serviceStatus ...
0x18001556b  mov     qword ptr cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, rsi; _SERVICE_STATUS g_serviceStatus ...
0x180015572  mov     qword ptr cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, rsi; _SERVICE_STATUS g_serviceStatus ...
0x180015579  mov     r9d, 1F0003h; dwDesiredAccess
0x18001557f  xor     r8d, r8d; dwFlags
0x180015582  xor     edx, edx; lpName
0x180015584  xor     ecx, ecx; lpEventAttributes
0x180015586  call    cs:__imp_CreateEventExW
0x18001558c  mov     rbx, rax
0x18001558f  test    rax, rax
0x180015592  jz      short loc_180015610
0x180015594  call    cs:__imp_GetLastError
0x18001559a  mov     rdx, rbx
0x18001559d  lea     rcx, qword_18011D728
0x1800155a4  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800155a9  xor     r8d, r8d; lpContext
0x1800155ac  lea     rdx, ?ServiceCtrlHandler@@YAKKKPEAX0@Z; lpHandlerProc
0x1800155b3  mov     rcx, [rdi]; lpServiceName
0x1800155b6  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x1800155bc  mov     cs:?g_serviceStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * g_serviceStatusHandle
0x1800155c3  test    rax, rax
0x1800155c6  jnz     short loc_180015647
0x1800155c8  call    cs:__imp_GetLastError
0x1800155ce  mov     ebx, eax
0x1800155d0  test    eax, eax
0x1800155d2  jle     short loc_1800155DD
0x1800155d4  movzx   ebx, ax
0x1800155d7  or      ebx, 80070000h
0x1800155dd  mov     dword ptr [rbp+arg_10], ebx
0x1800155e0  test    ebx, ebx
0x1800155e2  jns     short loc_1800155FD
0x1800155e4  mov     rcx, [rbp+18h]; this
0x1800155e8  mov     r9d, ebx; char *
0x1800155eb  lea     r8, aOnecoreBaseFli_45; "onecore\\base\\flighting\\flightsetting"...
0x1800155f2  mov     edx, 219h; void *
0x1800155f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800155fc  nop
0x1800155fd  mov     [rbp+var_10], sil
0x180015601  lea     rcx, [rbp+var_20]
0x180015605  call    _lambda_9d15a0f67537066254c22d3eb2f8431c___operator__
0x18001560a  nop
0x18001560b  jmp     loc_18001595F
0x180015610  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180015615  mov     ebx, eax
0x180015617  test    eax, eax
0x180015619  jns     short loc_1800155A9
0x18001561b  mov     rcx, [rbp+18h]; this
0x18001561f  mov     r9d, eax; char *
0x180015622  lea     r8, aOnecoreBaseFli_45; "onecore\\base\\flighting\\flightsetting"...
0x180015629  mov     edx, 212h; void *
0x18001562e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015633  nop
0x180015634  mov     [rbp+var_10], sil
0x180015638  lea     rcx, [rbp+var_20]
0x18001563c  call    _lambda_9d15a0f67537066254c22d3eb2f8431c___operator__
0x180015641  nop
0x180015642  jmp     loc_18001595F
0x180015647  mov     rdi, cs:?g_svchostSharedGlobals@@3PEAU_SVCHOST_GLOBAL_DATA@@EA; _SVCHOST_GLOBAL_DATA * g_svchostSharedGlobals
0x18001564e  test    rdi, rdi
0x180015651  jnz     short loc_18001565F
0x180015653  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "g_svchostSharedGlobals != nullptr")
0x180015658  mov     rdi, cs:?g_svchostSharedGlobals@@3PEAU_SVCHOST_GLOBAL_DATA@@EA; _SVCHOST_GLOBAL_DATA * g_svchostSharedGlobals
0x18001565f  mov     rdi, [rdi+0C0h]
0x180015666  mov     rbx, cs:qword_18011D728
0x18001566d  xor     edx, edx
0x18001566f  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AXPEAX@Z$1?UnregisterWaitNoCheck@@YAX0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<void (*)(void *),&UnregisterWaitNoCheck(void *)>>::reset(void *)
0x180015674  mov     dword ptr [rsp+80h+var_58], 18h
0x18001567c  mov     qword ptr [rsp+80h+var_60], rsi; int
0x180015681  lea     r9, ?ServiceStopCallback@@YAXPEAXE@Z; ServiceStopCallback(void *,uchar)
0x180015688  mov     r8, rbx
0x18001568b  lea     rdx, aWisvc; "wisvc"
0x180015692  lea     rcx, WaitHandle
0x180015699  mov     rax, rdi
0x18001569c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800156a1  mov     [rbp+arg_18], eax
0x1800156a4  test    eax, eax
0x1800156a6  jz      short loc_1800156F0
0x1800156a8  call    cs:__imp_GetLastError
0x1800156ae  mov     ebx, eax
0x1800156b0  test    eax, eax
0x1800156b2  jle     short loc_1800156BD
0x1800156b4  movzx   ebx, ax
0x1800156b7  or      ebx, 80070000h
0x1800156bd  mov     dword ptr [rbp+arg_10], ebx
0x1800156c0  test    ebx, ebx
0x1800156c2  jns     short loc_1800156DD
0x1800156c4  mov     rcx, [rbp+18h]; this
0x1800156c8  mov     r9d, ebx; char *
0x1800156cb  lea     r8, aOnecoreBaseFli_45; "onecore\\base\\flighting\\flightsetting"...
0x1800156d2  mov     edx, 22Ah; void *
0x1800156d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800156dc  nop
0x1800156dd  mov     [rbp+var_10], sil
0x1800156e1  lea     rcx, [rbp+var_20]
0x1800156e5  call    _lambda_9d15a0f67537066254c22d3eb2f8431c___operator__
0x1800156ea  nop
0x1800156eb  jmp     loc_18001595F
0x1800156f0  lea     rcx, dword_18011D65C
0x1800156f7  call    cs:__imp_CoGetSharedServiceId
0x1800156fd  mov     ebx, eax
0x1800156ff  mov     dword ptr [rbp+arg_10], eax
0x180015702  test    eax, eax
0x180015704  jns     short loc_180015732
0x180015706  mov     rcx, [rbp+18h]; this
0x18001570a  mov     r9d, eax; char *
0x18001570d  lea     r8, aOnecoreBaseFli_45; "onecore\\base\\flighting\\flightsetting"...
0x180015714  mov     edx, 22Dh; void *
0x180015719  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001571e  nop
0x18001571f  mov     [rbp+var_10], sil
0x180015723  lea     rcx, [rbp+var_20]
0x180015727  call    _lambda_9d15a0f67537066254c22d3eb2f8431c___operator__
0x18001572c  nop
0x18001572d  jmp     loc_18001595F
0x180015732  mov     edx, 0EA60h
0x180015737  mov     rcx, cs:qword_18011D728
0x18001573e  call    cs:__imp_CoRegisterServerShutdownDelay
0x180015744  mov     ebx, eax
0x180015746  mov     dword ptr [rbp+arg_10], eax
0x180015749  test    eax, eax
0x18001574b  jns     short loc_180015779
0x18001574d  mov     rcx, [rbp+18h]; this
0x180015751  mov     r9d, eax; char *
0x180015754  lea     r8, aOnecoreBaseFli_45; "onecore\\base\\flighting\\flightsetting"...
0x18001575b  mov     edx, 22Eh; void *
0x180015760  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015765  nop
0x180015766  mov     [rbp+var_10], sil
0x18001576a  lea     rcx, [rbp+var_20]
0x18001576e  call    _lambda_9d15a0f67537066254c22d3eb2f8431c___operator__
0x180015773  nop
0x180015774  jmp     loc_18001595F
0x180015779  call    ?Register@ServiceComContextRegistrar@@QEAAJXZ; ServiceComContextRegistrar::Register(void)
0x18001577e  mov     ebx, eax
0x180015780  test    eax, eax
0x180015782  jns     short loc_1800157B0
0x180015784  mov     rcx, [rbp+18h]; this
0x180015788  mov     r9d, eax; char *
0x18001578b  lea     r8, aOnecoreBaseFli_45; "onecore\\base\\flighting\\flightsetting"...
0x180015792  mov     edx, 230h; void *
0x180015797  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001579c  nop
0x18001579d  mov     [rbp+var_10], sil
0x1800157a1  lea     rcx, [rbp+var_20]
0x1800157a5  call    _lambda_9d15a0f67537066254c22d3eb2f8431c___operator__
0x1800157aa  nop
0x1800157ab  jmp     loc_18001595F
0x1800157b0  mov     cl, 1
0x1800157b2  call    SvcAllowAsyncActions
0x1800157b7  lea     rcx, SystemTimeAsFileTime; lpSystemTimeAsFileTime
0x1800157be  call    cs:__imp_GetSystemTimeAsFileTime
0x1800157c4  mov     cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwControlsAccepted, 5; _SERVICE_STATUS g_serviceStatus ...
0x1800157ce  mov     cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 4; _SERVICE_STATUS g_serviceStatus ...
0x1800157d8  call    ?RegisterForWNSIfNeeded@@YAXXZ; RegisterForWNSIfNeeded(void)
0x1800157dd  call    ?RequestNewChannelUriIfNeeded@@YAXXZ; RequestNewChannelUriIfNeeded(void)
0x1800157e2  mov     rbx, cs:WNF_FLTN_WNF_ARRIVED
0x1800157e9  mov     [rbp+var_40], esi
0x1800157ec  mov     qword ptr [rbp+var_38], 0FFFFFFFF80000002h
0x1800157f4  lea     r9, [rbp+var_40]
0x1800157f8  lea     r8, aWnfeventchange; "WNFEventChangeStamp"
0x1800157ff  xor     edx, edx
0x180015801  lea     rcx, [rbp+var_38]
0x180015805  call    ?GetFlightingRegDWORD@FSRegUtils@@SAJAEBQEAUHKEY__@@W4FlightingRegistryKey@@PEBGPEAK@Z; FSRegUtils::GetFlightingRegDWORD(HKEY__ * const &,FlightingRegistryKey,ushort const *,ulong *)
0x18001580a  mov     edi, eax
0x18001580c  test    eax, eax
0x18001580e  js      short loc_18001587A
0x180015810  mov     dword ptr [rbp+var_38], esi
0x180015813  mov     byte ptr [rbp+arg_0.Data], sil
0x180015817  lea     r8, [rbp+var_38]; bool *
0x18001581b  lea     rdx, [rbp+arg_0]; struct _WNF_STATE_NAME *
0x18001581f  call    ?wnf_is_published_nothrow@wil@@YAJAEBU_WNF_STATE_NAME@@PEA_NPEAUWNF_CHANGE_STAMP_STRUCT@1@@Z; wil::wnf_is_published_nothrow(_WNF_STATE_NAME const &,bool *,wil::WNF_CHANGE_STAMP_STRUCT *)
0x180015824  test    eax, eax
0x180015826  js      short loc_180015836
0x180015828  cmp     byte ptr [rbp+arg_0.Data], sil
0x18001582c  jz      short loc_180015836
0x18001582e  mov     edi, [rbp+var_40]
0x180015831  cmp     dword ptr [rbp+var_38], edi
0x180015834  jz      short loc_1800158A3
0x180015836  mov     qword ptr [rbp+var_38], 0FFFFFFFF80000002h
0x18001583e  lea     r9, aDelete_0; "##DELETE##"
0x180015845  lea     r8, aWnfeventchange; "WNFEventChangeStamp"
0x18001584c  xor     edx, edx
0x18001584e  lea     rcx, [rbp+var_38]
0x180015852  call    ?SetFlightingRegString@FSRegUtils@@SAJAEBQEAUHKEY__@@W4FlightingRegistryKey@@PEBG2@Z; FSRegUtils::SetFlightingRegString(HKEY__ * const &,FlightingRegistryKey,ushort const *,ushort const *)
0x180015857  mov     edi, eax
0x180015859  call    ?IsEnabled@FlightSettingsAPITelemetryClass@@SA_NE_K@Z; FlightSettingsAPITelemetryClass::IsEnabled(uchar,unsigned __int64)
0x18001585e  test    al, al
0x180015860  jz      short loc_1800158A1
0x180015862  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_144f2b6777ef104894e0ad961c1a2ea1_@@CA@XZ; _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_(void)
0x180015869  call    ?get@?$static_lazy@VFlightSettingsAPITelemetryClass@@@details@wil@@QEAAPEAVFlightSettingsAPITelemetryClass@@P6AXXZ@Z; wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(void (*)(void))
0x18001586e  mov     edx, edi; int
0x180015870  mov     rcx, rax; this
0x180015873  call    ?ServiceWNSChangeStampDelete_@FlightSettingsAPITelemetryClass@@QEAAXJ@Z; FlightSettingsAPITelemetryClass::ServiceWNSChangeStampDelete_(long)
0x180015878  jmp     short loc_1800158A1
0x18001587a  cmp     edi, 80070002h
0x180015880  jz      short loc_1800158A1
0x180015882  call    ?IsEnabled@FlightSettingsAPITelemetryClass@@SA_NE_K@Z; FlightSettingsAPITelemetryClass::IsEnabled(uchar,unsigned __int64)
0x180015887  test    al, al
0x180015889  jz      short loc_1800158A1
0x18001588b  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_144f2b6777ef104894e0ad961c1a2ea1_@@CA@XZ; _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_(void)
0x180015892  call    ?get@?$static_lazy@VFlightSettingsAPITelemetryClass@@@details@wil@@QEAAPEAVFlightSettingsAPITelemetryClass@@P6AXXZ@Z; wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(void (*)(void))
0x180015897  mov     edx, edi; int
0x180015899  mov     rcx, rax; this
0x18001589c  call    ?ServiceWNSChangeStampReadFromRegFailed_@FlightSettingsAPITelemetryClass@@QEAAXJ@Z; FlightSettingsAPITelemetryClass::ServiceWNSChangeStampReadFromRegFailed_(long)
0x1800158a1  mov     edi, esi
0x1800158a3  call    ?IsEnabled@FlightSettingsAPITelemetryClass@@SA_NE_K@Z; FlightSettingsAPITelemetryClass::IsEnabled(uchar,unsigned __int64)
0x1800158a8  test    al, al
0x1800158aa  jz      short loc_1800158C2
0x1800158ac  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_144f2b6777ef104894e0ad961c1a2ea1_@@CA@XZ; _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_(void)
0x1800158b3  call    ?get@?$static_lazy@VFlightSettingsAPITelemetryClass@@@details@wil@@QEAAPEAVFlightSettingsAPITelemetryClass@@P6AXXZ@Z; wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(void (*)(void))
0x1800158b8  mov     edx, edi; unsigned int
0x1800158ba  mov     rcx, rax; this
0x1800158bd  call    ?ServiceWNSChangeStamp_@FlightSettingsAPITelemetryClass@@QEAAXK@Z; FlightSettingsAPITelemetryClass::ServiceWNSChangeStamp_(ulong)
0x1800158c2  mov     [rsp+80h+var_48], esi
0x1800158c6  mov     [rsp+80h+var_50], esi
0x1800158ca  mov     [rsp+80h+var_58], rsi
0x1800158cf  mov     qword ptr [rsp+80h+var_60], rsi; int
0x1800158d4  lea     r9, TriggerCallback
0x1800158db  mov     r8d, edi
0x1800158de  mov     rdx, rbx
0x1800158e1  lea     rcx, ?g_WNFSubscription@@3PEAU_WNF_USER_SUBSCRIPTION@@EA; _WNF_USER_SUBSCRIPTION * g_WNFSubscription
0x1800158e8  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x1800158ee  mov     edi, eax
0x1800158f0  mov     ecx, eax; Status
0x1800158f2  call    cs:__imp_RtlNtStatusToDosError
0x1800158f8  mov     ebx, eax
0x1800158fa  test    eax, eax
0x1800158fc  jle     short loc_180015907
0x1800158fe  movzx   ebx, ax
0x180015901  or      ebx, 80070000h
0x180015907  call    ?IsEnabled@FlightSettingsAPITelemetryClass@@SA_NE_K@Z; FlightSettingsAPITelemetryClass::IsEnabled(uchar,unsigned __int64)
0x18001590c  test    al, al
0x18001590e  jz      short loc_180015926
0x180015910  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_144f2b6777ef104894e0ad961c1a2ea1_@@CA@XZ; _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_(void)
0x180015917  call    ?get@?$static_lazy@VFlightSettingsAPITelemetryClass@@@details@wil@@QEAAPEAVFlightSettingsAPITelemetryClass@@P6AXXZ@Z; wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(void (*)(void))
0x18001591c  mov     edx, ebx; int
0x18001591e  mov     rcx, rax; this
0x180015921  call    ?ServiceWNSRegister_@FlightSettingsAPITelemetryClass@@QEAAXJ@Z; FlightSettingsAPITelemetryClass::ServiceWNSRegister_(long)
0x180015926  test    edi, edi
0x180015928  jns     short loc_180015931
0x18001592a  mov     cs:?g_WNFSubscription@@3PEAU_WNF_USER_SUBSCRIPTION@@EA, rsi; _WNF_USER_SUBSCRIPTION * g_WNFSubscription
0x180015931  mov     ebx, dword ptr [rbp+arg_10]
0x180015934  test    ebx, ebx
0x180015936  jns     short loc_180015951
0x180015938  mov     rcx, [rbp+18h]; this
0x18001593c  mov     r9d, ebx; char *
0x18001593f  lea     r8, aOnecoreBaseFli_45; "onecore\\base\\flighting\\flightsetting"...
0x180015946  mov     edx, 284h; void *
0x18001594b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015950  nop
0x180015951  mov     [rbp+var_10], sil
0x180015955  lea     rcx, [rbp+var_20]
0x180015959  call    _lambda_9d15a0f67537066254c22d3eb2f8431c___operator__
0x18001595e  nop
0x18001595f  lea     rcx, [rbp+var_30]
0x180015963  call    ?InternalUnlock@?$SyncLockWithStatusT@UMutexTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT<Microsoft::WRL::Wrappers::HandleTraits::MutexTraits>::InternalUnlock(void)
0x180015968  mov     eax, ebx
0x18001596a  mov     rbx, [rsp+80h+arg_8]
0x180015972  add     rsp, 80h
0x180015979  pop     rdi
0x18001597a  pop     rsi
0x18001597b  pop     rbp
0x18001597c  retn
```
