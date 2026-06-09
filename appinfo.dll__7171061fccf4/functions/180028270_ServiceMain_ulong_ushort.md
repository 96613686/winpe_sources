# ServiceMain(ulong,ushort * *)

- ea: `0x180028270`
- end: `0x1800287f5`
- name: `?ServiceMain@@YAXKPEAPEAG@Z`
- size: `1413`
- prototype: `void __fastcall(__int64, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000f4a0`
- `0x18000f52c`
- `0x180011130`
- `0x18001c8f4`
- `0x18001cd20`
- `0x18001cd78`
- `0x180026f40`
- `0x18002763c`
- `0x1800276dc`
- `0x180027bd0`
- `0x180027ecc`
- `0x180028270`
- `0x1800287fc`
- `0x180028838`
- `0x180028860`
- `0x18003f868`
- `0x1800443a4`
- `0x180048010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180028430`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002847d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180028430`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002847d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028462`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800284bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028519`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002877c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028462`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800284bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028519`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002877c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028496`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800284f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800286c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800286d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028496`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800284f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800286c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800286d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028442`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002849f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800284f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800286ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028442`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002849f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800284f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800286ca`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028413`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028413`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x180028760`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x180028760`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800287b6`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800287b6`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800284da`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800284da`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002853c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002853c`
- `ntdll!EtwEventRegister` at `0x18002855b`
- `ntdll!EtwEventRegister` at `0x18002859b`
- `ntdll!EtwEventRegister` at `0x18002855b`
- `ntdll!EtwEventRegister` at `0x18002859b`
- `ntdll!EtwEventUnregister` at `0x1800286e9`
- `ntdll!EtwEventUnregister` at `0x180028702`
- `ntdll!EtwEventUnregister` at `0x1800286e9`
- `ntdll!EtwEventUnregister` at `0x180028702`
- `ntdll!RtlInitializeSRWLock` at `0x180028327`
- `ntdll!RtlInitializeSRWLock` at `0x180028334`
- `ntdll!RtlInitializeSRWLock` at `0x180028356`
- `ntdll!RtlInitializeSRWLock` at `0x180028327`
- `ntdll!RtlInitializeSRWLock` at `0x180028334`
- `ntdll!RtlInitializeSRWLock` at `0x180028356`

## pseudocode

```c
void __fastcall ServiceMain(__int64 a1, unsigned __int16 **a2)
{
  __int64 v2; // rax
  __int64 v3; // rax
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  HANDLE *v7; // rdi
  HANDLE EventW; // rax
  DWORD LastError; // eax
  __int64 v10; // r8
  __int64 v11; // rdx
  HANDLE v12; // rax
  HANDLE v13; // r8
  unsigned int v14; // eax
  __int64 v15; // r8
  unsigned int v16; // eax
  __int64 v17; // r8
  unsigned int v18; // eax
  __int64 v19; // r8
  DWORD v20; // ebx
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // r9
  DWORD v24; // eax
  __int64 v25; // r8
  int v26; // [rsp+90h] [rbp+48h] BYREF

  WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_UACLog;
  qword_18005FE20 = 0;
  WPP_MAIN_CB = 0;
  WPP_GLOBAL_Control = &WPP_MAIN_CB;
  qword_18005FE28 = 1;
  WppInitUm(a1, a2);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_ddbbeface36a3882165728722b0a7441_Traceguids);
  g_ssService.dwServiceType = 32;
  qword_18005FDB8 = (__int64)&g_ProfileList;
  g_ProfileList = &g_ProfileList;
  *(_QWORD *)&g_ssService.dwCurrentState = 2;
  *(_QWORD *)&g_ssService.dwWin32ExitCode = 0;
  *(_QWORD *)&g_ssService.dwCheckPoint = 0;
  RtlInitializeSRWLock(&g_ProfileListLock);
  RtlInitializeSRWLock(&g_SessionListLock);
  qword_18005FDD0 = (__int64)&g_SessionIdList;
  g_SessionIdList = &g_SessionIdList;
  RtlInitializeSRWLock(&g_SessionIdListLock);
  v2 = RateLimiter::CreateNewForGarrulousEvents(&v26);
  wistd::unique_ptr<RateLimiter,wistd::default_delete<RateLimiter>>::operator=(&g_pConsentExeTelemetryRateLimiter, v2);
  wistd::unique_ptr<RateLimiter,wistd::default_delete<RateLimiter>>::reset(&v26, 0);
  v3 = RateLimiter::CreateNewForGarrulousEvents(&v26);
  wistd::unique_ptr<RateLimiter,wistd::default_delete<RateLimiter>>::operator=(
    &g_pLaunchAdminProcessActivityTelemetryRateLimiter,
    v3);
  wistd::unique_ptr<RateLimiter,wistd::default_delete<RateLimiter>>::reset(&v26, 0);
  v4 = RateLimiter::CreateNewForGarrulousEvents(&v26);
  wistd::unique_ptr<RateLimiter,wistd::default_delete<RateLimiter>>::operator=(
    &g_pCentennialElevationTelemetryRateLimiter,
    v4);
  wistd::unique_ptr<RateLimiter,wistd::default_delete<RateLimiter>>::reset(&v26, 0);
  v5 = RateLimiter::CreateNewForGarrulousEvents(&v26);
  wistd::unique_ptr<RateLimiter,wistd::default_delete<RateLimiter>>::operator=(
    &g_pMSIElevationActivityTelemetryRateLimiter,
    v5);
  wistd::unique_ptr<RateLimiter,wistd::default_delete<RateLimiter>>::reset(&v26, 0);
  v6 = RateLimiter::CreateNewForGarrulousEvents(&v26);
  wistd::unique_ptr<RateLimiter,wistd::default_delete<RateLimiter>>::operator=(
    &g_pCOMElevationActivityTelemetryRateLimiter,
    v6);
  wistd::unique_ptr<RateLimiter,wistd::default_delete<RateLimiter>>::reset(&v26, 0);
  v7 = (HANDLE *)LocalAlloc(0x40u, 0x10u);
  if ( !v7 )
    goto LABEL_60;
  EventW = CreateEventW(0, 1, 0, 0);            // Object namespace audit: service events are unnamed (lpName=NULL); no fixed CreateEvent object squatting surface here.
  v7[1] = EventW;
  if ( !EventW )
  {
    LocalFree(v7);
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_60;
    LastError = GetLastError();
    v11 = 11;
LABEL_17:
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, v10, LastError);
LABEL_60:
    WppCleanupUm();
    return;
  }
  v12 = CreateEventW(0, 1, 0, 0);
  v13 = v7[1];
  g_hProfileRefEvent = v12;
  if ( !v12 )
  {
    CloseHandle(v13);
    LocalFree(v7);
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_60;
    LastError = GetLastError();
    v11 = 12;
    goto LABEL_17;
  }
  g_hssService = RegisterServiceCtrlHandlerExW(L"AppInfo", AipServiceCtrlHandler, v13);
  if ( !g_hssService )
  {
    CloseHandle(v7[1]);
    LocalFree(v7);
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_60;
    LastError = GetLastError();
    v11 = 13;
    goto LABEL_17;
  }
  g_ulPerfTrackId = GetTickCount();
  v14 = EtwEventRegister(Microsoft_Windows_LUA, 0, 0, &g_EventRegHandleLua);
  if ( v14 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, v15, v14);
  v16 = EtwEventRegister(AppModelRuntimeProviderId, 0, 0, &g_EventRegHandleAppModelRuntime);
  if ( v16 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, v17, v16);
  g_ulProfileReferences = 1;
  v18 = AiInitializeServiceInfo();
  v20 = v18;
  if ( v18 )
  {
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_44;
    v22 = 16;
    goto LABEL_30;
  }
  v18 = AiInitializeDirectories();
  v20 = v18;
  if ( v18 )
  {
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_44;
    v22 = 17;
    goto LABEL_30;
  }
  v18 = AipEnableRpcInterface();
  v20 = v18;
  if ( v18 )
  {
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_44;
    v22 = 18;
LABEL_30:
    v23 = v18;
LABEL_43:
    WPP_SF_d(v21[2], v22, v19, v23);
LABEL_44:
    AiFreeDirectories();
    CloseHandle(v7[1]);
    LocalFree(v7);
    CloseHandle(g_hProfileRefEvent);
    if ( g_EventRegHandleLua )
    {
      EtwEventUnregister();
      g_EventRegHandleLua = 0;
    }
    if ( g_EventRegHandleAppModelRuntime )
    {
      EtwEventUnregister();
      g_EventRegHandleAppModelRuntime = 0;
    }
    g_ssService.dwWin32ExitCode = v20;
    g_ssService.dwCurrentState = 1;
    goto LABEL_56;
  }
  v20 = (*((__int64 (__fastcall **)(HANDLE *, const WCHAR *, HANDLE, void (__fastcall *)(HLOCAL, unsigned __int8), HANDLE *, int))g_pSvchostSharedGlobals
         + 24))(
          v7,
          L"AppInfo",
          v7[1],
          AipStopCallback,
          v7,
          24);
  if ( v20 )
  {
    AipDisableRpcInterface();
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_44;
    v22 = 19;
    v23 = v20;
    goto LABEL_43;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdminPCATelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShadowAdminPCATelemetry>::GetImpl'::`2'::impl) )
    LUATelemetry::LogUACSettingsWithDescriptions();
  else
    LUATelemetry::LogUACSettings();
  g_ssService.dwControlsAccepted = 129;
  g_ssService.dwCurrentState = 4;
  v26 = 1;
  if ( !(unsigned int)SetProcessMitigationPolicy(16, &v26)
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v24 = GetLastError();
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_ddbbeface36a3882165728722b0a7441_Traceguids, v24);
  }
