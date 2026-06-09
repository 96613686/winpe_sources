# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180006050`
- end: `0x180006400`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `944`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, service_task`

## callees

- `0x180004224`
- `0x18000564c`
- `0x1800057e8`
- `0x180005b00`
- `0x180005f14`
- `0x180006050`
- `0x180007510`
- `0x180007544`
- `0x1800093ca`
- `0x18000941c`
- `0x18000a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006164`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006192`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006164`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006192`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800062c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800062c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800062df`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800062df`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000611b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000634c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800063d3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000611b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000634c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800063d3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000639a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800063ec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000639a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800063ec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000622b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000623b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000622b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000623b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800061cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800061fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800061cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800061fc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000620f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006262`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000620f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006262`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006223`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006223`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000621a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000621a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800061e7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800061e7`

## string_xrefs

- `0x1800062c1`: `ntdll.dll`

## pseudocode

```c
void __fastcall wil::details::WilApiImpl_RecordFeatureUsage(wil::details *this, int a2, unsigned int a3)
{
  DWORD v4; // esi
  int v6; // edx
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // rcx
  _DWORD *v10; // r9
  size_t v11; // r8
  struct _TP_TIMER *v12; // rcx
  DWORD LastError; // r14d
  struct _TP_TIMER *ThreadpoolTimer; // r15
  struct _TP_TIMER *v15; // rsi
  DWORD v16; // ebx
  RTL_SRWLOCK *v17; // rcx
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  PSRWLOCK v20; // rdi
  int v21; // eax
  char Ptr; // bl
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-18h] BYREF

  v4 = (unsigned int)this;
  v6 = a2 & 0x7FFFFFFF;
  v7 = v6;
  if ( !(_DWORD)this && !a3 && !v6 )
  {
    if ( !wil::details::g_processShutdownInProgress
      && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress())
      && wil::details::FeatureStateManager::EnsureStateData((RTL_SRWLOCK *)&wil::details::g_featureStateManager) )
    {
      wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_18000F018[25], qword_18000F018);
      wil::details_abi::FeatureStateData::RecordUsage(qword_18000F018);
    }
    return;
  }
  if ( (v6 & 0x40000000) != 0 )
  {
    if ( !wil::details::g_featureStateManager
      || wil::details::g_processShutdownInProgress
      || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
    {
      return;
    }
    AcquireSRWLockExclusive(&SRWLock);
    pftDueTime.dwLowDateTime = v4;
    pftDueTime.dwHighDateTime = (unsigned __int16)v7;
    if ( !wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)(&xmmword_18000F0E0 + 1), 0xCu) )
      goto LABEL_22;
    v10 = xmmword_18000F0F0;
    v11 = ((_BYTE *)*(&xmmword_18000F0F0 + 1) - (_BYTE *)xmmword_18000F0F0)
        & -(__int64)(xmmword_18000F0F0 < *(&xmmword_18000F0F0 + 1));
    if ( xmmword_18000F0F0 )
    {
      if ( v11 >= 0xC )
      {
        *(struct _FILETIME *)xmmword_18000F0F0 = pftDueTime;
        v10[2] = a3;
LABEL_21:
        xmmword_18000F0F0 = (char *)xmmword_18000F0F0 + 12;
LABEL_22:
        if ( !byte_18000F040 )
        {
          v12 = pti;
          if ( pti )
            goto LABEL_27;
          LastError = GetLastError();
          ThreadpoolTimer = CreateThreadpoolTimer(
                              (PTP_TIMER_CALLBACK)_lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                              &wil::details::g_featureStateManager,
                              0);
          v15 = pti;
          if ( pti )
          {
            v16 = GetLastError();
            SetThreadpoolTimer(v15, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(v15, 1);
            CloseThreadpoolTimer(v15);
            SetLastError(v16);
          }
          pti = ThreadpoolTimer;
          SetLastError(LastError);
          v12 = pti;
          if ( pti )
          {
LABEL_27:
            pftDueTime = (struct _FILETIME)-50000000LL;
            SetThreadpoolTimer(v12, &pftDueTime, 0, 0x4E2u);
            byte_18000F040 = 1;
          }
        }
        v17 = &SRWLock;
        goto LABEL_57;
      }
      memset_0(xmmword_18000F0F0, 0, v11);
      *(_DWORD *)((__int64 (*)(void))_o__errno)() = 34;
    }
    else
    {
      *(_DWORD *)_o__errno(v9, v8, v11) = 22;
    }
    invalid_parameter_noinfo();
    goto LABEL_21;
  }
  if ( !a3 && v6 != 254 )
  {
    pftDueTime.dwLowDateTime = (unsigned int)this;
    pftDueTime.dwHighDateTime = (unsigned __int16)v6;
    if ( a2 < 0 )
      HIWORD(pftDueTime.dwHighDateTime) |= 1u;
    ProcAddress = (FARPROC)g_wil_details_pfnRtlNotifyFeatureUsage;
    if ( g_wil_details_pfnRtlNotifyFeatureUsage )
      goto LABEL_37;
    ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
    if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
    {
      ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
      `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
    }
    ProcAddress = GetProcAddress(ModuleHandleW, "RtlNotifyFeatureUsage");
    g_wil_details_pfnRtlNotifyFeatureUsage = (__int64)ProcAddress;
    if ( ProcAddress )
LABEL_37:
      ((void (__fastcall *)(struct _FILETIME *))ProcAddress)(&pftDueTime);
    return;
  }
  if ( !wil::details::g_featureStateManager
    || !wil::details::FeatureStateManager::EnsureStateData((RTL_SRWLOCK *)&wil::details::g_featureStateManager) )
  {
    return;
  }
  v20 = qword_18000F018;
  if ( v7 == 254 )
  {
    wil::details_abi::FeatureStateData::RecordUsage(qword_18000F018);
LABEL_53:
    if ( wil::details::g_processShutdownInProgress
      || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
    {
      return;
    }
    AcquireSRWLockExclusive(&stru_18000F020);
    wil::details::FeatureStateManager::EnsureTimerUnderLock((struct _TP_TIMER **)&wil::details::g_featureStateManager);
    v17 = &stru_18000F020;
LABEL_57:
    ReleaseSRWLockExclusive(v17);
    return;
  }
  if ( v7 <= 0xC7 || v7 - 256 <= 0xFF )
  {
    AcquireSRWLockExclusive(qword_18000F018);
    if ( v7 <= 7 && (v21 = 204, _bittest(&v21, v7)) || v7 - 256 <= 0x7F )
    {
      wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,0>::RecordUsage(
        (wil::details_abi::RawUsageIndex *)&v20[1],
        v7,
        v4);
      Ptr = (char)v20[8].Ptr;
    }
    else
    {
      Ptr = wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,2>::RecordUsage(
              (wil::details_abi::RawUsageIndex *)&v20[9],
              v7,
              v4,
              a3);
    }
    if ( v20 )
      ReleaseSRWLockExclusive(v20);
    if ( Ptr )
      goto LABEL_53;
  }
}

```

## disassembly

```asm
0x180006050  push    rbp
0x180006052  push    rbx
0x180006053  push    rsi
0x180006054  push    rdi
0x180006055  push    r14
0x180006057  push    r15
0x180006059  mov     rbp, rsp
0x18000605c  sub     rsp, 38h
0x180006060  mov     r14d, r8d
0x180006063  mov     esi, ecx
0x180006065  mov     eax, edx
0x180006067  btr     edx, 1Fh
0x18000606b  mov     ebx, edx
0x18000606d  test    ecx, ecx
0x18000606f  jnz     short loc_1800060D7
0x180006071  test    r8d, r8d
0x180006074  jnz     short loc_1800060D7
0x180006076  test    edx, edx
0x180006078  jnz     short loc_1800060D7
0x18000607a  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, dl; bool wil::details::g_processShutdownInProgress
0x180006080  jnz     loc_1800063F3
0x180006086  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000608d  test    rax, rax
0x180006090  jz      short loc_18000609F
0x180006092  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006097  test    al, al
0x180006099  jnz     loc_1800063F3
0x18000609f  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x1800060a6  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1800060ab  test    al, al
0x1800060ad  jz      loc_1800063F3
0x1800060b3  mov     rdx, cs:qword_18000F018; SRWLock
0x1800060ba  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1800060c1  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x1800060c6  mov     rcx, cs:qword_18000F018; SRWLock
0x1800060cd  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1800060d2  jmp     loc_1800063F3
0x1800060d7  bt      ebx, 1Eh
0x1800060db  jnb     loc_18000627B
0x1800060e1  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1800060e8  jz      loc_1800063F3
0x1800060ee  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800060f5  jnz     loc_1800063F3
0x1800060fb  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180006102  test    rax, rax
0x180006105  jz      short loc_180006114
0x180006107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000610c  test    al, al
0x18000610e  jnz     loc_1800063F3
0x180006114  lea     rcx, SRWLock; SRWLock
0x18000611b  call    cs:__imp_AcquireSRWLockExclusive
0x180006121  xor     eax, eax
0x180006123  mov     word ptr [rbp+pftDueTime.dwHighDateTime+2], ax
0x180006127  mov     [rbp+pftDueTime.dwLowDateTime], esi
0x18000612a  mov     word ptr [rbp+pftDueTime.dwHighDateTime], bx
0x18000612e  lea     edx, [rax+0Ch]; unsigned __int64
0x180006131  lea     rcx, xmmword_18000F0E0+8; this
0x180006138  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000613d  test    al, al
0x18000613f  jz      short loc_1800061AB
0x180006141  mov     r9, qword ptr cs:xmmword_18000F0F0
0x180006148  mov     rax, qword ptr cs:xmmword_18000F0F0+8
0x18000614f  sub     rax, r9
0x180006152  cmp     r9, qword ptr cs:xmmword_18000F0F0+8
0x180006159  sbb     r8, r8
0x18000615c  and     r8, rax; Size
0x18000615f  test    r9, r9
0x180006162  jnz     short loc_180006172
0x180006164  call    cs:__imp__o__errno
0x18000616a  mov     dword ptr [rax], 16h
0x180006170  jmp     short loc_18000619E
0x180006172  cmp     r8, 0Ch
0x180006176  jb      short loc_180006188
0x180006178  movsd   xmm0, qword ptr [rbp+pftDueTime.dwLowDateTime]
0x18000617d  movsd   qword ptr [r9], xmm0
0x180006182  mov     [r9+8], r14d
0x180006186  jmp     short loc_1800061A3
0x180006188  xor     edx, edx; Val
0x18000618a  mov     rcx, r9; void *
0x18000618d  call    memset_0
0x180006192  call    cs:__imp__o__errno
0x180006198  mov     dword ptr [rax], 22h ; '"'
0x18000619e  call    _invalid_parameter_noinfo
0x1800061a3  add     qword ptr cs:xmmword_18000F0F0, 0Ch
0x1800061ab  cmp     cs:byte_18000F040, 0
0x1800061b2  jnz     loc_18000626F
0x1800061b8  mov     edi, 1
0x1800061bd  mov     rcx, cs:pti
0x1800061c4  test    rcx, rcx
0x1800061c7  jnz     loc_18000624D
0x1800061cd  call    cs:__imp_GetLastError
0x1800061d3  mov     r14d, eax
0x1800061d6  xor     r8d, r8d; pcbe
0x1800061d9  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x1800061e0  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800061e7  call    cs:__imp_CreateThreadpoolTimer
0x1800061ed  mov     r15, rax
0x1800061f0  mov     rsi, cs:pti
0x1800061f7  test    rsi, rsi
0x1800061fa  jz      short loc_180006231
0x1800061fc  call    cs:__imp_GetLastError
0x180006202  mov     ebx, eax
0x180006204  xor     r9d, r9d; msWindowLength
0x180006207  xor     r8d, r8d; msPeriod
0x18000620a  xor     edx, edx; pftDueTime
0x18000620c  mov     rcx, rsi; pti
0x18000620f  call    cs:__imp_SetThreadpoolTimer
0x180006215  mov     edx, edi; fCancelPendingCallbacks
0x180006217  mov     rcx, rsi; pti
0x18000621a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180006220  mov     rcx, rsi; pti
0x180006223  call    cs:__imp_CloseThreadpoolTimer
0x180006229  mov     ecx, ebx; dwErrCode
0x18000622b  call    cs:__imp_SetLastError
0x180006231  mov     cs:pti, r15
0x180006238  mov     ecx, r14d; dwErrCode
0x18000623b  call    cs:__imp_SetLastError
0x180006241  mov     rcx, cs:pti; pti
0x180006248  test    rcx, rcx
0x18000624b  jz      short loc_18000626F
0x18000624d  mov     qword ptr [rbp+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180006255  mov     r9d, 4E2h; msWindowLength
0x18000625b  xor     r8d, r8d; msPeriod
0x18000625e  lea     rdx, [rbp+pftDueTime]; pftDueTime
0x180006262  call    cs:__imp_SetThreadpoolTimer
0x180006268  mov     cs:byte_18000F040, dil
0x18000626f  lea     rcx, SRWLock
0x180006276  jmp     loc_1800063EC
0x18000627b  mov     r15d, 0FEh
0x180006281  test    r14d, r14d
0x180006284  jnz     short loc_180006303
0x180006286  cmp     ebx, r15d
0x180006289  jz      short loc_180006303
0x18000628b  mov     qword ptr [rbp+pftDueTime.dwLowDateTime], 0
0x180006293  mov     [rbp+pftDueTime.dwLowDateTime], esi
0x180006296  mov     word ptr [rbp+pftDueTime.dwHighDateTime], bx
0x18000629a  bt      rax, 1Fh
0x18000629f  jnb     short loc_1800062A9
0x1800062a1  lea     edi, [r14+1]
0x1800062a5  or      word ptr [rbp+pftDueTime.dwHighDateTime+2], di
0x1800062a9  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x1800062b0  test    rax, rax
0x1800062b3  jnz     short loc_1800062F5
0x1800062b5  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800062bc  test    rax, rax
0x1800062bf  jnz     short loc_1800062D5
0x1800062c1  lea     rcx, ModuleName; "ntdll.dll"
0x1800062c8  call    cs:__imp_GetModuleHandleW
0x1800062ce  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800062d5  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x1800062dc  mov     rcx, rax; hModule
0x1800062df  call    cs:__imp_GetProcAddress
0x1800062e5  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x1800062ec  test    rax, rax
0x1800062ef  jz      loc_1800063F3
0x1800062f5  lea     rcx, [rbp+pftDueTime]
0x1800062f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062fe  jmp     loc_1800063F3
0x180006303  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000630a  jz      loc_1800063F3
0x180006310  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180006317  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000631c  test    al, al
0x18000631e  jz      loc_1800063F3
0x180006324  mov     rdi, cs:qword_18000F018
0x18000632b  cmp     ebx, r15d
0x18000632e  jz      short loc_1800063A6
0x180006330  cmp     ebx, 0C7h
0x180006336  jbe     short loc_180006349
0x180006338  lea     eax, [rbx-100h]
0x18000633e  cmp     eax, 0FFh
0x180006343  ja      loc_1800063F3
0x180006349  mov     rcx, rdi; SRWLock
0x18000634c  call    cs:__imp_AcquireSRWLockExclusive
0x180006352  cmp     ebx, 7
0x180006355  ja      short loc_180006361
0x180006357  mov     eax, 0CCh
0x18000635c  bt      eax, ebx
0x18000635f  jb      short loc_180006381
0x180006361  lea     eax, [rbx-100h]
0x180006367  cmp     eax, 7Fh
0x18000636a  jbe     short loc_180006381
0x18000636c  lea     rcx, [rdi+48h]
0x180006370  mov     r9d, r14d
0x180006373  mov     r8d, esi
0x180006376  mov     edx, ebx
0x180006378  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000637d  mov     bl, al
0x18000637f  jmp     short loc_180006392
0x180006381  mov     r8d, esi
0x180006384  mov     edx, ebx
0x180006386  lea     rcx, [rdi+8]
0x18000638a  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000638f  mov     bl, [rdi+40h]
0x180006392  test    rdi, rdi
0x180006395  jz      short loc_1800063A0
0x180006397  mov     rcx, rdi; SRWLock
0x18000639a  call    cs:__imp_ReleaseSRWLockExclusive
0x1800063a0  test    bl, bl
0x1800063a2  jz      short loc_1800063F3
0x1800063a4  jmp     short loc_1800063AE
0x1800063a6  mov     rcx, rdi; SRWLock
0x1800063a9  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1800063ae  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800063b5  jnz     short loc_1800063F3
0x1800063b7  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800063be  test    rax, rax
0x1800063c1  jz      short loc_1800063CC
0x1800063c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063c8  test    al, al
0x1800063ca  jnz     short loc_1800063F3
0x1800063cc  lea     rcx, stru_18000F020; SRWLock
0x1800063d3  call    cs:__imp_AcquireSRWLockExclusive
0x1800063d9  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x1800063e0  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x1800063e5  lea     rcx, stru_18000F020; SRWLock
0x1800063ec  call    cs:__imp_ReleaseSRWLockExclusive
0x1800063f2  nop
0x1800063f3  add     rsp, 38h
0x1800063f7  pop     r15
0x1800063f9  pop     r14
0x1800063fb  pop     rdi
0x1800063fc  pop     rsi
0x1800063fd  pop     rbx
0x1800063fe  pop     rbp
0x1800063ff  retn
```
