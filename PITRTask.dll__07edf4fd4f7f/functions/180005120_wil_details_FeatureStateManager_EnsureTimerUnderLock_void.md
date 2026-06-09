# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180005120`
- end: `0x180005210`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `240`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800077c4`

## callees

- `0x180005120`
- `0x1800107c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005155`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000517c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005155`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000517c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800051ae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800051ba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800051ae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800051ba`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000518f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800051e6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000518f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800051e6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000516a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000516a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800051a6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800051a6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000519d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000519d`

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
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-28h] BYREF

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
0x180005120  mov     [rsp+arg_8], rbx
0x180005125  mov     [rsp+arg_10], rbp
0x18000512a  push    rsi
0x18000512b  push    rdi
0x18000512c  push    r14
0x18000512e  sub     rsp, 30h
0x180005132  mov     rax, cs:__security_cookie
0x180005139  xor     rax, rsp
0x18000513c  mov     [rsp+48h+var_20], rax
0x180005141  cmp     byte ptr [rcx+41h], 0
0x180005145  mov     rdi, rcx
0x180005148  jnz     loc_1800051F0
0x18000514e  cmp     qword ptr [rcx+30h], 0
0x180005153  jnz     short loc_1800051C0
0x180005155  call    cs:__imp_GetLastError
0x18000515b  xor     r8d, r8d; pcbe
0x18000515e  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180005165  mov     rdx, rdi; pv
0x180005168  mov     ebp, eax
0x18000516a  call    cs:__imp_CreateThreadpoolTimer
0x180005170  mov     rsi, [rdi+30h]
0x180005174  mov     r14, rax
0x180005177  test    rsi, rsi
0x18000517a  jz      short loc_1800051B4
0x18000517c  call    cs:__imp_GetLastError
0x180005182  xor     r9d, r9d; msWindowLength
0x180005185  xor     r8d, r8d; msPeriod
0x180005188  xor     edx, edx; pftDueTime
0x18000518a  mov     rcx, rsi; pti
0x18000518d  mov     ebx, eax
0x18000518f  call    cs:__imp_SetThreadpoolTimer
0x180005195  mov     edx, 1; fCancelPendingCallbacks
0x18000519a  mov     rcx, rsi; pti
0x18000519d  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800051a3  mov     rcx, rsi; pti
0x1800051a6  call    cs:__imp_CloseThreadpoolTimer
0x1800051ac  mov     ecx, ebx; dwErrCode
0x1800051ae  call    cs:__imp_SetLastError
0x1800051b4  mov     ecx, ebp; dwErrCode
0x1800051b6  mov     [rdi+30h], r14
0x1800051ba  call    cs:__imp_SetLastError
0x1800051c0  mov     rcx, [rdi+30h]; pti
0x1800051c4  test    rcx, rcx
0x1800051c7  jz      short loc_1800051F0
0x1800051c9  mov     rax, 0FFFFFFFF4D2FA200h
0x1800051d3  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x1800051d8  mov     r9d, 124F8h; msWindowLength
0x1800051de  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x1800051e3  xor     r8d, r8d; msPeriod
0x1800051e6  call    cs:__imp_SetThreadpoolTimer
0x1800051ec  mov     byte ptr [rdi+41h], 1
0x1800051f0  mov     rcx, [rsp+48h+var_20]
0x1800051f5  xor     rcx, rsp; StackCookie
0x1800051f8  call    __security_check_cookie
0x1800051fd  mov     rbx, [rsp+48h+arg_8]
0x180005202  mov     rbp, [rsp+48h+arg_10]
0x180005207  add     rsp, 30h
0x18000520b  pop     r14
0x18000520d  pop     rdi
0x18000520e  pop     rsi
0x18000520f  retn
```
