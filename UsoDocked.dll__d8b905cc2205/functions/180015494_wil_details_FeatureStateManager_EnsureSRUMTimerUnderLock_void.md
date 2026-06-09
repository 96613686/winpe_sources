# wil::details::FeatureStateManager::EnsureSRUMTimerUnderLock(void)

- ea: `0x180015494`
- end: `0x18001557e`
- name: `?EnsureSRUMTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `234`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180016e20`

## callees

- `0x180007660`
- `0x180015494`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800154c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800154f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800154c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800154f0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015522`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001552e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015522`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001552e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800154de`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800154de`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180015511`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180015511`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001551a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001551a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180015503`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180015554`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180015503`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180015554`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::EnsureSRUMTimerUnderLock(struct _TP_TIMER **pv)
{
  DWORD LastError; // ebp
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v4; // rsi
  PTP_TIMER v5; // r14
  DWORD v6; // ebx
  struct _TP_TIMER *v7; // rcx
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-28h] BYREF

  if ( !*((_BYTE *)pv + 64) )
  {
    if ( !pv[7] )
    {
      LastError = GetLastError();
      ThreadpoolTimer = CreateThreadpoolTimer(_lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_, pv, 0);
      v4 = pv[7];
      v5 = ThreadpoolTimer;
      if ( v4 )
      {
        v6 = GetLastError();
        SetThreadpoolTimer(v4, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(v4, 1);
        CloseThreadpoolTimer(v4);
        SetLastError(v6);
      }
      pv[7] = v5;
      SetLastError(LastError);
    }
    v7 = pv[7];
    if ( v7 )
    {
      pftDueTime = (struct _FILETIME)-50000000LL;
      SetThreadpoolTimer(v7, &pftDueTime, 0, 0x4E2u);
      *((_BYTE *)pv + 64) = 1;
    }
  }
}

```

## disassembly

```asm
0x180015494  mov     [rsp+arg_8], rbx
0x180015499  mov     [rsp+arg_10], rbp
0x18001549e  push    rsi
0x18001549f  push    rdi
0x1800154a0  push    r14
0x1800154a2  sub     rsp, 30h
0x1800154a6  mov     rax, cs:__security_cookie
0x1800154ad  xor     rax, rsp
0x1800154b0  mov     [rsp+48h+var_20], rax
0x1800154b5  cmp     byte ptr [rcx+40h], 0
0x1800154b9  mov     rdi, rcx
0x1800154bc  jnz     loc_18001555E
0x1800154c2  cmp     qword ptr [rcx+38h], 0
0x1800154c7  jnz     short loc_180015534
0x1800154c9  call    cs:__imp_GetLastError
0x1800154cf  xor     r8d, r8d; pcbe
0x1800154d2  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800154d9  mov     rdx, rdi; pv
0x1800154dc  mov     ebp, eax
0x1800154de  call    cs:__imp_CreateThreadpoolTimer
0x1800154e4  mov     rsi, [rdi+38h]
0x1800154e8  mov     r14, rax
0x1800154eb  test    rsi, rsi
0x1800154ee  jz      short loc_180015528
0x1800154f0  call    cs:__imp_GetLastError
0x1800154f6  xor     r9d, r9d; msWindowLength
0x1800154f9  xor     r8d, r8d; msPeriod
0x1800154fc  xor     edx, edx; pftDueTime
0x1800154fe  mov     rcx, rsi; pti
0x180015501  mov     ebx, eax
0x180015503  call    cs:__imp_SetThreadpoolTimer
0x180015509  mov     edx, 1; fCancelPendingCallbacks
0x18001550e  mov     rcx, rsi; pti
0x180015511  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180015517  mov     rcx, rsi; pti
0x18001551a  call    cs:__imp_CloseThreadpoolTimer
0x180015520  mov     ecx, ebx; dwErrCode
0x180015522  call    cs:__imp_SetLastError
0x180015528  mov     ecx, ebp; dwErrCode
0x18001552a  mov     [rdi+38h], r14
0x18001552e  call    cs:__imp_SetLastError
0x180015534  mov     rcx, [rdi+38h]; pti
0x180015538  test    rcx, rcx
0x18001553b  jz      short loc_18001555E
0x18001553d  mov     r9d, 4E2h; msWindowLength
0x180015543  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18001554c  xor     r8d, r8d; msPeriod
0x18001554f  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x180015554  call    cs:__imp_SetThreadpoolTimer
0x18001555a  mov     byte ptr [rdi+40h], 1
0x18001555e  mov     rcx, [rsp+48h+var_20]
0x180015563  xor     rcx, rsp; StackCookie
0x180015566  call    __security_check_cookie
0x18001556b  mov     rbx, [rsp+48h+arg_8]
0x180015570  mov     rbp, [rsp+48h+arg_10]
0x180015575  add     rsp, 30h
0x180015579  pop     r14
0x18001557b  pop     rdi
0x18001557c  pop     rsi
0x18001557d  retn
```
