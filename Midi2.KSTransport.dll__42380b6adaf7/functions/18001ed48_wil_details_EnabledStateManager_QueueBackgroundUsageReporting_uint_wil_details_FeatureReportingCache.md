# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18001ed48`
- end: `0x18001eeb1`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `361`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18001f2b8`

## callees

- `0x18000bbec`
- `0x18001ed48`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ee9d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ee9d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001ed94`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001ed94`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ee52`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ee5f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ee52`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ee5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001edf8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ee20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001edf8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ee20`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001ee33`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001ee8b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001ee33`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001ee8b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001ee0e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001ee0e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001ee4a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001ee4a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001ee41`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001ee41`

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
0x18001ed48  push    rbx
0x18001ed4a  push    rbp
0x18001ed4b  push    rsi
0x18001ed4c  push    rdi
0x18001ed4d  push    r14
0x18001ed4f  push    r15
0x18001ed51  sub     rsp, 38h
0x18001ed55  mov     rbx, r8
0x18001ed58  mov     ebp, edx
0x18001ed5a  mov     rdi, rcx
0x18001ed5d  mov     eax, [rcx]
0x18001ed5f  test    eax, eax
0x18001ed61  jz      loc_18001EEA4
0x18001ed67  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18001ed6e  jnz     loc_18001EEA4
0x18001ed74  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001ed7b  test    rax, rax
0x18001ed7e  jz      short loc_18001ED8D
0x18001ed80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed85  test    al, al
0x18001ed87  jnz     loc_18001EEA4
0x18001ed8d  lea     rsi, [rdi+8]
0x18001ed91  mov     rcx, rsi; SRWLock
0x18001ed94  call    cs:__imp_AcquireSRWLockExclusive
0x18001ed9a  mov     eax, [rdi]
0x18001ed9c  test    eax, eax
0x18001ed9e  jz      loc_18001EE95
0x18001eda4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18001edab  jnz     loc_18001EE95
0x18001edb1  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001edb8  test    rax, rax
0x18001edbb  jz      short loc_18001EDCA
0x18001edbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001edc2  test    al, al
0x18001edc4  jnz     loc_18001EE95
0x18001edca  mov     [rsp+68h+var_48], ebp
0x18001edce  xor     eax, eax
0x18001edd0  mov     [rsp+68h+var_44], eax
0x18001edd4  mov     [rsp+68h+var_40], rbx
0x18001edd9  lea     rcx, [rdi+20h]; this
0x18001eddd  lea     rdx, [rsp+68h+var_48]; void *
0x18001ede2  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18001ede7  cmp     byte ptr [rdi+18h], 0
0x18001edeb  jnz     loc_18001EE95
0x18001edf1  cmp     qword ptr [rdi+10h], 0
0x18001edf6  jnz     short loc_18001EE65
0x18001edf8  call    cs:__imp_GetLastError
0x18001edfe  mov     r14d, eax
0x18001ee01  xor     r8d, r8d; pcbe
0x18001ee04  mov     rdx, rdi; pv
0x18001ee07  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VEnabledStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVEnabledStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001ee0e  call    cs:__imp_CreateThreadpoolTimer
0x18001ee14  mov     r15, rax
0x18001ee17  mov     rbp, [rdi+10h]
0x18001ee1b  test    rbp, rbp
0x18001ee1e  jz      short loc_18001EE58
0x18001ee20  call    cs:__imp_GetLastError
0x18001ee26  mov     ebx, eax
0x18001ee28  xor     r9d, r9d; msWindowLength
0x18001ee2b  xor     r8d, r8d; msPeriod
0x18001ee2e  xor     edx, edx; pftDueTime
0x18001ee30  mov     rcx, rbp; pti
0x18001ee33  call    cs:__imp_SetThreadpoolTimer
0x18001ee39  mov     edx, 1; fCancelPendingCallbacks
0x18001ee3e  mov     rcx, rbp; pti
0x18001ee41  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001ee47  mov     rcx, rbp; pti
0x18001ee4a  call    cs:__imp_CloseThreadpoolTimer
0x18001ee50  mov     ecx, ebx; dwErrCode
0x18001ee52  call    cs:__imp_SetLastError
0x18001ee58  mov     [rdi+10h], r15
0x18001ee5c  mov     ecx, r14d; dwErrCode
0x18001ee5f  call    cs:__imp_SetLastError
0x18001ee65  mov     rcx, [rdi+10h]; pti
0x18001ee69  test    rcx, rcx
0x18001ee6c  jz      short loc_18001EE95
0x18001ee6e  mov     rax, 0FFFFFFFF4D2FA200h
0x18001ee78  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], rax
0x18001ee7d  mov     r9d, 124F8h; msWindowLength
0x18001ee83  xor     r8d, r8d; msPeriod
0x18001ee86  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18001ee8b  call    cs:__imp_SetThreadpoolTimer
0x18001ee91  mov     byte ptr [rdi+18h], 1
0x18001ee95  test    rsi, rsi
0x18001ee98  jz      short loc_18001EEA4
0x18001ee9a  mov     rcx, rsi; SRWLock
0x18001ee9d  call    cs:__imp_ReleaseSRWLockExclusive
0x18001eea3  nop
0x18001eea4  add     rsp, 38h
0x18001eea8  pop     r15
0x18001eeaa  pop     r14
0x18001eeac  pop     rdi
0x18001eead  pop     rsi
0x18001eeae  pop     rbp
0x18001eeaf  pop     rbx
0x18001eeb0  retn
```
