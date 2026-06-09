# ResettableTimer::~ResettableTimer(void)

- ea: `0x140003524`
- end: `0x140003665`
- name: `??1ResettableTimer@@UEAA@XZ`
- size: `321`
- prototype: `void __fastcall(ResettableTimer *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140003b00`
- `0x140004f6c`
- `0x14000944b`

## callees

- `0x140003124`
- `0x140003524`
- `0x14000a010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x140003545`
- `KERNEL32!EnterCriticalSection` at `0x140003545`
- `KERNEL32!LeaveCriticalSection` at `0x1400035e5`
- `KERNEL32!LeaveCriticalSection` at `0x1400035e5`
- `KERNEL32!SetLastError` at `0x1400035a9`
- `KERNEL32!SetLastError` at `0x140003641`
- `KERNEL32!SetLastError` at `0x1400035a9`
- `KERNEL32!SetLastError` at `0x140003641`
- `KERNEL32!DeleteCriticalSection` at `0x14000364a`
- `KERNEL32!DeleteCriticalSection` at `0x14000364a`
- `KERNEL32!SetThreadpoolTimer` at `0x14000358a`
- `KERNEL32!SetThreadpoolTimer` at `0x1400035fb`
- `KERNEL32!SetThreadpoolTimer` at `0x140003622`
- `KERNEL32!SetThreadpoolTimer` at `0x14000358a`
- `KERNEL32!SetThreadpoolTimer` at `0x1400035fb`
- `KERNEL32!SetThreadpoolTimer` at `0x140003622`
- `KERNEL32!CloseThreadpoolTimer` at `0x1400035a1`
- `KERNEL32!CloseThreadpoolTimer` at `0x140003639`
- `KERNEL32!CloseThreadpoolTimer` at `0x1400035a1`
- `KERNEL32!CloseThreadpoolTimer` at `0x140003639`
- `KERNEL32!GetLastError` at `0x140003577`
- `KERNEL32!GetLastError` at `0x14000360f`
- `KERNEL32!GetLastError` at `0x140003577`
- `KERNEL32!GetLastError` at `0x14000360f`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140003598`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140003609`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140003630`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140003598`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140003609`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140003630`

## pseudocode

```c
void __fastcall ResettableTimer::~ResettableTimer(ResettableTimer *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbp
  __int64 v3; // rdx
  struct _TP_TIMER *v4; // rbx
  char *v5; // rsi
  struct _TP_TIMER *v6; // r15
  DWORD LastError; // edi
  __int64 v8; // rcx
  DWORD v9; // edi
  char v10; // [rsp+20h] [rbp-48h] BYREF
  char v11; // [rsp+28h] [rbp-40h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 104);
  *(_QWORD *)this = &ResettableTimer::`vftable';
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  v4 = 0;
  v5 = (char *)this + 96;
  if ( &v10 != (char *)this + 96 )
  {
    v4 = *(struct _TP_TIMER **)v5;
    *(_QWORD *)v5 = 0;
  }
  if ( v5 != &v11 )
  {
    v6 = *(struct _TP_TIMER **)v5;
    if ( *(_QWORD *)v5 )
    {
      LastError = GetLastError();
      SetThreadpoolTimer(v6, 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(v6, 1);
      CloseThreadpoolTimer(v6);
      SetLastError(LastError);
    }
    *(_QWORD *)v5 = 0;
  }
  v8 = *((_QWORD *)this + 9);
  if ( v8 )
  {
    LOBYTE(v3) = v8 != (_QWORD)this + 16;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 32LL))(v8, v3);
    *((_QWORD *)this + 9) = 0;
  }
  if ( v2 )
    LeaveCriticalSection(v2);
  if ( v4 )
  {
    SetThreadpoolTimer(v4, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v4, 1);
    v9 = GetLastError();
    SetThreadpoolTimer(v4, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v4, 1);
    CloseThreadpoolTimer(v4);
    SetLastError(v9);
  }
  DeleteCriticalSection(v2);
  ResettableTimer::_unnamed_type_m_lockedData_::__unnamed_type_m_lockedData_((char *)this + 8);
}

