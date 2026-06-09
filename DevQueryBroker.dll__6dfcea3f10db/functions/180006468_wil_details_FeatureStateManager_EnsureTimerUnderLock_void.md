# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180006468`
- end: `0x18000653c`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007ec4`

## callees

- `0x180006468`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800064e7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800064f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800064e7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800064f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000648e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800064b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000648e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800064b5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800064a3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800064a3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800064d6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800064d6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800064df`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800064df`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800064c8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000651f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800064c8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000651f`

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
0x180006468  mov     [rsp+arg_8], rbx
0x18000646d  mov     [rsp+arg_10], rbp
0x180006472  push    rsi
0x180006473  push    rdi
0x180006474  push    r14
0x180006476  sub     rsp, 20h
0x18000647a  cmp     byte ptr [rcx+41h], 0
0x18000647e  mov     rdi, rcx
0x180006481  jnz     loc_180006529
0x180006487  cmp     qword ptr [rcx+30h], 0
0x18000648c  jnz     short loc_1800064F9
0x18000648e  call    cs:__imp_GetLastError
0x180006494  xor     r8d, r8d; pcbe
0x180006497  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000649e  mov     rdx, rdi; pv
0x1800064a1  mov     ebp, eax
0x1800064a3  call    cs:__imp_CreateThreadpoolTimer
0x1800064a9  mov     rsi, [rdi+30h]
0x1800064ad  mov     r14, rax
0x1800064b0  test    rsi, rsi
0x1800064b3  jz      short loc_1800064ED
0x1800064b5  call    cs:__imp_GetLastError
0x1800064bb  xor     r9d, r9d; msWindowLength
0x1800064be  xor     r8d, r8d; msPeriod
0x1800064c1  xor     edx, edx; pftDueTime
0x1800064c3  mov     rcx, rsi; pti
0x1800064c6  mov     ebx, eax
0x1800064c8  call    cs:__imp_SetThreadpoolTimer
0x1800064ce  mov     edx, 1; fCancelPendingCallbacks
0x1800064d3  mov     rcx, rsi; pti
0x1800064d6  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800064dc  mov     rcx, rsi; pti
0x1800064df  call    cs:__imp_CloseThreadpoolTimer
0x1800064e5  mov     ecx, ebx; dwErrCode
0x1800064e7  call    cs:__imp_SetLastError
0x1800064ed  mov     ecx, ebp; dwErrCode
0x1800064ef  mov     [rdi+30h], r14
0x1800064f3  call    cs:__imp_SetLastError
0x1800064f9  mov     rcx, [rdi+30h]; pti
0x1800064fd  test    rcx, rcx
0x180006500  jz      short loc_180006529
0x180006502  mov     rax, 0FFFFFFFF4D2FA200h
0x18000650c  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180006511  mov     r9d, 124F8h; msWindowLength
0x180006517  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x18000651c  xor     r8d, r8d; msPeriod
0x18000651f  call    cs:__imp_SetThreadpoolTimer
0x180006525  mov     byte ptr [rdi+41h], 1
0x180006529  mov     rbx, [rsp+38h+arg_8]
0x18000652e  mov     rbp, [rsp+38h+arg_10]
0x180006533  add     rsp, 20h
0x180006537  pop     r14
0x180006539  pop     rdi
0x18000653a  pop     rsi
0x18000653b  retn
```
