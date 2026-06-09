# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180009894`
- end: `0x180009968`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ba94`

## callees

- `0x180009894`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009913`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000991f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009913`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000991f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800098ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800098e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800098ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800098e1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800098f4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000994b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800098f4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000994b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000990b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000990b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800098cf`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800098cf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009902`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009902`

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
0x180009894  mov     [rsp+arg_8], rbx
0x180009899  mov     [rsp+arg_10], rbp
0x18000989e  push    rsi
0x18000989f  push    rdi
0x1800098a0  push    r14
0x1800098a2  sub     rsp, 20h
0x1800098a6  cmp     byte ptr [rcx+41h], 0
0x1800098aa  mov     rdi, rcx
0x1800098ad  jnz     loc_180009955
0x1800098b3  cmp     qword ptr [rcx+30h], 0
0x1800098b8  jnz     short loc_180009925
0x1800098ba  call    cs:__imp_GetLastError
0x1800098c0  xor     r8d, r8d; pcbe
0x1800098c3  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800098ca  mov     rdx, rdi; pv
0x1800098cd  mov     ebp, eax
0x1800098cf  call    cs:__imp_CreateThreadpoolTimer
0x1800098d5  mov     rsi, [rdi+30h]
0x1800098d9  mov     r14, rax
0x1800098dc  test    rsi, rsi
0x1800098df  jz      short loc_180009919
0x1800098e1  call    cs:__imp_GetLastError
0x1800098e7  xor     r9d, r9d; msWindowLength
0x1800098ea  xor     r8d, r8d; msPeriod
0x1800098ed  xor     edx, edx; pftDueTime
0x1800098ef  mov     rcx, rsi; pti
0x1800098f2  mov     ebx, eax
0x1800098f4  call    cs:__imp_SetThreadpoolTimer
0x1800098fa  mov     edx, 1; fCancelPendingCallbacks
0x1800098ff  mov     rcx, rsi; pti
0x180009902  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009908  mov     rcx, rsi; pti
0x18000990b  call    cs:__imp_CloseThreadpoolTimer
0x180009911  mov     ecx, ebx; dwErrCode
0x180009913  call    cs:__imp_SetLastError
0x180009919  mov     ecx, ebp; dwErrCode
0x18000991b  mov     [rdi+30h], r14
0x18000991f  call    cs:__imp_SetLastError
0x180009925  mov     rcx, [rdi+30h]; pti
0x180009929  test    rcx, rcx
0x18000992c  jz      short loc_180009955
0x18000992e  mov     rax, 0FFFFFFFF4D2FA200h
0x180009938  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x18000993d  mov     r9d, 124F8h; msWindowLength
0x180009943  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x180009948  xor     r8d, r8d; msPeriod
0x18000994b  call    cs:__imp_SetThreadpoolTimer
0x180009951  mov     byte ptr [rdi+41h], 1
0x180009955  mov     rbx, [rsp+38h+arg_8]
0x18000995a  mov     rbp, [rsp+38h+arg_10]
0x18000995f  add     rsp, 20h
0x180009963  pop     r14
0x180009965  pop     rdi
0x180009966  pop     rsi
0x180009967  retn
```
