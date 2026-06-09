# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180019300`
- end: `0x18001940d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x180018bf8`
- `0x180018cf4`
- `0x180019300`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800193f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800193f7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019350`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019350`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800193a1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800193a1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001938a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001938a`

## string_xrefs

- `0x180019383`: `ntdll.dll`
- `0x180019397`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      if ( qword_180037470 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_180037470 = 0;
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
               &qword_180037470);
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
0x180019300  mov     [rsp+arg_0], rbx
0x180019305  mov     [rsp+arg_8], rsi
0x18001930a  push    rdi
0x18001930b  sub     rsp, 30h
0x18001930f  mov     rdi, r8
0x180019312  mov     rsi, rdx
0x180019315  mov     rbx, rcx
0x180019318  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18001931c  jnz     short loc_180019335
0x18001931e  mov     r8, rdx; void (*)(void *)
0x180019321  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180019324  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18001932b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x180019330  jmp     loc_1800193FD
0x180019335  mov     qword ptr [rcx], 0
0x18001933c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180019343  jz      loc_1800193FD
0x180019349  lea     rcx, SRWLock; SRWLock
0x180019350  call    cs:__imp_AcquireSRWLockExclusive
0x180019356  cmp     cs:qword_180037470, 0
0x18001935e  jnz     short loc_1800193DB
0x180019360  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180019367  mov     cs:qword_180037470, 0
0x180019372  test    rax, rax
0x180019375  jnz     short loc_1800193BA
0x180019377  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001937e  test    rax, rax
0x180019381  jnz     short loc_180019397
0x180019383  lea     rcx, ModuleName; "ntdll.dll"
0x18001938a  call    cs:__imp_GetModuleHandleW
0x180019390  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180019397  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18001939e  mov     rcx, rax; hModule
0x1800193a1  call    cs:__imp_GetProcAddress
0x1800193a7  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x1800193ae  test    rax, rax
0x1800193b1  jnz     short loc_1800193BA
0x1800193b3  mov     eax, 0C0000139h
0x1800193b8  jmp     short loc_1800193D7
0x1800193ba  lea     r9, qword_180037470
0x1800193c1  xor     r8d, r8d
0x1800193c4  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1800193cb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x1800193d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800193d7  test    eax, eax
0x1800193d9  jnz     short loc_1800193F0
0x1800193db  mov     r9, rdi; void *
0x1800193de  lea     rcx, CriticalSection; this
0x1800193e5  mov     r8, rsi; void (*)(void *)
0x1800193e8  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1800193eb  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x1800193f0  lea     rcx, SRWLock; SRWLock
0x1800193f7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800193fd  mov     rbx, [rsp+38h+arg_0]
0x180019402  mov     rsi, [rsp+38h+arg_8]
0x180019407  add     rsp, 30h
0x18001940b  pop     rdi
0x18001940c  retn
```
