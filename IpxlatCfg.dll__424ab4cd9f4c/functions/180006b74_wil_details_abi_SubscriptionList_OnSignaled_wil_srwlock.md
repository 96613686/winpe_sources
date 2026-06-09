# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x180006b74`
- end: `0x180006c31`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180003270`
- `0x1800032a0`
- `0x180003350`
- `0x180009680`

## callees

- `0x180006b74`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180006b8a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180006b8a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180006ba4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180006ba4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006bc3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006bc3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006bfb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006bfb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006c19`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006c19`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006bba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006bba`

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
0x180006b74  push    rbx
0x180006b76  push    rbp
0x180006b77  push    rsi
0x180006b78  push    rdi
0x180006b79  push    r14
0x180006b7b  push    r15
0x180006b7d  sub     rsp, 28h
0x180006b81  mov     rbp, rdx
0x180006b84  mov     rsi, rcx
0x180006b87  mov     rcx, rdx; SRWLock
0x180006b8a  call    cs:__imp_AcquireSRWLockShared
0x180006b90  mov     rdi, [rsi+30h]
0x180006b94  sub     rdi, [rsi+28h]
0x180006b98  shr     rdi, 4
0x180006b9c  test    rbp, rbp
0x180006b9f  jz      short loc_180006BAA
0x180006ba1  mov     rcx, rbp; SRWLock
0x180006ba4  call    cs:__imp_ReleaseSRWLockShared
0x180006baa  xor     ebx, ebx
0x180006bac  test    rdi, rdi
0x180006baf  jz      short loc_180006C24
0x180006bb1  xor     r14d, r14d
0x180006bb4  xor     r15d, r15d
0x180006bb7  mov     rcx, rsi; lpCriticalSection
0x180006bba  call    cs:__imp_EnterCriticalSection
0x180006bc0  mov     rcx, rbp; SRWLock
0x180006bc3  call    cs:__imp_AcquireSRWLockExclusive
0x180006bc9  cmp     rbx, rdi
0x180006bcc  jnb     short loc_180006BF3
0x180006bce  mov     rdx, [rsi+28h]
0x180006bd2  lea     rax, [rbx+1]
0x180006bd6  add     rbx, rbx
0x180006bd9  lea     rcx, [rdx+rbx*8]
0x180006bdd  mov     rbx, rax
0x180006be0  cmp     [rcx], r14
0x180006be3  jnz     short loc_180006BEC
0x180006be5  cmp     rax, rdi
0x180006be8  jb      short loc_180006BD2
0x180006bea  jmp     short loc_180006BF3
0x180006bec  mov     r14, [rcx]
0x180006bef  mov     r15, [rcx+8]
0x180006bf3  test    rbp, rbp
0x180006bf6  jz      short loc_180006C01
0x180006bf8  mov     rcx, rbp; SRWLock
0x180006bfb  call    cs:__imp_ReleaseSRWLockExclusive
0x180006c01  test    r14, r14
0x180006c04  jz      short loc_180006C11
0x180006c06  mov     rcx, r15
0x180006c09  mov     rax, r14
0x180006c0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c11  test    rsi, rsi
0x180006c14  jz      short loc_180006C1F
0x180006c16  mov     rcx, rsi; lpCriticalSection
0x180006c19  call    cs:__imp_LeaveCriticalSection
0x180006c1f  cmp     rbx, rdi
0x180006c22  jb      short loc_180006BB1
0x180006c24  add     rsp, 28h
0x180006c28  pop     r15
0x180006c2a  pop     r14
0x180006c2c  pop     rdi
0x180006c2d  pop     rsi
0x180006c2e  pop     rbp
0x180006c2f  pop     rbx
0x180006c30  retn
```
