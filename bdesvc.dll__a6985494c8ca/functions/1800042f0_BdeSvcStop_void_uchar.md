# BdeSvcStop(void *,uchar)

- ea: `0x1800042f0`
- end: `0x1800045f5`
- name: `?BdeSvcStop@@YAXPEAXE@Z`
- size: `773`
- prototype: `void __fastcall(void *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180004cb0`

## callees

- `0x1800042f0`
- `0x1800045fc`
- `0x18000470c`
- `0x180004894`
- `0x180009f30`
- `0x180009f60`
- `0x18002da1c`
- `0x18002f3f4`
- `0x180030d5c`
- `0x180030f28`
- `0x1800311ac`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800043dc`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800043fb`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000441a`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800043dc`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800043fb`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000441a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000433a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000449f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800044ea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000433a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000449f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800044ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004351`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800044d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004588`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004351`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800044d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004588`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000437d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800043a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000437d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800043a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000447c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000447c`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800044c4`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800044c4`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000436d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18000436d`

## pseudocode

```c
void __fastcall BdeSvcStop(void *a1)
{
  DWORD LastError; // eax
  int v2; // eax
  PVOID *v3; // rcx
  PVOID *v4; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 148, WPP_ee35f73b350036074f815e40b51ef636_Traceguids);
  EnterCriticalSection(&BdeSvcWorkTracking::_svcWorkTracking);
  BdeSvcWorkTracking::CancelAndWaitForOutstandingWorkImpl((BdeSvcWorkTracking *)&BdeSvcWorkTracking::_svcWorkTracking);
  LeaveCriticalSection(&BdeSvcWorkTracking::_svcWorkTracking);
  if ( gSvchostWaitHandle )
  {
    if ( !UnregisterWaitEx(gSvchostWaitHandle, 0)
      && GetLastError() != 997
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 149, WPP_ee35f73b350036074f815e40b51ef636_Traceguids, LastError);
    }
    gSvchostWaitHandle = 0;
  }
  if ( g_BdeSvcTriggerSubscription )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion(g_BdeSvcTriggerSubscription);
    g_BdeSvcTriggerSubscription = 0;
  }
  if ( g_BdeSvcPersistentRequestSubscription )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion(g_BdeSvcPersistentRequestSubscription);
    g_BdeSvcPersistentRequestSubscription = 0;
  }
  if ( g_TpmWnfSubscription )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion(g_TpmWnfSubscription);
    g_TpmWnfSubscription = 0;
  }
  BdeSvcDeleteFveRequestCriticalSections();
  FveUninitializeAsyncRequestHandler();
  BdeSvcDeletePersistentRequestTimer();
  WnfSubscriptions::Cleanup();
  v2 = CBdeSvcDE::UninitializeStatics();
  if ( v2 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      150,
      WPP_ee35f73b350036074f815e40b51ef636_Traceguids,
      (unsigned int)v2);
  if ( g_hSvchostStopEvent )
  {
    CloseHandle(g_hSvchostStopEvent);
    g_hSvchostStopEvent = 0;
  }
  if ( g_hStatus )
  {
    EnterCriticalSection(&g_serviceStatusLock);
    *(_QWORD *)&g_serviceStatus.dwCurrentState = 1;
    SetServiceStatus(g_hStatus, &g_serviceStatus);
    LeaveCriticalSection(&g_serviceStatusLock);
  }
  EnterCriticalSection(&g_svcCtlInfo);
  if ( !*(_QWORD *)(qword_18009B9F0 + 8) )
    goto LABEL_29;
  v3 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 151, WPP_ee35f73b350036074f815e40b51ef636_Traceguids);
LABEL_29:
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( hDevNotify && v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 2) != 0 )
  {
    WPP_SF_(v3[2], 152, WPP_ee35f73b350036074f815e40b51ef636_Traceguids);
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( dword_18009B9E8 && v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 2) != 0 )
    WPP_SF_d(v3[2], 153, WPP_ee35f73b350036074f815e40b51ef636_Traceguids, (unsigned int)dword_18009B9E8);
  LeaveCriticalSection(&g_svcCtlInfo);
  McGenEventUnregister_EventUnregister();
  RecoveryTelemetery::DeleteInstance();
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 154, WPP_ee35f73b350036074f815e40b51ef636_Traceguids);
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x20) != 0 )
      WPP_SF_(v4[2], 155, WPP_ee35f73b350036074f815e40b51ef636_Traceguids);
  }
}

