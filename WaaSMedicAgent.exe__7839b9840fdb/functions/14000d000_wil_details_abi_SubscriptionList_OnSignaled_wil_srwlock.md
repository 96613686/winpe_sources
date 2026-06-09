# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x14000d000`
- end: `0x14000d0c6`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `198`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x14000b810`
- `0x14000b840`
- `0x14000b8f0`
- `0x14000e600`

## callees

- `0x14000d000`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000d0ae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000d0ae`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000d090`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000d090`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000d058`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000d058`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14000d039`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14000d039`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000d01f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000d01f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000d04f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000d04f`

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
0x14000d000  push    rbx
0x14000d002  push    rbp
0x14000d003  push    rsi
0x14000d004  push    rdi
0x14000d005  push    r14
0x14000d007  push    r15
0x14000d009  sub     rsp, 38h
0x14000d00d  mov     [rsp+68h+var_48], 0FFFFFFFFFFFFFFFEh
0x14000d016  mov     rbp, rdx
0x14000d019  mov     rsi, rcx
0x14000d01c  mov     rcx, rdx; SRWLock
0x14000d01f  call    cs:__imp_AcquireSRWLockShared
0x14000d025  mov     rdi, [rsi+30h]
0x14000d029  sub     rdi, [rsi+28h]
0x14000d02d  shr     rdi, 4
0x14000d031  test    rbp, rbp
0x14000d034  jz      short loc_14000D03F
0x14000d036  mov     rcx, rbp; SRWLock
0x14000d039  call    cs:__imp_ReleaseSRWLockShared
0x14000d03f  xor     ebx, ebx
0x14000d041  test    rdi, rdi
0x14000d044  jz      short loc_14000D0B9
0x14000d046  xor     r14d, r14d
0x14000d049  xor     r15d, r15d
0x14000d04c  mov     rcx, rsi; lpCriticalSection
0x14000d04f  call    cs:__imp_EnterCriticalSection
0x14000d055  mov     rcx, rbp; SRWLock
0x14000d058  call    cs:__imp_AcquireSRWLockExclusive
0x14000d05e  cmp     rbx, rdi
0x14000d061  jnb     short loc_14000D088
0x14000d063  mov     rdx, [rsi+28h]
0x14000d067  lea     rax, [rbx+1]
0x14000d06b  add     rbx, rbx
0x14000d06e  lea     rcx, [rdx+rbx*8]
0x14000d072  mov     rbx, rax
0x14000d075  cmp     [rcx], r14
0x14000d078  jnz     short loc_14000D081
0x14000d07a  cmp     rax, rdi
0x14000d07d  jb      short loc_14000D067
0x14000d07f  jmp     short loc_14000D088
0x14000d081  mov     r14, [rcx]
0x14000d084  mov     r15, [rcx+8]
0x14000d088  test    rbp, rbp
0x14000d08b  jz      short loc_14000D096
0x14000d08d  mov     rcx, rbp; SRWLock
0x14000d090  call    cs:__imp_ReleaseSRWLockExclusive
0x14000d096  test    r14, r14
0x14000d099  jz      short loc_14000D0A6
0x14000d09b  mov     rcx, r15
0x14000d09e  mov     rax, r14
0x14000d0a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d0a6  test    rsi, rsi
0x14000d0a9  jz      short loc_14000D0B4
0x14000d0ab  mov     rcx, rsi; lpCriticalSection
0x14000d0ae  call    cs:__imp_LeaveCriticalSection
0x14000d0b4  cmp     rbx, rdi
0x14000d0b7  jb      short loc_14000D046
0x14000d0b9  add     rsp, 38h
0x14000d0bd  pop     r15
0x14000d0bf  pop     r14
0x14000d0c1  pop     rdi
0x14000d0c2  pop     rsi
0x14000d0c3  pop     rbp
0x14000d0c4  pop     rbx
0x14000d0c5  retn
```
