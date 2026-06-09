# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x140004aa4`
- end: `0x140004b78`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140008634`

## callees

- `0x140004aa4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140004b12`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140004b12`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140004adf`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140004adf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140004b04`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140004b5b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140004b04`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140004b5b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140004b1b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140004b1b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004b23`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004b2f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004b23`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004b2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004aca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004af1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004aca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004af1`

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
0x140004aa4  mov     [rsp+arg_8], rbx
0x140004aa9  mov     [rsp+arg_10], rbp
0x140004aae  push    rsi
0x140004aaf  push    rdi
0x140004ab0  push    r14
0x140004ab2  sub     rsp, 20h
0x140004ab6  cmp     byte ptr [rcx+41h], 0
0x140004aba  mov     rdi, rcx
0x140004abd  jnz     loc_140004B65
0x140004ac3  cmp     qword ptr [rcx+30h], 0
0x140004ac8  jnz     short loc_140004B35
0x140004aca  call    cs:__imp_GetLastError
0x140004ad0  xor     r8d, r8d; pcbe
0x140004ad3  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140004ada  mov     rdx, rdi; pv
0x140004add  mov     ebp, eax
0x140004adf  call    cs:__imp_CreateThreadpoolTimer
0x140004ae5  mov     rsi, [rdi+30h]
0x140004ae9  mov     r14, rax
0x140004aec  test    rsi, rsi
0x140004aef  jz      short loc_140004B29
0x140004af1  call    cs:__imp_GetLastError
0x140004af7  xor     r9d, r9d; msWindowLength
0x140004afa  xor     r8d, r8d; msPeriod
0x140004afd  xor     edx, edx; pftDueTime
0x140004aff  mov     rcx, rsi; pti
0x140004b02  mov     ebx, eax
0x140004b04  call    cs:__imp_SetThreadpoolTimer
0x140004b0a  mov     edx, 1; fCancelPendingCallbacks
0x140004b0f  mov     rcx, rsi; pti
0x140004b12  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140004b18  mov     rcx, rsi; pti
0x140004b1b  call    cs:__imp_CloseThreadpoolTimer
0x140004b21  mov     ecx, ebx; dwErrCode
0x140004b23  call    cs:__imp_SetLastError
0x140004b29  mov     ecx, ebp; dwErrCode
0x140004b2b  mov     [rdi+30h], r14
0x140004b2f  call    cs:__imp_SetLastError
0x140004b35  mov     rcx, [rdi+30h]; pti
0x140004b39  test    rcx, rcx
0x140004b3c  jz      short loc_140004B65
0x140004b3e  mov     rax, 0FFFFFFFF4D2FA200h
0x140004b48  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x140004b4d  mov     r9d, 124F8h; msWindowLength
0x140004b53  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x140004b58  xor     r8d, r8d; msPeriod
0x140004b5b  call    cs:__imp_SetThreadpoolTimer
0x140004b61  mov     byte ptr [rdi+41h], 1
0x140004b65  mov     rbx, [rsp+38h+arg_8]
0x140004b6a  mov     rbp, [rsp+38h+arg_10]
0x140004b6f  add     rsp, 20h
0x140004b73  pop     r14
0x140004b75  pop     rdi
0x140004b76  pop     rsi
0x140004b77  retn
```
