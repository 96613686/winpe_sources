# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x1800093e0`
- end: `0x180009532`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `338`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x1800681a0`

## callees

- `0x1800093e0`
- `0x180018718`
- `0x180019938`
- `0x18001999c`
- `0x180027720`
- `0x180028804`
- `0x180029fa0`
- `0x18002a9a8`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009497`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800094f5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009497`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800094f5`

## string_xrefs

- `0x1800094b5`: `RtlUnregisterFeatureConfigurationChangeNotification`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::FeatureStateManager::~FeatureStateManager(
        wil::details::FeatureStateManager *this,
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *a2)
{
  struct _TP_TIMER *v3; // rdi
  struct _TP_TIMER *v4; // rdi
  wil::details *v5; // rcx
  struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *v6; // rcx
  wil::details *v7; // rcx
  void *v8; // rdx
  __int64 v9; // rdi
  __int64 (*NtDllProcedureAddress)(void); // rax
  wil::details *v11; // rcx
  struct _TP_TIMER *v12; // rcx
  struct _TP_TIMER *v13; // rcx
  void *v14; // rcx
  char v15; // [rsp+30h] [rbp+8h] BYREF

  *(_BYTE *)this = 0;
  v3 = (struct _TP_TIMER *)*((_QWORD *)this + 6);
  if ( v3 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v15);
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v3);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v15);
  }
  *((_QWORD *)this + 6) = 0;
  v4 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
  if ( v4 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v15);
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v4);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v15);
  }
  *((_QWORD *)this + 7) = 0;
  v5 = (wil::details *)*((_QWORD *)this + 32);
  *((_QWORD *)this + 32) = 0;
  if ( v5 )
    wil::details::FreeProcessHeap(v5, a2);
  v6 = (struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)*((_QWORD *)this + 28);
  if ( v6 )
    wil::details::UnsubscribeProcessWideUsageFlush(v6, a2);
  v7 = (wil::details *)*((_QWORD *)this + 27);
  *((_QWORD *)this + 27) = 0;
  if ( v7 )
    wil::details::FreeProcessHeap(v7, a2);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  v9 = *((_QWORD *)this + 18);
  if ( v9 )
  {
    NtDllProcedureAddress = (__int64 (*)(void))g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification;
    if ( g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
      || (NtDllProcedureAddress = wil_details_GetNtDllProcedureAddress("RtlUnregisterFeatureConfigurationChangeNotification"),
          (g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification = (__int64)NtDllProcedureAddress) != 0) )
    {
      ((void (__fastcall *)(__int64))NtDllProcedureAddress)(v9);
    }
  }
  v11 = (wil::details *)*((_QWORD *)this + 17);
  *((_QWORD *)this + 17) = 0;
  if ( v11 )
    wil::details::FreeProcessHeap(v11, v8);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  v12 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
  if ( v12 )
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v12);
  v13 = (struct _TP_TIMER *)*((_QWORD *)this + 6);
  if ( v13 )
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v13);
  v14 = (void *)*((_QWORD *)this + 2);
  if ( v14 )
    wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(v14);
}

```

## disassembly

```asm
0x1800093e0  mov     [rsp+arg_8], rbx
0x1800093e5  push    rdi
0x1800093e6  sub     rsp, 20h
0x1800093ea  mov     rbx, rcx
0x1800093ed  mov     byte ptr [rcx], 0
0x1800093f0  mov     rdi, [rcx+30h]
0x1800093f4  test    rdi, rdi
0x1800093f7  jz      short loc_180009415
0x1800093f9  lea     rcx, [rsp+28h+arg_0]; this
0x1800093fe  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180009403  mov     rcx, rdi; pti
0x180009406  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x18000940b  lea     rcx, [rsp+28h+arg_0]; this
0x180009410  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180009415  mov     qword ptr [rbx+30h], 0
0x18000941d  mov     rdi, [rbx+38h]
0x180009421  test    rdi, rdi
0x180009424  jz      short loc_180009442
0x180009426  lea     rcx, [rsp+28h+arg_0]; this
0x18000942b  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180009430  mov     rcx, rdi; pti
0x180009433  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x180009438  lea     rcx, [rsp+28h+arg_0]; this
0x18000943d  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180009442  mov     qword ptr [rbx+38h], 0
0x18000944a  mov     rcx, [rbx+100h]; this
0x180009451  mov     qword ptr [rbx+100h], 0
0x18000945c  test    rcx, rcx
0x18000945f  jz      short loc_180009466
0x180009461  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180009466  mov     rcx, [rbx+0E0h]; this
0x18000946d  test    rcx, rcx
0x180009470  jz      short loc_180009477
0x180009472  call    ?UnsubscribeProcessWideUsageFlush@details@wil@@YAXPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details::UnsubscribeProcessWideUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180009477  lea     rdi, [rbx+98h]
0x18000947e  mov     rcx, [rdi+40h]; this
0x180009482  mov     qword ptr [rdi+40h], 0
0x18000948a  test    rcx, rcx
0x18000948d  jz      short loc_180009494
0x18000948f  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180009494  mov     rcx, rdi; lpCriticalSection
0x180009497  call    cs:__imp_DeleteCriticalSection
0x18000949d  mov     rdi, [rbx+90h]
0x1800094a4  test    rdi, rdi
0x1800094a7  jz      short loc_1800094D5
0x1800094a9  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x1800094b0  test    rax, rax
0x1800094b3  jnz     short loc_1800094CD
0x1800094b5  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x1800094bc  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1800094c1  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x1800094c8  test    rax, rax
0x1800094cb  jz      short loc_1800094D5
0x1800094cd  mov     rcx, rdi
0x1800094d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094d5  mov     rcx, [rbx+88h]; this
0x1800094dc  mov     qword ptr [rbx+88h], 0
0x1800094e7  test    rcx, rcx
0x1800094ea  jz      short loc_1800094F1
0x1800094ec  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1800094f1  lea     rcx, [rbx+48h]; lpCriticalSection
0x1800094f5  call    cs:__imp_DeleteCriticalSection
0x1800094fb  mov     rcx, [rbx+38h]; pti
0x1800094ff  test    rcx, rcx
0x180009502  jz      short loc_180009509
0x180009504  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x180009509  mov     rcx, [rbx+30h]; pti
0x18000950d  test    rcx, rcx
0x180009510  jz      short loc_180009518
0x180009512  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x180009517  nop
0x180009518  mov     rcx, [rbx+10h]; lpMem
0x18000951c  test    rcx, rcx
0x18000951f  jz      short loc_180009527
0x180009521  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180009526  nop
0x180009527  mov     rbx, [rsp+28h+arg_8]
0x18000952c  add     rsp, 20h
0x180009530  pop     rdi
0x180009531  retn
```
