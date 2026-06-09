# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x1800059b4`
- end: `0x180005a88`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007884`

## callees

- `0x1800059b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005a33`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005a3f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005a33`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005a3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800059da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800059da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a01`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005a14`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005a6b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005a14`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005a6b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005a2b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005a2b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005a22`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005a22`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800059ef`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800059ef`

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
0x1800059b4  mov     [rsp+arg_8], rbx
0x1800059b9  mov     [rsp+arg_10], rbp
0x1800059be  push    rsi
0x1800059bf  push    rdi
0x1800059c0  push    r14
0x1800059c2  sub     rsp, 20h
0x1800059c6  cmp     byte ptr [rcx+41h], 0
0x1800059ca  mov     rdi, rcx
0x1800059cd  jnz     loc_180005A75
0x1800059d3  cmp     qword ptr [rcx+30h], 0
0x1800059d8  jnz     short loc_180005A45
0x1800059da  call    cs:__imp_GetLastError
0x1800059e0  xor     r8d, r8d; pcbe
0x1800059e3  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800059ea  mov     rdx, rdi; pv
0x1800059ed  mov     ebp, eax
0x1800059ef  call    cs:__imp_CreateThreadpoolTimer
0x1800059f5  mov     rsi, [rdi+30h]
0x1800059f9  mov     r14, rax
0x1800059fc  test    rsi, rsi
0x1800059ff  jz      short loc_180005A39
0x180005a01  call    cs:__imp_GetLastError
0x180005a07  xor     r9d, r9d; msWindowLength
0x180005a0a  xor     r8d, r8d; msPeriod
0x180005a0d  xor     edx, edx; pftDueTime
0x180005a0f  mov     rcx, rsi; pti
0x180005a12  mov     ebx, eax
0x180005a14  call    cs:__imp_SetThreadpoolTimer
0x180005a1a  mov     edx, 1; fCancelPendingCallbacks
0x180005a1f  mov     rcx, rsi; pti
0x180005a22  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005a28  mov     rcx, rsi; pti
0x180005a2b  call    cs:__imp_CloseThreadpoolTimer
0x180005a31  mov     ecx, ebx; dwErrCode
0x180005a33  call    cs:__imp_SetLastError
0x180005a39  mov     ecx, ebp; dwErrCode
0x180005a3b  mov     [rdi+30h], r14
0x180005a3f  call    cs:__imp_SetLastError
0x180005a45  mov     rcx, [rdi+30h]; pti
0x180005a49  test    rcx, rcx
0x180005a4c  jz      short loc_180005A75
0x180005a4e  mov     rax, 0FFFFFFFF4D2FA200h
0x180005a58  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180005a5d  mov     r9d, 124F8h; msWindowLength
0x180005a63  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x180005a68  xor     r8d, r8d; msPeriod
0x180005a6b  call    cs:__imp_SetThreadpoolTimer
0x180005a71  mov     byte ptr [rdi+41h], 1
0x180005a75  mov     rbx, [rsp+38h+arg_8]
0x180005a7a  mov     rbp, [rsp+38h+arg_10]
0x180005a7f  add     rsp, 20h
0x180005a83  pop     r14
0x180005a85  pop     rdi
0x180005a86  pop     rsi
0x180005a87  retn
```
