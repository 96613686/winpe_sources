# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x18000aa50`
- end: `0x18000ab24`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f2f4`

## callees

- `0x18000aa50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aa76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aa9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aa76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aa9d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000aacf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000aadb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000aacf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000aadb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000aa8b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000aa8b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000aab0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ab07`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000aab0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ab07`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000aac7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000aac7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000aabe`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000aabe`

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
0x18000aa50  mov     [rsp+arg_8], rbx
0x18000aa55  mov     [rsp+arg_10], rbp
0x18000aa5a  push    rsi
0x18000aa5b  push    rdi
0x18000aa5c  push    r14
0x18000aa5e  sub     rsp, 20h
0x18000aa62  cmp     byte ptr [rcx+41h], 0
0x18000aa66  mov     rdi, rcx
0x18000aa69  jnz     loc_18000AB11
0x18000aa6f  cmp     qword ptr [rcx+30h], 0
0x18000aa74  jnz     short loc_18000AAE1
0x18000aa76  call    cs:__imp_GetLastError
0x18000aa7c  xor     r8d, r8d; pcbe
0x18000aa7f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000aa86  mov     rdx, rdi; pv
0x18000aa89  mov     ebp, eax
0x18000aa8b  call    cs:__imp_CreateThreadpoolTimer
0x18000aa91  mov     rsi, [rdi+30h]
0x18000aa95  mov     r14, rax
0x18000aa98  test    rsi, rsi
0x18000aa9b  jz      short loc_18000AAD5
0x18000aa9d  call    cs:__imp_GetLastError
0x18000aaa3  xor     r9d, r9d; msWindowLength
0x18000aaa6  xor     r8d, r8d; msPeriod
0x18000aaa9  xor     edx, edx; pftDueTime
0x18000aaab  mov     rcx, rsi; pti
0x18000aaae  mov     ebx, eax
0x18000aab0  call    cs:__imp_SetThreadpoolTimer
0x18000aab6  mov     edx, 1; fCancelPendingCallbacks
0x18000aabb  mov     rcx, rsi; pti
0x18000aabe  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000aac4  mov     rcx, rsi; pti
0x18000aac7  call    cs:__imp_CloseThreadpoolTimer
0x18000aacd  mov     ecx, ebx; dwErrCode
0x18000aacf  call    cs:__imp_SetLastError
0x18000aad5  mov     ecx, ebp; dwErrCode
0x18000aad7  mov     [rdi+30h], r14
0x18000aadb  call    cs:__imp_SetLastError
0x18000aae1  mov     rcx, [rdi+30h]; pti
0x18000aae5  test    rcx, rcx
0x18000aae8  jz      short loc_18000AB11
0x18000aaea  mov     rax, 0FFFFFFFF4D2FA200h
0x18000aaf4  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x18000aaf9  mov     r9d, 124F8h; msWindowLength
0x18000aaff  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x18000ab04  xor     r8d, r8d; msPeriod
0x18000ab07  call    cs:__imp_SetThreadpoolTimer
0x18000ab0d  mov     byte ptr [rdi+41h], 1
0x18000ab11  mov     rbx, [rsp+38h+arg_8]
0x18000ab16  mov     rbp, [rsp+38h+arg_10]
0x18000ab1b  add     rsp, 20h
0x18000ab1f  pop     r14
0x18000ab21  pop     rdi
0x18000ab22  pop     rsi
0x18000ab23  retn
```
