# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180005c14`
- end: `0x180005ce8`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007b04`

## callees

- `0x180005c14`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005c93`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005c9f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005c93`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005c9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c61`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005c8b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005c8b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180005c4f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180005c4f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005c74`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005ccb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005c74`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005ccb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005c82`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005c82`

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
0x180005c14  mov     [rsp+arg_8], rbx
0x180005c19  mov     [rsp+arg_10], rbp
0x180005c1e  push    rsi
0x180005c1f  push    rdi
0x180005c20  push    r14
0x180005c22  sub     rsp, 20h
0x180005c26  cmp     byte ptr [rcx+41h], 0
0x180005c2a  mov     rdi, rcx
0x180005c2d  jnz     loc_180005CD5
0x180005c33  cmp     qword ptr [rcx+30h], 0
0x180005c38  jnz     short loc_180005CA5
0x180005c3a  call    cs:__imp_GetLastError
0x180005c40  xor     r8d, r8d; pcbe
0x180005c43  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180005c4a  mov     rdx, rdi; pv
0x180005c4d  mov     ebp, eax
0x180005c4f  call    cs:__imp_CreateThreadpoolTimer
0x180005c55  mov     rsi, [rdi+30h]
0x180005c59  mov     r14, rax
0x180005c5c  test    rsi, rsi
0x180005c5f  jz      short loc_180005C99
0x180005c61  call    cs:__imp_GetLastError
0x180005c67  xor     r9d, r9d; msWindowLength
0x180005c6a  xor     r8d, r8d; msPeriod
0x180005c6d  xor     edx, edx; pftDueTime
0x180005c6f  mov     rcx, rsi; pti
0x180005c72  mov     ebx, eax
0x180005c74  call    cs:__imp_SetThreadpoolTimer
0x180005c7a  mov     edx, 1; fCancelPendingCallbacks
0x180005c7f  mov     rcx, rsi; pti
0x180005c82  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005c88  mov     rcx, rsi; pti
0x180005c8b  call    cs:__imp_CloseThreadpoolTimer
0x180005c91  mov     ecx, ebx; dwErrCode
0x180005c93  call    cs:__imp_SetLastError
0x180005c99  mov     ecx, ebp; dwErrCode
0x180005c9b  mov     [rdi+30h], r14
0x180005c9f  call    cs:__imp_SetLastError
0x180005ca5  mov     rcx, [rdi+30h]; pti
0x180005ca9  test    rcx, rcx
0x180005cac  jz      short loc_180005CD5
0x180005cae  mov     rax, 0FFFFFFFF4D2FA200h
0x180005cb8  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180005cbd  mov     r9d, 124F8h; msWindowLength
0x180005cc3  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x180005cc8  xor     r8d, r8d; msPeriod
0x180005ccb  call    cs:__imp_SetThreadpoolTimer
0x180005cd1  mov     byte ptr [rdi+41h], 1
0x180005cd5  mov     rbx, [rsp+38h+arg_8]
0x180005cda  mov     rbp, [rsp+38h+arg_10]
0x180005cdf  add     rsp, 20h
0x180005ce3  pop     r14
0x180005ce5  pop     rdi
0x180005ce6  pop     rsi
0x180005ce7  retn
```
