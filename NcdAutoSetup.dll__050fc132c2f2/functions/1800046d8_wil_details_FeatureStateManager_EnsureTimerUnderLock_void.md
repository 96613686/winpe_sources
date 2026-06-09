# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x1800046d8`
- end: `0x1800047ac`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180006414`

## callees

- `0x1800046d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004725`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004725`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004757`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004763`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004757`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004763`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000474f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000474f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004738`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000478f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004738`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000478f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180004713`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180004713`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004746`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004746`

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
0x1800046d8  mov     [rsp+arg_8], rbx
0x1800046dd  mov     [rsp+arg_10], rbp
0x1800046e2  push    rsi
0x1800046e3  push    rdi
0x1800046e4  push    r14
0x1800046e6  sub     rsp, 20h
0x1800046ea  cmp     byte ptr [rcx+41h], 0
0x1800046ee  mov     rdi, rcx
0x1800046f1  jnz     loc_180004799
0x1800046f7  cmp     qword ptr [rcx+30h], 0
0x1800046fc  jnz     short loc_180004769
0x1800046fe  call    cs:__imp_GetLastError
0x180004704  xor     r8d, r8d; pcbe
0x180004707  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000470e  mov     rdx, rdi; pv
0x180004711  mov     ebp, eax
0x180004713  call    cs:__imp_CreateThreadpoolTimer
0x180004719  mov     rsi, [rdi+30h]
0x18000471d  mov     r14, rax
0x180004720  test    rsi, rsi
0x180004723  jz      short loc_18000475D
0x180004725  call    cs:__imp_GetLastError
0x18000472b  xor     r9d, r9d; msWindowLength
0x18000472e  xor     r8d, r8d; msPeriod
0x180004731  xor     edx, edx; pftDueTime
0x180004733  mov     rcx, rsi; pti
0x180004736  mov     ebx, eax
0x180004738  call    cs:__imp_SetThreadpoolTimer
0x18000473e  mov     edx, 1; fCancelPendingCallbacks
0x180004743  mov     rcx, rsi; pti
0x180004746  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000474c  mov     rcx, rsi; pti
0x18000474f  call    cs:__imp_CloseThreadpoolTimer
0x180004755  mov     ecx, ebx; dwErrCode
0x180004757  call    cs:__imp_SetLastError
0x18000475d  mov     ecx, ebp; dwErrCode
0x18000475f  mov     [rdi+30h], r14
0x180004763  call    cs:__imp_SetLastError
0x180004769  mov     rcx, [rdi+30h]; pti
0x18000476d  test    rcx, rcx
0x180004770  jz      short loc_180004799
0x180004772  mov     rax, 0FFFFFFFF4D2FA200h
0x18000477c  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180004781  mov     r9d, 124F8h; msWindowLength
0x180004787  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x18000478c  xor     r8d, r8d; msPeriod
0x18000478f  call    cs:__imp_SetThreadpoolTimer
0x180004795  mov     byte ptr [rdi+41h], 1
0x180004799  mov     rbx, [rsp+38h+arg_8]
0x18000479e  mov     rbp, [rsp+38h+arg_10]
0x1800047a3  add     rsp, 20h
0x1800047a7  pop     r14
0x1800047a9  pop     rdi
0x1800047aa  pop     rsi
0x1800047ab  retn
```
