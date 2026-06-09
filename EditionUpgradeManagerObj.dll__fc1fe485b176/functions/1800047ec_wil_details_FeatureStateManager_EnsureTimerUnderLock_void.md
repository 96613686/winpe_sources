# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x1800047ec`
- end: `0x1800048c0`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180006584`

## callees

- `0x1800047ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000486b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004877`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000486b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004877`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004812`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004839`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004812`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004839`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000485a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000485a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004863`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004863`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180004827`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180004827`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000484c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800048a3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000484c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800048a3`

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
0x1800047ec  mov     [rsp+arg_8], rbx
0x1800047f1  mov     [rsp+arg_10], rbp
0x1800047f6  push    rsi
0x1800047f7  push    rdi
0x1800047f8  push    r14
0x1800047fa  sub     rsp, 20h
0x1800047fe  cmp     byte ptr [rcx+41h], 0
0x180004802  mov     rdi, rcx
0x180004805  jnz     loc_1800048AD
0x18000480b  cmp     qword ptr [rcx+30h], 0
0x180004810  jnz     short loc_18000487D
0x180004812  call    cs:__imp_GetLastError
0x180004818  xor     r8d, r8d; pcbe
0x18000481b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180004822  mov     rdx, rdi; pv
0x180004825  mov     ebp, eax
0x180004827  call    cs:__imp_CreateThreadpoolTimer
0x18000482d  mov     rsi, [rdi+30h]
0x180004831  mov     r14, rax
0x180004834  test    rsi, rsi
0x180004837  jz      short loc_180004871
0x180004839  call    cs:__imp_GetLastError
0x18000483f  xor     r9d, r9d; msWindowLength
0x180004842  xor     r8d, r8d; msPeriod
0x180004845  xor     edx, edx; pftDueTime
0x180004847  mov     rcx, rsi; pti
0x18000484a  mov     ebx, eax
0x18000484c  call    cs:__imp_SetThreadpoolTimer
0x180004852  mov     edx, 1; fCancelPendingCallbacks
0x180004857  mov     rcx, rsi; pti
0x18000485a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180004860  mov     rcx, rsi; pti
0x180004863  call    cs:__imp_CloseThreadpoolTimer
0x180004869  mov     ecx, ebx; dwErrCode
0x18000486b  call    cs:__imp_SetLastError
0x180004871  mov     ecx, ebp; dwErrCode
0x180004873  mov     [rdi+30h], r14
0x180004877  call    cs:__imp_SetLastError
0x18000487d  mov     rcx, [rdi+30h]; pti
0x180004881  test    rcx, rcx
0x180004884  jz      short loc_1800048AD
0x180004886  mov     rax, 0FFFFFFFF4D2FA200h
0x180004890  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180004895  mov     r9d, 124F8h; msWindowLength
0x18000489b  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x1800048a0  xor     r8d, r8d; msPeriod
0x1800048a3  call    cs:__imp_SetThreadpoolTimer
0x1800048a9  mov     byte ptr [rdi+41h], 1
0x1800048ad  mov     rbx, [rsp+38h+arg_8]
0x1800048b2  mov     rbp, [rsp+38h+arg_10]
0x1800048b7  add     rsp, 20h
0x1800048bb  pop     r14
0x1800048bd  pop     rdi
0x1800048be  pop     rsi
0x1800048bf  retn
```