LABEL_56:
  *(_QWORD *)&g_ssService.dwCheckPoint = 0;
  SetServiceStatus(g_hssService, &g_ssService);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, v25, v20);
  if ( v20 )
    goto LABEL_60;
}

```

## disassembly

```asm
0x180028270  push    rbp
0x180028272  push    rbx
0x180028273  push    rsi
0x180028274  push    rdi
0x180028275  push    r14
0x180028277  push    r15
0x180028279  mov     rbp, rsp
0x18002827c  sub     rsp, 48h
0x180028280  xor     esi, esi
0x180028282  lea     rax, WPP_ThisDir_CTLGUID_UACLog
0x180028289  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x180028290  lea     rax, WPP_MAIN_CB
0x180028297  mov     cs:qword_18005FE20, rsi
0x18002829e  mov     cs:WPP_MAIN_CB, rsi
0x1800282a5  lea     r14d, [rsi+1]
0x1800282a9  mov     cs:WPP_GLOBAL_Control, rax
0x1800282b0  mov     cs:qword_18005FE28, r14
0x1800282b7  call    WppInitUm
0x1800282bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800282c3  lea     r15, WPP_GLOBAL_Control
0x1800282ca  cmp     rcx, r15
0x1800282cd  jz      short loc_1800282E8
0x1800282cf  test    [rcx+1Ch], r14b
0x1800282d3  jz      short loc_1800282E8
0x1800282d5  mov     rcx, [rcx+10h]
0x1800282d9  lea     edx, [rsi+0Ah]
0x1800282dc  lea     r8, WPP_ddbbeface36a3882165728722b0a7441_Traceguids
0x1800282e3  call    WPP_SF_
0x1800282e8  lea     rax, ?g_ProfileList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_ProfileList
0x1800282ef  mov     cs:?g_ssService@@3U_SERVICE_STATUS@@A.dwServiceType, 20h ; ' '; _SERVICE_STATUS g_ssService ...
0x1800282f9  lea     rcx, ?g_ProfileListLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK g_ProfileListLock
0x180028300  mov     cs:qword_18005FDB8, rax
0x180028307  mov     cs:?g_ProfileList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY g_ProfileList
0x18002830e  mov     qword ptr cs:?g_ssService@@3U_SERVICE_STATUS@@A.dwCurrentState, 2; _SERVICE_STATUS g_ssService ...
0x180028319  mov     qword ptr cs:?g_ssService@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, rsi; _SERVICE_STATUS g_ssService ...
0x180028320  mov     qword ptr cs:?g_ssService@@3U_SERVICE_STATUS@@A.dwCheckPoint, rsi; _SERVICE_STATUS g_ssService ...
0x180028327  call    cs:__imp_RtlInitializeSRWLock
0x18002832d  lea     rcx, ?g_SessionListLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK g_SessionListLock
0x180028334  call    cs:__imp_RtlInitializeSRWLock
0x18002833a  lea     rax, ?g_SessionIdList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_SessionIdList
0x180028341  lea     rcx, ?g_SessionIdListLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK g_SessionIdListLock
0x180028348  mov     cs:qword_18005FDD0, rax
0x18002834f  mov     cs:?g_SessionIdList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY g_SessionIdList
0x180028356  call    cs:__imp_RtlInitializeSRWLock
0x18002835c  lea     rcx, [rbp+arg_10]
0x180028360  call    ?CreateNewForGarrulousEvents@RateLimiter@@SA?AV?$unique_ptr@VRateLimiter@@U?$default_delete@VRateLimiter@@@wistd@@@wistd@@XZ; RateLimiter::CreateNewForGarrulousEvents(void)
0x180028365  mov     rdx, rax
0x180028368  lea     rcx, ?g_pConsentExeTelemetryRateLimiter@@3V?$unique_ptr@VRateLimiter@@U?$default_delete@VRateLimiter@@@wistd@@@wistd@@A; wistd::unique_ptr<RateLimiter,wistd::default_delete<RateLimiter>> g_pConsentExeTelemetryRateLimiter
0x18002836f  call    ??4?$unique_ptr@VRateLimiter@@U?$default_delete@VRateLimiter@@@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<RateLimiter,wistd::default_delete<RateLimiter>>::operator=(wistd::unique_ptr<RateLimiter,wistd::default_delete<RateLimiter>> &&)
0x180028374  xor     edx, edx
0x180028376  lea     rcx, [rbp+arg_10]
0x18002837a  call    ?reset@?$unique_ptr@VRateLimiter@@U?$default_delete@VRateLimiter@@@wistd@@@wistd@@QEAAXPEAVRateLimiter@@@Z; wistd::unique_ptr<RateLimiter,wistd::default_delete<RateLimiter>>::reset(RateLimiter *)
0x18002837f  lea     rcx, [rbp+arg_10]
0x180028383  call    ?CreateNewForGarrulousEvents@RateLimiter@@SA?AV?$unique_ptr@VRateLimiter@@U?$default_delete@VRateLimiter@@@wistd@@@wistd@@XZ; RateLimiter::CreateNewForGarrulousEvents(void)
0x180028388  mov     rdx, rax
0x18002838b  lea     rcx, ?g_pLaunchAdminProcessActivityTelemetryRateLimiter@@3V?$unique_ptr@VRateLimiter@@U?$default_delete@VRateLimiter@@@wistd@@@wistd@@A; wistd::unique_ptr<RateLimiter,wistd::default_delete<RateLimiter>> g_pLaunchAdminProcessActivityTelemetryRateLimiter
0x180028392  call    ??4?$unique_ptr@VRateLimiter@@U?$default_delete@VRateLimiter@@@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<RateLimiter,wistd::default_delete<RateLimiter>>::operator=(wistd::unique_ptr<RateLimiter,wistd::default_delete<RateLimiter>> &&)
0x180028397  xor     edx, edx
0x180028399  lea     rcx, [rbp+arg_10]
0x18002839d  call    ?reset@?$unique_ptr@VRateLimiter@@U?$default_delete@VRateLimiter@@@wistd@@@wistd@@QEAAXPEAVRateLimiter@@@Z; wistd::unique_ptr<RateLimiter,wistd::default_delete<RateLimiter>>::reset(RateLimiter *)
0x1800283a2  lea     rcx, [rbp+arg_10]
0x1800283a6  call    ?CreateNewForGarrulousEvents@RateLimiter@@SA?AV?$unique_ptr@VRateLimiter@@U?$default_delete@VRateLimiter@@@wistd@@@wistd@@XZ; RateLimiter::CreateNewForGarrulousEvents(void)
0x1800283ab  mov     rdx, rax
0x1800283ae  lea     rcx, ?g_pCentennialElevationTelemetryRateLimiter@@3V?$unique_ptr@VRateLimiter@@U?$default_delete@VRateLimiter@@@wistd@@@wistd@@A; wistd::unique_ptr<RateLimiter,wistd::default_delete<RateLimiter>> g_pCentennialElevationTelemetryRateLimiter
0x1800283b5  call    ??4?$unique_ptr@VRateLimiter@@U?$default_delete@VRateLimiter@@@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<RateLimiter,wistd::default_delete<RateLimiter>>::operator=(wistd::unique_ptr<RateLimiter,wistd::default_delete<RateLimiter>> &&)
0x1800283ba  xor     edx, edx
0x1800283bc  lea     rcx, [rbp+arg_10]
0x1800283c0  call    ?reset@?$unique_ptr@VRateLimiter@@U?$default_delete@VRateLimiter@@@wistd@@@wistd@@QEAAXPEAVRateLimiter@@@Z; wistd::unique_ptr<RateLimiter,wistd::default_delete<RateLimiter>>::reset(RateLimiter *)
0x1800283c5  lea     rcx, [rbp+arg_10]
0x1800283c9  call    ?CreateNewForGarrulousEvents@RateLimiter@@SA?AV?$unique_ptr@VRateLimiter@@U?$default_delete@VRateLimiter@@@wistd@@@wistd@@XZ; RateLimiter::CreateNewForGarrulousEvents(void)
0x1800283ce  mov     rdx, rax
0x1800283d1  lea     rcx, ?g_pMSIElevationActivityTelemetryRateLimiter@@3V?$unique_ptr@VRateLimiter@@U?$default_delete@VRateLimiter@@@wistd@@@wistd@@A; wistd::unique_ptr<RateLimiter,wistd::default_delete<RateLimiter>> g_pMSIElevationActivityTelemetryRateLimiter
0x1800283d8  call    ??4?$unique_ptr@VRateLimiter@@U?$default_delete@VRateLimiter@@@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<RateLimiter,wistd::default_delete<RateLimiter>>::operator=(wistd::unique_ptr<RateLimiter,wistd::default_delete<RateLimiter>> &&)
0x1800283dd  xor     edx, edx
0x1800283df  lea     rcx, [rbp+arg_10]
0x1800283e3  call    ?reset@?$unique_ptr@VRateLimiter@@U?$default_delete@VRateLimiter@@@wistd@@@wistd@@QEAAXPEAVRateLimiter@@@Z; wistd::unique_ptr<RateLimiter,wistd::default_delete<RateLimiter>>::reset(RateLimiter *)
0x1800283e8  lea     rcx, [rbp+arg_10]
0x1800283ec  call    ?CreateNewForGarrulousEvents@RateLimiter@@SA?AV?$unique_ptr@VRateLimiter@@U?$default_delete@VRateLimiter@@@wistd@@@wistd@@XZ; RateLimiter::CreateNewForGarrulousEvents(void)
0x1800283f1  mov     rdx, rax
0x1800283f4  lea     rcx, ?g_pCOMElevationActivityTelemetryRateLimiter@@3V?$unique_ptr@VRateLimiter@@U?$default_delete@VRateLimiter@@@wistd@@@wistd@@A; wistd::unique_ptr<RateLimiter,wistd::default_delete<RateLimiter>> g_pCOMElevationActivityTelemetryRateLimiter
0x1800283fb  call    ??4?$unique_ptr@VRateLimiter@@U?$default_delete@VRateLimiter@@@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<RateLimiter,wistd::default_delete<RateLimiter>>::operator=(wistd::unique_ptr<RateLimiter,wistd::default_delete<RateLimiter>> &&)
0x180028400  xor     edx, edx
0x180028402  lea     rcx, [rbp+arg_10]
0x180028406  call    ?reset@?$unique_ptr@VRateLimiter@@U?$default_delete@VRateLimiter@@@wistd@@@wistd@@QEAAXPEAVRateLimiter@@@Z; wistd::unique_ptr<RateLimiter,wistd::default_delete<RateLimiter>>::reset(RateLimiter *)
0x18002840b  mov     edx, 10h; uBytes
0x180028410  lea     ecx, [rdx+30h]; uFlags
0x180028413  call    cs:__imp_LocalAlloc
0x180028419  mov     rdi, rax
0x18002841c  test    rax, rax
0x18002841f  jz      loc_1800287E3
0x180028425  xor     r9d, r9d; lpName
0x180028428  xor     r8d, r8d; bInitialState
0x18002842b  mov     edx, r14d; bManualReset
0x18002842e  xor     ecx, ecx; lpEventAttributes
0x180028430  call    cs:__imp_CreateEventW; Object namespace audit: service events are unnamed (lpName=NULL); no fixed CreateEvent object squatting surface here.
0x180028436  mov     [rdi+8], rax
0x18002843a  test    rax, rax
0x18002843d  jnz     short loc_180028472
0x18002843f  mov     rcx, rdi; hMem
0x180028442  call    cs:__imp_LocalFree
0x180028448  mov     rax, cs:WPP_GLOBAL_Control
0x18002844f  cmp     rax, r15
0x180028452  jz      loc_1800287E3
0x180028458  test    [rax+1Ch], r14b
0x18002845c  jz      loc_1800287E3
0x180028462  call    cs:__imp_GetLastError
0x180028468  mov     edx, 0Bh
0x18002846d  jmp     loc_180028524
0x180028472  xor     r9d, r9d; lpName
0x180028475  xor     r8d, r8d; bInitialState
0x180028478  mov     edx, r14d; bManualReset
0x18002847b  xor     ecx, ecx; lpEventAttributes
0x18002847d  call    cs:__imp_CreateEventW
0x180028483  mov     r8, [rdi+8]; lpContext
0x180028487  mov     cs:?g_hProfileRefEvent@@3PEAXEA, rax; void * g_hProfileRefEvent
0x18002848e  test    rax, rax
0x180028491  jnz     short loc_1800284CC
0x180028493  mov     rcx, r8; hObject
0x180028496  call    cs:__imp_CloseHandle
0x18002849c  mov     rcx, rdi; hMem
0x18002849f  call    cs:__imp_LocalFree
0x1800284a5  mov     rax, cs:WPP_GLOBAL_Control
0x1800284ac  cmp     rax, r15
0x1800284af  jz      loc_1800287E3
0x1800284b5  test    [rax+1Ch], r14b
0x1800284b9  jz      loc_1800287E3
0x1800284bf  call    cs:__imp_GetLastError
0x1800284c5  mov     edx, 0Ch
0x1800284ca  jmp     short loc_180028524
0x1800284cc  lea     rdx, ?AipServiceCtrlHandler@@YAKKKPEAX0@Z; lpHandlerProc
0x1800284d3  lea     rcx, ServiceName; "AppInfo"
0x1800284da  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x1800284e0  mov     cs:?g_hssService@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * g_hssService
0x1800284e7  test    rax, rax
0x1800284ea  jnz     short loc_18002853C
0x1800284ec  mov     rcx, [rdi+8]; hObject
0x1800284f0  call    cs:__imp_CloseHandle
0x1800284f6  mov     rcx, rdi; hMem
0x1800284f9  call    cs:__imp_LocalFree
0x1800284ff  mov     rax, cs:WPP_GLOBAL_Control
0x180028506  cmp     rax, r15
0x180028509  jz      loc_1800287E3
0x18002850f  test    [rax+1Ch], r14b
0x180028513  jz      loc_1800287E3
0x180028519  call    cs:__imp_GetLastError
0x18002851f  mov     edx, 0Dh
0x180028524  mov     rcx, cs:WPP_GLOBAL_Control
0x18002852b  mov     r9d, eax
0x18002852e  mov     rcx, [rcx+10h]
0x180028532  call    WPP_SF_d
0x180028537  jmp     loc_1800287E3
0x18002853c  call    cs:__imp_GetTickCount
0x180028542  lea     r9, ?g_EventRegHandleLua@@3_KA; unsigned __int64 g_EventRegHandleLua
0x180028549  xor     r8d, r8d
0x18002854c  lea     rcx, Microsoft_Windows_LUA
0x180028553  mov     cs:?g_ulPerfTrackId@@3JC, eax; long volatile g_ulPerfTrackId
0x180028559  xor     edx, edx
0x18002855b  call    cs:__imp_EtwEventRegister
0x180028561  test    eax, eax
0x180028563  jz      short loc_180028588
0x180028565  mov     rcx, cs:WPP_GLOBAL_Control
0x18002856c  cmp     rcx, r15
0x18002856f  jz      short loc_180028588
0x180028571  test    [rcx+1Ch], r14b
0x180028575  jz      short loc_180028588
0x180028577  mov     rcx, [rcx+10h]
0x18002857b  mov     edx, 0Eh
0x180028580  mov     r9d, eax
0x180028583  call    WPP_SF_d
0x180028588  lea     r9, ?g_EventRegHandleAppModelRuntime@@3_KA; unsigned __int64 g_EventRegHandleAppModelRuntime
0x18002858f  xor     r8d, r8d
0x180028592  xor     edx, edx
0x180028594  lea     rcx, AppModelRuntimeProviderId
0x18002859b  call    cs:__imp_EtwEventRegister
0x1800285a1  test    eax, eax
0x1800285a3  jz      short loc_1800285C8
0x1800285a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800285ac  cmp     rcx, r15
0x1800285af  jz      short loc_1800285C8
0x1800285b1  test    [rcx+1Ch], r14b
0x1800285b5  jz      short loc_1800285C8
0x1800285b7  mov     rcx, [rcx+10h]
0x1800285bb  mov     edx, 0Fh
0x1800285c0  mov     r9d, eax
0x1800285c3  call    WPP_SF_d
0x1800285c8  mov     cs:?g_ulProfileReferences@@3JA, r14d; long g_ulProfileReferences
0x1800285cf  call    ?AiInitializeServiceInfo@@YAKXZ; AiInitializeServiceInfo(void)
0x1800285d4  mov     ebx, eax
0x1800285d6  test    eax, eax
0x1800285d8  jz      short loc_180028601
0x1800285da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800285e1  cmp     rcx, r15
0x1800285e4  jz      loc_1800286B8
0x1800285ea  test    [rcx+1Ch], r14b
0x1800285ee  jz      loc_1800286B8
0x1800285f4  mov     edx, 10h
0x1800285f9  mov     r9d, eax
0x1800285fc  jmp     loc_1800286AF
0x180028601  call    ?AiInitializeDirectories@@YAKXZ; AiInitializeDirectories(void)
0x180028606  mov     ebx, eax
0x180028608  test    eax, eax
0x18002860a  jz      short loc_18002862D
0x18002860c  mov     rcx, cs:WPP_GLOBAL_Control
0x180028613  cmp     rcx, r15
0x180028616  jz      loc_1800286B8
0x18002861c  test    [rcx+1Ch], r14b
0x180028620  jz      loc_1800286B8
0x180028626  mov     edx, 11h
0x18002862b  jmp     short loc_1800285F9
0x18002862d  call    ?AipEnableRpcInterface@@YAKXZ; AipEnableRpcInterface(void)
0x180028632  mov     ebx, eax
0x180028634  test    eax, eax
0x180028636  jz      short loc_180028651
0x180028638  mov     rcx, cs:WPP_GLOBAL_Control
0x18002863f  cmp     rcx, r15
0x180028642  jz      short loc_1800286B8
0x180028644  test    [rcx+1Ch], r14b
0x180028648  jz      short loc_1800286B8
0x18002864a  mov     edx, 12h
0x18002864f  jmp     short loc_1800285F9
0x180028651  mov     rax, cs:?g_pSvchostSharedGlobals@@3PEAU_SVCHOST_GLOBAL_DATA@@EA; _SVCHOST_GLOBAL_DATA * g_pSvchostSharedGlobals
0x180028658  lea     r9, ?AipStopCallback@@YAXPEAXE@Z; AipStopCallback(void *,uchar)
0x18002865f  mov     r8, [rdi+8]
0x180028663  lea     rdx, ServiceName; "AppInfo"
0x18002866a  mov     [rsp+48h+var_20], 18h
0x180028672  mov     rcx, rdi
0x180028675  mov     [rsp+48h+var_28], rdi
0x18002867a  mov     rax, [rax+0C0h]
0x180028681  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028686  mov     ebx, eax
0x180028688  test    eax, eax
0x18002868a  jz      loc_180028721
0x180028690  call    ?AipDisableRpcInterface@@YAXXZ; AipDisableRpcInterface(void)
0x180028695  mov     rcx, cs:WPP_GLOBAL_Control
0x18002869c  cmp     rcx, r15
0x18002869f  jz      short loc_1800286B8
0x1800286a1  test    [rcx+1Ch], r14b
0x1800286a5  jz      short loc_1800286B8
0x1800286a7  mov     edx, 13h
0x1800286ac  mov     r9d, ebx
0x1800286af  mov     rcx, [rcx+10h]
0x1800286b3  call    WPP_SF_d
0x1800286b8  call    ?AiFreeDirectories@@YAXXZ; AiFreeDirectories(void)
0x1800286bd  mov     rcx, [rdi+8]; hObject
0x1800286c1  call    cs:__imp_CloseHandle
0x1800286c7  mov     rcx, rdi; hMem
0x1800286ca  call    cs:__imp_LocalFree
0x1800286d0  mov     rcx, cs:?g_hProfileRefEvent@@3PEAXEA; hObject
0x1800286d7  call    cs:__imp_CloseHandle
0x1800286dd  mov     rcx, cs:?g_EventRegHandleLua@@3_KA; unsigned __int64 g_EventRegHandleLua
0x1800286e4  test    rcx, rcx
0x1800286e7  jz      short loc_1800286F6
0x1800286e9  call    cs:__imp_EtwEventUnregister
0x1800286ef  mov     cs:?g_EventRegHandleLua@@3_KA, rsi; unsigned __int64 g_EventRegHandleLua
0x1800286f6  mov     rcx, cs:?g_EventRegHandleAppModelRuntime@@3_KA; unsigned __int64 g_EventRegHandleAppModelRuntime
0x1800286fd  test    rcx, rcx
0x180028700  jz      short loc_18002870F
0x180028702  call    cs:__imp_EtwEventUnregister
0x180028708  mov     cs:?g_EventRegHandleAppModelRuntime@@3_KA, rsi; unsigned __int64 g_EventRegHandleAppModelRuntime
0x18002870f  mov     cs:?g_ssService@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, ebx; _SERVICE_STATUS g_ssService ...
0x180028715  mov     cs:?g_ssService@@3U_SERVICE_STATUS@@A.dwCurrentState, r14d; _SERVICE_STATUS g_ssService ...
0x18002871c  jmp     loc_1800287A1
0x180028721  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdminPCATelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdminPCATelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdminPCATelemetry> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdminPCATelemetry>::GetImpl(void)'::`2'::impl
0x180028728  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdminPCATelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdminPCATelemetry>::__private_IsEnabled(void)
0x18002872d  test    al, al
0x18002872f  jz      short loc_180028738
0x180028731  call    ?LogUACSettingsWithDescriptions@LUATelemetry@@SAXXZ; LUATelemetry::LogUACSettingsWithDescriptions(void)
0x180028736  jmp     short loc_18002873D
0x180028738  call    ?LogUACSettings@LUATelemetry@@SAXXZ; LUATelemetry::LogUACSettings(void)
0x18002873d  mov     r8d, 4
0x180028743  mov     cs:?g_ssService@@3U_SERVICE_STATUS@@A.dwControlsAccepted, 81h; _SERVICE_STATUS g_ssService ...
0x18002874d  lea     rdx, [rbp+arg_10]
0x180028751  mov     cs:?g_ssService@@3U_SERVICE_STATUS@@A.dwCurrentState, r8d; _SERVICE_STATUS g_ssService ...
0x180028758  mov     [rbp+arg_10], r14d
0x18002875c  lea     ecx, [r8+0Ch]
0x180028760  call    cs:__imp_SetProcessMitigationPolicy
0x180028766  test    eax, eax
0x180028768  jnz     short loc_1800287A1
0x18002876a  mov     rax, cs:WPP_GLOBAL_Control
0x180028771  cmp     rax, r15
0x180028774  jz      short loc_1800287A1
0x180028776  test    [rax+1Ch], r14b
0x18002877a  jz      short loc_1800287A1
0x18002877c  call    cs:__imp_GetLastError
0x180028782  mov     rcx, cs:WPP_GLOBAL_Control
0x180028789  lea     r8, WPP_ddbbeface36a3882165728722b0a7441_Traceguids
0x180028790  mov     edx, 14h
0x180028795  mov     r9d, eax
0x180028798  mov     rcx, [rcx+10h]
0x18002879c  call    WPP_SF_D
0x1800287a1  mov     rcx, cs:?g_hssService@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x1800287a8  lea     rdx, ?g_ssService@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x1800287af  mov     qword ptr cs:?g_ssService@@3U_SERVICE_STATUS@@A.dwCheckPoint, rsi; _SERVICE_STATUS g_ssService ...
0x1800287b6  call    cs:__imp_SetServiceStatus
0x1800287bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800287c3  cmp     rcx, r15
0x1800287c6  jz      short loc_1800287DF
0x1800287c8  test    [rcx+1Ch], r14b
0x1800287cc  jz      short loc_1800287DF
0x1800287ce  mov     rcx, [rcx+10h]
  ... truncated ...
```
