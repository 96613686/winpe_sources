# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x180005e2c`
- end: `0x180005ee9`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800025a0`
- `0x1800025d0`
- `0x1800026e0`
- `0x180008780`

## callees

- `0x180005e2c`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180005e5c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180005e5c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005eb3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005eb3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005e7b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005e7b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180005e42`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180005e42`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005ed1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005ed1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005e72`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005e72`

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
0x180005e2c  push    rbx
0x180005e2e  push    rbp
0x180005e2f  push    rsi
0x180005e30  push    rdi
0x180005e31  push    r14
0x180005e33  push    r15
0x180005e35  sub     rsp, 28h
0x180005e39  mov     rsi, rcx
0x180005e3c  mov     rbp, rdx
0x180005e3f  mov     rcx, rdx; SRWLock
0x180005e42  call    cs:__imp_AcquireSRWLockShared
0x180005e48  mov     rdi, [rsi+30h]
0x180005e4c  sub     rdi, [rsi+28h]
0x180005e50  shr     rdi, 4
0x180005e54  test    rbp, rbp
0x180005e57  jz      short loc_180005E62
0x180005e59  mov     rcx, rbp; SRWLock
0x180005e5c  call    cs:__imp_ReleaseSRWLockShared
0x180005e62  xor     ebx, ebx
0x180005e64  test    rdi, rdi
0x180005e67  jz      short loc_180005EDC
0x180005e69  mov     rcx, rsi; lpCriticalSection
0x180005e6c  xor     r14d, r14d
0x180005e6f  xor     r15d, r15d
0x180005e72  call    cs:__imp_EnterCriticalSection
0x180005e78  mov     rcx, rbp; SRWLock
0x180005e7b  call    cs:__imp_AcquireSRWLockExclusive
0x180005e81  cmp     rbx, rdi
0x180005e84  jnb     short loc_180005EAB
0x180005e86  mov     rdx, [rsi+28h]
0x180005e8a  lea     rax, [rbx+1]
0x180005e8e  add     rbx, rbx
0x180005e91  lea     rcx, [rdx+rbx*8]
0x180005e95  mov     rbx, rax
0x180005e98  cmp     [rcx], r14
0x180005e9b  jnz     short loc_180005EA4
0x180005e9d  cmp     rax, rdi
0x180005ea0  jb      short loc_180005E8A
0x180005ea2  jmp     short loc_180005EAB
0x180005ea4  mov     r14, [rcx]
0x180005ea7  mov     r15, [rcx+8]
0x180005eab  test    rbp, rbp
0x180005eae  jz      short loc_180005EB9
0x180005eb0  mov     rcx, rbp; SRWLock
0x180005eb3  call    cs:__imp_ReleaseSRWLockExclusive
0x180005eb9  test    r14, r14
0x180005ebc  jz      short loc_180005EC9
0x180005ebe  mov     rcx, r15
0x180005ec1  mov     rax, r14
0x180005ec4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ec9  test    rsi, rsi
0x180005ecc  jz      short loc_180005ED7
0x180005ece  mov     rcx, rsi; lpCriticalSection
0x180005ed1  call    cs:__imp_LeaveCriticalSection
0x180005ed7  cmp     rbx, rdi
0x180005eda  jb      short loc_180005E69
0x180005edc  add     rsp, 28h
0x180005ee0  pop     r15
0x180005ee2  pop     r14
0x180005ee4  pop     rdi
0x180005ee5  pop     rsi
0x180005ee6  pop     rbp
0x180005ee7  pop     rbx
0x180005ee8  retn
```
