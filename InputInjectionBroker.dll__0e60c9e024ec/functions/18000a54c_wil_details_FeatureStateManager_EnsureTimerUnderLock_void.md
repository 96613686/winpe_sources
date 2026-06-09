# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x18000a54c`
- end: `0x18000a620`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d09c`

## callees

- `0x18000a54c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a5cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a5d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a5cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a5d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a572`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a599`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a572`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a599`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000a587`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000a587`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a5ba`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a5ba`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a5c3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a5c3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a5ac`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a603`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a5ac`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a603`

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
0x18000a54c  mov     [rsp+arg_8], rbx
0x18000a551  mov     [rsp+arg_10], rbp
0x18000a556  push    rsi
0x18000a557  push    rdi
0x18000a558  push    r14
0x18000a55a  sub     rsp, 20h
0x18000a55e  cmp     byte ptr [rcx+41h], 0
0x18000a562  mov     rdi, rcx
0x18000a565  jnz     loc_18000A60D
0x18000a56b  cmp     qword ptr [rcx+30h], 0
0x18000a570  jnz     short loc_18000A5DD
0x18000a572  call    cs:__imp_GetLastError
0x18000a578  xor     r8d, r8d; pcbe
0x18000a57b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000a582  mov     rdx, rdi; pv
0x18000a585  mov     ebp, eax
0x18000a587  call    cs:__imp_CreateThreadpoolTimer
0x18000a58d  mov     rsi, [rdi+30h]
0x18000a591  mov     r14, rax
0x18000a594  test    rsi, rsi
0x18000a597  jz      short loc_18000A5D1
0x18000a599  call    cs:__imp_GetLastError
0x18000a59f  xor     r9d, r9d; msWindowLength
0x18000a5a2  xor     r8d, r8d; msPeriod
0x18000a5a5  xor     edx, edx; pftDueTime
0x18000a5a7  mov     rcx, rsi; pti
0x18000a5aa  mov     ebx, eax
0x18000a5ac  call    cs:__imp_SetThreadpoolTimer
0x18000a5b2  mov     edx, 1; fCancelPendingCallbacks
0x18000a5b7  mov     rcx, rsi; pti
0x18000a5ba  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000a5c0  mov     rcx, rsi; pti
0x18000a5c3  call    cs:__imp_CloseThreadpoolTimer
0x18000a5c9  mov     ecx, ebx; dwErrCode
0x18000a5cb  call    cs:__imp_SetLastError
0x18000a5d1  mov     ecx, ebp; dwErrCode
0x18000a5d3  mov     [rdi+30h], r14
0x18000a5d7  call    cs:__imp_SetLastError
0x18000a5dd  mov     rcx, [rdi+30h]; pti
0x18000a5e1  test    rcx, rcx
0x18000a5e4  jz      short loc_18000A60D
0x18000a5e6  mov     rax, 0FFFFFFFF4D2FA200h
0x18000a5f0  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x18000a5f5  mov     r9d, 124F8h; msWindowLength
0x18000a5fb  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x18000a600  xor     r8d, r8d; msPeriod
0x18000a603  call    cs:__imp_SetThreadpoolTimer
0x18000a609  mov     byte ptr [rdi+41h], 1
0x18000a60d  mov     rbx, [rsp+38h+arg_8]
0x18000a612  mov     rbp, [rsp+38h+arg_10]
0x18000a617  add     rsp, 20h
0x18000a61b  pop     r14
0x18000a61d  pop     rdi
0x18000a61e  pop     rsi
0x18000a61f  retn
```