```

## disassembly

```asm
0x140003524  push    rbx
0x140003526  push    rbp
0x140003527  push    rsi
0x140003528  push    rdi
0x140003529  push    r14
0x14000352b  push    r15
0x14000352d  sub     rsp, 38h
0x140003531  lea     rax, ??_7ResettableTimer@@6B@; const ResettableTimer::`vftable'
0x140003538  mov     r14, rcx
0x14000353b  lea     rbp, [rcx+68h]
0x14000353f  mov     [rcx], rax
0x140003542  mov     rcx, rbp; lpCriticalSection
0x140003545  call    cs:__imp_EnterCriticalSection
0x14000354b  lea     rax, [rsp+68h+var_48]
0x140003550  xor     ebx, ebx
0x140003552  lea     rsi, [r14+60h]
0x140003556  cmp     rax, rsi
0x140003559  jz      short loc_140003565
0x14000355b  mov     rbx, [rsi]
0x14000355e  mov     qword ptr [rsi], 0
0x140003565  lea     rax, [rsp+68h+var_40]
0x14000356a  cmp     rsi, rax
0x14000356d  jz      short loc_1400035B6
0x14000356f  mov     r15, [rsi]
0x140003572  test    r15, r15
0x140003575  jz      short loc_1400035AF
0x140003577  call    cs:__imp_GetLastError
0x14000357d  xor     r9d, r9d; msWindowLength
0x140003580  xor     r8d, r8d; msPeriod
0x140003583  xor     edx, edx; pftDueTime
0x140003585  mov     rcx, r15; pti
0x140003588  mov     edi, eax
0x14000358a  call    cs:__imp_SetThreadpoolTimer
0x140003590  mov     edx, 1; fCancelPendingCallbacks
0x140003595  mov     rcx, r15; pti
0x140003598  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000359e  mov     rcx, r15; pti
0x1400035a1  call    cs:__imp_CloseThreadpoolTimer
0x1400035a7  mov     ecx, edi; dwErrCode
0x1400035a9  call    cs:__imp_SetLastError
0x1400035af  mov     qword ptr [rsi], 0
0x1400035b6  lea     rdi, [r14+10h]
0x1400035ba  mov     rcx, [rdi+38h]
0x1400035be  test    rcx, rcx
0x1400035c1  jz      short loc_1400035DD
0x1400035c3  mov     rax, [rcx]
0x1400035c6  cmp     rcx, rdi
0x1400035c9  setnz   dl
0x1400035cc  mov     rax, [rax+20h]
0x1400035d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400035d5  mov     qword ptr [rdi+38h], 0
0x1400035dd  test    rbp, rbp
0x1400035e0  jz      short loc_1400035EB
0x1400035e2  mov     rcx, rbp; lpCriticalSection
0x1400035e5  call    cs:__imp_LeaveCriticalSection
0x1400035eb  test    rbx, rbx
0x1400035ee  jz      short loc_140003647
0x1400035f0  xor     r9d, r9d; msWindowLength
0x1400035f3  xor     r8d, r8d; msPeriod
0x1400035f6  xor     edx, edx; pftDueTime
0x1400035f8  mov     rcx, rbx; pti
0x1400035fb  call    cs:__imp_SetThreadpoolTimer
0x140003601  mov     edx, 1; fCancelPendingCallbacks
0x140003606  mov     rcx, rbx; pti
0x140003609  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000360f  call    cs:__imp_GetLastError
0x140003615  xor     r9d, r9d; msWindowLength
0x140003618  xor     r8d, r8d; msPeriod
0x14000361b  xor     edx, edx; pftDueTime
0x14000361d  mov     rcx, rbx; pti
0x140003620  mov     edi, eax
0x140003622  call    cs:__imp_SetThreadpoolTimer
0x140003628  mov     edx, 1; fCancelPendingCallbacks
0x14000362d  mov     rcx, rbx; pti
0x140003630  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140003636  mov     rcx, rbx; pti
0x140003639  call    cs:__imp_CloseThreadpoolTimer
0x14000363f  mov     ecx, edi; dwErrCode
0x140003641  call    cs:__imp_SetLastError
0x140003647  mov     rcx, rbp; lpCriticalSection
0x14000364a  call    cs:__imp_DeleteCriticalSection
0x140003650  lea     rcx, [r14+8]
0x140003654  add     rsp, 38h
0x140003658  pop     r15
0x14000365a  pop     r14
0x14000365c  pop     rdi
0x14000365d  pop     rsi
0x14000365e  pop     rbp
0x14000365f  pop     rbx
0x140003660  jmp     ResettableTimer___unnamed_type_m_lockedData_____unnamed_type_m_lockedData_
```
