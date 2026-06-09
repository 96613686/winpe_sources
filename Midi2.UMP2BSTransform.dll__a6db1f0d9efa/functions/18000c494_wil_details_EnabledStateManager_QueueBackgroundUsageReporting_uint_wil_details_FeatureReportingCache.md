# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18000c494`
- end: `0x18000c5fd`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `361`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000c93c`

## callees

- `0x18000c494`
- `0x18000e124`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c4e0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c4e0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c5e9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c5e9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c59e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c5ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c59e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c5ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c544`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c56c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c544`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c56c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000c55a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000c55a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000c596`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000c596`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c57f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c5d7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c57f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c5d7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000c58d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000c58d`

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
0x18000c494  push    rbx
0x18000c496  push    rbp
0x18000c497  push    rsi
0x18000c498  push    rdi
0x18000c499  push    r14
0x18000c49b  push    r15
0x18000c49d  sub     rsp, 38h
0x18000c4a1  mov     rbx, r8
0x18000c4a4  mov     ebp, edx
0x18000c4a6  mov     rdi, rcx
0x18000c4a9  mov     eax, [rcx]
0x18000c4ab  test    eax, eax
0x18000c4ad  jz      loc_18000C5F0
0x18000c4b3  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000c4ba  jnz     loc_18000C5F0
0x18000c4c0  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000c4c7  test    rax, rax
0x18000c4ca  jz      short loc_18000C4D9
0x18000c4cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c4d1  test    al, al
0x18000c4d3  jnz     loc_18000C5F0
0x18000c4d9  lea     rsi, [rdi+8]
0x18000c4dd  mov     rcx, rsi; SRWLock
0x18000c4e0  call    cs:__imp_AcquireSRWLockExclusive
0x18000c4e6  mov     eax, [rdi]
0x18000c4e8  test    eax, eax
0x18000c4ea  jz      loc_18000C5E1
0x18000c4f0  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000c4f7  jnz     loc_18000C5E1
0x18000c4fd  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000c504  test    rax, rax
0x18000c507  jz      short loc_18000C516
0x18000c509  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c50e  test    al, al
0x18000c510  jnz     loc_18000C5E1
0x18000c516  mov     [rsp+68h+var_48], ebp
0x18000c51a  xor     eax, eax
0x18000c51c  mov     [rsp+68h+var_44], eax
0x18000c520  mov     [rsp+68h+var_40], rbx
0x18000c525  lea     rcx, [rdi+20h]; this
0x18000c529  lea     rdx, [rsp+68h+var_48]; void *
0x18000c52e  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000c533  cmp     byte ptr [rdi+18h], 0
0x18000c537  jnz     loc_18000C5E1
0x18000c53d  cmp     qword ptr [rdi+10h], 0
0x18000c542  jnz     short loc_18000C5B1
0x18000c544  call    cs:__imp_GetLastError
0x18000c54a  mov     r14d, eax
0x18000c54d  xor     r8d, r8d; pcbe
0x18000c550  mov     rdx, rdi; pv
0x18000c553  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VEnabledStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVEnabledStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000c55a  call    cs:__imp_CreateThreadpoolTimer
0x18000c560  mov     r15, rax
0x18000c563  mov     rbp, [rdi+10h]
0x18000c567  test    rbp, rbp
0x18000c56a  jz      short loc_18000C5A4
0x18000c56c  call    cs:__imp_GetLastError
0x18000c572  mov     ebx, eax
0x18000c574  xor     r9d, r9d; msWindowLength
0x18000c577  xor     r8d, r8d; msPeriod
0x18000c57a  xor     edx, edx; pftDueTime
0x18000c57c  mov     rcx, rbp; pti
0x18000c57f  call    cs:__imp_SetThreadpoolTimer
0x18000c585  mov     edx, 1; fCancelPendingCallbacks
0x18000c58a  mov     rcx, rbp; pti
0x18000c58d  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000c593  mov     rcx, rbp; pti
0x18000c596  call    cs:__imp_CloseThreadpoolTimer
0x18000c59c  mov     ecx, ebx; dwErrCode
0x18000c59e  call    cs:__imp_SetLastError
0x18000c5a4  mov     [rdi+10h], r15
0x18000c5a8  mov     ecx, r14d; dwErrCode
0x18000c5ab  call    cs:__imp_SetLastError
0x18000c5b1  mov     rcx, [rdi+10h]; pti
0x18000c5b5  test    rcx, rcx
0x18000c5b8  jz      short loc_18000C5E1
0x18000c5ba  mov     rax, 0FFFFFFFF4D2FA200h
0x18000c5c4  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], rax
0x18000c5c9  mov     r9d, 124F8h; msWindowLength
0x18000c5cf  xor     r8d, r8d; msPeriod
0x18000c5d2  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18000c5d7  call    cs:__imp_SetThreadpoolTimer
0x18000c5dd  mov     byte ptr [rdi+18h], 1
0x18000c5e1  test    rsi, rsi
0x18000c5e4  jz      short loc_18000C5F0
0x18000c5e6  mov     rcx, rsi; SRWLock
0x18000c5e9  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c5ef  nop
0x18000c5f0  add     rsp, 38h
0x18000c5f4  pop     r15
0x18000c5f6  pop     r14
0x18000c5f8  pop     rdi
0x18000c5f9  pop     rsi
0x18000c5fa  pop     rbp
0x18000c5fb  pop     rbx
0x18000c5fc  retn
```
