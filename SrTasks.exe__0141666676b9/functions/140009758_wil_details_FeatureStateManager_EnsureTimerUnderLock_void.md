# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x140009758`
- end: `0x14000982c`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000b104`

## callees

- `0x140009758`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000977e`
- `KERNEL32!GetLastError` at `0x1400097a5`
- `KERNEL32!GetLastError` at `0x14000977e`
- `KERNEL32!GetLastError` at `0x1400097a5`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1400097c6`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1400097c6`
- `KERNEL32!CloseThreadpoolTimer` at `0x1400097cf`
- `KERNEL32!CloseThreadpoolTimer` at `0x1400097cf`
- `KERNEL32!CreateThreadpoolTimer` at `0x140009793`
- `KERNEL32!CreateThreadpoolTimer` at `0x140009793`
- `KERNEL32!SetThreadpoolTimer` at `0x1400097b8`
- `KERNEL32!SetThreadpoolTimer` at `0x14000980f`
- `KERNEL32!SetThreadpoolTimer` at `0x1400097b8`
- `KERNEL32!SetThreadpoolTimer` at `0x14000980f`
- `KERNEL32!SetLastError` at `0x1400097d7`
- `KERNEL32!SetLastError` at `0x1400097e3`
- `KERNEL32!SetLastError` at `0x1400097d7`
- `KERNEL32!SetLastError` at `0x1400097e3`

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
0x140009758  mov     [rsp+arg_8], rbx
0x14000975d  mov     [rsp+arg_10], rbp
0x140009762  push    rsi
0x140009763  push    rdi
0x140009764  push    r14
0x140009766  sub     rsp, 20h
0x14000976a  cmp     byte ptr [rcx+41h], 0
0x14000976e  mov     rdi, rcx
0x140009771  jnz     loc_140009819
0x140009777  cmp     qword ptr [rcx+30h], 0
0x14000977c  jnz     short loc_1400097E9
0x14000977e  call    cs:__imp_GetLastError
0x140009784  xor     r8d, r8d; pcbe
0x140009787  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14000978e  mov     rdx, rdi; pv
0x140009791  mov     ebp, eax
0x140009793  call    cs:__imp_CreateThreadpoolTimer
0x140009799  mov     rsi, [rdi+30h]
0x14000979d  mov     r14, rax
0x1400097a0  test    rsi, rsi
0x1400097a3  jz      short loc_1400097DD
0x1400097a5  call    cs:__imp_GetLastError
0x1400097ab  xor     r9d, r9d; msWindowLength
0x1400097ae  xor     r8d, r8d; msPeriod
0x1400097b1  xor     edx, edx; pftDueTime
0x1400097b3  mov     rcx, rsi; pti
0x1400097b6  mov     ebx, eax
0x1400097b8  call    cs:__imp_SetThreadpoolTimer
0x1400097be  mov     edx, 1; fCancelPendingCallbacks
0x1400097c3  mov     rcx, rsi; pti
0x1400097c6  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400097cc  mov     rcx, rsi; pti
0x1400097cf  call    cs:__imp_CloseThreadpoolTimer
0x1400097d5  mov     ecx, ebx; dwErrCode
0x1400097d7  call    cs:__imp_SetLastError
0x1400097dd  mov     ecx, ebp; dwErrCode
0x1400097df  mov     [rdi+30h], r14
0x1400097e3  call    cs:__imp_SetLastError
0x1400097e9  mov     rcx, [rdi+30h]; pti
0x1400097ed  test    rcx, rcx
0x1400097f0  jz      short loc_140009819
0x1400097f2  mov     rax, 0FFFFFFFF4D2FA200h
0x1400097fc  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x140009801  mov     r9d, 124F8h; msWindowLength
0x140009807  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x14000980c  xor     r8d, r8d; msPeriod
0x14000980f  call    cs:__imp_SetThreadpoolTimer
0x140009815  mov     byte ptr [rdi+41h], 1
0x140009819  mov     rbx, [rsp+38h+arg_8]
0x14000981e  mov     rbp, [rsp+38h+arg_10]
0x140009823  add     rsp, 20h
0x140009827  pop     r14
0x140009829  pop     rdi
0x14000982a  pop     rsi
0x14000982b  retn
```
