# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x14000b110`
- end: `0x14000b21d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x14000a998`
- `0x14000aa94`
- `0x14000b110`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000b19a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000b19a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b1b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b1b1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000b160`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000b160`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000b207`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000b207`

## string_xrefs

- `0x14000b193`: `ntdll.dll`
- `0x14000b1a7`: `RtlRegisterFeatureConfigurationChangeNotification`

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
      AcquireSRWLockExclusive(&stru_1400190B0);
      if ( qword_140019120 )
        goto LABEL_12;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
      qword_140019120 = 0;
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
               &qword_140019120);
      else
        v9 = -1073741511;
      if ( !v9 )
LABEL_12:
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&CriticalSection,
          this,
          (void (*)(void *))a2,
          a3);
      ReleaseSRWLockExclusive(&stru_1400190B0);
    }
  }
}

```

## disassembly

```asm
0x14000b110  mov     [rsp+arg_0], rbx
0x14000b115  mov     [rsp+arg_8], rsi
0x14000b11a  push    rdi
0x14000b11b  sub     rsp, 30h
0x14000b11f  mov     rdi, r8
0x14000b122  mov     rsi, rdx
0x14000b125  mov     rbx, rcx
0x14000b128  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x14000b12c  jnz     short loc_14000B145
0x14000b12e  mov     r8, rdx; void (*)(void *)
0x14000b131  mov     rdx, rcx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x14000b134  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x14000b13b  call    ?SubscribeToUsageFlush@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z@Z; wil::details::FeatureStateManager::SubscribeToUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *))
0x14000b140  jmp     loc_14000B20D
0x14000b145  mov     qword ptr [rcx], 0
0x14000b14c  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x14000b153  jz      loc_14000B20D
0x14000b159  lea     rcx, stru_1400190B0; SRWLock
0x14000b160  call    cs:__imp_AcquireSRWLockExclusive
0x14000b166  cmp     cs:qword_140019120, 0
0x14000b16e  jnz     short loc_14000B1EB
0x14000b170  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x14000b177  mov     cs:qword_140019120, 0
0x14000b182  test    rax, rax
0x14000b185  jnz     short loc_14000B1CA
0x14000b187  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000b18e  test    rax, rax
0x14000b191  jnz     short loc_14000B1A7
0x14000b193  lea     rcx, ModuleName; "ntdll.dll"
0x14000b19a  call    cs:__imp_GetModuleHandleW
0x14000b1a0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000b1a7  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x14000b1ae  mov     rcx, rax; hModule
0x14000b1b1  call    cs:__imp_GetProcAddress
0x14000b1b7  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x14000b1be  test    rax, rax
0x14000b1c1  jnz     short loc_14000B1CA
0x14000b1c3  mov     eax, 0C0000139h
0x14000b1c8  jmp     short loc_14000B1E7
0x14000b1ca  lea     r9, qword_140019120
0x14000b1d1  xor     r8d, r8d
0x14000b1d4  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x14000b1db  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x14000b1e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b1e7  test    eax, eax
0x14000b1e9  jnz     short loc_14000B200
0x14000b1eb  mov     r9, rdi; void *
0x14000b1ee  lea     rcx, CriticalSection; this
0x14000b1f5  mov     r8, rsi; void (*)(void *)
0x14000b1f8  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x14000b1fb  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x14000b200  lea     rcx, stru_1400190B0; SRWLock
0x14000b207  call    cs:__imp_ReleaseSRWLockExclusive
0x14000b20d  mov     rbx, [rsp+38h+arg_0]
0x14000b212  mov     rsi, [rsp+38h+arg_8]
0x14000b217  add     rsp, 30h
0x14000b21b  pop     rdi
0x14000b21c  retn
```
