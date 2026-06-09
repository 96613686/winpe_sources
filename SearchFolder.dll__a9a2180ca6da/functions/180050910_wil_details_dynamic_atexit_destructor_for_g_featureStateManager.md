# wil::details::_dynamic_atexit_destructor_for__g_featureStateManager__

- ea: `0x180050910`
- end: `0x180050adf`
- name: `wil::details::_dynamic_atexit_destructor_for__g_featureStateManager__`
- size: `463`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000a130`
- `0x18000d748`
- `0x18000f7cc`
- `0x180010488`
- `0x180050910`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180050a37`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180050a37`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180050a0a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180050a7f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180050a0a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180050a7f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800509c5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800509fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180050a72`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800509c5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800509fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180050a72`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800509b7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800509ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180050a64`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800509b7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800509ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180050a64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050958`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050985`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050958`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050985`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005096a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180050997`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005096a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180050997`

## string_xrefs

- `0x180050a30`: `RtlUnregisterFeatureConfigurationChangeNotification`

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
    v15 = qword_1800692A0;
    if ( !qword_1800692A0 )
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
  v4 = qword_1800692C8;
  if ( qword_1800692C8 )
  {
    v5 = GetLastError();
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v4);
    SetLastError(v5);
  }
  qword_1800692C8 = 0;
  v6 = lpMem;
  lpMem = 0;
  if ( v6 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v6);
  }
  if ( xmmword_180069370 )
    wil::details::UnsubscribeProcessWideUsageFlush(xmmword_180069370, a2);
  v8 = (void *)*((_QWORD *)&xmmword_180069360 + 1);
  *((_QWORD *)&xmmword_180069360 + 1) = 0;
  if ( v8 )
  {
    v9 = GetProcessHeap();
    HeapFree(v9, 0, v8);
  }
  DeleteCriticalSection(&stru_180069328);
  v10 = qword_180069320;
  if ( qword_180069320 )
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
  v13 = (void *)*((_QWORD *)&xmmword_180069310 + 1);
  *((_QWORD *)&xmmword_180069310 + 1) = 0;
  if ( v13 )
  {
    v14 = GetProcessHeap();
    HeapFree(v14, 0, v13);
  }
  DeleteCriticalSection(&CriticalSection);
  if ( qword_1800692C8 )
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(qword_1800692C8);
  if ( pti )
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(pti);
  v15 = qword_1800692A0;
  if ( qword_1800692A0 )
LABEL_27:
    wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(v15);
}

