# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x140009aec`
- end: `0x140009bc0`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000b064`

## callees

- `0x140009aec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009b12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009b39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009b12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009b39`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009b6b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009b77`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009b6b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009b77`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140009b5a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140009b5a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140009b27`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140009b27`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140009b63`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140009b63`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140009b4c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140009ba3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140009b4c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140009ba3`

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
0x140009aec  mov     [rsp+arg_8], rbx
0x140009af1  mov     [rsp+arg_10], rbp
0x140009af6  push    rsi
0x140009af7  push    rdi
0x140009af8  push    r14
0x140009afa  sub     rsp, 20h
0x140009afe  cmp     byte ptr [rcx+41h], 0
0x140009b02  mov     rdi, rcx
0x140009b05  jnz     loc_140009BAD
0x140009b0b  cmp     qword ptr [rcx+30h], 0
0x140009b10  jnz     short loc_140009B7D
0x140009b12  call    cs:__imp_GetLastError
0x140009b18  xor     r8d, r8d; pcbe
0x140009b1b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140009b22  mov     rdx, rdi; pv
0x140009b25  mov     ebp, eax
0x140009b27  call    cs:__imp_CreateThreadpoolTimer
0x140009b2d  mov     rsi, [rdi+30h]
0x140009b31  mov     r14, rax
0x140009b34  test    rsi, rsi
0x140009b37  jz      short loc_140009B71
0x140009b39  call    cs:__imp_GetLastError
0x140009b3f  xor     r9d, r9d; msWindowLength
0x140009b42  xor     r8d, r8d; msPeriod
0x140009b45  xor     edx, edx; pftDueTime
0x140009b47  mov     rcx, rsi; pti
0x140009b4a  mov     ebx, eax
0x140009b4c  call    cs:__imp_SetThreadpoolTimer
0x140009b52  mov     edx, 1; fCancelPendingCallbacks
0x140009b57  mov     rcx, rsi; pti
0x140009b5a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140009b60  mov     rcx, rsi; pti
0x140009b63  call    cs:__imp_CloseThreadpoolTimer
0x140009b69  mov     ecx, ebx; dwErrCode
0x140009b6b  call    cs:__imp_SetLastError
0x140009b71  mov     ecx, ebp; dwErrCode
0x140009b73  mov     [rdi+30h], r14
0x140009b77  call    cs:__imp_SetLastError
0x140009b7d  mov     rcx, [rdi+30h]; pti
0x140009b81  test    rcx, rcx
0x140009b84  jz      short loc_140009BAD
0x140009b86  mov     rax, 0FFFFFFFF4D2FA200h
0x140009b90  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x140009b95  mov     r9d, 124F8h; msWindowLength
0x140009b9b  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x140009ba0  xor     r8d, r8d; msPeriod
0x140009ba3  call    cs:__imp_SetThreadpoolTimer
0x140009ba9  mov     byte ptr [rdi+41h], 1
0x140009bad  mov     rbx, [rsp+38h+arg_8]
0x140009bb2  mov     rbp, [rsp+38h+arg_10]
0x140009bb7  add     rsp, 20h
0x140009bbb  pop     r14
0x140009bbd  pop     rdi
0x140009bbe  pop     rsi
0x140009bbf  retn
```
