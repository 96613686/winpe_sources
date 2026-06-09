# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180015610`
- end: `0x18001571d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180015150`
- `0x18001524c`
- `0x180015610`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001569a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001569a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800156b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800156b1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180015707`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180015707`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015660`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015660`

## string_xrefs

- `0x180015693`: `ntdll.dll`
- `0x1800156a7`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_180065350);
      if ( qword_1800653C0 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_1800653C0 = 0;
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
               &qword_1800653C0);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_180065350);
    }
  }
}

```

## disassembly

```asm
0x180015610  mov     [rsp+arg_0], rbx
0x180015615  mov     [rsp+arg_8], rsi
0x18001561a  push    rdi
0x18001561b  sub     rsp, 30h
0x18001561f  mov     rdi, r8
0x180015622  mov     rsi, rdx
0x180015625  mov     rbx, rcx
0x180015628  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18001562c  jnz     short loc_180015645
0x18001562e  mov     r8, rdx; void (*)(void *)
0x180015631  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180015634  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18001563b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x180015640  jmp     loc_18001570D
0x180015645  mov     qword ptr [rcx], 0
0x18001564c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180015653  jz      loc_18001570D
0x180015659  lea     rcx, stru_180065350; SRWLock
0x180015660  call    cs:__imp_AcquireSRWLockExclusive
0x180015666  cmp     cs:qword_1800653C0, 0
0x18001566e  jnz     short loc_1800156EB
0x180015670  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180015677  mov     cs:qword_1800653C0, 0
0x180015682  test    rax, rax
0x180015685  jnz     short loc_1800156CA
0x180015687  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001568e  test    rax, rax
0x180015691  jnz     short loc_1800156A7
0x180015693  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18001569a  call    cs:__imp_GetModuleHandleW
0x1800156a0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800156a7  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x1800156ae  mov     rcx, rax; hModule
0x1800156b1  call    cs:__imp_GetProcAddress
0x1800156b7  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x1800156be  test    rax, rax
0x1800156c1  jnz     short loc_1800156CA
0x1800156c3  mov     eax, 0C0000139h
0x1800156c8  jmp     short loc_1800156E7
0x1800156ca  lea     r9, qword_1800653C0
0x1800156d1  xor     r8d, r8d
0x1800156d4  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1800156db  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x1800156e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800156e7  test    eax, eax
0x1800156e9  jnz     short loc_180015700
0x1800156eb  mov     r9, rdi; void *
0x1800156ee  lea     rcx, CriticalSection; this
0x1800156f5  mov     r8, rsi; void (*)(void *)
0x1800156f8  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1800156fb  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180015700  lea     rcx, stru_180065350; SRWLock
0x180015707  call    cs:__imp_ReleaseSRWLockExclusive
0x18001570d  mov     rbx, [rsp+38h+arg_0]
0x180015712  mov     rsi, [rsp+38h+arg_8]
0x180015717  add     rsp, 30h
0x18001571b  pop     rdi
0x18001571c  retn
```
