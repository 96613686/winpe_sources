# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180007cb4`
- end: `0x180007d88`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180008534`

## callees

- `0x180007cb4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007cda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007cda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d01`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007d33`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007d3f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007d33`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007d3f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007d22`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007d22`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007d2b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180007d2b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180007cef`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180007cef`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007d14`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007d6b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007d14`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007d6b`

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
0x180007cb4  mov     [rsp+arg_8], rbx
0x180007cb9  mov     [rsp+arg_10], rbp
0x180007cbe  push    rsi
0x180007cbf  push    rdi
0x180007cc0  push    r14
0x180007cc2  sub     rsp, 20h
0x180007cc6  cmp     byte ptr [rcx+41h], 0
0x180007cca  mov     rdi, rcx
0x180007ccd  jnz     loc_180007D75
0x180007cd3  cmp     qword ptr [rcx+30h], 0
0x180007cd8  jnz     short loc_180007D45
0x180007cda  call    cs:__imp_GetLastError
0x180007ce0  xor     r8d, r8d; pcbe
0x180007ce3  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180007cea  mov     rdx, rdi; pv
0x180007ced  mov     ebp, eax
0x180007cef  call    cs:__imp_CreateThreadpoolTimer
0x180007cf5  mov     rsi, [rdi+30h]
0x180007cf9  mov     r14, rax
0x180007cfc  test    rsi, rsi
0x180007cff  jz      short loc_180007D39
0x180007d01  call    cs:__imp_GetLastError
0x180007d07  xor     r9d, r9d; msWindowLength
0x180007d0a  xor     r8d, r8d; msPeriod
0x180007d0d  xor     edx, edx; pftDueTime
0x180007d0f  mov     rcx, rsi; pti
0x180007d12  mov     ebx, eax
0x180007d14  call    cs:__imp_SetThreadpoolTimer
0x180007d1a  mov     edx, 1; fCancelPendingCallbacks
0x180007d1f  mov     rcx, rsi; pti
0x180007d22  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180007d28  mov     rcx, rsi; pti
0x180007d2b  call    cs:__imp_CloseThreadpoolTimer
0x180007d31  mov     ecx, ebx; dwErrCode
0x180007d33  call    cs:__imp_SetLastError
0x180007d39  mov     ecx, ebp; dwErrCode
0x180007d3b  mov     [rdi+30h], r14
0x180007d3f  call    cs:__imp_SetLastError
0x180007d45  mov     rcx, [rdi+30h]; pti
0x180007d49  test    rcx, rcx
0x180007d4c  jz      short loc_180007D75
0x180007d4e  mov     rax, 0FFFFFFFF4D2FA200h
0x180007d58  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180007d5d  mov     r9d, 124F8h; msWindowLength
0x180007d63  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x180007d68  xor     r8d, r8d; msPeriod
0x180007d6b  call    cs:__imp_SetThreadpoolTimer
0x180007d71  mov     byte ptr [rdi+41h], 1
0x180007d75  mov     rbx, [rsp+38h+arg_8]
0x180007d7a  mov     rbp, [rsp+38h+arg_10]
0x180007d7f  add     rsp, 20h
0x180007d83  pop     r14
0x180007d85  pop     rdi
0x180007d86  pop     rsi
0x180007d87  retn
```
