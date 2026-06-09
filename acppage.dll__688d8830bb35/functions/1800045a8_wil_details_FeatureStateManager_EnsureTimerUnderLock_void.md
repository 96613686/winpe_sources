# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x1800045a8`
- end: `0x18000467c`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180006414`

## callees

- `0x1800045a8`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180004627`
- `KERNEL32!SetLastError` at `0x180004633`
- `KERNEL32!SetLastError` at `0x180004627`
- `KERNEL32!SetLastError` at `0x180004633`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180004616`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180004616`
- `KERNEL32!GetLastError` at `0x1800045ce`
- `KERNEL32!GetLastError` at `0x1800045f5`
- `KERNEL32!GetLastError` at `0x1800045ce`
- `KERNEL32!GetLastError` at `0x1800045f5`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000461f`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000461f`
- `KERNEL32!SetThreadpoolTimer` at `0x180004608`
- `KERNEL32!SetThreadpoolTimer` at `0x18000465f`
- `KERNEL32!SetThreadpoolTimer` at `0x180004608`
- `KERNEL32!SetThreadpoolTimer` at `0x18000465f`
- `KERNEL32!CreateThreadpoolTimer` at `0x1800045e3`
- `KERNEL32!CreateThreadpoolTimer` at `0x1800045e3`

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
0x1800045a8  mov     [rsp+arg_8], rbx
0x1800045ad  mov     [rsp+arg_10], rbp
0x1800045b2  push    rsi
0x1800045b3  push    rdi
0x1800045b4  push    r14
0x1800045b6  sub     rsp, 20h
0x1800045ba  cmp     byte ptr [rcx+41h], 0
0x1800045be  mov     rdi, rcx
0x1800045c1  jnz     loc_180004669
0x1800045c7  cmp     qword ptr [rcx+30h], 0
0x1800045cc  jnz     short loc_180004639
0x1800045ce  call    cs:__imp_GetLastError
0x1800045d4  xor     r8d, r8d; pcbe
0x1800045d7  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800045de  mov     rdx, rdi; pv
0x1800045e1  mov     ebp, eax
0x1800045e3  call    cs:__imp_CreateThreadpoolTimer
0x1800045e9  mov     rsi, [rdi+30h]
0x1800045ed  mov     r14, rax
0x1800045f0  test    rsi, rsi
0x1800045f3  jz      short loc_18000462D
0x1800045f5  call    cs:__imp_GetLastError
0x1800045fb  xor     r9d, r9d; msWindowLength
0x1800045fe  xor     r8d, r8d; msPeriod
0x180004601  xor     edx, edx; pftDueTime
0x180004603  mov     rcx, rsi; pti
0x180004606  mov     ebx, eax
0x180004608  call    cs:__imp_SetThreadpoolTimer
0x18000460e  mov     edx, 1; fCancelPendingCallbacks
0x180004613  mov     rcx, rsi; pti
0x180004616  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000461c  mov     rcx, rsi; pti
0x18000461f  call    cs:__imp_CloseThreadpoolTimer
0x180004625  mov     ecx, ebx; dwErrCode
0x180004627  call    cs:__imp_SetLastError
0x18000462d  mov     ecx, ebp; dwErrCode
0x18000462f  mov     [rdi+30h], r14
0x180004633  call    cs:__imp_SetLastError
0x180004639  mov     rcx, [rdi+30h]; pti
0x18000463d  test    rcx, rcx
0x180004640  jz      short loc_180004669
0x180004642  mov     rax, 0FFFFFFFF4D2FA200h
0x18000464c  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180004651  mov     r9d, 124F8h; msWindowLength
0x180004657  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x18000465c  xor     r8d, r8d; msPeriod
0x18000465f  call    cs:__imp_SetThreadpoolTimer
0x180004665  mov     byte ptr [rdi+41h], 1
0x180004669  mov     rbx, [rsp+38h+arg_8]
0x18000466e  mov     rbp, [rsp+38h+arg_10]
0x180004673  add     rsp, 20h
0x180004677  pop     r14
0x180004679  pop     rdi
0x18000467a  pop     rsi
0x18000467b  retn
```
