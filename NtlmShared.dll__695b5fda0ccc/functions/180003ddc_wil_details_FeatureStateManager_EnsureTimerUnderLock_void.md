# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180003ddc`
- end: `0x180003eb0`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005b74`

## callees

- `0x180003ddc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e29`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003e5b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003e67`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003e5b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003e67`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003e3c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003e93`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003e3c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003e93`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180003e17`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180003e17`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003e4a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003e4a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003e53`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003e53`

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
0x180003ddc  mov     [rsp+arg_8], rbx
0x180003de1  mov     [rsp+arg_10], rbp
0x180003de6  push    rsi
0x180003de7  push    rdi
0x180003de8  push    r14
0x180003dea  sub     rsp, 20h
0x180003dee  cmp     byte ptr [rcx+41h], 0
0x180003df2  mov     rdi, rcx
0x180003df5  jnz     loc_180003E9D
0x180003dfb  cmp     qword ptr [rcx+30h], 0
0x180003e00  jnz     short loc_180003E6D
0x180003e02  call    cs:__imp_GetLastError
0x180003e08  xor     r8d, r8d; pcbe
0x180003e0b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180003e12  mov     rdx, rdi; pv
0x180003e15  mov     ebp, eax
0x180003e17  call    cs:__imp_CreateThreadpoolTimer
0x180003e1d  mov     rsi, [rdi+30h]
0x180003e21  mov     r14, rax
0x180003e24  test    rsi, rsi
0x180003e27  jz      short loc_180003E61
0x180003e29  call    cs:__imp_GetLastError
0x180003e2f  xor     r9d, r9d; msWindowLength
0x180003e32  xor     r8d, r8d; msPeriod
0x180003e35  xor     edx, edx; pftDueTime
0x180003e37  mov     rcx, rsi; pti
0x180003e3a  mov     ebx, eax
0x180003e3c  call    cs:__imp_SetThreadpoolTimer
0x180003e42  mov     edx, 1; fCancelPendingCallbacks
0x180003e47  mov     rcx, rsi; pti
0x180003e4a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003e50  mov     rcx, rsi; pti
0x180003e53  call    cs:__imp_CloseThreadpoolTimer
0x180003e59  mov     ecx, ebx; dwErrCode
0x180003e5b  call    cs:__imp_SetLastError
0x180003e61  mov     ecx, ebp; dwErrCode
0x180003e63  mov     [rdi+30h], r14
0x180003e67  call    cs:__imp_SetLastError
0x180003e6d  mov     rcx, [rdi+30h]; pti
0x180003e71  test    rcx, rcx
0x180003e74  jz      short loc_180003E9D
0x180003e76  mov     rax, 0FFFFFFFF4D2FA200h
0x180003e80  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180003e85  mov     r9d, 124F8h; msWindowLength
0x180003e8b  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x180003e90  xor     r8d, r8d; msPeriod
0x180003e93  call    cs:__imp_SetThreadpoolTimer
0x180003e99  mov     byte ptr [rdi+41h], 1
0x180003e9d  mov     rbx, [rsp+38h+arg_8]
0x180003ea2  mov     rbp, [rsp+38h+arg_10]
0x180003ea7  add     rsp, 20h
0x180003eab  pop     r14
0x180003ead  pop     rdi
0x180003eae  pop     rsi
0x180003eaf  retn
```
