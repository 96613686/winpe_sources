# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x1800080e4`
- end: `0x1800081a1`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180004c10`
- `0x180004c40`
- `0x180004cf0`
- `0x18000a620`

## callees

- `0x1800080e4`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000816b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000816b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008114`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008114`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008189`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008189`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000812a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000812a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800080fa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800080fa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008133`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008133`

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
0x1800080e4  push    rbx
0x1800080e6  push    rbp
0x1800080e7  push    rsi
0x1800080e8  push    rdi
0x1800080e9  push    r14
0x1800080eb  push    r15
0x1800080ed  sub     rsp, 28h
0x1800080f1  mov     rbp, rdx
0x1800080f4  mov     rsi, rcx
0x1800080f7  mov     rcx, rdx; SRWLock
0x1800080fa  call    cs:__imp_AcquireSRWLockShared
0x180008100  mov     rdi, [rsi+30h]
0x180008104  sub     rdi, [rsi+28h]
0x180008108  shr     rdi, 4
0x18000810c  test    rbp, rbp
0x18000810f  jz      short loc_18000811A
0x180008111  mov     rcx, rbp; SRWLock
0x180008114  call    cs:__imp_ReleaseSRWLockShared
0x18000811a  xor     ebx, ebx
0x18000811c  test    rdi, rdi
0x18000811f  jz      short loc_180008194
0x180008121  xor     r14d, r14d
0x180008124  xor     r15d, r15d
0x180008127  mov     rcx, rsi; lpCriticalSection
0x18000812a  call    cs:__imp_EnterCriticalSection
0x180008130  mov     rcx, rbp; SRWLock
0x180008133  call    cs:__imp_AcquireSRWLockExclusive
0x180008139  cmp     rbx, rdi
0x18000813c  jnb     short loc_180008163
0x18000813e  mov     rdx, [rsi+28h]
0x180008142  lea     rax, [rbx+1]
0x180008146  add     rbx, rbx
0x180008149  lea     rcx, [rdx+rbx*8]
0x18000814d  mov     rbx, rax
0x180008150  cmp     [rcx], r14
0x180008153  jnz     short loc_18000815C
0x180008155  cmp     rax, rdi
0x180008158  jb      short loc_180008142
0x18000815a  jmp     short loc_180008163
0x18000815c  mov     r14, [rcx]
0x18000815f  mov     r15, [rcx+8]
0x180008163  test    rbp, rbp
0x180008166  jz      short loc_180008171
0x180008168  mov     rcx, rbp; SRWLock
0x18000816b  call    cs:__imp_ReleaseSRWLockExclusive
0x180008171  test    r14, r14
0x180008174  jz      short loc_180008181
0x180008176  mov     rcx, r15
0x180008179  mov     rax, r14
0x18000817c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008181  test    rsi, rsi
0x180008184  jz      short loc_18000818F
0x180008186  mov     rcx, rsi; lpCriticalSection
0x180008189  call    cs:__imp_LeaveCriticalSection
0x18000818f  cmp     rbx, rdi
0x180008192  jb      short loc_180008121
0x180008194  add     rsp, 28h
0x180008198  pop     r15
0x18000819a  pop     r14
0x18000819c  pop     rdi
0x18000819d  pop     rsi
0x18000819e  pop     rbp
0x18000819f  pop     rbx
0x1800081a0  retn
```
