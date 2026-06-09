# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180004308`
- end: `0x1800043dc`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005dc4`

## callees

- `0x180004308`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000432e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004355`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000432e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004355`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004387`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004393`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004387`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004393`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000437f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000437f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004368`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800043bf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004368`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800043bf`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180004343`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180004343`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004376`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004376`

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
0x180004308  mov     [rsp+arg_8], rbx
0x18000430d  mov     [rsp+arg_10], rbp
0x180004312  push    rsi
0x180004313  push    rdi
0x180004314  push    r14
0x180004316  sub     rsp, 20h
0x18000431a  cmp     byte ptr [rcx+41h], 0
0x18000431e  mov     rdi, rcx
0x180004321  jnz     loc_1800043C9
0x180004327  cmp     qword ptr [rcx+30h], 0
0x18000432c  jnz     short loc_180004399
0x18000432e  call    cs:__imp_GetLastError
0x180004334  xor     r8d, r8d; pcbe
0x180004337  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000433e  mov     rdx, rdi; pv
0x180004341  mov     ebp, eax
0x180004343  call    cs:__imp_CreateThreadpoolTimer
0x180004349  mov     rsi, [rdi+30h]
0x18000434d  mov     r14, rax
0x180004350  test    rsi, rsi
0x180004353  jz      short loc_18000438D
0x180004355  call    cs:__imp_GetLastError
0x18000435b  xor     r9d, r9d; msWindowLength
0x18000435e  xor     r8d, r8d; msPeriod
0x180004361  xor     edx, edx; pftDueTime
0x180004363  mov     rcx, rsi; pti
0x180004366  mov     ebx, eax
0x180004368  call    cs:__imp_SetThreadpoolTimer
0x18000436e  mov     edx, 1; fCancelPendingCallbacks
0x180004373  mov     rcx, rsi; pti
0x180004376  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000437c  mov     rcx, rsi; pti
0x18000437f  call    cs:__imp_CloseThreadpoolTimer
0x180004385  mov     ecx, ebx; dwErrCode
0x180004387  call    cs:__imp_SetLastError
0x18000438d  mov     ecx, ebp; dwErrCode
0x18000438f  mov     [rdi+30h], r14
0x180004393  call    cs:__imp_SetLastError
0x180004399  mov     rcx, [rdi+30h]; pti
0x18000439d  test    rcx, rcx
0x1800043a0  jz      short loc_1800043C9
0x1800043a2  mov     rax, 0FFFFFFFF4D2FA200h
0x1800043ac  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x1800043b1  mov     r9d, 124F8h; msWindowLength
0x1800043b7  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x1800043bc  xor     r8d, r8d; msPeriod
0x1800043bf  call    cs:__imp_SetThreadpoolTimer
0x1800043c5  mov     byte ptr [rdi+41h], 1
0x1800043c9  mov     rbx, [rsp+38h+arg_8]
0x1800043ce  mov     rbp, [rsp+38h+arg_10]
0x1800043d3  add     rsp, 20h
0x1800043d7  pop     r14
0x1800043d9  pop     rdi
0x1800043da  pop     rsi
0x1800043db  retn
```
