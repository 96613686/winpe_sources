# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x140006ecc`
- end: `0x140006fa0`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140009534`

## callees

- `0x140006ecc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006ef2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006f19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006ef2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006f19`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006f4b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006f57`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006f4b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006f57`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140006f43`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140006f43`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140006f3a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140006f3a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140006f07`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140006f07`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140006f2c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140006f83`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140006f2c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140006f83`

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
0x140006ecc  mov     [rsp+arg_8], rbx
0x140006ed1  mov     [rsp+arg_10], rbp
0x140006ed6  push    rsi
0x140006ed7  push    rdi
0x140006ed8  push    r14
0x140006eda  sub     rsp, 20h
0x140006ede  cmp     byte ptr [rcx+41h], 0
0x140006ee2  mov     rdi, rcx
0x140006ee5  jnz     loc_140006F8D
0x140006eeb  cmp     qword ptr [rcx+30h], 0
0x140006ef0  jnz     short loc_140006F5D
0x140006ef2  call    cs:__imp_GetLastError
0x140006ef8  xor     r8d, r8d; pcbe
0x140006efb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140006f02  mov     rdx, rdi; pv
0x140006f05  mov     ebp, eax
0x140006f07  call    cs:__imp_CreateThreadpoolTimer
0x140006f0d  mov     rsi, [rdi+30h]
0x140006f11  mov     r14, rax
0x140006f14  test    rsi, rsi
0x140006f17  jz      short loc_140006F51
0x140006f19  call    cs:__imp_GetLastError
0x140006f1f  xor     r9d, r9d; msWindowLength
0x140006f22  xor     r8d, r8d; msPeriod
0x140006f25  xor     edx, edx; pftDueTime
0x140006f27  mov     rcx, rsi; pti
0x140006f2a  mov     ebx, eax
0x140006f2c  call    cs:__imp_SetThreadpoolTimer
0x140006f32  mov     edx, 1; fCancelPendingCallbacks
0x140006f37  mov     rcx, rsi; pti
0x140006f3a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140006f40  mov     rcx, rsi; pti
0x140006f43  call    cs:__imp_CloseThreadpoolTimer
0x140006f49  mov     ecx, ebx; dwErrCode
0x140006f4b  call    cs:__imp_SetLastError
0x140006f51  mov     ecx, ebp; dwErrCode
0x140006f53  mov     [rdi+30h], r14
0x140006f57  call    cs:__imp_SetLastError
0x140006f5d  mov     rcx, [rdi+30h]; pti
0x140006f61  test    rcx, rcx
0x140006f64  jz      short loc_140006F8D
0x140006f66  mov     rax, 0FFFFFFFF4D2FA200h
0x140006f70  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x140006f75  mov     r9d, 124F8h; msWindowLength
0x140006f7b  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x140006f80  xor     r8d, r8d; msPeriod
0x140006f83  call    cs:__imp_SetThreadpoolTimer
0x140006f89  mov     byte ptr [rdi+41h], 1
0x140006f8d  mov     rbx, [rsp+38h+arg_8]
0x140006f92  mov     rbp, [rsp+38h+arg_10]
0x140006f97  add     rsp, 20h
0x140006f9b  pop     r14
0x140006f9d  pop     rdi
0x140006f9e  pop     rsi
0x140006f9f  retn
```
