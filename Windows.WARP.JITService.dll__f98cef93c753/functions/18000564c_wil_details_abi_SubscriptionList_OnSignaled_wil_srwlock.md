# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x18000564c`
- end: `0x180005709`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180005ff0`
- `0x180006020`
- `0x180006050`
- `0x180007030`

## callees

- `0x18000564c`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180005662`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180005662`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000567c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000567c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000569b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000569b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800056d3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800056d3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005692`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005692`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800056f1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800056f1`

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
0x18000564c  push    rbx
0x18000564e  push    rbp
0x18000564f  push    rsi
0x180005650  push    rdi
0x180005651  push    r14
0x180005653  push    r15
0x180005655  sub     rsp, 28h
0x180005659  mov     rbp, rdx
0x18000565c  mov     rsi, rcx
0x18000565f  mov     rcx, rdx; SRWLock
0x180005662  call    cs:__imp_AcquireSRWLockShared
0x180005668  mov     rdi, [rsi+30h]
0x18000566c  sub     rdi, [rsi+28h]
0x180005670  shr     rdi, 4
0x180005674  test    rbp, rbp
0x180005677  jz      short loc_180005682
0x180005679  mov     rcx, rbp; SRWLock
0x18000567c  call    cs:__imp_ReleaseSRWLockShared
0x180005682  xor     ebx, ebx
0x180005684  test    rdi, rdi
0x180005687  jz      short loc_1800056FC
0x180005689  xor     r14d, r14d
0x18000568c  xor     r15d, r15d
0x18000568f  mov     rcx, rsi; lpCriticalSection
0x180005692  call    cs:__imp_EnterCriticalSection
0x180005698  mov     rcx, rbp; SRWLock
0x18000569b  call    cs:__imp_AcquireSRWLockExclusive
0x1800056a1  cmp     rbx, rdi
0x1800056a4  jnb     short loc_1800056CB
0x1800056a6  mov     rdx, [rsi+28h]
0x1800056aa  lea     rax, [rbx+1]
0x1800056ae  add     rbx, rbx
0x1800056b1  lea     rcx, [rdx+rbx*8]
0x1800056b5  mov     rbx, rax
0x1800056b8  cmp     [rcx], r14
0x1800056bb  jnz     short loc_1800056C4
0x1800056bd  cmp     rax, rdi
0x1800056c0  jb      short loc_1800056AA
0x1800056c2  jmp     short loc_1800056CB
0x1800056c4  mov     r14, [rcx]
0x1800056c7  mov     r15, [rcx+8]
0x1800056cb  test    rbp, rbp
0x1800056ce  jz      short loc_1800056D9
0x1800056d0  mov     rcx, rbp; SRWLock
0x1800056d3  call    cs:__imp_ReleaseSRWLockExclusive
0x1800056d9  test    r14, r14
0x1800056dc  jz      short loc_1800056E9
0x1800056de  mov     rcx, r15
0x1800056e1  mov     rax, r14
0x1800056e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056e9  test    rsi, rsi
0x1800056ec  jz      short loc_1800056F7
0x1800056ee  mov     rcx, rsi; lpCriticalSection
0x1800056f1  call    cs:__imp_LeaveCriticalSection
0x1800056f7  cmp     rbx, rdi
0x1800056fa  jb      short loc_180005689
0x1800056fc  add     rsp, 28h
0x180005700  pop     r15
0x180005702  pop     r14
0x180005704  pop     rdi
0x180005705  pop     rsi
0x180005706  pop     rbp
0x180005707  pop     rbx
0x180005708  retn
```
