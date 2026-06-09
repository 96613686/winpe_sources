# ShutdownCallback(void)

- ea: `0x1800102e0`
- end: `0x180010544`
- name: `?ShutdownCallback@@YAXXZ`
- size: `612`
- prototype: `void(void)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001108`
- `0x1800018ac`
- `0x180003ab0`
- `0x1800047f0`
- `0x180005c6c`
- `0x18000cd2c`
- `0x18000d67c`
- `0x18000f5c8`
- `0x1800102e0`
- `0x1800106cc`
- `0x180010f1c`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010309`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010309`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800103de`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800103de`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180010322`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180010322`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessMemoryInfo` at `0x1800103f1`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessMemoryInfo` at `0x1800103f1`

## string_xrefs

- `0x180010403`: `onecoreuap\windows\directx\dxg\gpm\service\service.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void ShutdownCallback(void)
{
  struct MLSDClassifier *Instance; // rdi
  std::_Ref_count_base *v1; // rcx
  std::_Ref_count_base *v2; // rcx
  HANDLE CurrentProcess; // rax
  const char *v4; // r9
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r10
  const char *v7; // [rsp+20h] [rbp-128h]
  DWORD PageFaultCount; // [rsp+40h] [rbp-108h] BYREF
  int v9; // [rsp+44h] [rbp-104h] BYREF
  SIZE_T PeakWorkingSetSize; // [rsp+48h] [rbp-100h] BYREF
  SIZE_T PeakPagefileUsage; // [rsp+50h] [rbp-F8h] BYREF
  __int64 v12; // [rsp+58h] [rbp-F0h] BYREF
  struct _RTL_CRITICAL_SECTION *v13; // [rsp+60h] [rbp-E8h] BYREF
  PROCESS_MEMORY_COUNTERS ppsmemCounters; // [rsp+70h] [rbp-D8h] BYREF
  _BYTE v15[32]; // [rsp+C0h] [rbp-88h] BYREF
  __int64 *v16; // [rsp+E0h] [rbp-68h]
  __int64 v17; // [rsp+E8h] [rbp-60h]
  int *v18; // [rsp+F0h] [rbp-58h]
  __int64 v19; // [rsp+F8h] [rbp-50h]
  DWORD *p_PageFaultCount; // [rsp+100h] [rbp-48h]
  __int64 v21; // [rsp+108h] [rbp-40h]
  SIZE_T *p_PeakPagefileUsage; // [rsp+110h] [rbp-38h]
  __int64 v23; // [rsp+118h] [rbp-30h]
  SIZE_T *p_PeakWorkingSetSize; // [rsp+120h] [rbp-28h]
  __int64 v25; // [rsp+128h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  EnterCriticalSection(&g::ShutdownCritsect);
  v13 = &g::ShutdownCritsect;
  if ( g::TelemetryTargetNotification )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion();
    g::TelemetryTargetNotification = 0;
  }
  ServiceEtwThreadHelper::WaitForJoinAndResetTraceConsumer(g::serviceEtwThreadHelper);
  try
  {
    Instance = MLSDClassifier::GetInstance();
    *((_QWORD *)Instance + 1) = 0;
    v1 = (std::_Ref_count_base *)*((_QWORD *)Instance + 2);
    *((_QWORD *)Instance + 2) = 0;
    if ( v1 )
      std::_Ref_count_base::_Decref(v1);
    *((_QWORD *)Instance + 3) = 0;
    v2 = (std::_Ref_count_base *)*((_QWORD *)Instance + 4);
    *((_QWORD *)Instance + 4) = 0;
    if ( v2 )
      std::_Ref_count_base::_Decref(v2);
    *(_DWORD *)Instance = 0;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtExceptionMsg(
      retaddr,
      (void *)0x152,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\gpm\\service\\service.cpp",
      "Exception thrown while shutting down MLSD",
      v7);
  }
  if ( g::pContextCallback )
  {
    (*(void (__fastcall **)(LPVOID, __int64 (__fastcall *)(struct tagComCallData *), _QWORD, GUID *, int, _QWORD))(*(_QWORD *)g::pContextCallback + 24LL))(
      g::pContextCallback,
      DisconnectCallback,
      0,
      &IID_IContextCallback,
      5,
      0);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)g::pContextCallback + 16LL))(g::pContextCallback);
    g::pContextCallback = 0;
  }
  memset_0(&ppsmemCounters, 0, 0x50u);
  ppsmemCounters.cb = 80;
  CurrentProcess = GetCurrentProcess();
  if ( !K32GetProcessMemoryInfo(CurrentProcess, &ppsmemCounters, ppsmemCounters.cb) )
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0x165,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\gpm\\service\\service.cpp",
      v4);
  v5 = gpm::TraceProvider::Provider();
  if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x400000000000LL) )
  {
    PeakWorkingSetSize = ppsmemCounters.PeakWorkingSetSize;
    PeakPagefileUsage = ppsmemCounters.PeakPagefileUsage;
    PageFaultCount = ppsmemCounters.PageFaultCount;
    v9 = 1;
    v12 = 0x1000000;
    p_PeakWorkingSetSize = &PeakWorkingSetSize;
    v25 = 8;
    p_PeakPagefileUsage = &PeakPagefileUsage;
    v23 = 8;
    p_PageFaultCount = &PageFaultCount;
    v21 = 4;
    v18 = &v9;
    v19 = 4;
    v16 = &v12;
    v17 = 8;
    tlgWriteTransfer_EventWriteTransfer(v6, &byte_180039C4F, 0, 0, 7, v15);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v13);
}

```

