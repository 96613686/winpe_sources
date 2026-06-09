# wil::details::_dynamic_atexit_destructor_for__g_featureStateManager__

- ea: `0x14006f840`
- end: `0x14006fa0f`
- name: `wil::details::_dynamic_atexit_destructor_for__g_featureStateManager__`
- size: `463`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x140011760`
- `0x140013a50`
- `0x1400148cc`
- `0x140015290`
- `0x14006f840`
- `0x140071010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006f888`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006f8b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006f888`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006f8b5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14006f89a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14006f8c7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14006f89a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14006f8c7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14006f8e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14006f91f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14006f994`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14006f8e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14006f91f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14006f994`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006f8f5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006f92d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006f9a2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006f8f5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006f92d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006f9a2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14006f967`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14006f967`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14006f93a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14006f9af`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14006f93a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14006f9af`

## string_xrefs

- `0x14006f960`: `RtlUnregisterFeatureConfigurationChangeNotification`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall wil::details::_dynamic_atexit_destructor_for__g_featureStateManager__(
        __int64 a1,
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *a2)
{
  struct _TP_TIMER *v2; // rdi
  DWORD LastError; // ebx
  struct _TP_TIMER *v4; // rdi
  DWORD v5; // ebx
  void *v6; // rbx
  HANDLE ProcessHeap; // rax
  void *v8; // rbx
  HANDLE v9; // rax
  __int64 v10; // rbx
  FARPROC ProcAddress; // rax
  HMODULE NtDllModuleHandle; // rax
  void *v13; // rbx
  HANDLE v14; // rax
  void *v15; // rcx

  if ( wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    wil::details::g_featureStateManager = 0;
    v15 = qword_14009A048;
    if ( !qword_14009A048 )
      return;
    goto LABEL_27;
  }
  wil::details::g_featureStateManager = 0;
  v2 = pti;
  if ( pti )
  {
    LastError = GetLastError();
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v2);
    SetLastError(LastError);
  }
  pti = 0;
  v4 = qword_14009A070;
  if ( qword_14009A070 )
  {
    v5 = GetLastError();
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v4);
    SetLastError(v5);
  }
  qword_14009A070 = 0;
  v6 = lpMem;
  lpMem = 0;
  if ( v6 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v6);
  }
  if ( xmmword_14009A118 )
    wil::details::UnsubscribeProcessWideUsageFlush(xmmword_14009A118, a2);
  v8 = (void *)*((_QWORD *)&xmmword_14009A108 + 1);
  *((_QWORD *)&xmmword_14009A108 + 1) = 0;
  if ( v8 )
  {
    v9 = GetProcessHeap();
    HeapFree(v9, 0, v8);
  }
  DeleteCriticalSection(&stru_14009A0D0);
  v10 = qword_14009A0C8;
  if ( qword_14009A0C8 )
  {
    ProcAddress = (FARPROC)g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification;
    if ( g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
      || (NtDllModuleHandle = wil_details_GetNtDllModuleHandle(),
          ProcAddress = GetProcAddress(NtDllModuleHandle, "RtlUnregisterFeatureConfigurationChangeNotification"),
          (g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification = (__int64)ProcAddress) != 0) )
    {
      ((void (__fastcall *)(__int64))ProcAddress)(v10);
    }
  }
  v13 = (void *)*((_QWORD *)&xmmword_14009A0B8 + 1);
  *((_QWORD *)&xmmword_14009A0B8 + 1) = 0;
  if ( v13 )
  {
    v14 = GetProcessHeap();
    HeapFree(v14, 0, v13);
  }
  DeleteCriticalSection(&CriticalSection);
  if ( qword_14009A070 )
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(qword_14009A070);
  if ( pti )
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(pti);
  v15 = qword_14009A048;
  if ( qword_14009A048 )
LABEL_27:
    wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(v15);
}

