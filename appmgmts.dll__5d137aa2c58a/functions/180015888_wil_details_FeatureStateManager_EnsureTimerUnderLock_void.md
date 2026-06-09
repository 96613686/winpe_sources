# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180015888`
- end: `0x18001595c`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180017314`

## callees

- `0x180015888`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800158ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800158d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800158ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800158d5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015907`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015913`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015907`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015913`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800158c3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800158c3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800158ff`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800158ff`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800158f6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800158f6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800158e8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001593f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800158e8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001593f`

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
0x180015888  mov     [rsp+arg_8], rbx
0x18001588d  mov     [rsp+arg_10], rbp
0x180015892  push    rsi
0x180015893  push    rdi
0x180015894  push    r14
0x180015896  sub     rsp, 20h
0x18001589a  cmp     byte ptr [rcx+41h], 0
0x18001589e  mov     rdi, rcx
0x1800158a1  jnz     loc_180015949
0x1800158a7  cmp     qword ptr [rcx+30h], 0
0x1800158ac  jnz     short loc_180015919
0x1800158ae  call    cs:__imp_GetLastError
0x1800158b4  xor     r8d, r8d; pcbe
0x1800158b7  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800158be  mov     rdx, rdi; pv
0x1800158c1  mov     ebp, eax
0x1800158c3  call    cs:__imp_CreateThreadpoolTimer
0x1800158c9  mov     rsi, [rdi+30h]
0x1800158cd  mov     r14, rax
0x1800158d0  test    rsi, rsi
0x1800158d3  jz      short loc_18001590D
0x1800158d5  call    cs:__imp_GetLastError
0x1800158db  xor     r9d, r9d; msWindowLength
0x1800158de  xor     r8d, r8d; msPeriod
0x1800158e1  xor     edx, edx; pftDueTime
0x1800158e3  mov     rcx, rsi; pti
0x1800158e6  mov     ebx, eax
0x1800158e8  call    cs:__imp_SetThreadpoolTimer
0x1800158ee  mov     edx, 1; fCancelPendingCallbacks
0x1800158f3  mov     rcx, rsi; pti
0x1800158f6  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800158fc  mov     rcx, rsi; pti
0x1800158ff  call    cs:__imp_CloseThreadpoolTimer
0x180015905  mov     ecx, ebx; dwErrCode
0x180015907  call    cs:__imp_SetLastError
0x18001590d  mov     ecx, ebp; dwErrCode
0x18001590f  mov     [rdi+30h], r14
0x180015913  call    cs:__imp_SetLastError
0x180015919  mov     rcx, [rdi+30h]; pti
0x18001591d  test    rcx, rcx
0x180015920  jz      short loc_180015949
0x180015922  mov     rax, 0FFFFFFFF4D2FA200h
0x18001592c  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180015931  mov     r9d, 124F8h; msWindowLength
0x180015937  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x18001593c  xor     r8d, r8d; msPeriod
0x18001593f  call    cs:__imp_SetThreadpoolTimer
0x180015945  mov     byte ptr [rdi+41h], 1
0x180015949  mov     rbx, [rsp+38h+arg_8]
0x18001594e  mov     rbp, [rsp+38h+arg_10]
0x180015953  add     rsp, 20h
0x180015957  pop     r14
0x180015959  pop     rdi
0x18001595a  pop     rsi
0x18001595b  retn
```
