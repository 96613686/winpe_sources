# wil::details::FeatureStateManager::EnsureSRUMTimerUnderLock(void)

- ea: `0x18000ca18`
- end: `0x18000cb02`
- name: `?EnsureSRUMTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `234`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001d5c0`

## callees

- `0x18000ca18`
- `0x180050300`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000caa6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cab2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000caa6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cab2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ca4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ca74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ca4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ca74`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ca95`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ca95`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000ca62`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000ca62`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000ca9e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000ca9e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ca87`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000cad8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ca87`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000cad8`

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
0x18000ca18  mov     [rsp+arg_8], rbx
0x18000ca1d  mov     [rsp+arg_10], rbp
0x18000ca22  push    rsi
0x18000ca23  push    rdi
0x18000ca24  push    r14
0x18000ca26  sub     rsp, 30h
0x18000ca2a  mov     rax, cs:__security_cookie
0x18000ca31  xor     rax, rsp
0x18000ca34  mov     [rsp+48h+var_20], rax
0x18000ca39  cmp     byte ptr [rcx+40h], 0
0x18000ca3d  mov     rdi, rcx
0x18000ca40  jnz     loc_18000CAE2
0x18000ca46  cmp     qword ptr [rcx+38h], 0
0x18000ca4b  jnz     short loc_18000CAB8
0x18000ca4d  call    cs:__imp_GetLastError
0x18000ca53  xor     r8d, r8d; pcbe
0x18000ca56  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000ca5d  mov     rdx, rdi; pv
0x18000ca60  mov     ebp, eax
0x18000ca62  call    cs:__imp_CreateThreadpoolTimer
0x18000ca68  mov     rsi, [rdi+38h]
0x18000ca6c  mov     r14, rax
0x18000ca6f  test    rsi, rsi
0x18000ca72  jz      short loc_18000CAAC
0x18000ca74  call    cs:__imp_GetLastError
0x18000ca7a  xor     r9d, r9d; msWindowLength
0x18000ca7d  xor     r8d, r8d; msPeriod
0x18000ca80  xor     edx, edx; pftDueTime
0x18000ca82  mov     rcx, rsi; pti
0x18000ca85  mov     ebx, eax
0x18000ca87  call    cs:__imp_SetThreadpoolTimer
0x18000ca8d  mov     edx, 1; fCancelPendingCallbacks
0x18000ca92  mov     rcx, rsi; pti
0x18000ca95  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000ca9b  mov     rcx, rsi; pti
0x18000ca9e  call    cs:__imp_CloseThreadpoolTimer
0x18000caa4  mov     ecx, ebx; dwErrCode
0x18000caa6  call    cs:__imp_SetLastError
0x18000caac  mov     ecx, ebp; dwErrCode
0x18000caae  mov     [rdi+38h], r14
0x18000cab2  call    cs:__imp_SetLastError
0x18000cab8  mov     rcx, [rdi+38h]; pti
0x18000cabc  test    rcx, rcx
0x18000cabf  jz      short loc_18000CAE2
0x18000cac1  mov     r9d, 4E2h; msWindowLength
0x18000cac7  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000cad0  xor     r8d, r8d; msPeriod
0x18000cad3  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x18000cad8  call    cs:__imp_SetThreadpoolTimer
0x18000cade  mov     byte ptr [rdi+40h], 1
0x18000cae2  mov     rcx, [rsp+48h+var_20]
0x18000cae7  xor     rcx, rsp; StackCookie
0x18000caea  call    __security_check_cookie
0x18000caef  mov     rbx, [rsp+48h+arg_8]
0x18000caf4  mov     rbp, [rsp+48h+arg_10]
0x18000caf9  add     rsp, 30h
0x18000cafd  pop     r14
0x18000caff  pop     rdi
0x18000cb00  pop     rsi
0x18000cb01  retn
```
