# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18000f870`
- end: `0x18000f9d9`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `361`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000fd0c`

## callees

- `0x18000f870`
- `0x1800104c0`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f8bc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f8bc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f9c5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f9c5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f97a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f987`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f97a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f987`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f920`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f948`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f920`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f948`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000f972`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000f972`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000f969`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000f969`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f95b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f9b3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f95b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f9b3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000f936`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000f936`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  unsigned __int64 v6; // r8
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *Ptr; // rbp
  DWORD v10; // ebx
  struct _TP_TIMER *v11; // rcx
  _DWORD v12[2]; // [rsp+20h] [rbp-48h] BYREF
  struct wil_details_FeatureReportingCache *v13; // [rsp+28h] [rbp-40h]
  struct _FILETIME pftDueTime; // [rsp+70h] [rbp+8h] BYREF

  if ( LODWORD(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(pv + 1);
    if ( LODWORD(pv->Ptr)
      && !wil::details::g_processShutdownInProgress
      && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
    {
      v12[0] = a2;
      v12[1] = 0;
      v13 = a3;
      wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[4], v12, v6);
      if ( !LOBYTE(pv[3].Ptr) )
      {
        if ( !pv[2].Ptr )
        {
          LastError = GetLastError();
          ThreadpoolTimer = CreateThreadpoolTimer(
                              `wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_,
                              pv,
                              0);
          Ptr = (struct _TP_TIMER *)pv[2].Ptr;
          if ( Ptr )
          {
            v10 = GetLastError();
            SetThreadpoolTimer(Ptr, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(Ptr, 1);
            CloseThreadpoolTimer(Ptr);
            SetLastError(v10);
          }
          pv[2].Ptr = ThreadpoolTimer;
          SetLastError(LastError);
        }
        v11 = (struct _TP_TIMER *)pv[2].Ptr;
        if ( v11 )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v11, &pftDueTime, 0, 0x124F8u);
          LOBYTE(pv[3].Ptr) = 1;
        }
      }
    }
    if ( pv != (RTL_SRWLOCK *)-8LL )
      ReleaseSRWLockExclusive(pv + 1);
  }
}

```

## disassembly

```asm
0x18000f870  push    rbx
0x18000f872  push    rbp
0x18000f873  push    rsi
0x18000f874  push    rdi
0x18000f875  push    r14
0x18000f877  push    r15
0x18000f879  sub     rsp, 38h
0x18000f87d  mov     rbx, r8
0x18000f880  mov     ebp, edx
0x18000f882  mov     rdi, rcx
0x18000f885  mov     eax, [rcx]
0x18000f887  test    eax, eax
0x18000f889  jz      loc_18000F9CC
0x18000f88f  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000f896  jnz     loc_18000F9CC
0x18000f89c  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000f8a3  test    rax, rax
0x18000f8a6  jz      short loc_18000F8B5
0x18000f8a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8ad  test    al, al
0x18000f8af  jnz     loc_18000F9CC
0x18000f8b5  lea     rsi, [rdi+8]
0x18000f8b9  mov     rcx, rsi; SRWLock
0x18000f8bc  call    cs:__imp_AcquireSRWLockExclusive
0x18000f8c2  mov     eax, [rdi]
0x18000f8c4  test    eax, eax
0x18000f8c6  jz      loc_18000F9BD
0x18000f8cc  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000f8d3  jnz     loc_18000F9BD
0x18000f8d9  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000f8e0  test    rax, rax
0x18000f8e3  jz      short loc_18000F8F2
0x18000f8e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8ea  test    al, al
0x18000f8ec  jnz     loc_18000F9BD
0x18000f8f2  mov     [rsp+68h+var_48], ebp
0x18000f8f6  xor     eax, eax
0x18000f8f8  mov     [rsp+68h+var_44], eax
0x18000f8fc  mov     [rsp+68h+var_40], rbx
0x18000f901  lea     rcx, [rdi+20h]; this
0x18000f905  lea     rdx, [rsp+68h+var_48]; void *
0x18000f90a  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000f90f  cmp     byte ptr [rdi+18h], 0
0x18000f913  jnz     loc_18000F9BD
0x18000f919  cmp     qword ptr [rdi+10h], 0
0x18000f91e  jnz     short loc_18000F98D
0x18000f920  call    cs:__imp_GetLastError
0x18000f926  mov     r14d, eax
0x18000f929  xor     r8d, r8d; pcbe
0x18000f92c  mov     rdx, rdi; pv
0x18000f92f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VEnabledStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVEnabledStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000f936  call    cs:__imp_CreateThreadpoolTimer
0x18000f93c  mov     r15, rax
0x18000f93f  mov     rbp, [rdi+10h]
0x18000f943  test    rbp, rbp
0x18000f946  jz      short loc_18000F980
0x18000f948  call    cs:__imp_GetLastError
0x18000f94e  mov     ebx, eax
0x18000f950  xor     r9d, r9d; msWindowLength
0x18000f953  xor     r8d, r8d; msPeriod
0x18000f956  xor     edx, edx; pftDueTime
0x18000f958  mov     rcx, rbp; pti
0x18000f95b  call    cs:__imp_SetThreadpoolTimer
0x18000f961  mov     edx, 1; fCancelPendingCallbacks
0x18000f966  mov     rcx, rbp; pti
0x18000f969  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000f96f  mov     rcx, rbp; pti
0x18000f972  call    cs:__imp_CloseThreadpoolTimer
0x18000f978  mov     ecx, ebx; dwErrCode
0x18000f97a  call    cs:__imp_SetLastError
0x18000f980  mov     [rdi+10h], r15
0x18000f984  mov     ecx, r14d; dwErrCode
0x18000f987  call    cs:__imp_SetLastError
0x18000f98d  mov     rcx, [rdi+10h]; pti
0x18000f991  test    rcx, rcx
0x18000f994  jz      short loc_18000F9BD
0x18000f996  mov     rax, 0FFFFFFFF4D2FA200h
0x18000f9a0  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], rax
0x18000f9a5  mov     r9d, 124F8h; msWindowLength
0x18000f9ab  xor     r8d, r8d; msPeriod
0x18000f9ae  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18000f9b3  call    cs:__imp_SetThreadpoolTimer
0x18000f9b9  mov     byte ptr [rdi+18h], 1
0x18000f9bd  test    rsi, rsi
0x18000f9c0  jz      short loc_18000F9CC
0x18000f9c2  mov     rcx, rsi; SRWLock
0x18000f9c5  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f9cb  nop
0x18000f9cc  add     rsp, 38h
0x18000f9d0  pop     r15
0x18000f9d2  pop     r14
0x18000f9d4  pop     rdi
0x18000f9d5  pop     rsi
0x18000f9d6  pop     rbp
0x18000f9d7  pop     rbx
0x18000f9d8  retn
```
