# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180009900`
- end: `0x180009a0d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18000924c`
- `0x180009348`
- `0x180009900`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800099f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800099f7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009950`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009950`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800099a1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800099a1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000998a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000998a`

## string_xrefs

- `0x180009983`: `ntdll.dll`
- `0x180009997`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_1800110C0 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_1800110C0 = 0;
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
        v9 = ((__int64 (__fastcall *)(__int64 (__fastcall *)(void *), char *, _QWORD, __int64 *))ProcAddress)(
               _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_,
               &wil::details::g_featureStateManager,
               0,
               &qword_1800110C0);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&SRWLock);
    }
  }
}

```

## disassembly

```asm
0x180009900  mov     [rsp+arg_0], rbx
0x180009905  mov     [rsp+arg_8], rsi
0x18000990a  push    rdi
0x18000990b  sub     rsp, 30h
0x18000990f  mov     rdi, r8
0x180009912  mov     rsi, rdx
0x180009915  mov     rbx, rcx
0x180009918  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000991c  jnz     short loc_180009935
0x18000991e  mov     r8, rdx; void (*)(void *)
0x180009921  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180009924  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000992b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x180009930  jmp     loc_1800099FD
0x180009935  mov     qword ptr [rcx], 0
0x18000993c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180009943  jz      loc_1800099FD
0x180009949  lea     rcx, SRWLock; SRWLock
0x180009950  call    cs:__imp_AcquireSRWLockExclusive
0x180009956  cmp     cs:qword_1800110C0, 0
0x18000995e  jnz     short loc_1800099DB
0x180009960  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180009967  mov     cs:qword_1800110C0, 0
0x180009972  test    rax, rax
0x180009975  jnz     short loc_1800099BA
0x180009977  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000997e  test    rax, rax
0x180009981  jnz     short loc_180009997
0x180009983  lea     rcx, ModuleName; "ntdll.dll"
0x18000998a  call    cs:__imp_GetModuleHandleW
0x180009990  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009997  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000999e  mov     rcx, rax; hModule
0x1800099a1  call    cs:__imp_GetProcAddress
0x1800099a7  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x1800099ae  test    rax, rax
0x1800099b1  jnz     short loc_1800099BA
0x1800099b3  mov     eax, 0C0000139h
0x1800099b8  jmp     short loc_1800099D7
0x1800099ba  lea     r9, qword_1800110C0
0x1800099c1  xor     r8d, r8d
0x1800099c4  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1800099cb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x1800099d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099d7  test    eax, eax
0x1800099d9  jnz     short loc_1800099F0
0x1800099db  mov     r9, rdi; void *
0x1800099de  lea     rcx, CriticalSection; this
0x1800099e5  mov     r8, rsi; void (*)(void *)
0x1800099e8  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1800099eb  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x1800099f0  lea     rcx, SRWLock; SRWLock
0x1800099f7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800099fd  mov     rbx, [rsp+38h+arg_0]
0x180009a02  mov     rsi, [rsp+38h+arg_8]
0x180009a07  add     rsp, 30h
0x180009a0b  pop     rdi
0x180009a0c  retn
```
