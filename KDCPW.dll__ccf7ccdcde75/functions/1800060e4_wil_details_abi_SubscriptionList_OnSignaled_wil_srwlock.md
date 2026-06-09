# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x1800060e4`
- end: `0x1800061a1`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002610`
- `0x180002640`
- `0x180002740`
- `0x180008960`

## callees

- `0x1800060e4`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000612a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000612a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800060fa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800060fa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180006114`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180006114`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006133`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006133`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000616b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000616b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006189`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006189`

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
0x1800060e4  push    rbx
0x1800060e6  push    rbp
0x1800060e7  push    rsi
0x1800060e8  push    rdi
0x1800060e9  push    r14
0x1800060eb  push    r15
0x1800060ed  sub     rsp, 28h
0x1800060f1  mov     rsi, rcx
0x1800060f4  mov     rbp, rdx
0x1800060f7  mov     rcx, rdx; SRWLock
0x1800060fa  call    cs:__imp_AcquireSRWLockShared
0x180006100  mov     rdi, [rsi+30h]
0x180006104  sub     rdi, [rsi+28h]
0x180006108  shr     rdi, 4
0x18000610c  test    rbp, rbp
0x18000610f  jz      short loc_18000611A
0x180006111  mov     rcx, rbp; SRWLock
0x180006114  call    cs:__imp_ReleaseSRWLockShared
0x18000611a  xor     ebx, ebx
0x18000611c  test    rdi, rdi
0x18000611f  jz      short loc_180006194
0x180006121  mov     rcx, rsi; lpCriticalSection
0x180006124  xor     r14d, r14d
0x180006127  xor     r15d, r15d
0x18000612a  call    cs:__imp_EnterCriticalSection
0x180006130  mov     rcx, rbp; SRWLock
0x180006133  call    cs:__imp_AcquireSRWLockExclusive
0x180006139  cmp     rbx, rdi
0x18000613c  jnb     short loc_180006163
0x18000613e  mov     rdx, [rsi+28h]
0x180006142  lea     rax, [rbx+1]
0x180006146  add     rbx, rbx
0x180006149  lea     rcx, [rdx+rbx*8]
0x18000614d  mov     rbx, rax
0x180006150  cmp     [rcx], r14
0x180006153  jnz     short loc_18000615C
0x180006155  cmp     rax, rdi
0x180006158  jb      short loc_180006142
0x18000615a  jmp     short loc_180006163
0x18000615c  mov     r14, [rcx]
0x18000615f  mov     r15, [rcx+8]
0x180006163  test    rbp, rbp
0x180006166  jz      short loc_180006171
0x180006168  mov     rcx, rbp; SRWLock
0x18000616b  call    cs:__imp_ReleaseSRWLockExclusive
0x180006171  test    r14, r14
0x180006174  jz      short loc_180006181
0x180006176  mov     rcx, r15
0x180006179  mov     rax, r14
0x18000617c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006181  test    rsi, rsi
0x180006184  jz      short loc_18000618F
0x180006186  mov     rcx, rsi; lpCriticalSection
0x180006189  call    cs:__imp_LeaveCriticalSection
0x18000618f  cmp     rbx, rdi
0x180006192  jb      short loc_180006121
0x180006194  add     rsp, 28h
0x180006198  pop     r15
0x18000619a  pop     r14
0x18000619c  pop     rdi
0x18000619d  pop     rsi
0x18000619e  pop     rbp
0x18000619f  pop     rbx
0x1800061a0  retn
```
