# wil::manually_managed_shutdown_aware_object<wil::details::FeatureStateManager>::destroy(void)

- ea: `0x1400016b0`
- end: `0x140001953`
- name: `?destroy@?$manually_managed_shutdown_aware_object@VFeatureStateManager@details@wil@@@wil@@QEAAXXZ`
- size: `675`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting`

## callers

- `0x140039110`

## callees

- `0x1400016b0`
- `0x140002910`
- `0x140002a40`
- `0x140007764`
- `0x140009400`
- `0x14000b458`
- `0x14000bdc0`
- `0x14000cef8`
- `0x14000d584`
- `0x14000dc5c`
- `0x14003a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000179d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400017c4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000179d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400017c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000178b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400017b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000178b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400017b2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140001874`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140001874`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140001847`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400018b9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140001847`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400018b9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140001761`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400017ef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000183a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400018af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140001761`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400017ef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000183a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400018af`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140001753`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400017e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000182c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400018a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140001753`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400017e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000182c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400018a1`

## string_xrefs

- `0x14000186d`: `RtlUnregisterFeatureConfigurationChangeNotification`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::manually_managed_shutdown_aware_object<wil::details::FeatureStateManager>::destroy(__int64 a1)
{
  bool v2; // al
  _DWORD *v3; // rbx
  void *v4; // rdx
  HANDLE v5; // rax
  struct _TP_TIMER *v6; // rsi
  DWORD LastError; // edi
  struct _TP_TIMER *v8; // rsi
  DWORD v9; // edi
  void *v10; // rdi
  HANDLE ProcessHeap; // rax
  struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *v12; // r8
  void *v13; // rsi
  HANDLE v14; // rax
  __int64 v15; // rdi
  FARPROC ProcAddress; // rax
  HMODULE NtDllModuleHandle; // rax
  void *v18; // rsi
  HANDLE v19; // rax
  struct _TP_TIMER *v20; // rcx
  struct _TP_TIMER *v21; // rcx
  wil::details *v22; // [rsp+68h] [rbp+10h] BYREF

  v2 = wil::details::g_processShutdownInProgress;
  if ( wil::details::g_processShutdownInProgress )
    goto LABEL_5;
  if ( wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    v2 = wil::details::g_processShutdownInProgress;
LABEL_5:
    *(_BYTE *)a1 = 0;
    v3 = *(_DWORD **)(a1 + 16);
    if ( !v3 )
      return;
    if ( !v2
      && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
    {
      _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
        v3 + 2,
        &v22);
      if ( --*v3 )
        goto LABEL_11;
      goto LABEL_10;
    }
    if ( --*v3 )
      return;
    goto LABEL_43;
  }
  *(_BYTE *)a1 = 0;
  v6 = *(struct _TP_TIMER **)(a1 + 48);
  if ( v6 )
  {
    LastError = GetLastError();
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v6);
    SetLastError(LastError);
  }
  *(_QWORD *)(a1 + 48) = 0;
  v8 = *(struct _TP_TIMER **)(a1 + 56);
  if ( v8 )
  {
    v9 = GetLastError();
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v8);
    SetLastError(v9);
  }
  *(_QWORD *)(a1 + 56) = 0;
  v10 = *(void **)(a1 + 256);
  *(_QWORD *)(a1 + 256) = 0;
  if ( v10 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v10);
  }
  v12 = *(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **)(a1 + 224);
  if ( v12 && qword_140052218 )
    wil::details_abi::SubscriptionList::Unsubscribe(
      (struct wil::srwlock *)((char *)qword_140052218 + 200),
      qword_140052218,
      v12);
  v13 = *(void **)(a1 + 216);
  *(_QWORD *)(a1 + 216) = 0;
  if ( v13 )
  {
    v14 = GetProcessHeap();
    HeapFree(v14, 0, v13);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 152));
  v15 = *(_QWORD *)(a1 + 144);
  if ( v15 )
  {
    ProcAddress = (FARPROC)g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification;
    if ( g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
      || (NtDllModuleHandle = wil_details_GetNtDllModuleHandle(),
          ProcAddress = GetProcAddress(NtDllModuleHandle, "RtlUnregisterFeatureConfigurationChangeNotification"),
          (g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification = (__int64)ProcAddress) != 0) )
    {
      ((void (__fastcall *)(__int64))ProcAddress)(v15);
    }
  }
  v18 = *(void **)(a1 + 136);
  *(_QWORD *)(a1 + 136) = 0;
  if ( v18 )
  {
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v18);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 72));
  v20 = *(struct _TP_TIMER **)(a1 + 56);
  if ( v20 )
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v20);
  v21 = *(struct _TP_TIMER **)(a1 + 48);
  if ( v21 )
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v21);
  v3 = *(_DWORD **)(a1 + 16);
  if ( v3 )
  {
    if ( !wil::details::g_processShutdownInProgress
      && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
    {
      _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
        v3 + 2,
        &v22);
      if ( --*v3 )
      {
LABEL_11:
        if ( v22 )
          wil::details::ReleaseMutex(v22, v4);
        return;
      }
LABEL_10:
      wil::details_abi::SemaphoreValue::Destroy((wil::details_abi::SemaphoreValue *)(v3 + 4));
      _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
        &v22,
        0);
      wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::~ProcessLocalStorageData<wil::details_abi::FeatureStateData>(v3);
      v5 = GetProcessHeap();
      HeapFree(v5, 0, v3);
      goto LABEL_11;
    }
    if ( --*v3 )
      return;
