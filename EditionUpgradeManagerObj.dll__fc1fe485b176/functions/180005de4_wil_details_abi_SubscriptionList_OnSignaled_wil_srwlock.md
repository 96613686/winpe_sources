# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x180005de4`
- end: `0x180005ea1`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002840`
- `0x180002870`
- `0x180002920`
- `0x1800081a0`

## callees

- `0x180005de4`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005e2a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005e2a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005e89`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005e89`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180005dfa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180005dfa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180005e14`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180005e14`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005e6b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005e6b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005e33`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005e33`

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
0x180005de4  push    rbx
0x180005de6  push    rbp
0x180005de7  push    rsi
0x180005de8  push    rdi
0x180005de9  push    r14
0x180005deb  push    r15
0x180005ded  sub     rsp, 28h
0x180005df1  mov     rsi, rcx
0x180005df4  mov     rbp, rdx
0x180005df7  mov     rcx, rdx; SRWLock
0x180005dfa  call    cs:__imp_AcquireSRWLockShared
0x180005e00  mov     rdi, [rsi+30h]
0x180005e04  sub     rdi, [rsi+28h]
0x180005e08  shr     rdi, 4
0x180005e0c  test    rbp, rbp
0x180005e0f  jz      short loc_180005E1A
0x180005e11  mov     rcx, rbp; SRWLock
0x180005e14  call    cs:__imp_ReleaseSRWLockShared
0x180005e1a  xor     ebx, ebx
0x180005e1c  test    rdi, rdi
0x180005e1f  jz      short loc_180005E94
0x180005e21  mov     rcx, rsi; lpCriticalSection
0x180005e24  xor     r14d, r14d
0x180005e27  xor     r15d, r15d
0x180005e2a  call    cs:__imp_EnterCriticalSection
0x180005e30  mov     rcx, rbp; SRWLock
0x180005e33  call    cs:__imp_AcquireSRWLockExclusive
0x180005e39  cmp     rbx, rdi
0x180005e3c  jnb     short loc_180005E63
0x180005e3e  mov     rdx, [rsi+28h]
0x180005e42  lea     rax, [rbx+1]
0x180005e46  add     rbx, rbx
0x180005e49  lea     rcx, [rdx+rbx*8]
0x180005e4d  mov     rbx, rax
0x180005e50  cmp     [rcx], r14
0x180005e53  jnz     short loc_180005E5C
0x180005e55  cmp     rax, rdi
0x180005e58  jb      short loc_180005E42
0x180005e5a  jmp     short loc_180005E63
0x180005e5c  mov     r14, [rcx]
0x180005e5f  mov     r15, [rcx+8]
0x180005e63  test    rbp, rbp
0x180005e66  jz      short loc_180005E71
0x180005e68  mov     rcx, rbp; SRWLock
0x180005e6b  call    cs:__imp_ReleaseSRWLockExclusive
0x180005e71  test    r14, r14
0x180005e74  jz      short loc_180005E81
0x180005e76  mov     rcx, r15
0x180005e79  mov     rax, r14
0x180005e7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e81  test    rsi, rsi
0x180005e84  jz      short loc_180005E8F
0x180005e86  mov     rcx, rsi; lpCriticalSection
0x180005e89  call    cs:__imp_LeaveCriticalSection
0x180005e8f  cmp     rbx, rdi
0x180005e92  jb      short loc_180005E21
0x180005e94  add     rsp, 28h
0x180005e98  pop     r15
0x180005e9a  pop     r14
0x180005e9c  pop     rdi
0x180005e9d  pop     rsi
0x180005e9e  pop     rbp
0x180005e9f  pop     rbx
0x180005ea0  retn
```
