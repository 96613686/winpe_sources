# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180006410`
- end: `0x1800065e3`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `467`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x1800054f0`
- `0x180005b00`
- `0x180006410`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006560`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006560`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006577`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006577`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006487`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800064b1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006526`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006487`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800064b1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006526`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800064db`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800065cd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800064db`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800065cd`

## string_xrefs

- `0x180006559`: `ntdll.dll`
- `0x18000656d`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c
void __fastcall wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this,
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **a2,
        void (*a3)(void *),
        void *a4)
{
  PSRWLOCK v7; // rdi
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v10; // eax

  *this = 0;
  if ( a3 != (void (*)(void *))-1LL )
  {
    if ( !wil::details::g_featureStateManager )
      return;
    AcquireSRWLockExclusive(&stru_18000F020);
    if ( qword_18000F090 )
      goto LABEL_21;
    ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
    qword_18000F090 = 0;
    if ( g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification )
      goto LABEL_19;
    ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
    if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
    {
      ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
      `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
    }
    ProcAddress = GetProcAddress(ModuleHandleW, "RtlRegisterFeatureConfigurationChangeNotification");
    g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification = (__int64)ProcAddress;
    if ( ProcAddress )
LABEL_19:
      v10 = ((__int64 (__fastcall *)(__int64 (__fastcall *)(void *), void *, _QWORD, __int64 *))ProcAddress)(
              _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_,
              &wil::details::g_featureStateManager,
              0,
              &qword_18000F090);
    else
      v10 = -1073741511;
    if ( !v10 )
LABEL_21:
      wil::details_abi::SubscriptionList::SubscribeUnderLock(
        (wil::details_abi::SubscriptionList *)&CriticalSection,
        this,
        (void (*)(void *))a2,
        a3);
    goto LABEL_22;
  }
  if ( wil::details::g_featureStateManager
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress
     || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress(this, a2, -1, a4))
    && wil::details::FeatureStateManager::EnsureStateData((RTL_SRWLOCK *)&wil::details::g_featureStateManager) )
  {
    AcquireSRWLockExclusive(&stru_18000F020);
    if ( !xmmword_18000F0E0 )
    {
      v7 = qword_18000F018;
      if ( qword_18000F018 )
      {
        xmmword_18000F0E0 = 0;
        AcquireSRWLockExclusive(qword_18000F018);
        wil::details_abi::SubscriptionList::SubscribeUnderLock(
          (wil::details_abi::SubscriptionList *)&v7[25],
          &xmmword_18000F0E0,
          (void (*)(void *))_lambda_152aa9d2a3a0648fa2fa7fcef514b376_::_lambda_invoker_cdecl_,
          &wil::details::g_featureStateManager);
        ReleaseSRWLockExclusive(v7);
      }
    }
    wil::details_abi::SubscriptionList::SubscribeUnderLock(
      (wil::details_abi::SubscriptionList *)&stru_18000F098,
      this,
      (void (*)(void *))a2,
      0);
    if ( *this )
      *this = (struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)((unsigned __int64)*this | 0x80000000);
LABEL_22:
    ReleaseSRWLockExclusive(&stru_18000F020);
  }
}

```

## disassembly

```asm
0x180006410  mov     [rsp+arg_0], rbx
0x180006415  mov     [rsp+arg_8], rsi
0x18000641a  push    rdi
0x18000641b  sub     rsp, 30h
0x18000641f  mov     qword ptr [rcx], 0
0x180006426  mov     rdi, r8
0x180006429  mov     rsi, rdx
0x18000642c  mov     rbx, rcx
0x18000642f  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180006433  jnz     loc_180006512
0x180006439  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180006440  jz      loc_1800065D3
0x180006446  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000644d  jnz     loc_1800065D3
0x180006453  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000645a  test    rax, rax
0x18000645d  jz      short loc_18000646C
0x18000645f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006464  test    al, al
0x180006466  jnz     loc_1800065D3
0x18000646c  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180006473  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180006478  test    al, al
0x18000647a  jz      loc_1800065D3
0x180006480  lea     rcx, stru_18000F020; SRWLock
0x180006487  call    cs:__imp_AcquireSRWLockExclusive
0x18000648d  cmp     qword ptr cs:xmmword_18000F0E0, 0
0x180006495  jnz     short loc_1800064E1
0x180006497  mov     rdi, cs:qword_18000F018
0x18000649e  test    rdi, rdi
0x1800064a1  jz      short loc_1800064E1
0x1800064a3  mov     rcx, rdi; SRWLock
0x1800064a6  mov     qword ptr cs:xmmword_18000F0E0, 0
0x1800064b1  call    cs:__imp_AcquireSRWLockExclusive
0x1800064b7  lea     rcx, [rdi+0C8h]; this
0x1800064be  lea     r9, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; void *
0x1800064c5  lea     r8, ?_lambda_invoker_cdecl_@_lambda_152aa9d2a3a0648fa2fa7fcef514b376_@@CA@PEAX@Z; void (*)(void *)
0x1800064cc  lea     rdx, xmmword_18000F0E0; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1800064d3  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x1800064d8  mov     rcx, rdi; SRWLock
0x1800064db  call    cs:__imp_ReleaseSRWLockExclusive
0x1800064e1  xor     r9d, r9d; void *
0x1800064e4  lea     rcx, stru_18000F098; this
0x1800064eb  mov     r8, rsi; void (*)(void *)
0x1800064ee  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1800064f1  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x1800064f6  mov     rax, [rbx]
0x1800064f9  test    rax, rax
0x1800064fc  jz      loc_1800065C6
0x180006502  mov     ecx, 80000000h
0x180006507  or      rax, rcx
0x18000650a  mov     [rbx], rax
0x18000650d  jmp     loc_1800065C6
0x180006512  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180006519  jz      loc_1800065D3
0x18000651f  lea     rcx, stru_18000F020; SRWLock
0x180006526  call    cs:__imp_AcquireSRWLockExclusive
0x18000652c  cmp     cs:qword_18000F090, 0
0x180006534  jnz     short loc_1800065B1
0x180006536  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000653d  mov     cs:qword_18000F090, 0
0x180006548  test    rax, rax
0x18000654b  jnz     short loc_180006590
0x18000654d  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006554  test    rax, rax
0x180006557  jnz     short loc_18000656D
0x180006559  lea     rcx, ModuleName; "ntdll.dll"
0x180006560  call    cs:__imp_GetModuleHandleW
0x180006566  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000656d  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180006574  mov     rcx, rax; hModule
0x180006577  call    cs:__imp_GetProcAddress
0x18000657d  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x180006584  test    rax, rax
0x180006587  jnz     short loc_180006590
0x180006589  mov     eax, 0C0000139h
0x18000658e  jmp     short loc_1800065AD
0x180006590  lea     r9, qword_18000F090
0x180006597  xor     r8d, r8d
0x18000659a  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1800065a1  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x1800065a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065ad  test    eax, eax
0x1800065af  jnz     short loc_1800065C6
0x1800065b1  mov     r9, rdi; void *
0x1800065b4  lea     rcx, CriticalSection; this
0x1800065bb  mov     r8, rsi; void (*)(void *)
0x1800065be  mov     rdx, rbx; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1800065c1  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x1800065c6  lea     rcx, stru_18000F020; SRWLock
0x1800065cd  call    cs:__imp_ReleaseSRWLockExclusive
0x1800065d3  mov     rbx, [rsp+38h+arg_0]
0x1800065d8  mov     rsi, [rsp+38h+arg_8]
0x1800065dd  add     rsp, 30h
0x1800065e1  pop     rdi
0x1800065e2  retn
```
