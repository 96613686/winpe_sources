# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x18000d46c`
- end: `0x18000d540`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000fd38`
- `0x1800125b0`

## callees

- `0x18000d46c`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x18000d4a7`
- `KERNEL32!CreateThreadpoolTimer` at `0x18000d4a7`
- `KERNEL32!SetThreadpoolTimer` at `0x18000d4cc`
- `KERNEL32!SetThreadpoolTimer` at `0x18000d523`
- `KERNEL32!SetThreadpoolTimer` at `0x18000d4cc`
- `KERNEL32!SetThreadpoolTimer` at `0x18000d523`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000d4e3`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000d4e3`
- `KERNEL32!GetLastError` at `0x18000d492`
- `KERNEL32!GetLastError` at `0x18000d4b9`
- `KERNEL32!GetLastError` at `0x18000d492`
- `KERNEL32!GetLastError` at `0x18000d4b9`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000d4da`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000d4da`
- `KERNEL32!SetLastError` at `0x18000d4eb`
- `KERNEL32!SetLastError` at `0x18000d4f7`
- `KERNEL32!SetLastError` at `0x18000d4eb`
- `KERNEL32!SetLastError` at `0x18000d4f7`

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
0x18000d46c  mov     [rsp+arg_8], rbx
0x18000d471  mov     [rsp+arg_10], rbp
0x18000d476  push    rsi
0x18000d477  push    rdi
0x18000d478  push    r14
0x18000d47a  sub     rsp, 20h
0x18000d47e  cmp     byte ptr [rcx+41h], 0
0x18000d482  mov     rdi, rcx
0x18000d485  jnz     loc_18000D52D
0x18000d48b  cmp     qword ptr [rcx+30h], 0
0x18000d490  jnz     short loc_18000D4FD
0x18000d492  call    cs:__imp_GetLastError
0x18000d498  xor     r8d, r8d; pcbe
0x18000d49b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000d4a2  mov     rdx, rdi; pv
0x18000d4a5  mov     ebp, eax
0x18000d4a7  call    cs:__imp_CreateThreadpoolTimer
0x18000d4ad  mov     rsi, [rdi+30h]
0x18000d4b1  mov     r14, rax
0x18000d4b4  test    rsi, rsi
0x18000d4b7  jz      short loc_18000D4F1
0x18000d4b9  call    cs:__imp_GetLastError
0x18000d4bf  xor     r9d, r9d; msWindowLength
0x18000d4c2  xor     r8d, r8d; msPeriod
0x18000d4c5  xor     edx, edx; pftDueTime
0x18000d4c7  mov     rcx, rsi; pti
0x18000d4ca  mov     ebx, eax
0x18000d4cc  call    cs:__imp_SetThreadpoolTimer
0x18000d4d2  mov     edx, 1; fCancelPendingCallbacks
0x18000d4d7  mov     rcx, rsi; pti
0x18000d4da  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000d4e0  mov     rcx, rsi; pti
0x18000d4e3  call    cs:__imp_CloseThreadpoolTimer
0x18000d4e9  mov     ecx, ebx; dwErrCode
0x18000d4eb  call    cs:__imp_SetLastError
0x18000d4f1  mov     ecx, ebp; dwErrCode
0x18000d4f3  mov     [rdi+30h], r14
0x18000d4f7  call    cs:__imp_SetLastError
0x18000d4fd  mov     rcx, [rdi+30h]; pti
0x18000d501  test    rcx, rcx
0x18000d504  jz      short loc_18000D52D
0x18000d506  mov     rax, 0FFFFFFFF4D2FA200h
0x18000d510  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x18000d515  mov     r9d, 124F8h; msWindowLength
0x18000d51b  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x18000d520  xor     r8d, r8d; msPeriod
0x18000d523  call    cs:__imp_SetThreadpoolTimer
0x18000d529  mov     byte ptr [rdi+41h], 1
0x18000d52d  mov     rbx, [rsp+38h+arg_8]
0x18000d532  mov     rbp, [rsp+38h+arg_10]
0x18000d537  add     rsp, 20h
0x18000d53b  pop     r14
0x18000d53d  pop     rdi
0x18000d53e  pop     rsi
0x18000d53f  retn
```
