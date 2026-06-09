# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x1800e7860`
- end: `0x1800e7934`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800e97e4`

## callees

- `0x1800e7860`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e78df`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e78eb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e78df`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e78eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e7886`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e78ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e7886`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e78ad`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800e789b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800e789b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800e78ce`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800e78ce`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800e78d7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800e78d7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800e78c0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800e7917`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800e78c0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800e7917`

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
0x1800e7860  mov     [rsp+arg_8], rbx
0x1800e7865  mov     [rsp+arg_10], rbp
0x1800e786a  push    rsi
0x1800e786b  push    rdi
0x1800e786c  push    r14
0x1800e786e  sub     rsp, 20h
0x1800e7872  cmp     byte ptr [rcx+41h], 0
0x1800e7876  mov     rdi, rcx
0x1800e7879  jnz     loc_1800E7921
0x1800e787f  cmp     qword ptr [rcx+30h], 0
0x1800e7884  jnz     short loc_1800E78F1
0x1800e7886  call    cs:__imp_GetLastError
0x1800e788c  xor     r8d, r8d; pcbe
0x1800e788f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800e7896  mov     rdx, rdi; pv
0x1800e7899  mov     ebp, eax
0x1800e789b  call    cs:__imp_CreateThreadpoolTimer
0x1800e78a1  mov     rsi, [rdi+30h]
0x1800e78a5  mov     r14, rax
0x1800e78a8  test    rsi, rsi
0x1800e78ab  jz      short loc_1800E78E5
0x1800e78ad  call    cs:__imp_GetLastError
0x1800e78b3  xor     r9d, r9d; msWindowLength
0x1800e78b6  xor     r8d, r8d; msPeriod
0x1800e78b9  xor     edx, edx; pftDueTime
0x1800e78bb  mov     rcx, rsi; pti
0x1800e78be  mov     ebx, eax
0x1800e78c0  call    cs:__imp_SetThreadpoolTimer
0x1800e78c6  mov     edx, 1; fCancelPendingCallbacks
0x1800e78cb  mov     rcx, rsi; pti
0x1800e78ce  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800e78d4  mov     rcx, rsi; pti
0x1800e78d7  call    cs:__imp_CloseThreadpoolTimer
0x1800e78dd  mov     ecx, ebx; dwErrCode
0x1800e78df  call    cs:__imp_SetLastError
0x1800e78e5  mov     ecx, ebp; dwErrCode
0x1800e78e7  mov     [rdi+30h], r14
0x1800e78eb  call    cs:__imp_SetLastError
0x1800e78f1  mov     rcx, [rdi+30h]; pti
0x1800e78f5  test    rcx, rcx
0x1800e78f8  jz      short loc_1800E7921
0x1800e78fa  mov     rax, 0FFFFFFFF4D2FA200h
0x1800e7904  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x1800e7909  mov     r9d, 124F8h; msWindowLength
0x1800e790f  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x1800e7914  xor     r8d, r8d; msPeriod
0x1800e7917  call    cs:__imp_SetThreadpoolTimer
0x1800e791d  mov     byte ptr [rdi+41h], 1
0x1800e7921  mov     rbx, [rsp+38h+arg_8]
0x1800e7926  mov     rbp, [rsp+38h+arg_10]
0x1800e792b  add     rsp, 20h
0x1800e792f  pop     r14
0x1800e7931  pop     rdi
0x1800e7932  pop     rsi
0x1800e7933  retn
```
