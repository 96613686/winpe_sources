# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x1800080c0`
- end: `0x18000817d`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180007060`
- `0x180007090`
- `0x180007140`
- `0x1800096a0`

## callees

- `0x1800080c0`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008165`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008165`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008106`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008106`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008147`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008147`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000810f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000810f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800080f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800080f0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800080d6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800080d6`

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
0x1800080c0  push    rbx
0x1800080c2  push    rbp
0x1800080c3  push    rsi
0x1800080c4  push    rdi
0x1800080c5  push    r14
0x1800080c7  push    r15
0x1800080c9  sub     rsp, 28h
0x1800080cd  mov     rbp, rdx
0x1800080d0  mov     rsi, rcx
0x1800080d3  mov     rcx, rdx; SRWLock
0x1800080d6  call    cs:__imp_AcquireSRWLockShared
0x1800080dc  mov     rdi, [rsi+30h]
0x1800080e0  sub     rdi, [rsi+28h]
0x1800080e4  shr     rdi, 4
0x1800080e8  test    rbp, rbp
0x1800080eb  jz      short loc_1800080F6
0x1800080ed  mov     rcx, rbp; SRWLock
0x1800080f0  call    cs:__imp_ReleaseSRWLockShared
0x1800080f6  xor     ebx, ebx
0x1800080f8  test    rdi, rdi
0x1800080fb  jz      short loc_180008170
0x1800080fd  xor     r14d, r14d
0x180008100  xor     r15d, r15d
0x180008103  mov     rcx, rsi; lpCriticalSection
0x180008106  call    cs:__imp_EnterCriticalSection
0x18000810c  mov     rcx, rbp; SRWLock
0x18000810f  call    cs:__imp_AcquireSRWLockExclusive
0x180008115  cmp     rbx, rdi
0x180008118  jnb     short loc_18000813F
0x18000811a  mov     rdx, [rsi+28h]
0x18000811e  lea     rax, [rbx+1]
0x180008122  add     rbx, rbx
0x180008125  lea     rcx, [rdx+rbx*8]
0x180008129  mov     rbx, rax
0x18000812c  cmp     [rcx], r14
0x18000812f  jnz     short loc_180008138
0x180008131  cmp     rax, rdi
0x180008134  jb      short loc_18000811E
0x180008136  jmp     short loc_18000813F
0x180008138  mov     r14, [rcx]
0x18000813b  mov     r15, [rcx+8]
0x18000813f  test    rbp, rbp
0x180008142  jz      short loc_18000814D
0x180008144  mov     rcx, rbp; SRWLock
0x180008147  call    cs:__imp_ReleaseSRWLockExclusive
0x18000814d  test    r14, r14
0x180008150  jz      short loc_18000815D
0x180008152  mov     rcx, r15
0x180008155  mov     rax, r14
0x180008158  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000815d  test    rsi, rsi
0x180008160  jz      short loc_18000816B
0x180008162  mov     rcx, rsi; lpCriticalSection
0x180008165  call    cs:__imp_LeaveCriticalSection
0x18000816b  cmp     rbx, rdi
0x18000816e  jb      short loc_1800080FD
0x180008170  add     rsp, 28h
0x180008174  pop     r15
0x180008176  pop     r14
0x180008178  pop     rdi
0x180008179  pop     rsi
0x18000817a  pop     rbp
0x18000817b  pop     rbx
0x18000817c  retn
```
