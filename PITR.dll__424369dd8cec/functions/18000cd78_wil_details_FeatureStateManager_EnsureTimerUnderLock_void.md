# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x18000cd78`
- end: `0x18000ce68`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `240`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180013a74`

## callees

- `0x18000cd78`
- `0x180050300`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ce06`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ce12`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ce06`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ce12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cdad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cdd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cdad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cdd4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000cdf5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000cdf5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000cdc2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000cdc2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000cdfe`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000cdfe`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000cde7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ce3e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000cde7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ce3e`

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
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-28h] BYREF

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
0x18000cd78  mov     [rsp+arg_8], rbx
0x18000cd7d  mov     [rsp+arg_10], rbp
0x18000cd82  push    rsi
0x18000cd83  push    rdi
0x18000cd84  push    r14
0x18000cd86  sub     rsp, 30h
0x18000cd8a  mov     rax, cs:__security_cookie
0x18000cd91  xor     rax, rsp
0x18000cd94  mov     [rsp+48h+var_20], rax
0x18000cd99  cmp     byte ptr [rcx+41h], 0
0x18000cd9d  mov     rdi, rcx
0x18000cda0  jnz     loc_18000CE48
0x18000cda6  cmp     qword ptr [rcx+30h], 0
0x18000cdab  jnz     short loc_18000CE18
0x18000cdad  call    cs:__imp_GetLastError
0x18000cdb3  xor     r8d, r8d; pcbe
0x18000cdb6  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000cdbd  mov     rdx, rdi; pv
0x18000cdc0  mov     ebp, eax
0x18000cdc2  call    cs:__imp_CreateThreadpoolTimer
0x18000cdc8  mov     rsi, [rdi+30h]
0x18000cdcc  mov     r14, rax
0x18000cdcf  test    rsi, rsi
0x18000cdd2  jz      short loc_18000CE0C
0x18000cdd4  call    cs:__imp_GetLastError
0x18000cdda  xor     r9d, r9d; msWindowLength
0x18000cddd  xor     r8d, r8d; msPeriod
0x18000cde0  xor     edx, edx; pftDueTime
0x18000cde2  mov     rcx, rsi; pti
0x18000cde5  mov     ebx, eax
0x18000cde7  call    cs:__imp_SetThreadpoolTimer
0x18000cded  mov     edx, 1; fCancelPendingCallbacks
0x18000cdf2  mov     rcx, rsi; pti
0x18000cdf5  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000cdfb  mov     rcx, rsi; pti
0x18000cdfe  call    cs:__imp_CloseThreadpoolTimer
0x18000ce04  mov     ecx, ebx; dwErrCode
0x18000ce06  call    cs:__imp_SetLastError
0x18000ce0c  mov     ecx, ebp; dwErrCode
0x18000ce0e  mov     [rdi+30h], r14
0x18000ce12  call    cs:__imp_SetLastError
0x18000ce18  mov     rcx, [rdi+30h]; pti
0x18000ce1c  test    rcx, rcx
0x18000ce1f  jz      short loc_18000CE48
0x18000ce21  mov     rax, 0FFFFFFFF4D2FA200h
0x18000ce2b  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x18000ce30  mov     r9d, 124F8h; msWindowLength
0x18000ce36  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x18000ce3b  xor     r8d, r8d; msPeriod
0x18000ce3e  call    cs:__imp_SetThreadpoolTimer
0x18000ce44  mov     byte ptr [rdi+41h], 1
0x18000ce48  mov     rcx, [rsp+48h+var_20]
0x18000ce4d  xor     rcx, rsp; StackCookie
0x18000ce50  call    __security_check_cookie
0x18000ce55  mov     rbx, [rsp+48h+arg_8]
0x18000ce5a  mov     rbp, [rsp+48h+arg_10]
0x18000ce5f  add     rsp, 30h
0x18000ce63  pop     r14
0x18000ce65  pop     rdi
0x18000ce66  pop     rsi
0x18000ce67  retn
```
