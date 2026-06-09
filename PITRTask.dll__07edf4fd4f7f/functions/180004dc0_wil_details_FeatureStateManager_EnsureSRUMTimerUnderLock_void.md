# wil::details::FeatureStateManager::EnsureSRUMTimerUnderLock(void)

- ea: `0x180004dc0`
- end: `0x180004eaa`
- name: `?EnsureSRUMTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `234`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180009f30`

## callees

- `0x180004dc0`
- `0x1800107c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004df5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004e1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004df5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004e1c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004e4e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004e5a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004e4e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004e5a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004e2f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004e80`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004e2f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004e80`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180004e0a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180004e0a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004e46`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004e46`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004e3d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004e3d`

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
0x180004dc0  mov     [rsp+arg_8], rbx
0x180004dc5  mov     [rsp+arg_10], rbp
0x180004dca  push    rsi
0x180004dcb  push    rdi
0x180004dcc  push    r14
0x180004dce  sub     rsp, 30h
0x180004dd2  mov     rax, cs:__security_cookie
0x180004dd9  xor     rax, rsp
0x180004ddc  mov     [rsp+48h+var_20], rax
0x180004de1  cmp     byte ptr [rcx+40h], 0
0x180004de5  mov     rdi, rcx
0x180004de8  jnz     loc_180004E8A
0x180004dee  cmp     qword ptr [rcx+38h], 0
0x180004df3  jnz     short loc_180004E60
0x180004df5  call    cs:__imp_GetLastError
0x180004dfb  xor     r8d, r8d; pcbe
0x180004dfe  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180004e05  mov     rdx, rdi; pv
0x180004e08  mov     ebp, eax
0x180004e0a  call    cs:__imp_CreateThreadpoolTimer
0x180004e10  mov     rsi, [rdi+38h]
0x180004e14  mov     r14, rax
0x180004e17  test    rsi, rsi
0x180004e1a  jz      short loc_180004E54
0x180004e1c  call    cs:__imp_GetLastError
0x180004e22  xor     r9d, r9d; msWindowLength
0x180004e25  xor     r8d, r8d; msPeriod
0x180004e28  xor     edx, edx; pftDueTime
0x180004e2a  mov     rcx, rsi; pti
0x180004e2d  mov     ebx, eax
0x180004e2f  call    cs:__imp_SetThreadpoolTimer
0x180004e35  mov     edx, 1; fCancelPendingCallbacks
0x180004e3a  mov     rcx, rsi; pti
0x180004e3d  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180004e43  mov     rcx, rsi; pti
0x180004e46  call    cs:__imp_CloseThreadpoolTimer
0x180004e4c  mov     ecx, ebx; dwErrCode
0x180004e4e  call    cs:__imp_SetLastError
0x180004e54  mov     ecx, ebp; dwErrCode
0x180004e56  mov     [rdi+38h], r14
0x180004e5a  call    cs:__imp_SetLastError
0x180004e60  mov     rcx, [rdi+38h]; pti
0x180004e64  test    rcx, rcx
0x180004e67  jz      short loc_180004E8A
0x180004e69  mov     r9d, 4E2h; msWindowLength
0x180004e6f  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180004e78  xor     r8d, r8d; msPeriod
0x180004e7b  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x180004e80  call    cs:__imp_SetThreadpoolTimer
0x180004e86  mov     byte ptr [rdi+40h], 1
0x180004e8a  mov     rcx, [rsp+48h+var_20]
0x180004e8f  xor     rcx, rsp; StackCookie
0x180004e92  call    __security_check_cookie
0x180004e97  mov     rbx, [rsp+48h+arg_8]
0x180004e9c  mov     rbp, [rsp+48h+arg_10]
0x180004ea1  add     rsp, 30h
0x180004ea5  pop     r14
0x180004ea7  pop     rdi
0x180004ea8  pop     rsi
0x180004ea9  retn
```