```

## disassembly

```asm
0x180050910  mov     [rsp+arg_0], rbx
0x180050915  mov     [rsp+arg_8], rsi
0x18005091a  push    rdi
0x18005091b  sub     rsp, 20h
0x18005091f  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180050926  jnz     loc_180050AB6
0x18005092c  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180050933  test    rax, rax
0x180050936  jz      short loc_180050945
0x180050938  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005093d  test    al, al
0x18005093f  jnz     loc_180050AB6
0x180050945  mov     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18005094c  mov     rdi, cs:pti
0x180050953  test    rdi, rdi
0x180050956  jz      short loc_180050970
0x180050958  call    cs:__imp_GetLastError
0x18005095e  mov     ebx, eax
0x180050960  mov     rcx, rdi; pti
0x180050963  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x180050968  mov     ecx, ebx; dwErrCode
0x18005096a  call    cs:__imp_SetLastError
0x180050970  xor     esi, esi
0x180050972  mov     cs:pti, rsi
0x180050979  mov     rdi, cs:qword_1800692C8
0x180050980  test    rdi, rdi
0x180050983  jz      short loc_18005099D
0x180050985  call    cs:__imp_GetLastError
0x18005098b  mov     ebx, eax
0x18005098d  mov     rcx, rdi; pti
0x180050990  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x180050995  mov     ecx, ebx; dwErrCode
0x180050997  call    cs:__imp_SetLastError
0x18005099d  mov     cs:qword_1800692C8, rsi
0x1800509a4  mov     rbx, cs:lpMem
0x1800509ab  mov     cs:lpMem, rsi
0x1800509b2  test    rbx, rbx
0x1800509b5  jz      short loc_1800509CB
0x1800509b7  call    cs:__imp_GetProcessHeap
0x1800509bd  mov     rcx, rax; hHeap
0x1800509c0  mov     r8, rbx; lpMem
0x1800509c3  xor     edx, edx; dwFlags
0x1800509c5  call    cs:__imp_HeapFree
0x1800509cb  mov     rcx, qword ptr cs:xmmword_180069370; this
0x1800509d2  test    rcx, rcx
0x1800509d5  jz      short loc_1800509DC
0x1800509d7  call    ?UnsubscribeProcessWideUsageFlush@details@wil@@YAXPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details::UnsubscribeProcessWideUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x1800509dc  mov     rbx, qword ptr cs:xmmword_180069360+8
0x1800509e3  mov     qword ptr cs:xmmword_180069360+8, rsi
0x1800509ea  test    rbx, rbx
0x1800509ed  jz      short loc_180050A03
0x1800509ef  call    cs:__imp_GetProcessHeap
0x1800509f5  mov     rcx, rax; hHeap
0x1800509f8  mov     r8, rbx; lpMem
0x1800509fb  xor     edx, edx; dwFlags
0x1800509fd  call    cs:__imp_HeapFree
0x180050a03  lea     rcx, stru_180069328; lpCriticalSection
0x180050a0a  call    cs:__imp_DeleteCriticalSection
0x180050a10  mov     rbx, cs:qword_180069320
0x180050a17  test    rbx, rbx
0x180050a1a  jz      short loc_180050A51
0x180050a1c  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x180050a23  test    rax, rax
0x180050a26  jnz     short loc_180050A49
0x180050a28  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x180050a2d  mov     rcx, rax; hModule
0x180050a30  lea     rdx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x180050a37  call    cs:__imp_GetProcAddress
0x180050a3d  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x180050a44  test    rax, rax
0x180050a47  jz      short loc_180050A51
0x180050a49  mov     rcx, rbx
0x180050a4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050a51  mov     rbx, qword ptr cs:xmmword_180069310+8
0x180050a58  mov     qword ptr cs:xmmword_180069310+8, rsi
0x180050a5f  test    rbx, rbx
0x180050a62  jz      short loc_180050A78
0x180050a64  call    cs:__imp_GetProcessHeap
0x180050a6a  mov     rcx, rax; hHeap
0x180050a6d  mov     r8, rbx; lpMem
0x180050a70  xor     edx, edx; dwFlags
0x180050a72  call    cs:__imp_HeapFree
0x180050a78  lea     rcx, CriticalSection; lpCriticalSection
0x180050a7f  call    cs:__imp_DeleteCriticalSection
0x180050a85  mov     rcx, cs:qword_1800692C8; pti
0x180050a8c  test    rcx, rcx
0x180050a8f  jz      short loc_180050A96
0x180050a91  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x180050a96  mov     rcx, cs:pti; pti
0x180050a9d  test    rcx, rcx
0x180050aa0  jz      short loc_180050AA8
0x180050aa2  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x180050aa7  nop
0x180050aa8  mov     rcx, cs:qword_1800692A0
0x180050aaf  test    rcx, rcx
0x180050ab2  jnz     short loc_180050AC9
0x180050ab4  jmp     short loc_180050ACF
0x180050ab6  mov     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180050abd  mov     rcx, cs:qword_1800692A0; lpMem
0x180050ac4  test    rcx, rcx
0x180050ac7  jz      short loc_180050ACF
0x180050ac9  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180050ace  nop
0x180050acf  mov     rbx, [rsp+28h+arg_0]
0x180050ad4  mov     rsi, [rsp+28h+arg_8]
0x180050ad9  add     rsp, 20h
0x180050add  pop     rdi
0x180050ade  retn
```
