# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x140009278`
- end: `0x14000934c`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000a334`

## callees

- `0x140009278`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000929e`
- `KERNEL32!GetLastError` at `0x1400092c5`
- `KERNEL32!GetLastError` at `0x14000929e`
- `KERNEL32!GetLastError` at `0x1400092c5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400092f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009303`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400092f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140009303`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400092b3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400092b3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400092e6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400092e6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400092d8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000932f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400092d8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000932f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400092ef`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400092ef`

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
0x140009278  mov     [rsp+arg_8], rbx
0x14000927d  mov     [rsp+arg_10], rbp
0x140009282  push    rsi
0x140009283  push    rdi
0x140009284  push    r14
0x140009286  sub     rsp, 20h
0x14000928a  cmp     byte ptr [rcx+41h], 0
0x14000928e  mov     rdi, rcx
0x140009291  jnz     loc_140009339
0x140009297  cmp     qword ptr [rcx+30h], 0
0x14000929c  jnz     short loc_140009309
0x14000929e  call    cs:__imp_GetLastError
0x1400092a4  xor     r8d, r8d; pcbe
0x1400092a7  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1400092ae  mov     rdx, rdi; pv
0x1400092b1  mov     ebp, eax
0x1400092b3  call    cs:__imp_CreateThreadpoolTimer
0x1400092b9  mov     rsi, [rdi+30h]
0x1400092bd  mov     r14, rax
0x1400092c0  test    rsi, rsi
0x1400092c3  jz      short loc_1400092FD
0x1400092c5  call    cs:__imp_GetLastError
0x1400092cb  xor     r9d, r9d; msWindowLength
0x1400092ce  xor     r8d, r8d; msPeriod
0x1400092d1  xor     edx, edx; pftDueTime
0x1400092d3  mov     rcx, rsi; pti
0x1400092d6  mov     ebx, eax
0x1400092d8  call    cs:__imp_SetThreadpoolTimer
0x1400092de  mov     edx, 1; fCancelPendingCallbacks
0x1400092e3  mov     rcx, rsi; pti
0x1400092e6  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400092ec  mov     rcx, rsi; pti
0x1400092ef  call    cs:__imp_CloseThreadpoolTimer
0x1400092f5  mov     ecx, ebx; dwErrCode
0x1400092f7  call    cs:__imp_SetLastError
0x1400092fd  mov     ecx, ebp; dwErrCode
0x1400092ff  mov     [rdi+30h], r14
0x140009303  call    cs:__imp_SetLastError
0x140009309  mov     rcx, [rdi+30h]; pti
0x14000930d  test    rcx, rcx
0x140009310  jz      short loc_140009339
0x140009312  mov     rax, 0FFFFFFFF4D2FA200h
0x14000931c  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x140009321  mov     r9d, 124F8h; msWindowLength
0x140009327  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x14000932c  xor     r8d, r8d; msPeriod
0x14000932f  call    cs:__imp_SetThreadpoolTimer
0x140009335  mov     byte ptr [rdi+41h], 1
0x140009339  mov     rbx, [rsp+38h+arg_8]
0x14000933e  mov     rbp, [rsp+38h+arg_10]
0x140009343  add     rsp, 20h
0x140009347  pop     r14
0x140009349  pop     rdi
0x14000934a  pop     rsi
0x14000934b  retn
```
