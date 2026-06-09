# wil::details::FeatureStateManager::EnsureSRUMTimerUnderLock(void)

- ea: `0x18000d258`
- end: `0x18000d342`
- name: `?EnsureSRUMTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `234`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ea50`

## callees

- `0x180003a00`
- `0x18000d258`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d28d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d2b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d28d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d2b4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d2e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d2f2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d2e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d2f2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d2c7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d318`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d2c7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d318`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000d2a2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000d2a2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d2de`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d2de`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d2d5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d2d5`

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
0x18000d258  mov     [rsp+arg_8], rbx
0x18000d25d  mov     [rsp+arg_10], rbp
0x18000d262  push    rsi
0x18000d263  push    rdi
0x18000d264  push    r14
0x18000d266  sub     rsp, 30h
0x18000d26a  mov     rax, cs:__security_cookie
0x18000d271  xor     rax, rsp
0x18000d274  mov     [rsp+48h+var_20], rax
0x18000d279  cmp     byte ptr [rcx+40h], 0
0x18000d27d  mov     rdi, rcx
0x18000d280  jnz     loc_18000D322
0x18000d286  cmp     qword ptr [rcx+38h], 0
0x18000d28b  jnz     short loc_18000D2F8
0x18000d28d  call    cs:__imp_GetLastError
0x18000d293  xor     r8d, r8d; pcbe
0x18000d296  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000d29d  mov     rdx, rdi; pv
0x18000d2a0  mov     ebp, eax
0x18000d2a2  call    cs:__imp_CreateThreadpoolTimer
0x18000d2a8  mov     rsi, [rdi+38h]
0x18000d2ac  mov     r14, rax
0x18000d2af  test    rsi, rsi
0x18000d2b2  jz      short loc_18000D2EC
0x18000d2b4  call    cs:__imp_GetLastError
0x18000d2ba  xor     r9d, r9d; msWindowLength
0x18000d2bd  xor     r8d, r8d; msPeriod
0x18000d2c0  xor     edx, edx; pftDueTime
0x18000d2c2  mov     rcx, rsi; pti
0x18000d2c5  mov     ebx, eax
0x18000d2c7  call    cs:__imp_SetThreadpoolTimer
0x18000d2cd  mov     edx, 1; fCancelPendingCallbacks
0x18000d2d2  mov     rcx, rsi; pti
0x18000d2d5  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000d2db  mov     rcx, rsi; pti
0x18000d2de  call    cs:__imp_CloseThreadpoolTimer
0x18000d2e4  mov     ecx, ebx; dwErrCode
0x18000d2e6  call    cs:__imp_SetLastError
0x18000d2ec  mov     ecx, ebp; dwErrCode
0x18000d2ee  mov     [rdi+38h], r14
0x18000d2f2  call    cs:__imp_SetLastError
0x18000d2f8  mov     rcx, [rdi+38h]; pti
0x18000d2fc  test    rcx, rcx
0x18000d2ff  jz      short loc_18000D322
0x18000d301  mov     r9d, 4E2h; msWindowLength
0x18000d307  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000d310  xor     r8d, r8d; msPeriod
0x18000d313  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x18000d318  call    cs:__imp_SetThreadpoolTimer
0x18000d31e  mov     byte ptr [rdi+40h], 1
0x18000d322  mov     rcx, [rsp+48h+var_20]
0x18000d327  xor     rcx, rsp; StackCookie
0x18000d32a  call    __security_check_cookie
0x18000d32f  mov     rbx, [rsp+48h+arg_8]
0x18000d334  mov     rbp, [rsp+48h+arg_10]
0x18000d339  add     rsp, 30h
0x18000d33d  pop     r14
0x18000d33f  pop     rdi
0x18000d340  pop     rsi
0x18000d341  retn
```
