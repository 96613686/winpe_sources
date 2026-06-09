# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180016220`
- end: `0x18001632d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180015afc`
- `0x180015bf8`
- `0x180016220`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800162aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800162aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800162c1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800162c1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016270`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016270`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016317`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016317`

## string_xrefs

- `0x1800162a3`: `ntdll.dll`
- `0x1800162b7`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_180023070);
      if ( qword_1800230E0 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_1800230E0 = 0;
      if ( g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification )
        goto LABEL_10;
      ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
               &qword_1800230E0);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_180023070);
    }
  }
}

```

## disassembly

```asm
0x180016220  mov     [rsp+arg_0], rbx
0x180016225  mov     [rsp+arg_8], rsi
0x18001622a  push    rdi
0x18001622b  sub     rsp, 30h
0x18001622f  mov     rdi, r8
0x180016232  mov     rsi, rdx
0x180016235  mov     rbx, rcx
0x180016238  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18001623c  jnz     short loc_180016255
0x18001623e  mov     r8, rdx; void (*)(void *)
0x180016241  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180016244  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18001624b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x180016250  jmp     loc_18001631D
0x180016255  mov     qword ptr [rcx], 0
0x18001625c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180016263  jz      loc_18001631D
0x180016269  lea     rcx, stru_180023070; SRWLock
0x180016270  call    cs:__imp_AcquireSRWLockExclusive
0x180016276  cmp     cs:qword_1800230E0, 0
0x18001627e  jnz     short loc_1800162FB
0x180016280  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180016287  mov     cs:qword_1800230E0, 0
0x180016292  test    rax, rax
0x180016295  jnz     short loc_1800162DA
0x180016297  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001629e  test    rax, rax
0x1800162a1  jnz     short loc_1800162B7
0x1800162a3  lea     rcx, ModuleName; "ntdll.dll"
0x1800162aa  call    cs:__imp_GetModuleHandleW
0x1800162b0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800162b7  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x1800162be  mov     rcx, rax; hModule
0x1800162c1  call    cs:__imp_GetProcAddress
0x1800162c7  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x1800162ce  test    rax, rax
0x1800162d1  jnz     short loc_1800162DA
0x1800162d3  mov     eax, 0C0000139h
0x1800162d8  jmp     short loc_1800162F7
0x1800162da  lea     r9, qword_1800230E0
0x1800162e1  xor     r8d, r8d
0x1800162e4  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1800162eb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x1800162f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800162f7  test    eax, eax
0x1800162f9  jnz     short loc_180016310
0x1800162fb  mov     r9, rdi; void *
0x1800162fe  lea     rcx, CriticalSection; this
0x180016305  mov     r8, rsi; void (*)(void *)
0x180016308  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18001630b  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180016310  lea     rcx, stru_180023070; SRWLock
0x180016317  call    cs:__imp_ReleaseSRWLockExclusive
0x18001631d  mov     rbx, [rsp+38h+arg_0]
0x180016322  mov     rsi, [rsp+38h+arg_8]
0x180016327  add     rsp, 30h
0x18001632b  pop     rdi
0x18001632c  retn
```
