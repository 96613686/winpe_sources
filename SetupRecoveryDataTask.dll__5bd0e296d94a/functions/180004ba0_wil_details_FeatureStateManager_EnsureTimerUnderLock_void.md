# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180004ba0`
- end: `0x180004c90`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `240`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800076d4`

## callees

- `0x180004ba0`
- `0x18000c610`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004bd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004bfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004bd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004bfc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004c2e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004c3a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004c2e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004c3a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004c1d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004c1d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004c26`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004c26`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180004bea`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180004bea`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004c0f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004c66`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004c0f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004c66`

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
0x180004ba0  mov     [rsp+arg_8], rbx
0x180004ba5  mov     [rsp+arg_10], rbp
0x180004baa  push    rsi
0x180004bab  push    rdi
0x180004bac  push    r14
0x180004bae  sub     rsp, 30h
0x180004bb2  mov     rax, cs:__security_cookie
0x180004bb9  xor     rax, rsp
0x180004bbc  mov     [rsp+48h+var_20], rax
0x180004bc1  cmp     byte ptr [rcx+41h], 0
0x180004bc5  mov     rdi, rcx
0x180004bc8  jnz     loc_180004C70
0x180004bce  cmp     qword ptr [rcx+30h], 0
0x180004bd3  jnz     short loc_180004C40
0x180004bd5  call    cs:__imp_GetLastError
0x180004bdb  xor     r8d, r8d; pcbe
0x180004bde  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180004be5  mov     rdx, rdi; pv
0x180004be8  mov     ebp, eax
0x180004bea  call    cs:__imp_CreateThreadpoolTimer
0x180004bf0  mov     rsi, [rdi+30h]
0x180004bf4  mov     r14, rax
0x180004bf7  test    rsi, rsi
0x180004bfa  jz      short loc_180004C34
0x180004bfc  call    cs:__imp_GetLastError
0x180004c02  xor     r9d, r9d; msWindowLength
0x180004c05  xor     r8d, r8d; msPeriod
0x180004c08  xor     edx, edx; pftDueTime
0x180004c0a  mov     rcx, rsi; pti
0x180004c0d  mov     ebx, eax
0x180004c0f  call    cs:__imp_SetThreadpoolTimer
0x180004c15  mov     edx, 1; fCancelPendingCallbacks
0x180004c1a  mov     rcx, rsi; pti
0x180004c1d  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180004c23  mov     rcx, rsi; pti
0x180004c26  call    cs:__imp_CloseThreadpoolTimer
0x180004c2c  mov     ecx, ebx; dwErrCode
0x180004c2e  call    cs:__imp_SetLastError
0x180004c34  mov     ecx, ebp; dwErrCode
0x180004c36  mov     [rdi+30h], r14
0x180004c3a  call    cs:__imp_SetLastError
0x180004c40  mov     rcx, [rdi+30h]; pti
0x180004c44  test    rcx, rcx
0x180004c47  jz      short loc_180004C70
0x180004c49  mov     rax, 0FFFFFFFF4D2FA200h
0x180004c53  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x180004c58  mov     r9d, 124F8h; msWindowLength
0x180004c5e  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x180004c63  xor     r8d, r8d; msPeriod
0x180004c66  call    cs:__imp_SetThreadpoolTimer
0x180004c6c  mov     byte ptr [rdi+41h], 1
0x180004c70  mov     rcx, [rsp+48h+var_20]
0x180004c75  xor     rcx, rsp; StackCookie
0x180004c78  call    __security_check_cookie
0x180004c7d  mov     rbx, [rsp+48h+arg_8]
0x180004c82  mov     rbp, [rsp+48h+arg_10]
0x180004c87  add     rsp, 30h
0x180004c8b  pop     r14
0x180004c8d  pop     rdi
0x180004c8e  pop     rsi
0x180004c8f  retn
```
