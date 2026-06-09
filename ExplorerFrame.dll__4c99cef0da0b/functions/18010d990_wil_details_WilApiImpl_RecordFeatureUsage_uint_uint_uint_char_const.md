# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x18010d990`
- end: `0x18010dd49`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `953`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting`

## callees

- `0x180039c98`
- `0x18003b720`
- `0x18009c278`
- `0x18009d314`
- `0x18009df58`
- `0x18009e538`
- `0x18010d990`
- `0x18014066e`
- `0x1801406ec`
- `0x180210010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18010db70`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18010dba2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18010db70`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18010dba2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18010dcfb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18010dcfb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18010dce4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18010dce4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18010da58`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18010da58`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18010dc84`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18010dc84`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18010db17`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18010db17`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18010db25`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18010db25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010dab6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010dbd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010dc06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010dab6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010dbd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010dc06`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18010dada`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18010db4a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18010dc38`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18010dc47`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18010dada`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18010db4a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18010dc38`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18010dc47`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18010dbf1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18010dbf1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18010dc27`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18010dc27`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18010dc30`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18010dc30`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18010dc19`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18010dc70`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18010dc19`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18010dc70`

## string_xrefs

- `0x18010dcdd`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::WilApiImpl_RecordFeatureUsage(wil::details *this, int a2, DWORD a3)
{
  DWORD v4; // ebp
  unsigned int v5; // ebx
  size_t v6; // rdi
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rdx
  struct _FILETIME *v9; // r9
  unsigned __int64 v10; // rbx
  DWORD LastError; // ebp
  unsigned __int64 v12; // r15
  unsigned __int64 v13; // r8
  char *v14; // rax
  char *v15; // rbx
  signed __int64 v16; // r14
  void *v17; // r12
  HANDLE ProcessHeap; // rax
  struct _TP_TIMER *v19; // rcx
  DWORD v20; // esi
  struct _TP_TIMER *ThreadpoolTimer; // rbp
  struct _TP_TIMER *v22; // rdi
  DWORD v23; // ebx
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-48h] BYREF

  v4 = (unsigned int)this;
  v5 = a2 & 0x7FFFFFFF;
  if ( !(_DWORD)this && !a3 && !v5 )
  {
    if ( !wil::details::g_processShutdownInProgress
      && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress())
      && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)&wil::details::g_featureStateManager) )
    {
      wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_1802944F8[25], qword_1802944F8);
      wil::details_abi::FeatureStateData::RecordUsage(qword_1802944F8);
    }
    return;
  }
  if ( (a2 & 0x40000000) != 0 )
  {
    if ( !wil::details::g_featureStateManager
      || wil::details::g_processShutdownInProgress
      || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
    {
      return;
    }
    AcquireSRWLockExclusive(&stru_180294508);
    v6 = 0;
    pftDueTime.dwLowDateTime = v4;
    pftDueTime.dwHighDateTime = (unsigned __int16)v5;
    v7 = qword_1802945D8;
    v8 = qword_1802945D8 - (_QWORD)Source;
    v9 = (struct _FILETIME *)qword_1802945D0;
    if ( (_BYTE *)qword_1802945D0 - (_BYTE *)Source + 12 >= (unsigned __int64)(qword_1802945D8 - (_QWORD)Source) )
    {
      v10 = 12;
      if ( 2 * v8 > 0xC )
        v10 = 2 * v8;
      if ( v8 < v10 )
      {
        LastError = GetLastError();
        v12 = (v10 & 0xFFFFFFFFFFFFFFC0uLL) + 64;
        v14 = (char *)wil::details::ProcessHeapAlloc(0, v12, v13);
        v15 = v14;
        if ( !v14 )
        {
          SetLastError(LastError);
          goto LABEL_32;
        }
        v16 = (_BYTE *)qword_1802945D0 - (_BYTE *)Source;
        memcpy_s_0(v14, v12, Source, (_BYTE *)qword_1802945D0 - (_BYTE *)Source);
        v17 = lpMem;
        lpMem = v15;
        if ( v17 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v17);
        }
        Source = v15;
        qword_1802945D0 = &v15[v16];
        qword_1802945D8 = (__int64)&v15[v12];
        SetLastError(LastError);
        v7 = qword_1802945D8;
        v9 = (struct _FILETIME *)qword_1802945D0;
      }
    }
    if ( (unsigned __int64)v9 < v7 )
      v6 = v7 - (_QWORD)v9;
    if ( v9 )
    {
      if ( v6 >= 0xC )
      {
        *v9 = pftDueTime;
        v9[1].dwLowDateTime = a3;
LABEL_31:
        qword_1802945D0 = (char *)qword_1802945D0 + 12;
LABEL_32:
        if ( !byte_180294520 )
        {
          v19 = pti;
          if ( pti )
            goto LABEL_37;
          v20 = GetLastError();
          ThreadpoolTimer = CreateThreadpoolTimer(
                              _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                              &wil::details::g_featureStateManager,
                              0);
          v22 = pti;
          if ( pti )
          {
            v23 = GetLastError();
            SetThreadpoolTimer(v22, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(v22, 1);
            CloseThreadpoolTimer(v22);
            SetLastError(v23);
          }
          pti = ThreadpoolTimer;
          SetLastError(v20);
          v19 = pti;
          if ( pti )
          {
LABEL_37:
            pftDueTime = (struct _FILETIME)-50000000LL;
            SetThreadpoolTimer(v19, &pftDueTime, 0, 0x4E2u);
            byte_180294520 = 1;
          }
        }
        ReleaseSRWLockExclusive(&stru_180294508);
        return;
      }
      memset_0(v9, 0, v6);
      *(_DWORD *)_o__errno() = 34;
    }
    else
    {
      *(_DWORD *)_o__errno() = 22;
    }
    invalid_parameter_noinfo();
    goto LABEL_31;
  }
  if ( a3 || v5 == 254 )
  {
    wil::details::FeatureStateManager::RecordFeatureUsage(
      &wil::details::g_featureStateManager,
      (unsigned int)this,
      v5,
      a3);
  }
  else
  {
    pftDueTime.dwLowDateTime = (unsigned int)this;
    pftDueTime.dwHighDateTime = (unsigned __int16)a2;
    if ( a2 < 0 )
      HIWORD(pftDueTime.dwHighDateTime) |= 1u;
    ProcAddress = (FARPROC)g_wil_details_pfnRtlNotifyFeatureUsage;
    if ( g_wil_details_pfnRtlNotifyFeatureUsage )
      goto LABEL_48;
    ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
    if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
    {
      ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
      `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
    }
    ProcAddress = GetProcAddress(ModuleHandleW, "RtlNotifyFeatureUsage");
    g_wil_details_pfnRtlNotifyFeatureUsage = (__int64)ProcAddress;
    if ( ProcAddress )
LABEL_48:
      ((void (__fastcall *)(struct _FILETIME *))ProcAddress)(&pftDueTime);
  }
}

```

## disassembly

```asm
0x18010d990  push    rbx
0x18010d992  push    rbp
0x18010d993  push    rsi
0x18010d994  push    rdi
0x18010d995  push    r12
0x18010d997  push    r14
0x18010d999  push    r15
0x18010d99b  sub     rsp, 30h
0x18010d99f  mov     esi, r8d
0x18010d9a2  mov     ebp, ecx
0x18010d9a4  mov     ebx, edx
0x18010d9a6  btr     ebx, 1Fh
0x18010d9aa  test    ecx, ecx
0x18010d9ac  jnz     short loc_18010DA14
0x18010d9ae  test    r8d, r8d
0x18010d9b1  jnz     short loc_18010DA14
0x18010d9b3  test    ebx, ebx
0x18010d9b5  jnz     short loc_18010DA14
0x18010d9b7  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, bl; bool wil::details::g_processShutdownInProgress
0x18010d9bd  jnz     loc_18010DC8B
0x18010d9c3  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18010d9ca  test    rax, rax
0x18010d9cd  jz      short loc_18010D9DC
0x18010d9cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010d9d4  test    al, al
0x18010d9d6  jnz     loc_18010DC8B
0x18010d9dc  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18010d9e3  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18010d9e8  test    al, al
0x18010d9ea  jz      loc_18010DC8B
0x18010d9f0  mov     rdx, cs:qword_1802944F8; SRWLock
0x18010d9f7  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18010d9fe  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18010da03  mov     rcx, cs:qword_1802944F8; SRWLock
0x18010da0a  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18010da0f  jmp     loc_18010DC8B
0x18010da14  bt      ebx, 1Eh
0x18010da18  jnb     loc_18010DC9A
0x18010da1e  cmp     cs:?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18010da25  jz      loc_18010DC8B
0x18010da2b  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18010da32  jnz     loc_18010DC8B
0x18010da38  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18010da3f  test    rax, rax
0x18010da42  jz      short loc_18010DA51
0x18010da44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010da49  test    al, al
0x18010da4b  jnz     loc_18010DC8B
0x18010da51  lea     rcx, stru_180294508; SRWLock
0x18010da58  call    cs:__imp_AcquireSRWLockExclusive
0x18010da5e  xor     edi, edi
0x18010da60  mov     word ptr [rsp+68h+pftDueTime.dwHighDateTime+2], di
0x18010da65  mov     [rsp+68h+pftDueTime.dwLowDateTime], ebp
0x18010da69  mov     word ptr [rsp+68h+pftDueTime.dwHighDateTime], bx
0x18010da6e  mov     r8, cs:qword_1802945D8
0x18010da75  mov     rdx, r8
0x18010da78  sub     rdx, cs:Source
0x18010da7f  mov     r9, cs:qword_1802945D0
0x18010da86  mov     rax, r9
0x18010da89  sub     rax, cs:Source
0x18010da90  add     rax, 0Ch
0x18010da94  cmp     rax, rdx
0x18010da97  jb      loc_18010DB5E
0x18010da9d  lea     rax, [rdx+rdx]
0x18010daa1  mov     ebx, 0Ch
0x18010daa6  cmp     rax, rbx
0x18010daa9  cmova   rbx, rax
0x18010daad  cmp     rdx, rbx
0x18010dab0  jnb     loc_18010DB5E
0x18010dab6  call    cs:__imp_GetLastError
0x18010dabc  mov     ebp, eax
0x18010dabe  and     rbx, 0FFFFFFFFFFFFFFC0h
0x18010dac2  lea     r15, [rbx+40h]
0x18010dac6  mov     rdx, r15; dwBytes
0x18010dac9  xor     ecx, ecx; dwFlags
0x18010dacb  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18010dad0  mov     rbx, rax
0x18010dad3  test    rax, rax
0x18010dad6  jnz     short loc_18010DAE5
0x18010dad8  mov     ecx, ebp; dwErrCode
0x18010dada  call    cs:__imp_SetLastError
0x18010dae0  jmp     loc_18010DBBB
0x18010dae5  mov     r8, cs:Source; Source
0x18010daec  mov     r14, cs:qword_1802945D0
0x18010daf3  sub     r14, r8
0x18010daf6  mov     r9, r14; SourceSize
0x18010daf9  mov     rdx, r15; DestinationSize
0x18010dafc  mov     rcx, rbx; Destination
0x18010daff  call    memcpy_s_0
0x18010db04  mov     r12, cs:lpMem
0x18010db0b  mov     cs:lpMem, rbx
0x18010db12  test    r12, r12
0x18010db15  jz      short loc_18010DB2B
0x18010db17  call    cs:__imp_GetProcessHeap
0x18010db1d  mov     rcx, rax; hHeap
0x18010db20  mov     r8, r12; lpMem
0x18010db23  xor     edx, edx; dwFlags
0x18010db25  call    cs:__imp_HeapFree
0x18010db2b  mov     cs:Source, rbx
0x18010db32  lea     rax, [r14+rbx]
0x18010db36  mov     cs:qword_1802945D0, rax
0x18010db3d  lea     rax, [r15+rbx]
0x18010db41  mov     cs:qword_1802945D8, rax
0x18010db48  mov     ecx, ebp; dwErrCode
0x18010db4a  call    cs:__imp_SetLastError
0x18010db50  mov     r8, cs:qword_1802945D8
0x18010db57  mov     r9, cs:qword_1802945D0
0x18010db5e  mov     rax, r8
0x18010db61  sub     rax, r9
0x18010db64  cmp     r9, r8
0x18010db67  cmovb   rdi, rax
0x18010db6b  test    r9, r9
0x18010db6e  jnz     short loc_18010DB7E
0x18010db70  call    cs:__imp__o__errno
0x18010db76  mov     dword ptr [rax], 16h
0x18010db7c  jmp     short loc_18010DBAE
0x18010db7e  cmp     rdi, 0Ch
0x18010db82  jb      short loc_18010DB95
0x18010db84  movsd   xmm0, qword ptr [rsp+68h+pftDueTime.dwLowDateTime]
0x18010db8a  movsd   qword ptr [r9], xmm0
0x18010db8f  mov     [r9+8], esi
0x18010db93  jmp     short loc_18010DBB3
0x18010db95  mov     r8, rdi; Size
0x18010db98  xor     edx, edx; Val
0x18010db9a  mov     rcx, r9; void *
0x18010db9d  call    memset_0
0x18010dba2  call    cs:__imp__o__errno
0x18010dba8  mov     dword ptr [rax], 22h ; '"'
0x18010dbae  call    _invalid_parameter_noinfo
0x18010dbb3  add     cs:qword_1802945D0, 0Ch
0x18010dbbb  cmp     cs:byte_180294520, 0
0x18010dbc2  jnz     loc_18010DC7D
0x18010dbc8  mov     rcx, cs:pti
0x18010dbcf  test    rcx, rcx
0x18010dbd2  jnz     loc_18010DC59
0x18010dbd8  call    cs:__imp_GetLastError
0x18010dbde  mov     esi, eax
0x18010dbe0  xor     r8d, r8d; pcbe
0x18010dbe3  lea     rdx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18010dbea  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18010dbf1  call    cs:__imp_CreateThreadpoolTimer
0x18010dbf7  mov     rbp, rax
0x18010dbfa  mov     rdi, cs:pti
0x18010dc01  test    rdi, rdi
0x18010dc04  jz      short loc_18010DC3E
0x18010dc06  call    cs:__imp_GetLastError
0x18010dc0c  mov     ebx, eax
0x18010dc0e  xor     r9d, r9d; msWindowLength
0x18010dc11  xor     r8d, r8d; msPeriod
0x18010dc14  xor     edx, edx; pftDueTime
0x18010dc16  mov     rcx, rdi; pti
0x18010dc19  call    cs:__imp_SetThreadpoolTimer
0x18010dc1f  mov     edx, 1; fCancelPendingCallbacks
0x18010dc24  mov     rcx, rdi; pti
0x18010dc27  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18010dc2d  mov     rcx, rdi; pti
0x18010dc30  call    cs:__imp_CloseThreadpoolTimer
0x18010dc36  mov     ecx, ebx; dwErrCode
0x18010dc38  call    cs:__imp_SetLastError
0x18010dc3e  mov     cs:pti, rbp
0x18010dc45  mov     ecx, esi; dwErrCode
0x18010dc47  call    cs:__imp_SetLastError
0x18010dc4d  mov     rcx, cs:pti; pti
0x18010dc54  test    rcx, rcx
0x18010dc57  jz      short loc_18010DC7D
0x18010dc59  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18010dc62  mov     r9d, 4E2h; msWindowLength
0x18010dc68  xor     r8d, r8d; msPeriod
0x18010dc6b  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18010dc70  call    cs:__imp_SetThreadpoolTimer
0x18010dc76  mov     cs:byte_180294520, 1
0x18010dc7d  lea     rcx, stru_180294508; SRWLock
0x18010dc84  call    cs:__imp_ReleaseSRWLockExclusive
0x18010dc8a  nop
0x18010dc8b  add     rsp, 30h
0x18010dc8f  pop     r15
0x18010dc91  pop     r14
0x18010dc93  pop     r12
0x18010dc95  pop     rdi
0x18010dc96  pop     rsi
0x18010dc97  pop     rbp
0x18010dc98  pop     rbx
0x18010dc99  retn
0x18010dc9a  test    r8d, r8d
0x18010dc9d  jnz     loc_18010DD26
0x18010dca3  cmp     ebx, 0FEh
0x18010dca9  jz      short loc_18010DD26
0x18010dcab  xor     edi, edi
0x18010dcad  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], rdi
0x18010dcb2  mov     [rsp+68h+pftDueTime.dwLowDateTime], ebp
0x18010dcb6  mov     word ptr [rsp+68h+pftDueTime.dwHighDateTime], bx
0x18010dcbb  test    edx, edx
0x18010dcbd  jns     short loc_18010DCC5
0x18010dcbf  or      word ptr [rsp+68h+pftDueTime.dwHighDateTime+2], 1
0x18010dcc5  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18010dccc  test    rax, rax
0x18010dccf  jnz     short loc_18010DD0D
0x18010dcd1  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18010dcd8  test    rax, rax
0x18010dcdb  jnz     short loc_18010DCF1
0x18010dcdd  lea     rcx, ModuleName; "ntdll.dll"
0x18010dce4  call    cs:__imp_GetModuleHandleW
0x18010dcea  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18010dcf1  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18010dcf8  mov     rcx, rax; hModule
0x18010dcfb  call    cs:__imp_GetProcAddress
0x18010dd01  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18010dd08  test    rax, rax
0x18010dd0b  jz      short loc_18010DD3A
0x18010dd0d  lea     rcx, [rsp+68h+pftDueTime]
0x18010dd12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010dd17  add     rsp, 30h
0x18010dd1b  pop     r15
0x18010dd1d  pop     r14
0x18010dd1f  pop     r12
0x18010dd21  pop     rdi
0x18010dd22  pop     rsi
0x18010dd23  pop     rbp
0x18010dd24  pop     rbx
0x18010dd25  retn
0x18010dd26  mov     r9, rsi
0x18010dd29  mov     r8d, ebx
0x18010dd2c  mov     edx, ebp
0x18010dd2e  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18010dd35  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18010dd3a  add     rsp, 30h
0x18010dd3e  pop     r15
0x18010dd40  pop     r14
0x18010dd42  pop     r12
0x18010dd44  pop     rdi
0x18010dd45  pop     rsi
0x18010dd46  pop     rbp
0x18010dd47  pop     rbx
0x18010dd48  retn
```
