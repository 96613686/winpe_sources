# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180006bdc`
- end: `0x180006cb0`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800092b4`

## callees

- `0x180006bdc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006c5b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006c67`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006c5b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006c67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006c02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006c29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006c02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006c29`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006c4a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006c4a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006c53`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006c53`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180006c17`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180006c17`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006c3c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006c93`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006c3c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006c93`

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
0x180006bdc  mov     [rsp+arg_8], rbx
0x180006be1  mov     [rsp+arg_10], rbp
0x180006be6  push    rsi
0x180006be7  push    rdi
0x180006be8  push    r14
0x180006bea  sub     rsp, 20h
0x180006bee  cmp     byte ptr [rcx+41h], 0
0x180006bf2  mov     rdi, rcx
0x180006bf5  jnz     loc_180006C9D
0x180006bfb  cmp     qword ptr [rcx+30h], 0
0x180006c00  jnz     short loc_180006C6D
0x180006c02  call    cs:__imp_GetLastError
0x180006c08  xor     r8d, r8d; pcbe
0x180006c0b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180006c12  mov     rdx, rdi; pv
0x180006c15  mov     ebp, eax
0x180006c17  call    cs:__imp_CreateThreadpoolTimer
0x180006c1d  mov     rsi, [rdi+30h]
0x180006c21  mov     r14, rax
0x180006c24  test    rsi, rsi
0x180006c27  jz      short loc_180006C61
0x180006c29  call    cs:__imp_GetLastError
0x180006c2f  xor     r9d, r9d; msWindowLength
0x180006c32  xor     r8d, r8d; msPeriod
0x180006c35  xor     edx, edx; pftDueTime
0x180006c37  mov     rcx, rsi; pti
0x180006c3a  mov     ebx, eax
0x180006c3c  call    cs:__imp_SetThreadpoolTimer
0x180006c42  mov     edx, 1; fCancelPendingCallbacks
0x180006c47  mov     rcx, rsi; pti
0x180006c4a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180006c50  mov     rcx, rsi; pti
0x180006c53  call    cs:__imp_CloseThreadpoolTimer
0x180006c59  mov     ecx, ebx; dwErrCode
0x180006c5b  call    cs:__imp_SetLastError
0x180006c61  mov     ecx, ebp; dwErrCode
0x180006c63  mov     [rdi+30h], r14
0x180006c67  call    cs:__imp_SetLastError
0x180006c6d  mov     rcx, [rdi+30h]; pti
0x180006c71  test    rcx, rcx
0x180006c74  jz      short loc_180006C9D
0x180006c76  mov     rax, 0FFFFFFFF4D2FA200h
0x180006c80  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180006c85  mov     r9d, 124F8h; msWindowLength
0x180006c8b  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x180006c90  xor     r8d, r8d; msPeriod
0x180006c93  call    cs:__imp_SetThreadpoolTimer
0x180006c99  mov     byte ptr [rdi+41h], 1
0x180006c9d  mov     rbx, [rsp+38h+arg_8]
0x180006ca2  mov     rbp, [rsp+38h+arg_10]
0x180006ca7  add     rsp, 20h
0x180006cab  pop     r14
0x180006cad  pop     rdi
0x180006cae  pop     rsi
0x180006caf  retn
```
