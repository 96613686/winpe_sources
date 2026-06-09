# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180010ce0`
- end: `0x180010db4`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180011534`

## callees

- `0x180010ce0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180010d5f`
- `KERNEL32!SetLastError` at `0x180010d6b`
- `KERNEL32!SetLastError` at `0x180010d5f`
- `KERNEL32!SetLastError` at `0x180010d6b`
- `KERNEL32!GetLastError` at `0x180010d06`
- `KERNEL32!GetLastError` at `0x180010d2d`
- `KERNEL32!GetLastError` at `0x180010d06`
- `KERNEL32!GetLastError` at `0x180010d2d`
- `KERNEL32!CloseThreadpoolTimer` at `0x180010d57`
- `KERNEL32!CloseThreadpoolTimer` at `0x180010d57`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180010d4e`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180010d4e`
- `KERNEL32!SetThreadpoolTimer` at `0x180010d40`
- `KERNEL32!SetThreadpoolTimer` at `0x180010d97`
- `KERNEL32!SetThreadpoolTimer` at `0x180010d40`
- `KERNEL32!SetThreadpoolTimer` at `0x180010d97`
- `KERNEL32!CreateThreadpoolTimer` at `0x180010d1b`
- `KERNEL32!CreateThreadpoolTimer` at `0x180010d1b`

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
0x180010ce0  mov     [rsp+arg_8], rbx
0x180010ce5  mov     [rsp+arg_10], rbp
0x180010cea  push    rsi
0x180010ceb  push    rdi
0x180010cec  push    r14
0x180010cee  sub     rsp, 20h
0x180010cf2  cmp     byte ptr [rcx+41h], 0
0x180010cf6  mov     rdi, rcx
0x180010cf9  jnz     loc_180010DA1
0x180010cff  cmp     qword ptr [rcx+30h], 0
0x180010d04  jnz     short loc_180010D71
0x180010d06  call    cs:__imp_GetLastError
0x180010d0c  xor     r8d, r8d; pcbe
0x180010d0f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180010d16  mov     rdx, rdi; pv
0x180010d19  mov     ebp, eax
0x180010d1b  call    cs:__imp_CreateThreadpoolTimer
0x180010d21  mov     rsi, [rdi+30h]
0x180010d25  mov     r14, rax
0x180010d28  test    rsi, rsi
0x180010d2b  jz      short loc_180010D65
0x180010d2d  call    cs:__imp_GetLastError
0x180010d33  xor     r9d, r9d; msWindowLength
0x180010d36  xor     r8d, r8d; msPeriod
0x180010d39  xor     edx, edx; pftDueTime
0x180010d3b  mov     rcx, rsi; pti
0x180010d3e  mov     ebx, eax
0x180010d40  call    cs:__imp_SetThreadpoolTimer
0x180010d46  mov     edx, 1; fCancelPendingCallbacks
0x180010d4b  mov     rcx, rsi; pti
0x180010d4e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180010d54  mov     rcx, rsi; pti
0x180010d57  call    cs:__imp_CloseThreadpoolTimer
0x180010d5d  mov     ecx, ebx; dwErrCode
0x180010d5f  call    cs:__imp_SetLastError
0x180010d65  mov     ecx, ebp; dwErrCode
0x180010d67  mov     [rdi+30h], r14
0x180010d6b  call    cs:__imp_SetLastError
0x180010d71  mov     rcx, [rdi+30h]; pti
0x180010d75  test    rcx, rcx
0x180010d78  jz      short loc_180010DA1
0x180010d7a  mov     rax, 0FFFFFFFF4D2FA200h
0x180010d84  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180010d89  mov     r9d, 124F8h; msWindowLength
0x180010d8f  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x180010d94  xor     r8d, r8d; msPeriod
0x180010d97  call    cs:__imp_SetThreadpoolTimer
0x180010d9d  mov     byte ptr [rdi+41h], 1
0x180010da1  mov     rbx, [rsp+38h+arg_8]
0x180010da6  mov     rbp, [rsp+38h+arg_10]
0x180010dab  add     rsp, 20h
0x180010daf  pop     r14
0x180010db1  pop     rdi
0x180010db2  pop     rsi
0x180010db3  retn
```
