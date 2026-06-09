# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x14000c610`
- end: `0x14000c6e4`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000d514`

## callees

- `0x14000c610`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c636`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c65d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c636`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c65d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000c68f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000c69b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000c68f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000c69b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000c670`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000c6c7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000c670`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000c6c7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14000c64b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14000c64b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000c67e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000c67e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000c687`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000c687`

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
0x14000c610  mov     [rsp+arg_8], rbx
0x14000c615  mov     [rsp+arg_10], rbp
0x14000c61a  push    rsi
0x14000c61b  push    rdi
0x14000c61c  push    r14
0x14000c61e  sub     rsp, 20h
0x14000c622  cmp     byte ptr [rcx+41h], 0
0x14000c626  mov     rdi, rcx
0x14000c629  jnz     loc_14000C6D1
0x14000c62f  cmp     qword ptr [rcx+30h], 0
0x14000c634  jnz     short loc_14000C6A1
0x14000c636  call    cs:__imp_GetLastError
0x14000c63c  xor     r8d, r8d; pcbe
0x14000c63f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14000c646  mov     rdx, rdi; pv
0x14000c649  mov     ebp, eax
0x14000c64b  call    cs:__imp_CreateThreadpoolTimer
0x14000c651  mov     rsi, [rdi+30h]
0x14000c655  mov     r14, rax
0x14000c658  test    rsi, rsi
0x14000c65b  jz      short loc_14000C695
0x14000c65d  call    cs:__imp_GetLastError
0x14000c663  xor     r9d, r9d; msWindowLength
0x14000c666  xor     r8d, r8d; msPeriod
0x14000c669  xor     edx, edx; pftDueTime
0x14000c66b  mov     rcx, rsi; pti
0x14000c66e  mov     ebx, eax
0x14000c670  call    cs:__imp_SetThreadpoolTimer
0x14000c676  mov     edx, 1; fCancelPendingCallbacks
0x14000c67b  mov     rcx, rsi; pti
0x14000c67e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000c684  mov     rcx, rsi; pti
0x14000c687  call    cs:__imp_CloseThreadpoolTimer
0x14000c68d  mov     ecx, ebx; dwErrCode
0x14000c68f  call    cs:__imp_SetLastError
0x14000c695  mov     ecx, ebp; dwErrCode
0x14000c697  mov     [rdi+30h], r14
0x14000c69b  call    cs:__imp_SetLastError
0x14000c6a1  mov     rcx, [rdi+30h]; pti
0x14000c6a5  test    rcx, rcx
0x14000c6a8  jz      short loc_14000C6D1
0x14000c6aa  mov     rax, 0FFFFFFFF4D2FA200h
0x14000c6b4  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x14000c6b9  mov     r9d, 124F8h; msWindowLength
0x14000c6bf  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x14000c6c4  xor     r8d, r8d; msPeriod
0x14000c6c7  call    cs:__imp_SetThreadpoolTimer
0x14000c6cd  mov     byte ptr [rdi+41h], 1
0x14000c6d1  mov     rbx, [rsp+38h+arg_8]
0x14000c6d6  mov     rbp, [rsp+38h+arg_10]
0x14000c6db  add     rsp, 20h
0x14000c6df  pop     r14
0x14000c6e1  pop     rdi
0x14000c6e2  pop     rsi
0x14000c6e3  retn
```
