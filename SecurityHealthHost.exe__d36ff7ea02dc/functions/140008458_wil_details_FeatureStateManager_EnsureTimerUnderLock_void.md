# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x140008458`
- end: `0x14000852c`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140009680`

## callees

- `0x140008458`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000847e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400084a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000847e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400084a5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400084d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400084e3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400084d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400084e3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400084cf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400084cf`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140008493`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140008493`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400084b8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000850f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400084b8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000850f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400084c6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400084c6`

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
0x140008458  mov     [rsp+arg_8], rbx
0x14000845d  mov     [rsp+arg_10], rbp
0x140008462  push    rsi
0x140008463  push    rdi
0x140008464  push    r14
0x140008466  sub     rsp, 20h
0x14000846a  cmp     byte ptr [rcx+41h], 0
0x14000846e  mov     rdi, rcx
0x140008471  jnz     loc_140008519
0x140008477  cmp     qword ptr [rcx+30h], 0
0x14000847c  jnz     short loc_1400084E9
0x14000847e  call    cs:__imp_GetLastError
0x140008484  xor     r8d, r8d; pcbe
0x140008487  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14000848e  mov     rdx, rdi; pv
0x140008491  mov     ebp, eax
0x140008493  call    cs:__imp_CreateThreadpoolTimer
0x140008499  mov     rsi, [rdi+30h]
0x14000849d  mov     r14, rax
0x1400084a0  test    rsi, rsi
0x1400084a3  jz      short loc_1400084DD
0x1400084a5  call    cs:__imp_GetLastError
0x1400084ab  xor     r9d, r9d; msWindowLength
0x1400084ae  xor     r8d, r8d; msPeriod
0x1400084b1  xor     edx, edx; pftDueTime
0x1400084b3  mov     rcx, rsi; pti
0x1400084b6  mov     ebx, eax
0x1400084b8  call    cs:__imp_SetThreadpoolTimer
0x1400084be  mov     edx, 1; fCancelPendingCallbacks
0x1400084c3  mov     rcx, rsi; pti
0x1400084c6  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400084cc  mov     rcx, rsi; pti
0x1400084cf  call    cs:__imp_CloseThreadpoolTimer
0x1400084d5  mov     ecx, ebx; dwErrCode
0x1400084d7  call    cs:__imp_SetLastError
0x1400084dd  mov     ecx, ebp; dwErrCode
0x1400084df  mov     [rdi+30h], r14
0x1400084e3  call    cs:__imp_SetLastError
0x1400084e9  mov     rcx, [rdi+30h]; pti
0x1400084ed  test    rcx, rcx
0x1400084f0  jz      short loc_140008519
0x1400084f2  mov     rax, 0FFFFFFFF4D2FA200h
0x1400084fc  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x140008501  mov     r9d, 124F8h; msWindowLength
0x140008507  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x14000850c  xor     r8d, r8d; msPeriod
0x14000850f  call    cs:__imp_SetThreadpoolTimer
0x140008515  mov     byte ptr [rdi+41h], 1
0x140008519  mov     rbx, [rsp+38h+arg_8]
0x14000851e  mov     rbp, [rsp+38h+arg_10]
0x140008523  add     rsp, 20h
0x140008527  pop     r14
0x140008529  pop     rdi
0x14000852a  pop     rsi
0x14000852b  retn
```
