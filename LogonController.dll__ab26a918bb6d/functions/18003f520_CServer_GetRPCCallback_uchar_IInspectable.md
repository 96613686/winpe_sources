# CServer::GetRPCCallback(uchar,IInspectable * *)

- ea: `0x18003f520`
- end: `0x18003f5d6`
- name: `?GetRPCCallback@CServer@@UEAAJEPEAPEAUIInspectable@@@Z`
- size: `182`
- prototype: `__int64 __fastcall(CServer *__hidden this, unsigned __int8, struct IInspectable **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18003f520`
- `0x18009d010`

## import_xrefs

- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18003f5a5`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18003f5a5`
- `KERNEL32!CloseThreadpoolTimer` at `0x18003f5c5`
- `KERNEL32!CloseThreadpoolTimer` at `0x18003f5c5`
- `KERNEL32!SetThreadpoolTimer` at `0x18003f596`
- `KERNEL32!SetThreadpoolTimer` at `0x18003f596`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18003f586`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18003f586`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18003f56f`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18003f56f`
- `KERNEL32!SetLastError` at `0x18003f5cd`
- `KERNEL32!SetLastError` at `0x18003f5cd`
- `KERNEL32!GetLastError` at `0x18003f5ba`
- `KERNEL32!GetLastError` at `0x18003f5ba`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CServer::GetRPCCallback(CServer *this, char a2, struct IInspectable **a3)
{
  RTL_SRWLOCK *v6; // rbp
  struct _TP_TIMER *v7; // rcx
  struct _TP_TIMER *v8; // r14
  DWORD LastError; // edi

  *a3 = 0;
  if ( *((_QWORD *)this + 9) && a2 )
  {
    v6 = (RTL_SRWLOCK *)((char *)this + 64);
    AcquireSRWLockExclusive((PSRWLOCK)this + 8);
    v7 = (struct _TP_TIMER *)*((_QWORD *)this + 9);
    if ( v7 )
    {
      SetThreadpoolTimer(v7, 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 9), 1);
      v8 = (struct _TP_TIMER *)*((_QWORD *)this + 9);
      if ( v8 )
      {
        LastError = GetLastError();
        CloseThreadpoolTimer(v8);
        SetLastError(LastError);
      }
      *((_QWORD *)this + 9) = 0;
    }
    if ( v6 )
      ReleaseSRWLockExclusive(v6);
  }
  return (***((__int64 (__fastcall ****)(_QWORD, GUID *, struct IInspectable **))this + 10))(
           *((_QWORD *)this + 10),
           &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
           a3);
}

```

## disassembly

```asm
0x18003f520  push    rbx
0x18003f522  push    rbp
0x18003f523  push    rsi
0x18003f524  push    rdi
0x18003f525  push    r14
0x18003f527  push    r15
0x18003f529  sub     rsp, 28h
0x18003f52d  mov     rsi, r8
0x18003f530  mov     rbx, rcx
0x18003f533  xor     r15d, r15d
0x18003f536  mov     [r8], r15
0x18003f539  cmp     [rcx+48h], r15
0x18003f53d  jnz     short loc_18003F564
0x18003f53f  mov     rcx, [rbx+50h]
0x18003f543  mov     rax, [rcx]
0x18003f546  mov     r8, rsi
0x18003f549  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x18003f550  mov     rax, [rax]
0x18003f553  add     rsp, 28h
0x18003f557  pop     r15
0x18003f559  pop     r14
0x18003f55b  pop     rdi
0x18003f55c  pop     rsi
0x18003f55d  pop     rbp
0x18003f55e  pop     rbx
0x18003f55f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18003f564  test    dl, dl
0x18003f566  jz      short loc_18003F53F
0x18003f568  lea     rbp, [rcx+40h]
0x18003f56c  mov     rcx, rbp; SRWLock
0x18003f56f  call    cs:__imp_AcquireSRWLockExclusive
0x18003f575  mov     rcx, [rbx+48h]; pti
0x18003f579  test    rcx, rcx
0x18003f57c  jnz     short loc_18003F58E
0x18003f57e  test    rbp, rbp
0x18003f581  jz      short loc_18003F53F
0x18003f583  mov     rcx, rbp; SRWLock
0x18003f586  call    cs:__imp_ReleaseSRWLockExclusive
0x18003f58c  jmp     short loc_18003F53F
0x18003f58e  xor     r9d, r9d; msWindowLength
0x18003f591  xor     r8d, r8d; msPeriod
0x18003f594  xor     edx, edx; pftDueTime
0x18003f596  call    cs:__imp_SetThreadpoolTimer
0x18003f59c  mov     edx, 1; fCancelPendingCallbacks
0x18003f5a1  mov     rcx, [rbx+48h]; pti
0x18003f5a5  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18003f5ab  mov     r14, [rbx+48h]
0x18003f5af  test    r14, r14
0x18003f5b2  jnz     short loc_18003F5BA
0x18003f5b4  mov     [rbx+48h], r15
0x18003f5b8  jmp     short loc_18003F57E
0x18003f5ba  call    cs:__imp_GetLastError
0x18003f5c0  mov     edi, eax
0x18003f5c2  mov     rcx, r14; pti
0x18003f5c5  call    cs:__imp_CloseThreadpoolTimer
0x18003f5cb  mov     ecx, edi; dwErrCode
0x18003f5cd  call    cs:__imp_SetLastError
0x18003f5d3  nop
0x18003f5d4  jmp     short loc_18003F5B4
```