## disassembly

```asm
0x1800102e0  mov     [rsp+arg_0], rbx
0x1800102e5  push    rdi
0x1800102e6  sub     rsp, 140h
0x1800102ed  mov     rax, cs:__security_cookie
0x1800102f4  xor     rax, rsp
0x1800102f7  mov     [rsp+148h+var_18], rax
0x1800102ff  lea     rbx, ?ShutdownCritsect@g@@3Vcritical_section@wil@@A; wil::critical_section g::ShutdownCritsect
0x180010306  mov     rcx, rbx; lpCriticalSection
0x180010309  call    cs:__imp_EnterCriticalSection
0x18001030f  mov     [rsp+148h+var_E8], rbx
0x180010314  mov     rcx, cs:?TelemetryTargetNotification@g@@3PEAU_WNF_USER_SUBSCRIPTION@@EA; _WNF_USER_SUBSCRIPTION * g::TelemetryTargetNotification
0x18001031b  xor     ebx, ebx
0x18001031d  test    rcx, rcx
0x180010320  jz      short loc_18001032F
0x180010322  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180010328  mov     cs:?TelemetryTargetNotification@g@@3PEAU_WNF_USER_SUBSCRIPTION@@EA, rbx; _WNF_USER_SUBSCRIPTION * g::TelemetryTargetNotification
0x18001032f  mov     rcx, cs:?serviceEtwThreadHelper@g@@3V?$unique_ptr@VServiceEtwThreadHelper@@U?$default_delete@VServiceEtwThreadHelper@@@std@@@std@@A; this
0x180010336  call    ?WaitForJoinAndResetTraceConsumer@ServiceEtwThreadHelper@@QEAAXXZ; ServiceEtwThreadHelper::WaitForJoinAndResetTraceConsumer(void)
0x18001033b  nop
0x18001033c  call    ?GetInstance@MLSDClassifier@@SAAEAV1@XZ; MLSDClassifier::GetInstance(void)
0x180010341  mov     rdi, rax
0x180010344  mov     [rax+8], rbx
0x180010348  mov     rcx, [rax+10h]; this
0x18001034c  mov     [rax+10h], rbx
0x180010350  test    rcx, rcx
0x180010353  jz      short loc_18001035A
0x180010355  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001035a  mov     [rdi+18h], rbx
0x18001035e  mov     rcx, [rdi+20h]; this
0x180010362  mov     [rdi+20h], rbx
0x180010366  test    rcx, rcx
0x180010369  jz      short loc_180010370
0x18001036b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180010370  mov     [rdi], ebx
0x180010372  jmp     short loc_180010376
0x180010374  xor     ebx, ebx
0x180010376  mov     rcx, cs:?pContextCallback@g@@3PEAUIContextCallback@@EA; IContextCallback * g::pContextCallback
0x18001037d  test    rcx, rcx
0x180010380  jz      short loc_1800103C6
0x180010382  mov     rax, [rcx]
0x180010385  mov     [rsp+148h+var_120], rbx
0x18001038a  mov     [rsp+148h+var_128], 5
0x180010392  lea     r9, IID_IContextCallback
0x180010399  xor     r8d, r8d
0x18001039c  lea     rdx, ?DisconnectCallback@@YAJPEAUtagComCallData@@@Z; DisconnectCallback(tagComCallData *)
0x1800103a3  mov     rax, [rax+18h]
0x1800103a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103ac  mov     rcx, cs:?pContextCallback@g@@3PEAUIContextCallback@@EA; IContextCallback * g::pContextCallback
0x1800103b3  mov     rax, [rcx]
0x1800103b6  mov     rax, [rax+10h]
0x1800103ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103bf  mov     cs:?pContextCallback@g@@3PEAUIContextCallback@@EA, rbx; IContextCallback * g::pContextCallback
0x1800103c6  mov     edi, 50h ; 'P'
0x1800103cb  mov     r8d, edi; Size
0x1800103ce  xor     edx, edx; Val
0x1800103d0  lea     rcx, [rsp+148h+ppsmemCounters]; void *
0x1800103d5  call    memset_0
0x1800103da  mov     [rsp+148h+ppsmemCounters.cb], edi
0x1800103de  call    cs:__imp_GetCurrentProcess
0x1800103e4  mov     rcx, rax; Process
0x1800103e7  mov     r8d, [rsp+148h+ppsmemCounters.cb]; cb
0x1800103ec  lea     rdx, [rsp+148h+ppsmemCounters]; ppsmemCounters
0x1800103f1  call    cs:__imp_K32GetProcessMemoryInfo
0x1800103f7  mov     rcx, [rsp+148h]; this
0x1800103ff  test    eax, eax
0x180010401  jnz     short loc_180010414
0x180010403  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\directx\\dxg\\gpm"...
0x18001040a  mov     edx, 165h; void *
0x18001040f  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180010414  call    ?Provider@TraceProvider@gpm@@SAPEBU_tlgProvider_t@@XZ; gpm::TraceProvider::Provider(void)
0x180010419  mov     r10, rax
0x18001041c  mov     ecx, [rax]
0x18001041e  cmp     ecx, 5
0x180010421  jbe     loc_180010519
0x180010427  mov     rdx, 400000000000h
0x180010431  mov     rcx, rax
0x180010434  call    _tlgKeywordOn
0x180010439  test    al, al
0x18001043b  jz      loc_180010519
0x180010441  mov     rcx, [rsp+148h+ppsmemCounters.PeakWorkingSetSize]
0x180010446  mov     [rsp+148h+var_100], rcx
0x18001044b  mov     rax, [rsp+148h+ppsmemCounters.PeakPagefileUsage]
0x180010453  mov     [rsp+148h+var_F8], rax
0x180010458  mov     eax, [rsp+148h+ppsmemCounters.PageFaultCount]
0x18001045c  mov     dword ptr [rsp+148h+var_108], eax
0x180010460  mov     dword ptr [rsp+148h+var_108+4], 1
0x180010468  mov     [rsp+148h+var_F0], 1000000h
0x180010471  lea     rax, [rsp+148h+var_100]
0x180010476  mov     [rsp+148h+var_28], rax
0x18001047e  mov     [rsp+148h+var_20], 8
0x18001048a  lea     rax, [rsp+148h+var_F8]
0x18001048f  mov     [rsp+148h+var_38], rax
0x180010497  mov     [rsp+148h+var_30], 8
0x1800104a3  lea     rax, [rsp+148h+var_108]
0x1800104a8  mov     [rsp+148h+var_48], rax
0x1800104b0  mov     [rsp+148h+var_40], 4
0x1800104bc  lea     rax, [rsp+148h+var_108+4]
0x1800104c1  mov     [rsp+148h+var_58], rax
0x1800104c9  mov     [rsp+148h+var_50], 4
0x1800104d5  lea     rax, [rsp+148h+var_F0]
0x1800104da  mov     [rsp+148h+var_68], rax
0x1800104e2  mov     [rsp+148h+var_60], 8
0x1800104ee  lea     rax, [rsp+148h+var_88]
0x1800104f6  mov     [rsp+148h+var_120], rax
0x1800104fb  mov     [rsp+148h+var_128], 7
0x180010503  xor     r9d, r9d
0x180010506  xor     r8d, r8d
0x180010509  lea     rdx, byte_180039C4F
0x180010510  mov     rcx, r10
0x180010513  call    _tlgWriteTransfer_EventWriteTransfer
0x180010518  nop
0x180010519  lea     rcx, [rsp+148h+var_E8]
0x18001051e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180010523  mov     rcx, [rsp+148h+var_18]
0x18001052b  xor     rcx, rsp; StackCookie
0x18001052e  call    __security_check_cookie
0x180010533  mov     rbx, [rsp+148h+arg_0]
0x18001053b  add     rsp, 140h
0x180010542  pop     rdi
0x180010543  retn
```
