# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x140004ddc`
- end: `0x140004eb0`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140007f14`

## callees

- `0x140004ddc`

## import_xrefs

- `KERNEL32!SetLastError` at `0x140004e5b`
- `KERNEL32!SetLastError` at `0x140004e67`
- `KERNEL32!SetLastError` at `0x140004e5b`
- `KERNEL32!SetLastError` at `0x140004e67`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140004e4a`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140004e4a`
- `KERNEL32!GetLastError` at `0x140004e02`
- `KERNEL32!GetLastError` at `0x140004e29`
- `KERNEL32!GetLastError` at `0x140004e02`
- `KERNEL32!GetLastError` at `0x140004e29`
- `KERNEL32!CloseThreadpoolTimer` at `0x140004e53`
- `KERNEL32!CloseThreadpoolTimer` at `0x140004e53`
- `KERNEL32!SetThreadpoolTimer` at `0x140004e3c`
- `KERNEL32!SetThreadpoolTimer` at `0x140004e93`
- `KERNEL32!SetThreadpoolTimer` at `0x140004e3c`
- `KERNEL32!SetThreadpoolTimer` at `0x140004e93`
- `KERNEL32!CreateThreadpoolTimer` at `0x140004e17`
- `KERNEL32!CreateThreadpoolTimer` at `0x140004e17`

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
0x140004ddc  mov     [rsp+arg_8], rbx
0x140004de1  mov     [rsp+arg_10], rbp
0x140004de6  push    rsi
0x140004de7  push    rdi
0x140004de8  push    r14
0x140004dea  sub     rsp, 20h
0x140004dee  cmp     byte ptr [rcx+41h], 0
0x140004df2  mov     rdi, rcx
0x140004df5  jnz     loc_140004E9D
0x140004dfb  cmp     qword ptr [rcx+30h], 0
0x140004e00  jnz     short loc_140004E6D
0x140004e02  call    cs:__imp_GetLastError
0x140004e08  xor     r8d, r8d; pcbe
0x140004e0b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140004e12  mov     rdx, rdi; pv
0x140004e15  mov     ebp, eax
0x140004e17  call    cs:__imp_CreateThreadpoolTimer
0x140004e1d  mov     rsi, [rdi+30h]
0x140004e21  mov     r14, rax
0x140004e24  test    rsi, rsi
0x140004e27  jz      short loc_140004E61
0x140004e29  call    cs:__imp_GetLastError
0x140004e2f  xor     r9d, r9d; msWindowLength
0x140004e32  xor     r8d, r8d; msPeriod
0x140004e35  xor     edx, edx; pftDueTime
0x140004e37  mov     rcx, rsi; pti
0x140004e3a  mov     ebx, eax
0x140004e3c  call    cs:__imp_SetThreadpoolTimer
0x140004e42  mov     edx, 1; fCancelPendingCallbacks
0x140004e47  mov     rcx, rsi; pti
0x140004e4a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140004e50  mov     rcx, rsi; pti
0x140004e53  call    cs:__imp_CloseThreadpoolTimer
0x140004e59  mov     ecx, ebx; dwErrCode
0x140004e5b  call    cs:__imp_SetLastError
0x140004e61  mov     ecx, ebp; dwErrCode
0x140004e63  mov     [rdi+30h], r14
0x140004e67  call    cs:__imp_SetLastError
0x140004e6d  mov     rcx, [rdi+30h]; pti
0x140004e71  test    rcx, rcx
0x140004e74  jz      short loc_140004E9D
0x140004e76  mov     rax, 0FFFFFFFF4D2FA200h
0x140004e80  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x140004e85  mov     r9d, 124F8h; msWindowLength
0x140004e8b  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x140004e90  xor     r8d, r8d; msPeriod
0x140004e93  call    cs:__imp_SetThreadpoolTimer
0x140004e99  mov     byte ptr [rdi+41h], 1
0x140004e9d  mov     rbx, [rsp+38h+arg_8]
0x140004ea2  mov     rbp, [rsp+38h+arg_10]
0x140004ea7  add     rsp, 20h
0x140004eab  pop     r14
0x140004ead  pop     rdi
0x140004eae  pop     rsi
0x140004eaf  retn
```