```

## disassembly

```asm
0x1800042f0  mov     [rsp+arg_0], rbx
0x1800042f5  mov     [rsp+arg_8], rsi
0x1800042fa  push    rdi
0x1800042fb  sub     rsp, 20h
0x1800042ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180004306  lea     rdi, WPP_GLOBAL_Control
0x18000430d  lea     rsi, WPP_ee35f73b350036074f815e40b51ef636_Traceguids
0x180004314  cmp     rcx, rdi
0x180004317  jz      short loc_180004330
0x180004319  test    byte ptr [rcx+1Ch], 20h
0x18000431d  jz      short loc_180004330
0x18000431f  mov     rcx, [rcx+10h]
0x180004323  mov     edx, 94h
0x180004328  mov     r8, rsi
0x18000432b  call    WPP_SF_
0x180004330  lea     rbx, ?_svcWorkTracking@BdeSvcWorkTracking@@0V1@A; BdeSvcWorkTracking BdeSvcWorkTracking::_svcWorkTracking
0x180004337  mov     rcx, rbx; lpCriticalSection
0x18000433a  call    cs:__imp_EnterCriticalSection
0x180004341  nop     dword ptr [rax+rax+00h]
0x180004346  mov     rcx, rbx; this
0x180004349  call    ?CancelAndWaitForOutstandingWorkImpl@BdeSvcWorkTracking@@AEAAXXZ; BdeSvcWorkTracking::CancelAndWaitForOutstandingWorkImpl(void)
0x18000434e  mov     rcx, rbx; lpCriticalSection
0x180004351  call    cs:__imp_LeaveCriticalSection
0x180004358  nop     dword ptr [rax+rax+00h]
0x18000435d  mov     rcx, cs:?gSvchostWaitHandle@@3PEAXEA; WaitHandle
0x180004364  xor     ebx, ebx
0x180004366  test    rcx, rcx
0x180004369  jz      short loc_1800043D0
0x18000436b  xor     edx, edx; CompletionEvent
0x18000436d  call    cs:__imp_UnregisterWaitEx
0x180004374  nop     dword ptr [rax+rax+00h]
0x180004379  test    eax, eax
0x18000437b  jnz     short loc_1800043C9
0x18000437d  call    cs:__imp_GetLastError
0x180004384  nop     dword ptr [rax+rax+00h]
0x180004389  cmp     eax, 3E5h
0x18000438e  jz      short loc_1800043C9
0x180004390  mov     rax, cs:WPP_GLOBAL_Control
0x180004397  cmp     rax, rdi
0x18000439a  jz      short loc_1800043C9
0x18000439c  test    byte ptr [rax+1Ch], 2
0x1800043a0  jz      short loc_1800043C9
0x1800043a2  call    cs:__imp_GetLastError
0x1800043a9  nop     dword ptr [rax+rax+00h]
0x1800043ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800043b5  mov     edx, 95h
0x1800043ba  mov     r9d, eax
0x1800043bd  mov     r8, rsi
0x1800043c0  mov     rcx, [rcx+10h]
0x1800043c4  call    WPP_SF_d
0x1800043c9  mov     cs:?gSvchostWaitHandle@@3PEAXEA, rbx; void * gSvchostWaitHandle
0x1800043d0  mov     rcx, cs:?g_BdeSvcTriggerSubscription@@3PEAU_WNF_USER_SUBSCRIPTION@@EA; _WNF_USER_SUBSCRIPTION * g_BdeSvcTriggerSubscription
0x1800043d7  test    rcx, rcx
0x1800043da  jz      short loc_1800043EF
0x1800043dc  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1800043e3  nop     dword ptr [rax+rax+00h]
0x1800043e8  mov     cs:?g_BdeSvcTriggerSubscription@@3PEAU_WNF_USER_SUBSCRIPTION@@EA, rbx; _WNF_USER_SUBSCRIPTION * g_BdeSvcTriggerSubscription
0x1800043ef  mov     rcx, cs:?g_BdeSvcPersistentRequestSubscription@@3PEAU_WNF_USER_SUBSCRIPTION@@EA; _WNF_USER_SUBSCRIPTION * g_BdeSvcPersistentRequestSubscription
0x1800043f6  test    rcx, rcx
0x1800043f9  jz      short loc_18000440E
0x1800043fb  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180004402  nop     dword ptr [rax+rax+00h]
0x180004407  mov     cs:?g_BdeSvcPersistentRequestSubscription@@3PEAU_WNF_USER_SUBSCRIPTION@@EA, rbx; _WNF_USER_SUBSCRIPTION * g_BdeSvcPersistentRequestSubscription
0x18000440e  mov     rcx, cs:?g_TpmWnfSubscription@@3PEAU_WNF_USER_SUBSCRIPTION@@EA; _WNF_USER_SUBSCRIPTION * g_TpmWnfSubscription
0x180004415  test    rcx, rcx
0x180004418  jz      short loc_18000442D
0x18000441a  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180004421  nop     dword ptr [rax+rax+00h]
0x180004426  mov     cs:?g_TpmWnfSubscription@@3PEAU_WNF_USER_SUBSCRIPTION@@EA, rbx; _WNF_USER_SUBSCRIPTION * g_TpmWnfSubscription
0x18000442d  call    ?BdeSvcDeleteFveRequestCriticalSections@@YAXXZ; BdeSvcDeleteFveRequestCriticalSections(void)
0x180004432  call    ?FveUninitializeAsyncRequestHandler@@YAXXZ; FveUninitializeAsyncRequestHandler(void)
0x180004437  call    ?BdeSvcDeletePersistentRequestTimer@@YAXXZ; BdeSvcDeletePersistentRequestTimer(void)
0x18000443c  call    ?Cleanup@WnfSubscriptions@@SAXXZ; WnfSubscriptions::Cleanup(void)
0x180004441  call    ?UninitializeStatics@CBdeSvcDE@@SAJXZ; CBdeSvcDE::UninitializeStatics(void)
0x180004446  test    eax, eax
0x180004448  jns     short loc_180004470
0x18000444a  mov     rcx, cs:WPP_GLOBAL_Control
0x180004451  cmp     rcx, rdi
0x180004454  jz      short loc_180004470
0x180004456  test    byte ptr [rcx+1Ch], 2
0x18000445a  jz      short loc_180004470
0x18000445c  mov     rcx, [rcx+10h]
0x180004460  mov     edx, 96h
0x180004465  mov     r9d, eax
0x180004468  mov     r8, rsi
0x18000446b  call    WPP_SF_d
0x180004470  mov     rcx, cs:?g_hSvchostStopEvent@@3PEAXEA; hObject
0x180004477  test    rcx, rcx
0x18000447a  jz      short loc_18000448F
0x18000447c  call    cs:__imp_CloseHandle
0x180004483  nop     dword ptr [rax+rax+00h]
0x180004488  mov     cs:?g_hSvchostStopEvent@@3PEAXEA, rbx; void * g_hSvchostStopEvent
0x18000448f  cmp     cs:?g_hStatus@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rbx; SERVICE_STATUS_HANDLE__ * g_hStatus
0x180004496  jz      short loc_1800044E3
0x180004498  lea     rcx, ?g_serviceStatusLock@@3VCAutoCS@@A; lpCriticalSection
0x18000449f  call    cs:__imp_EnterCriticalSection
0x1800044a6  nop     dword ptr [rax+rax+00h]
0x1800044ab  mov     rcx, cs:?g_hStatus@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x1800044b2  lea     rdx, ?g_serviceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x1800044b9  mov     qword ptr cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 1; _SERVICE_STATUS g_serviceStatus ...
0x1800044c4  call    cs:__imp_SetServiceStatus
0x1800044cb  nop     dword ptr [rax+rax+00h]
0x1800044d0  lea     rcx, ?g_serviceStatusLock@@3VCAutoCS@@A; lpCriticalSection
0x1800044d7  call    cs:__imp_LeaveCriticalSection
0x1800044de  nop     dword ptr [rax+rax+00h]
0x1800044e3  lea     rcx, ?g_svcCtlInfo@@3U_BDESVC_SVC_CTL_INFO@@A; lpCriticalSection
0x1800044ea  call    cs:__imp_EnterCriticalSection
0x1800044f1  nop     dword ptr [rax+rax+00h]
0x1800044f6  mov     rax, cs:qword_18009B9F0
0x1800044fd  cmp     [rax+8], rbx
0x180004501  jz      short loc_180004526
0x180004503  mov     rcx, cs:WPP_GLOBAL_Control
0x18000450a  cmp     rcx, rdi
0x18000450d  jz      short loc_18000452D
0x18000450f  test    byte ptr [rcx+1Ch], 2
0x180004513  jz      short loc_18000452D
0x180004515  mov     rcx, [rcx+10h]
0x180004519  mov     edx, 97h
0x18000451e  mov     r8, rsi
0x180004521  call    WPP_SF_
0x180004526  mov     rcx, cs:WPP_GLOBAL_Control
0x18000452d  cmp     cs:?hDevNotify@@3PEAUHCMNOTIFICATION__@@EA, rbx; HCMNOTIFICATION__ * hDevNotify
0x180004534  jz      short loc_180004559
0x180004536  cmp     rcx, rdi
0x180004539  jz      short loc_180004559
0x18000453b  test    byte ptr [rcx+1Ch], 2
0x18000453f  jz      short loc_180004559
0x180004541  mov     rcx, [rcx+10h]
0x180004545  mov     edx, 98h
0x18000454a  mov     r8, rsi
0x18000454d  call    WPP_SF_
0x180004552  mov     rcx, cs:WPP_GLOBAL_Control
0x180004559  mov     r9d, cs:dword_18009B9E8
0x180004560  test    r9d, r9d
0x180004563  jz      short loc_180004581
0x180004565  cmp     rcx, rdi
0x180004568  jz      short loc_180004581
0x18000456a  test    byte ptr [rcx+1Ch], 2
0x18000456e  jz      short loc_180004581
0x180004570  mov     rcx, [rcx+10h]
0x180004574  mov     edx, 99h
0x180004579  mov     r8, rsi
0x18000457c  call    WPP_SF_d
0x180004581  lea     rcx, ?g_svcCtlInfo@@3U_BDESVC_SVC_CTL_INFO@@A; lpCriticalSection
0x180004588  call    cs:__imp_LeaveCriticalSection
0x18000458f  nop     dword ptr [rax+rax+00h]
0x180004594  call    McGenEventUnregister_EventUnregister
0x180004599  call    ?DeleteInstance@RecoveryTelemetery@@SAXXZ; RecoveryTelemetery::DeleteInstance(void)
0x18000459e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800045a5  cmp     rcx, rdi
0x1800045a8  jz      short loc_1800045E4
0x1800045aa  test    byte ptr [rcx+1Ch], 8
0x1800045ae  jz      short loc_1800045C8
0x1800045b0  mov     rcx, [rcx+10h]
0x1800045b4  mov     edx, 9Ah
0x1800045b9  mov     r8, rsi
0x1800045bc  call    WPP_SF_
0x1800045c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800045c8  cmp     rcx, rdi
0x1800045cb  jz      short loc_1800045E4
0x1800045cd  test    byte ptr [rcx+1Ch], 20h
0x1800045d1  jz      short loc_1800045E4
0x1800045d3  mov     rcx, [rcx+10h]
0x1800045d7  mov     edx, 9Bh
0x1800045dc  mov     r8, rsi
0x1800045df  call    WPP_SF_
0x1800045e4  mov     rbx, [rsp+28h+arg_0]
0x1800045e9  mov     rsi, [rsp+28h+arg_8]
0x1800045ee  add     rsp, 20h
0x1800045f2  pop     rdi
0x1800045f3  retn
```
