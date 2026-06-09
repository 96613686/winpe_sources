# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x14000749c`
- end: `0x140007559`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140002b30`
- `0x140002b60`
- `0x140002c60`
- `0x14000a210`

## callees

- `0x14000749c`
- `0x140017010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1400074e2`
- `KERNEL32!EnterCriticalSection` at `0x1400074e2`
- `KERNEL32!LeaveCriticalSection` at `0x140007541`
- `KERNEL32!LeaveCriticalSection` at `0x140007541`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140007523`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140007523`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1400074eb`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1400074eb`
- `KERNEL32!ReleaseSRWLockShared` at `0x1400074cc`
- `KERNEL32!ReleaseSRWLockShared` at `0x1400074cc`
- `KERNEL32!AcquireSRWLockShared` at `0x1400074b2`
- `KERNEL32!AcquireSRWLockShared` at `0x1400074b2`

## pseudocode

```c
void __fastcall wil::details_abi::SubscriptionList::OnSignaled(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)
{
  unsigned __int64 v4; // rdi
  unsigned __int64 v5; // rbx
  void (__fastcall *v6)(__int64); // r14
  __int64 v7; // r15
  unsigned __int64 v8; // rax
  WORD *v9; // rcx

  AcquireSRWLockShared(SRWLock);
  v4 = (*(_QWORD *)&lpCriticalSection[1].LockCount - (unsigned __int64)lpCriticalSection[1].DebugInfo) >> 4;
  if ( SRWLock )
    ReleaseSRWLockShared(SRWLock);
  v5 = 0;
  while ( v5 < v4 )
  {
    v6 = 0;
    v7 = 0;
    EnterCriticalSection(lpCriticalSection);
    AcquireSRWLockExclusive(SRWLock);
    if ( v5 < v4 )
    {
      while ( 1 )
      {
        v8 = v5 + 1;
        v9 = &lpCriticalSection[1].DebugInfo->Type + 8 * v5++;
        if ( *(_QWORD *)v9 )
          break;
        if ( v8 >= v4 )
          goto LABEL_9;
      }
      v6 = *(void (__fastcall **)(__int64))v9;
      v7 = *((_QWORD *)v9 + 1);
    }
LABEL_9:
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    if ( v6 )
      v6(v7);
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
  }
}

```

## disassembly

```asm
0x14000749c  push    rbx
0x14000749e  push    rbp
0x14000749f  push    rsi
0x1400074a0  push    rdi
0x1400074a1  push    r14
0x1400074a3  push    r15
0x1400074a5  sub     rsp, 28h
0x1400074a9  mov     rsi, rcx
0x1400074ac  mov     rbp, rdx
0x1400074af  mov     rcx, rdx; SRWLock
0x1400074b2  call    cs:__imp_AcquireSRWLockShared
0x1400074b8  mov     rdi, [rsi+30h]
0x1400074bc  sub     rdi, [rsi+28h]
0x1400074c0  shr     rdi, 4
0x1400074c4  test    rbp, rbp
0x1400074c7  jz      short loc_1400074D2
0x1400074c9  mov     rcx, rbp; SRWLock
0x1400074cc  call    cs:__imp_ReleaseSRWLockShared
0x1400074d2  xor     ebx, ebx
0x1400074d4  test    rdi, rdi
0x1400074d7  jz      short loc_14000754C
0x1400074d9  mov     rcx, rsi; lpCriticalSection
0x1400074dc  xor     r14d, r14d
0x1400074df  xor     r15d, r15d
0x1400074e2  call    cs:__imp_EnterCriticalSection
0x1400074e8  mov     rcx, rbp; SRWLock
0x1400074eb  call    cs:__imp_AcquireSRWLockExclusive
0x1400074f1  cmp     rbx, rdi
0x1400074f4  jnb     short loc_14000751B
0x1400074f6  mov     rdx, [rsi+28h]
0x1400074fa  lea     rax, [rbx+1]
0x1400074fe  add     rbx, rbx
0x140007501  lea     rcx, [rdx+rbx*8]
0x140007505  mov     rbx, rax
0x140007508  cmp     [rcx], r14
0x14000750b  jnz     short loc_140007514
0x14000750d  cmp     rax, rdi
0x140007510  jb      short loc_1400074FA
0x140007512  jmp     short loc_14000751B
0x140007514  mov     r14, [rcx]
0x140007517  mov     r15, [rcx+8]
0x14000751b  test    rbp, rbp
0x14000751e  jz      short loc_140007529
0x140007520  mov     rcx, rbp; SRWLock
0x140007523  call    cs:__imp_ReleaseSRWLockExclusive
0x140007529  test    r14, r14
0x14000752c  jz      short loc_140007539
0x14000752e  mov     rcx, r15
0x140007531  mov     rax, r14
0x140007534  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007539  test    rsi, rsi
0x14000753c  jz      short loc_140007547
0x14000753e  mov     rcx, rsi; lpCriticalSection
0x140007541  call    cs:__imp_LeaveCriticalSection
0x140007547  cmp     rbx, rdi
0x14000754a  jb      short loc_1400074D9
0x14000754c  add     rsp, 28h
0x140007550  pop     r15
0x140007552  pop     r14
0x140007554  pop     rdi
0x140007555  pop     rsi
0x140007556  pop     rbp
0x140007557  pop     rbx
0x140007558  retn
```