LABEL_43:
    wil::details_abi::FeatureStateData::ProcessShutdown((wil::details_abi::FeatureStateData *)(v3 + 8));
  }
}

```

## disassembly

```asm
0x1400016b0  push    rbx
0x1400016b2  push    rbp
0x1400016b3  push    rsi
0x1400016b4  push    rdi
0x1400016b5  sub     rsp, 38h
0x1400016b9  mov     rbx, rcx
0x1400016bc  movzx   eax, cs:?g_processShutdownInProgress@details@wil@@3_NA; bool wil::details::g_processShutdownInProgress
0x1400016c3  test    al, al
0x1400016c5  jnz     short loc_1400016EB
0x1400016c7  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1400016ce  test    rax, rax
0x1400016d1  jz      loc_14000177F
0x1400016d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400016dc  test    al, al
0x1400016de  jz      loc_14000177F
0x1400016e4  movzx   eax, cs:?g_processShutdownInProgress@details@wil@@3_NA; bool wil::details::g_processShutdownInProgress
0x1400016eb  mov     byte ptr [rbx], 0
0x1400016ee  mov     rbx, [rbx+10h]
0x1400016f2  test    rbx, rbx
0x1400016f5  jz      loc_14000194A
0x1400016fb  test    al, al
0x1400016fd  jnz     loc_140001934
0x140001703  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000170a  test    rax, rax
0x14000170d  jz      short loc_14000171C
0x14000170f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001714  test    al, al
0x140001716  jnz     loc_140001934
0x14000171c  lea     rcx, [rbx+8]
0x140001720  lea     rdx, [rsp+58h+arg_8]
0x140001725  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x14000172a  mov     eax, [rbx]
0x14000172c  dec     eax
0x14000172e  mov     [rbx], eax
0x140001730  mov     eax, [rbx]
0x140001732  test    eax, eax
0x140001734  jnz     short loc_140001767
0x140001736  lea     rcx, [rbx+10h]; this
0x14000173a  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x14000173f  xor     edx, edx
0x140001741  lea     rcx, [rsp+58h+arg_8]
0x140001746  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x14000174b  mov     rcx, rbx
0x14000174e  call    ??1?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::~ProcessLocalStorageData<wil::details_abi::FeatureStateData>(void)
0x140001753  call    cs:__imp_GetProcessHeap
0x140001759  mov     rcx, rax; hHeap
0x14000175c  mov     r8, rbx; lpMem
0x14000175f  xor     edx, edx; dwFlags
0x140001761  call    cs:__imp_HeapFree
0x140001767  mov     rcx, [rsp+58h+arg_8]; this
0x14000176c  test    rcx, rcx
0x14000176f  jz      loc_14000194A
0x140001775  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x14000177a  jmp     loc_14000194A
0x14000177f  mov     byte ptr [rbx], 0
0x140001782  mov     rsi, [rbx+30h]
0x140001786  test    rsi, rsi
0x140001789  jz      short loc_1400017A3
0x14000178b  call    cs:__imp_GetLastError
0x140001791  mov     edi, eax
0x140001793  mov     rcx, rsi; pti
0x140001796  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x14000179b  mov     ecx, edi; dwErrCode
0x14000179d  call    cs:__imp_SetLastError
0x1400017a3  xor     ebp, ebp
0x1400017a5  mov     [rbx+30h], rbp
0x1400017a9  mov     rsi, [rbx+38h]
0x1400017ad  test    rsi, rsi
0x1400017b0  jz      short loc_1400017CA
0x1400017b2  call    cs:__imp_GetLastError
0x1400017b8  mov     edi, eax
0x1400017ba  mov     rcx, rsi; pti
0x1400017bd  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x1400017c2  mov     ecx, edi; dwErrCode
0x1400017c4  call    cs:__imp_SetLastError
0x1400017ca  mov     [rbx+38h], rbp
0x1400017ce  mov     rdi, [rbx+100h]
0x1400017d5  mov     [rbx+100h], rbp
0x1400017dc  test    rdi, rdi
0x1400017df  jz      short loc_1400017F5
0x1400017e1  call    cs:__imp_GetProcessHeap
0x1400017e7  mov     rcx, rax; hHeap
0x1400017ea  mov     r8, rdi; lpMem
0x1400017ed  xor     edx, edx; dwFlags
0x1400017ef  call    cs:__imp_HeapFree
0x1400017f5  mov     r8, [rbx+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x1400017fc  test    r8, r8
0x1400017ff  jz      short loc_140001819
0x140001801  mov     rdx, cs:qword_140052218; struct wil::srwlock *
0x140001808  test    rdx, rdx
0x14000180b  jz      short loc_140001819
0x14000180d  lea     rcx, [rdx+0C8h]; this
0x140001814  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x140001819  mov     rsi, [rbx+0D8h]
0x140001820  mov     [rbx+0D8h], rbp
0x140001827  test    rsi, rsi
0x14000182a  jz      short loc_140001840
0x14000182c  call    cs:__imp_GetProcessHeap
0x140001832  mov     rcx, rax; hHeap
0x140001835  mov     r8, rsi; lpMem
0x140001838  xor     edx, edx; dwFlags
0x14000183a  call    cs:__imp_HeapFree
0x140001840  lea     rcx, [rbx+98h]; lpCriticalSection
0x140001847  call    cs:__imp_DeleteCriticalSection
0x14000184d  mov     rdi, [rbx+90h]
0x140001854  test    rdi, rdi
0x140001857  jz      short loc_14000188E
0x140001859  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x140001860  test    rax, rax
0x140001863  jnz     short loc_140001886
0x140001865  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x14000186a  mov     rcx, rax; hModule
0x14000186d  lea     rdx, ProcName; "RtlUnregisterFeatureConfigurationChange"...
0x140001874  call    cs:__imp_GetProcAddress
0x14000187a  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x140001881  test    rax, rax
0x140001884  jz      short loc_14000188E
0x140001886  mov     rcx, rdi
0x140001889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000188e  mov     rsi, [rbx+88h]
0x140001895  mov     [rbx+88h], rbp
0x14000189c  test    rsi, rsi
0x14000189f  jz      short loc_1400018B5
0x1400018a1  call    cs:__imp_GetProcessHeap
0x1400018a7  mov     rcx, rax; hHeap
0x1400018aa  mov     r8, rsi; lpMem
0x1400018ad  xor     edx, edx; dwFlags
0x1400018af  call    cs:__imp_HeapFree
0x1400018b5  lea     rcx, [rbx+48h]; lpCriticalSection
0x1400018b9  call    cs:__imp_DeleteCriticalSection
0x1400018bf  mov     rcx, [rbx+38h]; pti
0x1400018c3  test    rcx, rcx
0x1400018c6  jz      short loc_1400018CD
0x1400018c8  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x1400018cd  mov     rcx, [rbx+30h]; pti
0x1400018d1  test    rcx, rcx
0x1400018d4  jz      short loc_1400018DC
0x1400018d6  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x1400018db  nop
0x1400018dc  mov     rbx, [rbx+10h]
0x1400018e0  test    rbx, rbx
0x1400018e3  jz      short loc_14000194A
0x1400018e5  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1400018ec  jnz     short loc_140001926
0x1400018ee  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1400018f5  test    rax, rax
0x1400018f8  jz      short loc_140001903
0x1400018fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400018ff  test    al, al
0x140001901  jnz     short loc_140001926
0x140001903  lea     rcx, [rbx+8]
0x140001907  lea     rdx, [rsp+58h+arg_8]
0x14000190c  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x140001911  mov     eax, [rbx]
0x140001913  dec     eax
0x140001915  mov     [rbx], eax
0x140001917  mov     eax, [rbx]
0x140001919  test    eax, eax
0x14000191b  jz      loc_140001736
0x140001921  jmp     loc_140001767
0x140001926  mov     eax, [rbx]
0x140001928  dec     eax
0x14000192a  mov     [rbx], eax
0x14000192c  mov     eax, [rbx]
0x14000192e  test    eax, eax
0x140001930  jz      short loc_140001940
0x140001932  jmp     short loc_14000194A
0x140001934  mov     eax, [rbx]
0x140001936  dec     eax
0x140001938  mov     [rbx], eax
0x14000193a  mov     eax, [rbx]
0x14000193c  test    eax, eax
0x14000193e  jnz     short loc_14000194A
0x140001940  lea     rcx, [rbx+20h]; this
0x140001944  call    ?ProcessShutdown@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::ProcessShutdown(void)
0x140001949  nop
0x14000194a  add     rsp, 38h
0x14000194e  pop     rdi
0x14000194f  pop     rsi
0x140001950  pop     rbp
0x140001951  pop     rbx
0x140001952  retn
```
