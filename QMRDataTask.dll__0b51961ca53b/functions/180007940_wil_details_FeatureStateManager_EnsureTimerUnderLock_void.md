# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180007940`
- end: `0x180007a14`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000cdd4`

## callees

- `0x180007940`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180007966`
- `KERNEL32!GetLastError` at `0x18000798d`
- `KERNEL32!GetLastError` at `0x180007966`
- `KERNEL32!GetLastError` at `0x18000798d`
- `KERNEL32!CreateThreadpoolTimer` at `0x18000797b`
- `KERNEL32!CreateThreadpoolTimer` at `0x18000797b`
- `KERNEL32!SetThreadpoolTimer` at `0x1800079a0`
- `KERNEL32!SetThreadpoolTimer` at `0x1800079f7`
- `KERNEL32!SetThreadpoolTimer` at `0x1800079a0`
- `KERNEL32!SetThreadpoolTimer` at `0x1800079f7`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800079b7`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800079b7`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800079ae`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800079ae`
- `KERNEL32!SetLastError` at `0x1800079bf`
- `KERNEL32!SetLastError` at `0x1800079cb`
- `KERNEL32!SetLastError` at `0x1800079bf`
- `KERNEL32!SetLastError` at `0x1800079cb`

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
0x180007940  mov     [rsp+arg_8], rbx
0x180007945  mov     [rsp+arg_10], rbp
0x18000794a  push    rsi
0x18000794b  push    rdi
0x18000794c  push    r14
0x18000794e  sub     rsp, 20h
0x180007952  cmp     byte ptr [rcx+41h], 0
0x180007956  mov     rdi, rcx
0x180007959  jnz     loc_180007A01
0x18000795f  cmp     qword ptr [rcx+30h], 0
0x180007964  jnz     short loc_1800079D1
0x180007966  call    cs:__imp_GetLastError
0x18000796c  xor     r8d, r8d; pcbe
0x18000796f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180007976  mov     rdx, rdi; pv
0x180007979  mov     ebp, eax
0x18000797b  call    cs:__imp_CreateThreadpoolTimer
0x180007981  mov     rsi, [rdi+30h]
0x180007985  mov     r14, rax
0x180007988  test    rsi, rsi
0x18000798b  jz      short loc_1800079C5
0x18000798d  call    cs:__imp_GetLastError
0x180007993  xor     r9d, r9d; msWindowLength
0x180007996  xor     r8d, r8d; msPeriod
0x180007999  xor     edx, edx; pftDueTime
0x18000799b  mov     rcx, rsi; pti
0x18000799e  mov     ebx, eax
0x1800079a0  call    cs:__imp_SetThreadpoolTimer
0x1800079a6  mov     edx, 1; fCancelPendingCallbacks
0x1800079ab  mov     rcx, rsi; pti
0x1800079ae  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800079b4  mov     rcx, rsi; pti
0x1800079b7  call    cs:__imp_CloseThreadpoolTimer
0x1800079bd  mov     ecx, ebx; dwErrCode
0x1800079bf  call    cs:__imp_SetLastError
0x1800079c5  mov     ecx, ebp; dwErrCode
0x1800079c7  mov     [rdi+30h], r14
0x1800079cb  call    cs:__imp_SetLastError
0x1800079d1  mov     rcx, [rdi+30h]; pti
0x1800079d5  test    rcx, rcx
0x1800079d8  jz      short loc_180007A01
0x1800079da  mov     rax, 0FFFFFFFF4D2FA200h
0x1800079e4  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x1800079e9  mov     r9d, 124F8h; msWindowLength
0x1800079ef  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x1800079f4  xor     r8d, r8d; msPeriod
0x1800079f7  call    cs:__imp_SetThreadpoolTimer
0x1800079fd  mov     byte ptr [rdi+41h], 1
0x180007a01  mov     rbx, [rsp+38h+arg_8]
0x180007a06  mov     rbp, [rsp+38h+arg_10]
0x180007a0b  add     rsp, 20h
0x180007a0f  pop     r14
0x180007a11  pop     rdi
0x180007a12  pop     rsi
0x180007a13  retn
```
