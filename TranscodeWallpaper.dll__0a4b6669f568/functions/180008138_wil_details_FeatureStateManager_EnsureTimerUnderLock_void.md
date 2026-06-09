# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180008138`
- end: `0x18000820c`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180008ff0`

## callees

- `0x180008138`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000815e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008185`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000815e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008185`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800081b7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800081c3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800081b7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800081c3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800081af`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800081af`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800081a6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800081a6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008198`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800081ef`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008198`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800081ef`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180008173`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180008173`

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
0x180008138  mov     [rsp+arg_8], rbx
0x18000813d  mov     [rsp+arg_10], rbp
0x180008142  push    rsi
0x180008143  push    rdi
0x180008144  push    r14
0x180008146  sub     rsp, 20h
0x18000814a  cmp     byte ptr [rcx+41h], 0
0x18000814e  mov     rdi, rcx
0x180008151  jnz     loc_1800081F9
0x180008157  cmp     qword ptr [rcx+30h], 0
0x18000815c  jnz     short loc_1800081C9
0x18000815e  call    cs:__imp_GetLastError
0x180008164  xor     r8d, r8d; pcbe
0x180008167  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000816e  mov     rdx, rdi; pv
0x180008171  mov     ebp, eax
0x180008173  call    cs:__imp_CreateThreadpoolTimer
0x180008179  mov     rsi, [rdi+30h]
0x18000817d  mov     r14, rax
0x180008180  test    rsi, rsi
0x180008183  jz      short loc_1800081BD
0x180008185  call    cs:__imp_GetLastError
0x18000818b  xor     r9d, r9d; msWindowLength
0x18000818e  xor     r8d, r8d; msPeriod
0x180008191  xor     edx, edx; pftDueTime
0x180008193  mov     rcx, rsi; pti
0x180008196  mov     ebx, eax
0x180008198  call    cs:__imp_SetThreadpoolTimer
0x18000819e  mov     edx, 1; fCancelPendingCallbacks
0x1800081a3  mov     rcx, rsi; pti
0x1800081a6  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800081ac  mov     rcx, rsi; pti
0x1800081af  call    cs:__imp_CloseThreadpoolTimer
0x1800081b5  mov     ecx, ebx; dwErrCode
0x1800081b7  call    cs:__imp_SetLastError
0x1800081bd  mov     ecx, ebp; dwErrCode
0x1800081bf  mov     [rdi+30h], r14
0x1800081c3  call    cs:__imp_SetLastError
0x1800081c9  mov     rcx, [rdi+30h]; pti
0x1800081cd  test    rcx, rcx
0x1800081d0  jz      short loc_1800081F9
0x1800081d2  mov     rax, 0FFFFFFFF4D2FA200h
0x1800081dc  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x1800081e1  mov     r9d, 124F8h; msWindowLength
0x1800081e7  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x1800081ec  xor     r8d, r8d; msPeriod
0x1800081ef  call    cs:__imp_SetThreadpoolTimer
0x1800081f5  mov     byte ptr [rdi+41h], 1
0x1800081f9  mov     rbx, [rsp+38h+arg_8]
0x1800081fe  mov     rbp, [rsp+38h+arg_10]
0x180008203  add     rsp, 20h
0x180008207  pop     r14
0x180008209  pop     rdi
0x18000820a  pop     rsi
0x18000820b  retn
```
