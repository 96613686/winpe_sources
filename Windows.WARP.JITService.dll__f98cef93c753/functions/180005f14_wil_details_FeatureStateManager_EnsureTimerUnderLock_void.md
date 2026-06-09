# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180005f14`
- end: `0x180005fe8`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180006050`

## callees

- `0x180005f14`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005f93`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005f9f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005f93`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005f9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f61`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005f74`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005fcb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005f74`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005fcb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005f8b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005f8b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005f82`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005f82`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180005f4f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180005f4f`

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
  _FILETIME pftDueTime; // [rsp+40h] [rbp+8h] BYREF

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
      pftDueTime = (_FILETIME)-3000000000LL;
      SetThreadpoolTimer(v7, &pftDueTime, 0, 0x124F8u);
      *((_BYTE *)pv + 65) = 1;
    }
  }
}

```

## disassembly

```asm
0x180005f14  mov     [rsp+arg_8], rbx
0x180005f19  mov     [rsp+arg_10], rbp
0x180005f1e  push    rsi
0x180005f1f  push    rdi
0x180005f20  push    r14
0x180005f22  sub     rsp, 20h
0x180005f26  cmp     byte ptr [rcx+41h], 0
0x180005f2a  mov     rdi, rcx
0x180005f2d  jnz     loc_180005FD5
0x180005f33  cmp     qword ptr [rcx+30h], 0
0x180005f38  jnz     short loc_180005FA5
0x180005f3a  call    cs:__imp_GetLastError
0x180005f40  xor     r8d, r8d; pcbe
0x180005f43  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180005f4a  mov     rdx, rdi; pv
0x180005f4d  mov     ebp, eax
0x180005f4f  call    cs:__imp_CreateThreadpoolTimer
0x180005f55  mov     rsi, [rdi+30h]
0x180005f59  mov     r14, rax
0x180005f5c  test    rsi, rsi
0x180005f5f  jz      short loc_180005F99
0x180005f61  call    cs:__imp_GetLastError
0x180005f67  xor     r9d, r9d; msWindowLength
0x180005f6a  xor     r8d, r8d; msPeriod
0x180005f6d  xor     edx, edx; pftDueTime
0x180005f6f  mov     rcx, rsi; pti
0x180005f72  mov     ebx, eax
0x180005f74  call    cs:__imp_SetThreadpoolTimer
0x180005f7a  mov     edx, 1; fCancelPendingCallbacks
0x180005f7f  mov     rcx, rsi; pti
0x180005f82  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005f88  mov     rcx, rsi; pti
0x180005f8b  call    cs:__imp_CloseThreadpoolTimer
0x180005f91  mov     ecx, ebx; dwErrCode
0x180005f93  call    cs:__imp_SetLastError
0x180005f99  mov     ecx, ebp; dwErrCode
0x180005f9b  mov     [rdi+30h], r14
0x180005f9f  call    cs:__imp_SetLastError
0x180005fa5  mov     rcx, [rdi+30h]; pti
0x180005fa9  test    rcx, rcx
0x180005fac  jz      short loc_180005FD5
0x180005fae  mov     rax, 0FFFFFFFF4D2FA200h
0x180005fb8  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180005fbd  mov     r9d, 124F8h; msWindowLength
0x180005fc3  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x180005fc8  xor     r8d, r8d; msPeriod
0x180005fcb  call    cs:__imp_SetThreadpoolTimer
0x180005fd1  mov     byte ptr [rdi+41h], 1
0x180005fd5  mov     rbx, [rsp+38h+arg_8]
0x180005fda  mov     rbp, [rsp+38h+arg_10]
0x180005fdf  add     rsp, 20h
0x180005fe3  pop     r14
0x180005fe5  pop     rdi
0x180005fe6  pop     rsi
0x180005fe7  retn
```
