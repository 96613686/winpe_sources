# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180018c60`
- end: `0x180018d34`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180019b4c`

## callees

- `0x180018c60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018c86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018cad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018c86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018cad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018cdf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018ceb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018cdf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018ceb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180018c9b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180018c9b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180018cd7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180018cd7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180018cc0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180018d17`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180018cc0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180018d17`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180018cce`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180018cce`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::EnsureTimerUnderLock(struct _TP_TIMER **pv)
{
  DWORD LastError; // ebp
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v4; // rsi
  PTP_TIMER v5; // r14
  DWORD v6; // ebx
  struct _TP_TIMER *v7; // rcx
  struct _FILETIME pftDueTime; // [rsp+40h] [rbp+8h] BYREF

  if ( !*((_BYTE *)pv + 65) )
  {
    if ( !pv[6] )
    {
      LastError = GetLastError();
      ThreadpoolTimer = CreateThreadpoolTimer(_lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_, pv, 0);
      v4 = pv[6];
      v5 = ThreadpoolTimer;
      if ( v4 )
      {
        v6 = GetLastError();
        SetThreadpoolTimer(v4, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(v4, 1);
        CloseThreadpoolTimer(v4);
        SetLastError(v6);
      }
      pv[6] = v5;
      SetLastError(LastError);
    }
    v7 = pv[6];
    if ( v7 )
    {
      pftDueTime = (struct _FILETIME)-3000000000LL;
      SetThreadpoolTimer(v7, &pftDueTime, 0, 0x124F8u);
      *((_BYTE *)pv + 65) = 1;
    }
  }
}

```

## disassembly

```asm
0x180018c60  mov     [rsp+arg_8], rbx
0x180018c65  mov     [rsp+arg_10], rbp
0x180018c6a  push    rsi
0x180018c6b  push    rdi
0x180018c6c  push    r14
0x180018c6e  sub     rsp, 20h
0x180018c72  cmp     byte ptr [rcx+41h], 0
0x180018c76  mov     rdi, rcx
0x180018c79  jnz     loc_180018D21
0x180018c7f  cmp     qword ptr [rcx+30h], 0
0x180018c84  jnz     short loc_180018CF1
0x180018c86  call    cs:__imp_GetLastError
0x180018c8c  xor     r8d, r8d; pcbe
0x180018c8f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180018c96  mov     rdx, rdi; pv
0x180018c99  mov     ebp, eax
0x180018c9b  call    cs:__imp_CreateThreadpoolTimer
0x180018ca1  mov     rsi, [rdi+30h]
0x180018ca5  mov     r14, rax
0x180018ca8  test    rsi, rsi
0x180018cab  jz      short loc_180018CE5
0x180018cad  call    cs:__imp_GetLastError
0x180018cb3  xor     r9d, r9d; msWindowLength
0x180018cb6  xor     r8d, r8d; msPeriod
0x180018cb9  xor     edx, edx; pftDueTime
0x180018cbb  mov     rcx, rsi; pti
0x180018cbe  mov     ebx, eax
0x180018cc0  call    cs:__imp_SetThreadpoolTimer
0x180018cc6  mov     edx, 1; fCancelPendingCallbacks
0x180018ccb  mov     rcx, rsi; pti
0x180018cce  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180018cd4  mov     rcx, rsi; pti
0x180018cd7  call    cs:__imp_CloseThreadpoolTimer
0x180018cdd  mov     ecx, ebx; dwErrCode
0x180018cdf  call    cs:__imp_SetLastError
0x180018ce5  mov     ecx, ebp; dwErrCode
0x180018ce7  mov     [rdi+30h], r14
0x180018ceb  call    cs:__imp_SetLastError
0x180018cf1  mov     rcx, [rdi+30h]; pti
0x180018cf5  test    rcx, rcx
0x180018cf8  jz      short loc_180018D21
0x180018cfa  mov     rax, 0FFFFFFFF4D2FA200h
0x180018d04  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180018d09  mov     r9d, 124F8h; msWindowLength
0x180018d0f  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x180018d14  xor     r8d, r8d; msPeriod
0x180018d17  call    cs:__imp_SetThreadpoolTimer
0x180018d1d  mov     byte ptr [rdi+41h], 1
0x180018d21  mov     rbx, [rsp+38h+arg_8]
0x180018d26  mov     rbp, [rsp+38h+arg_10]
0x180018d2b  add     rsp, 20h
0x180018d2f  pop     r14
0x180018d31  pop     rdi
0x180018d32  pop     rsi
0x180018d33  retn
```
