# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180029af8`
- end: `0x180029bcc`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002c7b4`

## callees

- `0x180029af8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029b1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029b45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029b1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029b45`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029b77`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029b83`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029b77`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029b83`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180029b66`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180029b66`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180029b6f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180029b6f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180029b58`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180029baf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180029b58`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180029baf`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180029b33`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180029b33`

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
0x180029af8  mov     [rsp+arg_8], rbx
0x180029afd  mov     [rsp+arg_10], rbp
0x180029b02  push    rsi
0x180029b03  push    rdi
0x180029b04  push    r14
0x180029b06  sub     rsp, 20h
0x180029b0a  cmp     byte ptr [rcx+41h], 0
0x180029b0e  mov     rdi, rcx
0x180029b11  jnz     loc_180029BB9
0x180029b17  cmp     qword ptr [rcx+30h], 0
0x180029b1c  jnz     short loc_180029B89
0x180029b1e  call    cs:__imp_GetLastError
0x180029b24  xor     r8d, r8d; pcbe
0x180029b27  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180029b2e  mov     rdx, rdi; pv
0x180029b31  mov     ebp, eax
0x180029b33  call    cs:__imp_CreateThreadpoolTimer
0x180029b39  mov     rsi, [rdi+30h]
0x180029b3d  mov     r14, rax
0x180029b40  test    rsi, rsi
0x180029b43  jz      short loc_180029B7D
0x180029b45  call    cs:__imp_GetLastError
0x180029b4b  xor     r9d, r9d; msWindowLength
0x180029b4e  xor     r8d, r8d; msPeriod
0x180029b51  xor     edx, edx; pftDueTime
0x180029b53  mov     rcx, rsi; pti
0x180029b56  mov     ebx, eax
0x180029b58  call    cs:__imp_SetThreadpoolTimer
0x180029b5e  mov     edx, 1; fCancelPendingCallbacks
0x180029b63  mov     rcx, rsi; pti
0x180029b66  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180029b6c  mov     rcx, rsi; pti
0x180029b6f  call    cs:__imp_CloseThreadpoolTimer
0x180029b75  mov     ecx, ebx; dwErrCode
0x180029b77  call    cs:__imp_SetLastError
0x180029b7d  mov     ecx, ebp; dwErrCode
0x180029b7f  mov     [rdi+30h], r14
0x180029b83  call    cs:__imp_SetLastError
0x180029b89  mov     rcx, [rdi+30h]; pti
0x180029b8d  test    rcx, rcx
0x180029b90  jz      short loc_180029BB9
0x180029b92  mov     rax, 0FFFFFFFF4D2FA200h
0x180029b9c  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180029ba1  mov     r9d, 124F8h; msWindowLength
0x180029ba7  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x180029bac  xor     r8d, r8d; msPeriod
0x180029baf  call    cs:__imp_SetThreadpoolTimer
0x180029bb5  mov     byte ptr [rdi+41h], 1
0x180029bb9  mov     rbx, [rsp+38h+arg_8]
0x180029bbe  mov     rbp, [rsp+38h+arg_10]
0x180029bc3  add     rsp, 20h
0x180029bc7  pop     r14
0x180029bc9  pop     rdi
0x180029bca  pop     rsi
0x180029bcb  retn
```
