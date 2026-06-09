# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x18000d7e0`
- end: `0x18000d8b4`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f520`

## callees

- `0x18000d7e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d806`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d82d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d806`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d82d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d85f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d86b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d85f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d86b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d84e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d84e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d857`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d857`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000d81b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000d81b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d840`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d897`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d840`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d897`

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
0x18000d7e0  mov     [rsp+arg_8], rbx
0x18000d7e5  mov     [rsp+arg_10], rbp
0x18000d7ea  push    rsi
0x18000d7eb  push    rdi
0x18000d7ec  push    r14
0x18000d7ee  sub     rsp, 20h
0x18000d7f2  cmp     byte ptr [rcx+41h], 0
0x18000d7f6  mov     rdi, rcx
0x18000d7f9  jnz     loc_18000D8A1
0x18000d7ff  cmp     qword ptr [rcx+30h], 0
0x18000d804  jnz     short loc_18000D871
0x18000d806  call    cs:__imp_GetLastError
0x18000d80c  xor     r8d, r8d; pcbe
0x18000d80f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000d816  mov     rdx, rdi; pv
0x18000d819  mov     ebp, eax
0x18000d81b  call    cs:__imp_CreateThreadpoolTimer
0x18000d821  mov     rsi, [rdi+30h]
0x18000d825  mov     r14, rax
0x18000d828  test    rsi, rsi
0x18000d82b  jz      short loc_18000D865
0x18000d82d  call    cs:__imp_GetLastError
0x18000d833  xor     r9d, r9d; msWindowLength
0x18000d836  xor     r8d, r8d; msPeriod
0x18000d839  xor     edx, edx; pftDueTime
0x18000d83b  mov     rcx, rsi; pti
0x18000d83e  mov     ebx, eax
0x18000d840  call    cs:__imp_SetThreadpoolTimer
0x18000d846  mov     edx, 1; fCancelPendingCallbacks
0x18000d84b  mov     rcx, rsi; pti
0x18000d84e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000d854  mov     rcx, rsi; pti
0x18000d857  call    cs:__imp_CloseThreadpoolTimer
0x18000d85d  mov     ecx, ebx; dwErrCode
0x18000d85f  call    cs:__imp_SetLastError
0x18000d865  mov     ecx, ebp; dwErrCode
0x18000d867  mov     [rdi+30h], r14
0x18000d86b  call    cs:__imp_SetLastError
0x18000d871  mov     rcx, [rdi+30h]; pti
0x18000d875  test    rcx, rcx
0x18000d878  jz      short loc_18000D8A1
0x18000d87a  mov     rax, 0FFFFFFFF4D2FA200h
0x18000d884  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x18000d889  mov     r9d, 124F8h; msWindowLength
0x18000d88f  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x18000d894  xor     r8d, r8d; msPeriod
0x18000d897  call    cs:__imp_SetThreadpoolTimer
0x18000d89d  mov     byte ptr [rdi+41h], 1
0x18000d8a1  mov     rbx, [rsp+38h+arg_8]
0x18000d8a6  mov     rbp, [rsp+38h+arg_10]
0x18000d8ab  add     rsp, 20h
0x18000d8af  pop     r14
0x18000d8b1  pop     rdi
0x18000d8b2  pop     rsi
0x18000d8b3  retn
```
