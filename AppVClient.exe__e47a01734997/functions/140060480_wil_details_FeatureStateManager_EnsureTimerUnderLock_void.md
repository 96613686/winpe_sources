# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x140060480`
- end: `0x140060554`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400619b0`

## callees

- `0x140060480`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x1400604bb`
- `KERNEL32!CreateThreadpoolTimer` at `0x1400604bb`
- `KERNEL32!SetThreadpoolTimer` at `0x1400604e0`
- `KERNEL32!SetThreadpoolTimer` at `0x140060537`
- `KERNEL32!SetThreadpoolTimer` at `0x1400604e0`
- `KERNEL32!SetThreadpoolTimer` at `0x140060537`
- `KERNEL32!CloseThreadpoolTimer` at `0x1400604f7`
- `KERNEL32!CloseThreadpoolTimer` at `0x1400604f7`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1400604ee`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1400604ee`
- `KERNEL32!GetLastError` at `0x1400604a6`
- `KERNEL32!GetLastError` at `0x1400604cd`
- `KERNEL32!GetLastError` at `0x1400604a6`
- `KERNEL32!GetLastError` at `0x1400604cd`
- `KERNEL32!SetLastError` at `0x1400604ff`
- `KERNEL32!SetLastError` at `0x14006050b`
- `KERNEL32!SetLastError` at `0x1400604ff`
- `KERNEL32!SetLastError` at `0x14006050b`

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
0x140060480  mov     [rsp+arg_8], rbx
0x140060485  mov     [rsp+arg_10], rbp
0x14006048a  push    rsi
0x14006048b  push    rdi
0x14006048c  push    r14
0x14006048e  sub     rsp, 20h
0x140060492  cmp     byte ptr [rcx+41h], 0
0x140060496  mov     rdi, rcx
0x140060499  jnz     loc_140060541
0x14006049f  cmp     qword ptr [rcx+30h], 0
0x1400604a4  jnz     short loc_140060511
0x1400604a6  call    cs:__imp_GetLastError
0x1400604ac  xor     r8d, r8d; pcbe
0x1400604af  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1400604b6  mov     rdx, rdi; pv
0x1400604b9  mov     ebp, eax
0x1400604bb  call    cs:__imp_CreateThreadpoolTimer
0x1400604c1  mov     rsi, [rdi+30h]
0x1400604c5  mov     r14, rax
0x1400604c8  test    rsi, rsi
0x1400604cb  jz      short loc_140060505
0x1400604cd  call    cs:__imp_GetLastError
0x1400604d3  xor     r9d, r9d; msWindowLength
0x1400604d6  xor     r8d, r8d; msPeriod
0x1400604d9  xor     edx, edx; pftDueTime
0x1400604db  mov     rcx, rsi; pti
0x1400604de  mov     ebx, eax
0x1400604e0  call    cs:__imp_SetThreadpoolTimer
0x1400604e6  mov     edx, 1; fCancelPendingCallbacks
0x1400604eb  mov     rcx, rsi; pti
0x1400604ee  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400604f4  mov     rcx, rsi; pti
0x1400604f7  call    cs:__imp_CloseThreadpoolTimer
0x1400604fd  mov     ecx, ebx; dwErrCode
0x1400604ff  call    cs:__imp_SetLastError
0x140060505  mov     ecx, ebp; dwErrCode
0x140060507  mov     [rdi+30h], r14
0x14006050b  call    cs:__imp_SetLastError
0x140060511  mov     rcx, [rdi+30h]; pti
0x140060515  test    rcx, rcx
0x140060518  jz      short loc_140060541
0x14006051a  mov     rax, 0FFFFFFFF4D2FA200h
0x140060524  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x140060529  mov     r9d, 124F8h; msWindowLength
0x14006052f  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x140060534  xor     r8d, r8d; msPeriod
0x140060537  call    cs:__imp_SetThreadpoolTimer
0x14006053d  mov     byte ptr [rdi+41h], 1
0x140060541  mov     rbx, [rsp+38h+arg_8]
0x140060546  mov     rbp, [rsp+38h+arg_10]
0x14006054b  add     rsp, 20h
0x14006054f  pop     r14
0x140060551  pop     rdi
0x140060552  pop     rsi
0x140060553  retn
```
