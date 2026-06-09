# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x1800041e8`
- end: `0x1800042bc`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005c64`

## callees

- `0x1800041e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000420e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004235`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000420e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004235`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004267`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004273`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004267`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004273`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004248`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000429f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004248`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000429f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000425f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000425f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180004223`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180004223`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004256`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004256`

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
0x1800041e8  mov     [rsp+arg_8], rbx
0x1800041ed  mov     [rsp+arg_10], rbp
0x1800041f2  push    rsi
0x1800041f3  push    rdi
0x1800041f4  push    r14
0x1800041f6  sub     rsp, 20h
0x1800041fa  cmp     byte ptr [rcx+41h], 0
0x1800041fe  mov     rdi, rcx
0x180004201  jnz     loc_1800042A9
0x180004207  cmp     qword ptr [rcx+30h], 0
0x18000420c  jnz     short loc_180004279
0x18000420e  call    cs:__imp_GetLastError
0x180004214  xor     r8d, r8d; pcbe
0x180004217  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000421e  mov     rdx, rdi; pv
0x180004221  mov     ebp, eax
0x180004223  call    cs:__imp_CreateThreadpoolTimer
0x180004229  mov     rsi, [rdi+30h]
0x18000422d  mov     r14, rax
0x180004230  test    rsi, rsi
0x180004233  jz      short loc_18000426D
0x180004235  call    cs:__imp_GetLastError
0x18000423b  xor     r9d, r9d; msWindowLength
0x18000423e  xor     r8d, r8d; msPeriod
0x180004241  xor     edx, edx; pftDueTime
0x180004243  mov     rcx, rsi; pti
0x180004246  mov     ebx, eax
0x180004248  call    cs:__imp_SetThreadpoolTimer
0x18000424e  mov     edx, 1; fCancelPendingCallbacks
0x180004253  mov     rcx, rsi; pti
0x180004256  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000425c  mov     rcx, rsi; pti
0x18000425f  call    cs:__imp_CloseThreadpoolTimer
0x180004265  mov     ecx, ebx; dwErrCode
0x180004267  call    cs:__imp_SetLastError
0x18000426d  mov     ecx, ebp; dwErrCode
0x18000426f  mov     [rdi+30h], r14
0x180004273  call    cs:__imp_SetLastError
0x180004279  mov     rcx, [rdi+30h]; pti
0x18000427d  test    rcx, rcx
0x180004280  jz      short loc_1800042A9
0x180004282  mov     rax, 0FFFFFFFF4D2FA200h
0x18000428c  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180004291  mov     r9d, 124F8h; msWindowLength
0x180004297  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x18000429c  xor     r8d, r8d; msPeriod
0x18000429f  call    cs:__imp_SetThreadpoolTimer
0x1800042a5  mov     byte ptr [rdi+41h], 1
0x1800042a9  mov     rbx, [rsp+38h+arg_8]
0x1800042ae  mov     rbp, [rsp+38h+arg_10]
0x1800042b3  add     rsp, 20h
0x1800042b7  pop     r14
0x1800042b9  pop     rdi
0x1800042ba  pop     rsi
0x1800042bb  retn
```
