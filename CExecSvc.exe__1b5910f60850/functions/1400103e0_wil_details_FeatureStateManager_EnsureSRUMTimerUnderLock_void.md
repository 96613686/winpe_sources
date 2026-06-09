# wil::details::FeatureStateManager::EnsureSRUMTimerUnderLock(void)

- ea: `0x1400103e0`
- end: `0x1400104ca`
- name: `?EnsureSRUMTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `234`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140011024`

## callees

- `0x140002310`
- `0x1400103e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010415`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001043c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010415`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001043c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001046e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001047a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001046e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001047a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14001042a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14001042a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14001044f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400104a0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14001044f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400104a0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140010466`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140010466`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14001045d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14001045d`

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
0x1400103e0  mov     [rsp+arg_8], rbx
0x1400103e5  mov     [rsp+arg_10], rbp
0x1400103ea  push    rsi
0x1400103eb  push    rdi
0x1400103ec  push    r14
0x1400103ee  sub     rsp, 30h
0x1400103f2  mov     rax, cs:__security_cookie
0x1400103f9  xor     rax, rsp
0x1400103fc  mov     [rsp+48h+var_20], rax
0x140010401  cmp     byte ptr [rcx+40h], 0
0x140010405  mov     rdi, rcx
0x140010408  jnz     loc_1400104AA
0x14001040e  cmp     qword ptr [rcx+38h], 0
0x140010413  jnz     short loc_140010480
0x140010415  call    cs:__imp_GetLastError
0x14001041b  xor     r8d, r8d; pcbe
0x14001041e  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140010425  mov     rdx, rdi; pv
0x140010428  mov     ebp, eax
0x14001042a  call    cs:__imp_CreateThreadpoolTimer
0x140010430  mov     rsi, [rdi+38h]
0x140010434  mov     r14, rax
0x140010437  test    rsi, rsi
0x14001043a  jz      short loc_140010474
0x14001043c  call    cs:__imp_GetLastError
0x140010442  xor     r9d, r9d; msWindowLength
0x140010445  xor     r8d, r8d; msPeriod
0x140010448  xor     edx, edx; pftDueTime
0x14001044a  mov     rcx, rsi; pti
0x14001044d  mov     ebx, eax
0x14001044f  call    cs:__imp_SetThreadpoolTimer
0x140010455  mov     edx, 1; fCancelPendingCallbacks
0x14001045a  mov     rcx, rsi; pti
0x14001045d  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140010463  mov     rcx, rsi; pti
0x140010466  call    cs:__imp_CloseThreadpoolTimer
0x14001046c  mov     ecx, ebx; dwErrCode
0x14001046e  call    cs:__imp_SetLastError
0x140010474  mov     ecx, ebp; dwErrCode
0x140010476  mov     [rdi+38h], r14
0x14001047a  call    cs:__imp_SetLastError
0x140010480  mov     rcx, [rdi+38h]; pti
0x140010484  test    rcx, rcx
0x140010487  jz      short loc_1400104AA
0x140010489  mov     r9d, 4E2h; msWindowLength
0x14001048f  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x140010498  xor     r8d, r8d; msPeriod
0x14001049b  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x1400104a0  call    cs:__imp_SetThreadpoolTimer
0x1400104a6  mov     byte ptr [rdi+40h], 1
0x1400104aa  mov     rcx, [rsp+48h+var_20]
0x1400104af  xor     rcx, rsp; StackCookie
0x1400104b2  call    __security_check_cookie
0x1400104b7  mov     rbx, [rsp+48h+arg_8]
0x1400104bc  mov     rbp, [rsp+48h+arg_10]
0x1400104c1  add     rsp, 30h
0x1400104c5  pop     r14
0x1400104c7  pop     rdi
0x1400104c8  pop     rsi
0x1400104c9  retn
```
