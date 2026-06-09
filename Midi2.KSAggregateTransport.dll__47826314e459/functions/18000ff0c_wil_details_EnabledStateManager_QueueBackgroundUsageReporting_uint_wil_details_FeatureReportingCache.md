# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18000ff0c`
- end: `0x180010075`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `361`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180010290`

## callees

- `0x18000c76c`
- `0x18000ff0c`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010061`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010061`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ff58`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ff58`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010016`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010023`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010016`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010023`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ffbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ffe4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ffbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ffe4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000ffd2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000ffd2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001000e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001000e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000fff7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001004f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000fff7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001004f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180010005`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180010005`

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
0x18000ff0c  push    rbx
0x18000ff0e  push    rbp
0x18000ff0f  push    rsi
0x18000ff10  push    rdi
0x18000ff11  push    r14
0x18000ff13  push    r15
0x18000ff15  sub     rsp, 38h
0x18000ff19  mov     rbx, r8
0x18000ff1c  mov     ebp, edx
0x18000ff1e  mov     rdi, rcx
0x18000ff21  mov     eax, [rcx]
0x18000ff23  test    eax, eax
0x18000ff25  jz      loc_180010068
0x18000ff2b  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000ff32  jnz     loc_180010068
0x18000ff38  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000ff3f  test    rax, rax
0x18000ff42  jz      short loc_18000FF51
0x18000ff44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff49  test    al, al
0x18000ff4b  jnz     loc_180010068
0x18000ff51  lea     rsi, [rdi+8]
0x18000ff55  mov     rcx, rsi; SRWLock
0x18000ff58  call    cs:__imp_AcquireSRWLockExclusive
0x18000ff5e  mov     eax, [rdi]
0x18000ff60  test    eax, eax
0x18000ff62  jz      loc_180010059
0x18000ff68  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000ff6f  jnz     loc_180010059
0x18000ff75  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000ff7c  test    rax, rax
0x18000ff7f  jz      short loc_18000FF8E
0x18000ff81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff86  test    al, al
0x18000ff88  jnz     loc_180010059
0x18000ff8e  mov     [rsp+68h+var_48], ebp
0x18000ff92  xor     eax, eax
0x18000ff94  mov     [rsp+68h+var_44], eax
0x18000ff98  mov     [rsp+68h+var_40], rbx
0x18000ff9d  lea     rcx, [rdi+20h]; this
0x18000ffa1  lea     rdx, [rsp+68h+var_48]; void *
0x18000ffa6  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000ffab  cmp     byte ptr [rdi+18h], 0
0x18000ffaf  jnz     loc_180010059
0x18000ffb5  cmp     qword ptr [rdi+10h], 0
0x18000ffba  jnz     short loc_180010029
0x18000ffbc  call    cs:__imp_GetLastError
0x18000ffc2  mov     r14d, eax
0x18000ffc5  xor     r8d, r8d; pcbe
0x18000ffc8  mov     rdx, rdi; pv
0x18000ffcb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VEnabledStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVEnabledStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000ffd2  call    cs:__imp_CreateThreadpoolTimer
0x18000ffd8  mov     r15, rax
0x18000ffdb  mov     rbp, [rdi+10h]
0x18000ffdf  test    rbp, rbp
0x18000ffe2  jz      short loc_18001001C
0x18000ffe4  call    cs:__imp_GetLastError
0x18000ffea  mov     ebx, eax
0x18000ffec  xor     r9d, r9d; msWindowLength
0x18000ffef  xor     r8d, r8d; msPeriod
0x18000fff2  xor     edx, edx; pftDueTime
0x18000fff4  mov     rcx, rbp; pti
0x18000fff7  call    cs:__imp_SetThreadpoolTimer
0x18000fffd  mov     edx, 1; fCancelPendingCallbacks
0x180010002  mov     rcx, rbp; pti
0x180010005  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001000b  mov     rcx, rbp; pti
0x18001000e  call    cs:__imp_CloseThreadpoolTimer
0x180010014  mov     ecx, ebx; dwErrCode
0x180010016  call    cs:__imp_SetLastError
0x18001001c  mov     [rdi+10h], r15
0x180010020  mov     ecx, r14d; dwErrCode
0x180010023  call    cs:__imp_SetLastError
0x180010029  mov     rcx, [rdi+10h]; pti
0x18001002d  test    rcx, rcx
0x180010030  jz      short loc_180010059
0x180010032  mov     rax, 0FFFFFFFF4D2FA200h
0x18001003c  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], rax
0x180010041  mov     r9d, 124F8h; msWindowLength
0x180010047  xor     r8d, r8d; msPeriod
0x18001004a  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18001004f  call    cs:__imp_SetThreadpoolTimer
0x180010055  mov     byte ptr [rdi+18h], 1
0x180010059  test    rsi, rsi
0x18001005c  jz      short loc_180010068
0x18001005e  mov     rcx, rsi; SRWLock
0x180010061  call    cs:__imp_ReleaseSRWLockExclusive
0x180010067  nop
0x180010068  add     rsp, 38h
0x18001006c  pop     r15
0x18001006e  pop     r14
0x180010070  pop     rdi
0x180010071  pop     rsi
0x180010072  pop     rbp
0x180010073  pop     rbx
0x180010074  retn
```
