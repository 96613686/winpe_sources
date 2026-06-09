# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180008ad0`
- end: `0x180008c5b`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `395`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, __int64, struct wil_details_FeatureReportingCache *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800081e8`
- `0x180008760`

## callees

- `0x180008ad0`
- `0x18000ba60`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008c49`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008c49`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008b19`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008b19`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008bef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008bfc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008bef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008bfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008bbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008bbd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008bd0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008c37`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008bd0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008c37`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180008bab`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180008bab`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008bde`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008bde`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008be7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008be7`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        __int64 a2,
        struct wil_details_FeatureReportingCache *a3)
{
  __int64 v5; // rcx
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *Ptr; // rbp
  PTP_TIMER v9; // r15
  DWORD v10; // ebx
  struct _TP_TIMER *v11; // rcx
  _QWORD v12[2]; // [rsp+20h] [rbp-28h] BYREF
  _FILETIME pftDueTime; // [rsp+50h] [rbp+8h] BYREF

  if ( LODWORD(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress(pv)) )
  {
    AcquireSRWLockExclusive(pv + 1);
    if ( LODWORD(pv->Ptr)
      && !wil::details::g_processShutdownInProgress
      && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress(v5)) )
    {
      v12[0] = 31261443;
      v12[1] = a3;
      wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[4], v12, 0x10u);
      if ( !LOBYTE(pv[3].Ptr) )
      {
        if ( !pv[2].Ptr )
        {
          LastError = GetLastError();
          ThreadpoolTimer = CreateThreadpoolTimer(
                              _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                              pv,
                              0);
          Ptr = (struct _TP_TIMER *)pv[2].Ptr;
          v9 = ThreadpoolTimer;
          if ( Ptr )
          {
            v10 = GetLastError();
            SetThreadpoolTimer(Ptr, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(Ptr, 1);
            CloseThreadpoolTimer(Ptr);
            SetLastError(v10);
          }
          pv[2].Ptr = v9;
          SetLastError(LastError);
        }
        v11 = (struct _TP_TIMER *)pv[2].Ptr;
        if ( v11 )
        {
          pftDueTime = (_FILETIME)-3000000000LL;
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
0x180008ad0  push    rbx
0x180008ad2  push    rdi
0x180008ad3  sub     rsp, 38h
0x180008ad7  mov     eax, [rcx]
0x180008ad9  mov     rbx, r8
0x180008adc  mov     rdi, rcx
0x180008adf  test    eax, eax
0x180008ae1  jz      loc_180008C54
0x180008ae7  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180008aee  jnz     loc_180008C54
0x180008af4  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180008afb  test    rax, rax
0x180008afe  jz      short loc_180008B0D
0x180008b00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b05  test    al, al
0x180008b07  jnz     loc_180008C54
0x180008b0d  mov     [rsp+48h+arg_10], rsi
0x180008b12  lea     rsi, [rdi+8]
0x180008b16  mov     rcx, rsi; SRWLock
0x180008b19  call    cs:__imp_AcquireSRWLockExclusive
0x180008b1f  mov     eax, [rdi]
0x180008b21  test    eax, eax
0x180008b23  jz      loc_180008C41
0x180008b29  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180008b30  jnz     loc_180008C41
0x180008b36  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180008b3d  test    rax, rax
0x180008b40  jz      short loc_180008B4F
0x180008b42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b47  test    al, al
0x180008b49  jnz     loc_180008C41
0x180008b4f  lea     rcx, [rdi+20h]; this
0x180008b53  mov     [rsp+48h+var_28], 1DD0303h
0x180008b5c  mov     r8d, 10h; unsigned __int64
0x180008b62  mov     [rsp+48h+var_20], rbx
0x180008b67  lea     rdx, [rsp+48h+var_28]; void *
0x180008b6c  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180008b71  cmp     byte ptr [rdi+18h], 0
0x180008b75  jnz     loc_180008C41
0x180008b7b  cmp     qword ptr [rdi+10h], 0
0x180008b80  jnz     loc_180008C11
0x180008b86  mov     [rsp+48h+arg_8], rbp
0x180008b8b  mov     [rsp+48h+arg_18], r14
0x180008b90  mov     [rsp+48h+var_18], r15
0x180008b95  call    cs:__imp_GetLastError
0x180008b9b  xor     r8d, r8d; pcbe
0x180008b9e  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180008ba5  mov     rdx, rdi; pv
0x180008ba8  mov     r14d, eax
0x180008bab  call    cs:__imp_CreateThreadpoolTimer
0x180008bb1  mov     rbp, [rdi+10h]
0x180008bb5  mov     r15, rax
0x180008bb8  test    rbp, rbp
0x180008bbb  jz      short loc_180008BF5
0x180008bbd  call    cs:__imp_GetLastError
0x180008bc3  xor     r9d, r9d; msWindowLength
0x180008bc6  xor     r8d, r8d; msPeriod
0x180008bc9  xor     edx, edx; pftDueTime
0x180008bcb  mov     rcx, rbp; pti
0x180008bce  mov     ebx, eax
0x180008bd0  call    cs:__imp_SetThreadpoolTimer
0x180008bd6  mov     edx, 1; fCancelPendingCallbacks
0x180008bdb  mov     rcx, rbp; pti
0x180008bde  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008be4  mov     rcx, rbp; pti
0x180008be7  call    cs:__imp_CloseThreadpoolTimer
0x180008bed  mov     ecx, ebx; dwErrCode
0x180008bef  call    cs:__imp_SetLastError
0x180008bf5  mov     ecx, r14d; dwErrCode
0x180008bf8  mov     [rdi+10h], r15
0x180008bfc  call    cs:__imp_SetLastError
0x180008c02  mov     r15, [rsp+48h+var_18]
0x180008c07  mov     r14, [rsp+48h+arg_18]
0x180008c0c  mov     rbp, [rsp+48h+arg_8]
0x180008c11  mov     rcx, [rdi+10h]; pti
0x180008c15  test    rcx, rcx
0x180008c18  jz      short loc_180008C41
0x180008c1a  mov     rax, 0FFFFFFFF4D2FA200h
0x180008c24  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x180008c29  mov     r9d, 124F8h; msWindowLength
0x180008c2f  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x180008c34  xor     r8d, r8d; msPeriod
0x180008c37  call    cs:__imp_SetThreadpoolTimer
0x180008c3d  mov     byte ptr [rdi+18h], 1
0x180008c41  test    rsi, rsi
0x180008c44  jz      short loc_180008C4F
0x180008c46  mov     rcx, rsi; SRWLock
0x180008c49  call    cs:__imp_ReleaseSRWLockExclusive
0x180008c4f  mov     rsi, [rsp+48h+arg_10]
0x180008c54  add     rsp, 38h
0x180008c58  pop     rdi
0x180008c59  pop     rbx
0x180008c5a  retn
```