```

## disassembly

```asm
0x14006f840  mov     [rsp+arg_0], rbx
0x14006f845  mov     [rsp+arg_8], rsi
0x14006f84a  push    rdi
0x14006f84b  sub     rsp, 20h
0x14006f84f  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x14006f856  jnz     loc_14006F9E6
0x14006f85c  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14006f863  test    rax, rax
0x14006f866  jz      short loc_14006F875
0x14006f868  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006f86d  test    al, al
0x14006f86f  jnz     loc_14006F9E6
0x14006f875  mov     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x14006f87c  mov     rdi, cs:pti
0x14006f883  test    rdi, rdi
0x14006f886  jz      short loc_14006F8A0
0x14006f888  call    cs:__imp_GetLastError
0x14006f88e  mov     ebx, eax
0x14006f890  mov     rcx, rdi; pti
0x14006f893  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x14006f898  mov     ecx, ebx; dwErrCode
0x14006f89a  call    cs:__imp_SetLastError
0x14006f8a0  xor     esi, esi
0x14006f8a2  mov     cs:pti, rsi
0x14006f8a9  mov     rdi, cs:qword_14009A070
0x14006f8b0  test    rdi, rdi
0x14006f8b3  jz      short loc_14006F8CD
0x14006f8b5  call    cs:__imp_GetLastError
0x14006f8bb  mov     ebx, eax
0x14006f8bd  mov     rcx, rdi; pti
0x14006f8c0  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x14006f8c5  mov     ecx, ebx; dwErrCode
0x14006f8c7  call    cs:__imp_SetLastError
0x14006f8cd  mov     cs:qword_14009A070, rsi
0x14006f8d4  mov     rbx, cs:lpMem
0x14006f8db  mov     cs:lpMem, rsi
0x14006f8e2  test    rbx, rbx
0x14006f8e5  jz      short loc_14006F8FB
0x14006f8e7  call    cs:__imp_GetProcessHeap
0x14006f8ed  mov     rcx, rax; hHeap
0x14006f8f0  mov     r8, rbx; lpMem
0x14006f8f3  xor     edx, edx; dwFlags
0x14006f8f5  call    cs:__imp_HeapFree
0x14006f8fb  mov     rcx, qword ptr cs:xmmword_14009A118; this
0x14006f902  test    rcx, rcx
0x14006f905  jz      short loc_14006F90C
0x14006f907  call    ?UnsubscribeProcessWideUsageFlush@details@wil@@YAXPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details::UnsubscribeProcessWideUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x14006f90c  mov     rbx, qword ptr cs:xmmword_14009A108+8
0x14006f913  mov     qword ptr cs:xmmword_14009A108+8, rsi
0x14006f91a  test    rbx, rbx
0x14006f91d  jz      short loc_14006F933
0x14006f91f  call    cs:__imp_GetProcessHeap
0x14006f925  mov     rcx, rax; hHeap
0x14006f928  mov     r8, rbx; lpMem
0x14006f92b  xor     edx, edx; dwFlags
0x14006f92d  call    cs:__imp_HeapFree
0x14006f933  lea     rcx, stru_14009A0D0; lpCriticalSection
0x14006f93a  call    cs:__imp_DeleteCriticalSection
0x14006f940  mov     rbx, cs:qword_14009A0C8
0x14006f947  test    rbx, rbx
0x14006f94a  jz      short loc_14006F981
0x14006f94c  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x14006f953  test    rax, rax
0x14006f956  jnz     short loc_14006F979
0x14006f958  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x14006f95d  mov     rcx, rax; hModule
0x14006f960  lea     rdx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x14006f967  call    cs:__imp_GetProcAddress
0x14006f96d  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x14006f974  test    rax, rax
0x14006f977  jz      short loc_14006F981
0x14006f979  mov     rcx, rbx
0x14006f97c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006f981  mov     rbx, qword ptr cs:xmmword_14009A0B8+8
0x14006f988  mov     qword ptr cs:xmmword_14009A0B8+8, rsi
0x14006f98f  test    rbx, rbx
0x14006f992  jz      short loc_14006F9A8
0x14006f994  call    cs:__imp_GetProcessHeap
0x14006f99a  mov     rcx, rax; hHeap
0x14006f99d  mov     r8, rbx; lpMem
0x14006f9a0  xor     edx, edx; dwFlags
0x14006f9a2  call    cs:__imp_HeapFree
0x14006f9a8  lea     rcx, CriticalSection; lpCriticalSection
0x14006f9af  call    cs:__imp_DeleteCriticalSection
0x14006f9b5  mov     rcx, cs:qword_14009A070; pti
0x14006f9bc  test    rcx, rcx
0x14006f9bf  jz      short loc_14006F9C6
0x14006f9c1  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x14006f9c6  mov     rcx, cs:pti; pti
0x14006f9cd  test    rcx, rcx
0x14006f9d0  jz      short loc_14006F9D8
0x14006f9d2  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x14006f9d7  nop
0x14006f9d8  mov     rcx, cs:qword_14009A048
0x14006f9df  test    rcx, rcx
0x14006f9e2  jnz     short loc_14006F9F9
0x14006f9e4  jmp     short loc_14006F9FF
0x14006f9e6  mov     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x14006f9ed  mov     rcx, cs:qword_14009A048; lpMem
0x14006f9f4  test    rcx, rcx
0x14006f9f7  jz      short loc_14006F9FF
0x14006f9f9  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x14006f9fe  nop
0x14006f9ff  mov     rbx, [rsp+28h+arg_0]
0x14006fa04  mov     rsi, [rsp+28h+arg_8]
0x14006fa09  add     rsp, 20h
0x14006fa0d  pop     rdi
0x14006fa0e  retn
```
