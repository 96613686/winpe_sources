# ResettableTimer::SetDueTimeFromNow(ulong)

- ea: `0x140006734`
- end: `0x14000683c`
- name: `?SetDueTimeFromNow@ResettableTimer@@QEAAJK@Z`
- size: `264`
- prototype: `__int64 __fastcall(PVOID pv, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140004f6c`

## callees

- `0x140001460`
- `0x140006734`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x140006768`
- `KERNEL32!EnterCriticalSection` at `0x140006768`
- `KERNEL32!LeaveCriticalSection` at `0x140006816`
- `KERNEL32!LeaveCriticalSection` at `0x140006816`
- `KERNEL32!SetLastError` at `0x1400067c6`
- `KERNEL32!SetLastError` at `0x1400067c6`
- `KERNEL32!CreateThreadpoolTimer` at `0x140006782`
- `KERNEL32!CreateThreadpoolTimer` at `0x140006782`
- `KERNEL32!SetThreadpoolTimer` at `0x1400067a7`
- `KERNEL32!SetThreadpoolTimer` at `0x140006808`
- `KERNEL32!SetThreadpoolTimer` at `0x1400067a7`
- `KERNEL32!SetThreadpoolTimer` at `0x140006808`
- `KERNEL32!CloseThreadpoolTimer` at `0x1400067be`
- `KERNEL32!CloseThreadpoolTimer` at `0x1400067be`
- `KERNEL32!GetLastError` at `0x140006794`
- `KERNEL32!GetLastError` at `0x140006794`
- `KERNEL32!GetTickCount64` at `0x140006758`
- `KERNEL32!GetTickCount64` at `0x1400067d0`
- `KERNEL32!GetTickCount64` at `0x140006758`
- `KERNEL32!GetTickCount64` at `0x1400067d0`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1400067b5`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1400067b5`

## pseudocode

```c
__int64 __fastcall ResettableTimer::SetDueTimeFromNow(char *pv, unsigned int a2)
{
  struct _RTL_CRITICAL_SECTION *v3; // rbp
  ULONGLONG v4; // rsi
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v6; // r14
  PTP_TIMER v7; // r15
  DWORD LastError; // ebx
  ULONGLONG TickCount64; // rax
  struct _FILETIME v10; // rdx
  DWORD v11; // r9d
  struct _TP_TIMER *v12; // rcx
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-38h] BYREF

  v3 = (struct _RTL_CRITICAL_SECTION *)(pv + 104);
  v4 = GetTickCount64() + a2;
  EnterCriticalSection(v3);
  if ( !*((_QWORD *)pv + 12) )
  {
    ThreadpoolTimer = CreateThreadpoolTimer(ResettableTimer::TimerCallback, pv, 0);
    v6 = (struct _TP_TIMER *)*((_QWORD *)pv + 12);
    v7 = ThreadpoolTimer;
    if ( v6 )
    {
      LastError = GetLastError();
      SetThreadpoolTimer(v6, 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(v6, 1);
      CloseThreadpoolTimer(v6);
      SetLastError(LastError);
    }
    *((_QWORD *)pv + 12) = v7;
  }
  TickCount64 = GetTickCount64();
  if ( (__int64)(v4 - TickCount64) <= 0 )
  {
    v10 = 0;
    v4 = TickCount64;
  }
  else
  {
    v10 = (struct _FILETIME)(-10000LL * (v4 - TickCount64));
  }
  *((_QWORD *)pv + 11) = v4;
  v11 = *((_DWORD *)pv + 2);
  v12 = (struct _TP_TIMER *)*((_QWORD *)pv + 12);
  pftDueTime = v10;
  SetThreadpoolTimer(v12, &pftDueTime, 0, v11);
  if ( pv != (char *)-104LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)(pv + 104));
  return 0;
}

```

## disassembly

```asm
0x140006734  mov     [rsp+arg_10], rbx
0x140006739  push    rbp
0x14000673a  push    rsi
0x14000673b  push    rdi
0x14000673c  push    r14
0x14000673e  push    r15
0x140006740  sub     rsp, 30h
0x140006744  mov     rax, cs:__security_cookie
0x14000674b  xor     rax, rsp
0x14000674e  mov     [rsp+58h+var_30], rax
0x140006753  mov     esi, edx
0x140006755  mov     rdi, rcx
0x140006758  call    cs:__imp_GetTickCount64
0x14000675e  lea     rbp, [rdi+68h]
0x140006762  add     rsi, rax
0x140006765  mov     rcx, rbp; lpCriticalSection
0x140006768  call    cs:__imp_EnterCriticalSection
0x14000676e  cmp     qword ptr [rdi+60h], 0
0x140006773  jnz     short loc_1400067D0
0x140006775  xor     r8d, r8d; pcbe
0x140006778  lea     rcx, ?TimerCallback@ResettableTimer@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14000677f  mov     rdx, rdi; pv
0x140006782  call    cs:__imp_CreateThreadpoolTimer
0x140006788  mov     r14, [rdi+60h]
0x14000678c  mov     r15, rax
0x14000678f  test    r14, r14
0x140006792  jz      short loc_1400067CC
0x140006794  call    cs:__imp_GetLastError
0x14000679a  xor     r9d, r9d; msWindowLength
0x14000679d  xor     r8d, r8d; msPeriod
0x1400067a0  xor     edx, edx; pftDueTime
0x1400067a2  mov     rcx, r14; pti
0x1400067a5  mov     ebx, eax
0x1400067a7  call    cs:__imp_SetThreadpoolTimer
0x1400067ad  mov     edx, 1; fCancelPendingCallbacks
0x1400067b2  mov     rcx, r14; pti
0x1400067b5  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400067bb  mov     rcx, r14; pti
0x1400067be  call    cs:__imp_CloseThreadpoolTimer
0x1400067c4  mov     ecx, ebx; dwErrCode
0x1400067c6  call    cs:__imp_SetLastError
0x1400067cc  mov     [rdi+60h], r15
0x1400067d0  call    cs:__imp_GetTickCount64
0x1400067d6  mov     rcx, rsi
0x1400067d9  sub     rcx, rax
0x1400067dc  test    rcx, rcx
0x1400067df  jle     short loc_1400067EA
0x1400067e1  imul    rdx, rcx, 0FFFFFFFFFFFFD8F0h
0x1400067e8  jmp     short loc_1400067EF
0x1400067ea  xor     edx, edx
0x1400067ec  mov     rsi, rax
0x1400067ef  mov     [rdi+58h], rsi
0x1400067f3  xor     r8d, r8d; msPeriod
0x1400067f6  mov     r9d, [rdi+8]; msWindowLength
0x1400067fa  mov     rcx, [rdi+60h]; pti
0x1400067fe  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rdx
0x140006803  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x140006808  call    cs:__imp_SetThreadpoolTimer
0x14000680e  test    rbp, rbp
0x140006811  jz      short loc_14000681C
0x140006813  mov     rcx, rbp; lpCriticalSection
0x140006816  call    cs:__imp_LeaveCriticalSection
0x14000681c  xor     eax, eax
0x14000681e  mov     rcx, [rsp+58h+var_30]
0x140006823  xor     rcx, rsp; StackCookie
0x140006826  call    __security_check_cookie
0x14000682b  mov     rbx, [rsp+58h+arg_10]
0x140006830  add     rsp, 30h
0x140006834  pop     r15
0x140006836  pop     r14
0x140006838  pop     rdi
0x140006839  pop     rsi
0x14000683a  pop     rbp
0x14000683b  retn
```
