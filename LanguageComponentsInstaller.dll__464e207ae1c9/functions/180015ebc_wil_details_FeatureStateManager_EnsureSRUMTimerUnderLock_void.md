# wil::details::FeatureStateManager::EnsureSRUMTimerUnderLock(void)

- ea: `0x180015ebc`
- end: `0x180015fa6`
- name: `?EnsureSRUMTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `234`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001977c`

## callees

- `0x180003520`
- `0x180015ebc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015f4a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015f56`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015f4a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015f56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015ef1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015f18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015ef1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015f18`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180015f42`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180015f42`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180015f06`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180015f06`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180015f2b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180015f7c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180015f2b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180015f7c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180015f39`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180015f39`

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
0x180015ebc  mov     [rsp+arg_8], rbx
0x180015ec1  mov     [rsp+arg_10], rbp
0x180015ec6  push    rsi
0x180015ec7  push    rdi
0x180015ec8  push    r14
0x180015eca  sub     rsp, 30h
0x180015ece  mov     rax, cs:__security_cookie
0x180015ed5  xor     rax, rsp
0x180015ed8  mov     [rsp+48h+var_20], rax
0x180015edd  cmp     byte ptr [rcx+40h], 0
0x180015ee1  mov     rdi, rcx
0x180015ee4  jnz     loc_180015F86
0x180015eea  cmp     qword ptr [rcx+38h], 0
0x180015eef  jnz     short loc_180015F5C
0x180015ef1  call    cs:__imp_GetLastError
0x180015ef7  xor     r8d, r8d; pcbe
0x180015efa  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180015f01  mov     rdx, rdi; pv
0x180015f04  mov     ebp, eax
0x180015f06  call    cs:__imp_CreateThreadpoolTimer
0x180015f0c  mov     rsi, [rdi+38h]
0x180015f10  mov     r14, rax
0x180015f13  test    rsi, rsi
0x180015f16  jz      short loc_180015F50
0x180015f18  call    cs:__imp_GetLastError
0x180015f1e  xor     r9d, r9d; msWindowLength
0x180015f21  xor     r8d, r8d; msPeriod
0x180015f24  xor     edx, edx; pftDueTime
0x180015f26  mov     rcx, rsi; pti
0x180015f29  mov     ebx, eax
0x180015f2b  call    cs:__imp_SetThreadpoolTimer
0x180015f31  mov     edx, 1; fCancelPendingCallbacks
0x180015f36  mov     rcx, rsi; pti
0x180015f39  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180015f3f  mov     rcx, rsi; pti
0x180015f42  call    cs:__imp_CloseThreadpoolTimer
0x180015f48  mov     ecx, ebx; dwErrCode
0x180015f4a  call    cs:__imp_SetLastError
0x180015f50  mov     ecx, ebp; dwErrCode
0x180015f52  mov     [rdi+38h], r14
0x180015f56  call    cs:__imp_SetLastError
0x180015f5c  mov     rcx, [rdi+38h]; pti
0x180015f60  test    rcx, rcx
0x180015f63  jz      short loc_180015F86
0x180015f65  mov     r9d, 4E2h; msWindowLength
0x180015f6b  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180015f74  xor     r8d, r8d; msPeriod
0x180015f77  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x180015f7c  call    cs:__imp_SetThreadpoolTimer
0x180015f82  mov     byte ptr [rdi+40h], 1
0x180015f86  mov     rcx, [rsp+48h+var_20]
0x180015f8b  xor     rcx, rsp; StackCookie
0x180015f8e  call    __security_check_cookie
0x180015f93  mov     rbx, [rsp+48h+arg_8]
0x180015f98  mov     rbp, [rsp+48h+arg_10]
0x180015f9d  add     rsp, 30h
0x180015fa1  pop     r14
0x180015fa3  pop     rdi
0x180015fa4  pop     rsi
0x180015fa5  retn
```
