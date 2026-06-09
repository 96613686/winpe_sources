# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x180008dd4`
- end: `0x180008e91`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800023d0`
- `0x180002400`
- `0x1800024b0`
- `0x18000b6a0`

## callees

- `0x180008dd4`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008e04`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008e04`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008e1a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008e1a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180008dea`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180008dea`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008e23`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008e23`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008e79`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008e79`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008e5b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008e5b`

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
0x180008dd4  push    rbx
0x180008dd6  push    rbp
0x180008dd7  push    rsi
0x180008dd8  push    rdi
0x180008dd9  push    r14
0x180008ddb  push    r15
0x180008ddd  sub     rsp, 28h
0x180008de1  mov     rbp, rdx
0x180008de4  mov     rsi, rcx
0x180008de7  mov     rcx, rdx; SRWLock
0x180008dea  call    cs:__imp_AcquireSRWLockShared
0x180008df0  mov     rdi, [rsi+30h]
0x180008df4  sub     rdi, [rsi+28h]
0x180008df8  shr     rdi, 4
0x180008dfc  test    rbp, rbp
0x180008dff  jz      short loc_180008E0A
0x180008e01  mov     rcx, rbp; SRWLock
0x180008e04  call    cs:__imp_ReleaseSRWLockShared
0x180008e0a  xor     ebx, ebx
0x180008e0c  test    rdi, rdi
0x180008e0f  jz      short loc_180008E84
0x180008e11  xor     r14d, r14d
0x180008e14  xor     r15d, r15d
0x180008e17  mov     rcx, rsi; lpCriticalSection
0x180008e1a  call    cs:__imp_EnterCriticalSection
0x180008e20  mov     rcx, rbp; SRWLock
0x180008e23  call    cs:__imp_AcquireSRWLockExclusive
0x180008e29  cmp     rbx, rdi
0x180008e2c  jnb     short loc_180008E53
0x180008e2e  mov     rdx, [rsi+28h]
0x180008e32  lea     rax, [rbx+1]
0x180008e36  add     rbx, rbx
0x180008e39  lea     rcx, [rdx+rbx*8]
0x180008e3d  mov     rbx, rax
0x180008e40  cmp     [rcx], r14
0x180008e43  jnz     short loc_180008E4C
0x180008e45  cmp     rax, rdi
0x180008e48  jb      short loc_180008E32
0x180008e4a  jmp     short loc_180008E53
0x180008e4c  mov     r14, [rcx]
0x180008e4f  mov     r15, [rcx+8]
0x180008e53  test    rbp, rbp
0x180008e56  jz      short loc_180008E61
0x180008e58  mov     rcx, rbp; SRWLock
0x180008e5b  call    cs:__imp_ReleaseSRWLockExclusive
0x180008e61  test    r14, r14
0x180008e64  jz      short loc_180008E71
0x180008e66  mov     rcx, r15
0x180008e69  mov     rax, r14
0x180008e6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e71  test    rsi, rsi
0x180008e74  jz      short loc_180008E7F
0x180008e76  mov     rcx, rsi; lpCriticalSection
0x180008e79  call    cs:__imp_LeaveCriticalSection
0x180008e7f  cmp     rbx, rdi
0x180008e82  jb      short loc_180008E11
0x180008e84  add     rsp, 28h
0x180008e88  pop     r15
0x180008e8a  pop     r14
0x180008e8c  pop     rdi
0x180008e8d  pop     rsi
0x180008e8e  pop     rbp
0x180008e8f  pop     rbx
0x180008e90  retn
```
