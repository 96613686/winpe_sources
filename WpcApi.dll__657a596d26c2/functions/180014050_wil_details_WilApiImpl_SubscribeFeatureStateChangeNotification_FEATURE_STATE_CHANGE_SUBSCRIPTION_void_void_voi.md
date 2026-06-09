# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180014050`
- end: `0x18001415d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180013b34`
- `0x180013c30`
- `0x180014050`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800140da`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800140da`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800140f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800140f1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014147`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014147`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800140a0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800140a0`

## string_xrefs

- `0x1800140d3`: `ntdll.dll`
- `0x1800140e7`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c
void __fastcall wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this,
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **a2,
        void (*a3)(void *),
        void *a4)
{
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v9; // eax

  if ( a3 == (void (*)(void *))-1LL )
  {
    wil::details::FeatureStateManager::SubscribeToUsageFlush(
      (wil::details::FeatureStateManager *)&wil::details::g_featureStateManager,
      this,
      (void (*)(void *))a2);
  }
  else
  {
    *this = 0;
    if ( wil::details::g_featureStateManager )
    {
      AcquireSRWLockExclusive(&stru_1800440F8);
      if ( qword_180044168 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_180044168 = 0;
      if ( g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification )
        goto LABEL_10;
      ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
      if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
      {
        ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
        `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
      }
      ProcAddress = GetProcAddress(ModuleHandleW, "RtlRegisterFeatureConfigurationChangeNotification");
      g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification = (__int64)ProcAddress;
      if ( ProcAddress )
LABEL_10:
        v9 = ((__int64 (__fastcall *)(__int64 (__fastcall *)(void *), void *, _QWORD, __int64 *))ProcAddress)(
               _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_,
               &wil::details::g_featureStateManager,
               0,
               &qword_180044168);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&stru_180044120,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_1800440F8);
    }
  }
}

```

## disassembly

```asm
0x180014050  mov     [rsp+arg_0], rbx
0x180014055  mov     [rsp+arg_8], rsi
0x18001405a  push    rdi
0x18001405b  sub     rsp, 30h
0x18001405f  mov     rdi, r8
0x180014062  mov     rsi, rdx
0x180014065  mov     rbx, rcx
0x180014068  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18001406c  jnz     short loc_180014085
0x18001406e  mov     r8, rdx; void (*)(void *)
0x180014071  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180014074  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18001407b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x180014080  jmp     loc_18001414D
0x180014085  mov     qword ptr [rcx], 0
0x18001408c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180014093  jz      loc_18001414D
0x180014099  lea     rcx, stru_1800440F8; SRWLock
0x1800140a0  call    cs:__imp_AcquireSRWLockExclusive
0x1800140a6  cmp     cs:qword_180044168, 0
0x1800140ae  jnz     short loc_18001412B
0x1800140b0  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x1800140b7  mov     cs:qword_180044168, 0
0x1800140c2  test    rax, rax
0x1800140c5  jnz     short loc_18001410A
0x1800140c7  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800140ce  test    rax, rax
0x1800140d1  jnz     short loc_1800140E7
0x1800140d3  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x1800140da  call    cs:__imp_GetModuleHandleW
0x1800140e0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800140e7  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x1800140ee  mov     rcx, rax; hModule
0x1800140f1  call    cs:__imp_GetProcAddress
0x1800140f7  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x1800140fe  test    rax, rax
0x180014101  jnz     short loc_18001410A
0x180014103  mov     eax, 0C0000139h
0x180014108  jmp     short loc_180014127
0x18001410a  lea     r9, qword_180044168
0x180014111  xor     r8d, r8d
0x180014114  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18001411b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x180014122  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014127  test    eax, eax
0x180014129  jnz     short loc_180014140
0x18001412b  mov     r9, rdi; void *
0x18001412e  lea     rcx, stru_180044120; this
0x180014135  mov     r8, rsi; void (*)(void *)
0x180014138  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18001413b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180014140  lea     rcx, stru_1800440F8; SRWLock
0x180014147  call    cs:__imp_ReleaseSRWLockExclusive
0x18001414d  mov     rbx, [rsp+38h+arg_0]
0x180014152  mov     rsi, [rsp+38h+arg_8]
0x180014157  add     rsp, 30h
0x18001415b  pop     rdi
0x18001415c  retn
```
