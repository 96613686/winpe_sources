# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x1800110e4`
- end: `0x1800111a1`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180010130`
- `0x180010160`
- `0x180010210`
- `0x180012600`

## callees

- `0x1800110e4`
- `0x180014010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180011189`
- `KERNEL32!LeaveCriticalSection` at `0x180011189`
- `KERNEL32!EnterCriticalSection` at `0x18001112a`
- `KERNEL32!EnterCriticalSection` at `0x18001112a`
- `KERNEL32!AcquireSRWLockShared` at `0x1800110fa`
- `KERNEL32!AcquireSRWLockShared` at `0x1800110fa`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001116b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001116b`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180011133`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180011133`
- `KERNEL32!ReleaseSRWLockShared` at `0x180011114`
- `KERNEL32!ReleaseSRWLockShared` at `0x180011114`

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
0x1800110e4  push    rbx
0x1800110e6  push    rbp
0x1800110e7  push    rsi
0x1800110e8  push    rdi
0x1800110e9  push    r14
0x1800110eb  push    r15
0x1800110ed  sub     rsp, 28h
0x1800110f1  mov     rsi, rcx
0x1800110f4  mov     rbp, rdx
0x1800110f7  mov     rcx, rdx; SRWLock
0x1800110fa  call    cs:__imp_AcquireSRWLockShared
0x180011100  mov     rdi, [rsi+30h]
0x180011104  sub     rdi, [rsi+28h]
0x180011108  shr     rdi, 4
0x18001110c  test    rbp, rbp
0x18001110f  jz      short loc_18001111A
0x180011111  mov     rcx, rbp; SRWLock
0x180011114  call    cs:__imp_ReleaseSRWLockShared
0x18001111a  xor     ebx, ebx
0x18001111c  test    rdi, rdi
0x18001111f  jz      short loc_180011194
0x180011121  mov     rcx, rsi; lpCriticalSection
0x180011124  xor     r14d, r14d
0x180011127  xor     r15d, r15d
0x18001112a  call    cs:__imp_EnterCriticalSection
0x180011130  mov     rcx, rbp; SRWLock
0x180011133  call    cs:__imp_AcquireSRWLockExclusive
0x180011139  cmp     rbx, rdi
0x18001113c  jnb     short loc_180011163
0x18001113e  mov     rdx, [rsi+28h]
0x180011142  lea     rax, [rbx+1]
0x180011146  add     rbx, rbx
0x180011149  lea     rcx, [rdx+rbx*8]
0x18001114d  mov     rbx, rax
0x180011150  cmp     [rcx], r14
0x180011153  jnz     short loc_18001115C
0x180011155  cmp     rax, rdi
0x180011158  jb      short loc_180011142
0x18001115a  jmp     short loc_180011163
0x18001115c  mov     r14, [rcx]
0x18001115f  mov     r15, [rcx+8]
0x180011163  test    rbp, rbp
0x180011166  jz      short loc_180011171
0x180011168  mov     rcx, rbp; SRWLock
0x18001116b  call    cs:__imp_ReleaseSRWLockExclusive
0x180011171  test    r14, r14
0x180011174  jz      short loc_180011181
0x180011176  mov     rcx, r15
0x180011179  mov     rax, r14
0x18001117c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011181  test    rsi, rsi
0x180011184  jz      short loc_18001118F
0x180011186  mov     rcx, rsi; lpCriticalSection
0x180011189  call    cs:__imp_LeaveCriticalSection
0x18001118f  cmp     rbx, rdi
0x180011192  jb      short loc_180011121
0x180011194  add     rsp, 28h
0x180011198  pop     r15
0x18001119a  pop     r14
0x18001119c  pop     rdi
0x18001119d  pop     rsi
0x18001119e  pop     rbp
0x18001119f  pop     rbx
0x1800111a0  retn
```
