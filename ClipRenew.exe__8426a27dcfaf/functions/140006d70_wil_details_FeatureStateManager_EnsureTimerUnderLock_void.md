# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x140006d70`
- end: `0x140006e44`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140010314`

## callees

- `0x140006d70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006def`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006dfb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006def`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006dfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006d96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006dbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006d96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006dbd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140006dde`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140006dde`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140006de7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140006de7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140006dd0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140006e27`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140006dd0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140006e27`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140006dab`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140006dab`

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
0x140006d70  mov     [rsp+arg_8], rbx
0x140006d75  mov     [rsp+arg_10], rbp
0x140006d7a  push    rsi
0x140006d7b  push    rdi
0x140006d7c  push    r14
0x140006d7e  sub     rsp, 20h
0x140006d82  cmp     byte ptr [rcx+41h], 0
0x140006d86  mov     rdi, rcx
0x140006d89  jnz     loc_140006E31
0x140006d8f  cmp     qword ptr [rcx+30h], 0
0x140006d94  jnz     short loc_140006E01
0x140006d96  call    cs:__imp_GetLastError
0x140006d9c  xor     r8d, r8d; pcbe
0x140006d9f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140006da6  mov     rdx, rdi; pv
0x140006da9  mov     ebp, eax
0x140006dab  call    cs:__imp_CreateThreadpoolTimer
0x140006db1  mov     rsi, [rdi+30h]
0x140006db5  mov     r14, rax
0x140006db8  test    rsi, rsi
0x140006dbb  jz      short loc_140006DF5
0x140006dbd  call    cs:__imp_GetLastError
0x140006dc3  xor     r9d, r9d; msWindowLength
0x140006dc6  xor     r8d, r8d; msPeriod
0x140006dc9  xor     edx, edx; pftDueTime
0x140006dcb  mov     rcx, rsi; pti
0x140006dce  mov     ebx, eax
0x140006dd0  call    cs:__imp_SetThreadpoolTimer
0x140006dd6  mov     edx, 1; fCancelPendingCallbacks
0x140006ddb  mov     rcx, rsi; pti
0x140006dde  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140006de4  mov     rcx, rsi; pti
0x140006de7  call    cs:__imp_CloseThreadpoolTimer
0x140006ded  mov     ecx, ebx; dwErrCode
0x140006def  call    cs:__imp_SetLastError
0x140006df5  mov     ecx, ebp; dwErrCode
0x140006df7  mov     [rdi+30h], r14
0x140006dfb  call    cs:__imp_SetLastError
0x140006e01  mov     rcx, [rdi+30h]; pti
0x140006e05  test    rcx, rcx
0x140006e08  jz      short loc_140006E31
0x140006e0a  mov     rax, 0FFFFFFFF4D2FA200h
0x140006e14  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x140006e19  mov     r9d, 124F8h; msWindowLength
0x140006e1f  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x140006e24  xor     r8d, r8d; msPeriod
0x140006e27  call    cs:__imp_SetThreadpoolTimer
0x140006e2d  mov     byte ptr [rdi+41h], 1
0x140006e31  mov     rbx, [rsp+38h+arg_8]
0x140006e36  mov     rbp, [rsp+38h+arg_10]
0x140006e3b  add     rsp, 20h
0x140006e3f  pop     r14
0x140006e41  pop     rdi
0x140006e42  pop     rsi
0x140006e43  retn
```
