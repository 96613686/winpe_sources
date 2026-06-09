# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180012d84`
- end: `0x180012e58`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180013eb0`

## callees

- `0x180012d84`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012daa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012dd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012daa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012dd1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012e03`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012e0f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012e03`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012e0f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180012dfb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180012dfb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180012df2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180012df2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180012dbf`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180012dbf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180012de4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180012e3b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180012de4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180012e3b`

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
0x180012d84  mov     [rsp+arg_8], rbx
0x180012d89  mov     [rsp+arg_10], rbp
0x180012d8e  push    rsi
0x180012d8f  push    rdi
0x180012d90  push    r14
0x180012d92  sub     rsp, 20h
0x180012d96  cmp     byte ptr [rcx+41h], 0
0x180012d9a  mov     rdi, rcx
0x180012d9d  jnz     loc_180012E45
0x180012da3  cmp     qword ptr [rcx+30h], 0
0x180012da8  jnz     short loc_180012E15
0x180012daa  call    cs:__imp_GetLastError
0x180012db0  xor     r8d, r8d; pcbe
0x180012db3  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180012dba  mov     rdx, rdi; pv
0x180012dbd  mov     ebp, eax
0x180012dbf  call    cs:__imp_CreateThreadpoolTimer
0x180012dc5  mov     rsi, [rdi+30h]
0x180012dc9  mov     r14, rax
0x180012dcc  test    rsi, rsi
0x180012dcf  jz      short loc_180012E09
0x180012dd1  call    cs:__imp_GetLastError
0x180012dd7  xor     r9d, r9d; msWindowLength
0x180012dda  xor     r8d, r8d; msPeriod
0x180012ddd  xor     edx, edx; pftDueTime
0x180012ddf  mov     rcx, rsi; pti
0x180012de2  mov     ebx, eax
0x180012de4  call    cs:__imp_SetThreadpoolTimer
0x180012dea  mov     edx, 1; fCancelPendingCallbacks
0x180012def  mov     rcx, rsi; pti
0x180012df2  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180012df8  mov     rcx, rsi; pti
0x180012dfb  call    cs:__imp_CloseThreadpoolTimer
0x180012e01  mov     ecx, ebx; dwErrCode
0x180012e03  call    cs:__imp_SetLastError
0x180012e09  mov     ecx, ebp; dwErrCode
0x180012e0b  mov     [rdi+30h], r14
0x180012e0f  call    cs:__imp_SetLastError
0x180012e15  mov     rcx, [rdi+30h]; pti
0x180012e19  test    rcx, rcx
0x180012e1c  jz      short loc_180012E45
0x180012e1e  mov     rax, 0FFFFFFFF4D2FA200h
0x180012e28  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180012e2d  mov     r9d, 124F8h; msWindowLength
0x180012e33  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x180012e38  xor     r8d, r8d; msPeriod
0x180012e3b  call    cs:__imp_SetThreadpoolTimer
0x180012e41  mov     byte ptr [rdi+41h], 1
0x180012e45  mov     rbx, [rsp+38h+arg_8]
0x180012e4a  mov     rbp, [rsp+38h+arg_10]
0x180012e4f  add     rsp, 20h
0x180012e53  pop     r14
0x180012e55  pop     rdi
0x180012e56  pop     rsi
0x180012e57  retn
```
