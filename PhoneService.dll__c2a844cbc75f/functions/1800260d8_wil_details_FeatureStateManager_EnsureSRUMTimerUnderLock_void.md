# wil::details::FeatureStateManager::EnsureSRUMTimerUnderLock(void)

- ea: `0x1800260d8`
- end: `0x1800261c2`
- name: `?EnsureSRUMTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `234`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180034470`

## callees

- `0x1800260d8`
- `0x18008d9b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026166`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026172`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026166`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026172`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002610d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026134`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002610d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026134`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180026147`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180026198`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180026147`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180026198`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002615e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002615e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180026155`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180026155`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180026122`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180026122`

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
0x1800260d8  mov     [rsp+arg_8], rbx
0x1800260dd  mov     [rsp+arg_10], rbp
0x1800260e2  push    rsi
0x1800260e3  push    rdi
0x1800260e4  push    r14
0x1800260e6  sub     rsp, 30h
0x1800260ea  mov     rax, cs:__security_cookie
0x1800260f1  xor     rax, rsp
0x1800260f4  mov     [rsp+48h+var_20], rax
0x1800260f9  cmp     byte ptr [rcx+40h], 0
0x1800260fd  mov     rdi, rcx
0x180026100  jnz     loc_1800261A2
0x180026106  cmp     qword ptr [rcx+38h], 0
0x18002610b  jnz     short loc_180026178
0x18002610d  call    cs:__imp_GetLastError
0x180026113  xor     r8d, r8d; pcbe
0x180026116  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18002611d  mov     rdx, rdi; pv
0x180026120  mov     ebp, eax
0x180026122  call    cs:__imp_CreateThreadpoolTimer
0x180026128  mov     rsi, [rdi+38h]
0x18002612c  mov     r14, rax
0x18002612f  test    rsi, rsi
0x180026132  jz      short loc_18002616C
0x180026134  call    cs:__imp_GetLastError
0x18002613a  xor     r9d, r9d; msWindowLength
0x18002613d  xor     r8d, r8d; msPeriod
0x180026140  xor     edx, edx; pftDueTime
0x180026142  mov     rcx, rsi; pti
0x180026145  mov     ebx, eax
0x180026147  call    cs:__imp_SetThreadpoolTimer
0x18002614d  mov     edx, 1; fCancelPendingCallbacks
0x180026152  mov     rcx, rsi; pti
0x180026155  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18002615b  mov     rcx, rsi; pti
0x18002615e  call    cs:__imp_CloseThreadpoolTimer
0x180026164  mov     ecx, ebx; dwErrCode
0x180026166  call    cs:__imp_SetLastError
0x18002616c  mov     ecx, ebp; dwErrCode
0x18002616e  mov     [rdi+38h], r14
0x180026172  call    cs:__imp_SetLastError
0x180026178  mov     rcx, [rdi+38h]; pti
0x18002617c  test    rcx, rcx
0x18002617f  jz      short loc_1800261A2
0x180026181  mov     r9d, 4E2h; msWindowLength
0x180026187  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180026190  xor     r8d, r8d; msPeriod
0x180026193  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x180026198  call    cs:__imp_SetThreadpoolTimer
0x18002619e  mov     byte ptr [rdi+40h], 1
0x1800261a2  mov     rcx, [rsp+48h+var_20]
0x1800261a7  xor     rcx, rsp; StackCookie
0x1800261aa  call    __security_check_cookie
0x1800261af  mov     rbx, [rsp+48h+arg_8]
0x1800261b4  mov     rbp, [rsp+48h+arg_10]
0x1800261b9  add     rsp, 30h
0x1800261bd  pop     r14
0x1800261bf  pop     rdi
0x1800261c0  pop     rsi
0x1800261c1  retn
```
