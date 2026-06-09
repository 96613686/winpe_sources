# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180011b54`
- end: `0x180011c2c`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `216`
- prototype: `void __fastcall(_QWORD *pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180013804`

## callees

- `0x180011b54`

## import_xrefs

- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180011bc4`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180011bc4`
- `KERNEL32!CloseThreadpoolTimer` at `0x180011bcd`
- `KERNEL32!CloseThreadpoolTimer` at `0x180011bcd`
- `KERNEL32!SetThreadpoolTimer` at `0x180011bb6`
- `KERNEL32!SetThreadpoolTimer` at `0x180011c0f`
- `KERNEL32!SetThreadpoolTimer` at `0x180011bb6`
- `KERNEL32!SetThreadpoolTimer` at `0x180011c0f`
- `KERNEL32!CreateThreadpoolTimer` at `0x180011b91`
- `KERNEL32!CreateThreadpoolTimer` at `0x180011b91`
- `KERNEL32!GetLastError` at `0x180011b7c`
- `KERNEL32!GetLastError` at `0x180011ba3`
- `KERNEL32!GetLastError` at `0x180011b7c`
- `KERNEL32!GetLastError` at `0x180011ba3`
- `KERNEL32!SetLastError` at `0x180011bd6`
- `KERNEL32!SetLastError` at `0x180011be3`
- `KERNEL32!SetLastError` at `0x180011bd6`
- `KERNEL32!SetLastError` at `0x180011be3`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::EnsureTimerUnderLock(_QWORD *pv)
{
  struct _TP_TIMER *v2; // rcx
  DWORD LastError; // ebp
  PTP_TIMER ThreadpoolTimer; // r14
  struct _TP_TIMER *v5; // rsi
  DWORD v6; // ebx
  struct _FILETIME pftDueTime; // [rsp+40h] [rbp+8h] BYREF

  if ( !*((_BYTE *)pv + 65) )
  {
    v2 = (struct _TP_TIMER *)pv[6];
    if ( v2 )
      goto LABEL_6;
    LastError = GetLastError();
    ThreadpoolTimer = CreateThreadpoolTimer(_lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_, pv, 0);
    v5 = (struct _TP_TIMER *)pv[6];
    if ( v5 )
    {
      v6 = GetLastError();
      SetThreadpoolTimer(v5, 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(v5, 1);
      CloseThreadpoolTimer(v5);
      SetLastError(v6);
    }
    pv[6] = ThreadpoolTimer;
    SetLastError(LastError);
    v2 = (struct _TP_TIMER *)pv[6];
    if ( v2 )
    {
LABEL_6:
      pftDueTime = (struct _FILETIME)-3000000000LL;
      SetThreadpoolTimer(v2, &pftDueTime, 0, 0x124F8u);
      *((_BYTE *)pv + 65) = 1;
    }
  }
}

```

## disassembly

```asm
0x180011b54  mov     [rsp+arg_8], rbx
0x180011b59  mov     [rsp+arg_10], rbp
0x180011b5e  push    rsi
0x180011b5f  push    rdi
0x180011b60  push    r14
0x180011b62  sub     rsp, 20h
0x180011b66  mov     rdi, rcx
0x180011b69  cmp     byte ptr [rcx+41h], 0
0x180011b6d  jnz     loc_180011C19
0x180011b73  mov     rcx, [rcx+30h]
0x180011b77  test    rcx, rcx
0x180011b7a  jnz     short loc_180011BF2
0x180011b7c  call    cs:__imp_GetLastError
0x180011b82  mov     ebp, eax
0x180011b84  xor     r8d, r8d; pcbe
0x180011b87  mov     rdx, rdi; pv
0x180011b8a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180011b91  call    cs:__imp_CreateThreadpoolTimer
0x180011b97  mov     r14, rax
0x180011b9a  mov     rsi, [rdi+30h]
0x180011b9e  test    rsi, rsi
0x180011ba1  jz      short loc_180011BDD
0x180011ba3  call    cs:__imp_GetLastError
0x180011ba9  mov     ebx, eax
0x180011bab  xor     r9d, r9d; msWindowLength
0x180011bae  xor     r8d, r8d; msPeriod
0x180011bb1  xor     edx, edx; pftDueTime
0x180011bb3  mov     rcx, rsi; pti
0x180011bb6  call    cs:__imp_SetThreadpoolTimer
0x180011bbc  mov     edx, 1; fCancelPendingCallbacks
0x180011bc1  mov     rcx, rsi; pti
0x180011bc4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180011bca  mov     rcx, rsi; pti
0x180011bcd  call    cs:__imp_CloseThreadpoolTimer
0x180011bd3  nop
0x180011bd4  mov     ecx, ebx; dwErrCode
0x180011bd6  call    cs:__imp_SetLastError
0x180011bdc  nop
0x180011bdd  mov     [rdi+30h], r14
0x180011be1  mov     ecx, ebp; dwErrCode
0x180011be3  call    cs:__imp_SetLastError
0x180011be9  mov     rcx, [rdi+30h]; pti
0x180011bed  test    rcx, rcx
0x180011bf0  jz      short loc_180011C19
0x180011bf2  mov     rax, 0FFFFFFFF4D2FA200h
0x180011bfc  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x180011c01  mov     r9d, 124F8h; msWindowLength
0x180011c07  xor     r8d, r8d; msPeriod
0x180011c0a  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180011c0f  call    cs:__imp_SetThreadpoolTimer
0x180011c15  mov     byte ptr [rdi+41h], 1
0x180011c19  mov     rbx, [rsp+38h+arg_8]
0x180011c1e  mov     rbp, [rsp+38h+arg_10]
0x180011c23  add     rsp, 20h
0x180011c27  pop     r14
0x180011c29  pop     rdi
0x180011c2a  pop     rsi
0x180011c2b  retn
```
