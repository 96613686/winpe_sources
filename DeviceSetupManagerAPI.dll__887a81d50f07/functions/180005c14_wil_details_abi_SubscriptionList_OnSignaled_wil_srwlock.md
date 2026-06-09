# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x180005c14`
- end: `0x180005cd1`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800026b0`
- `0x1800026e0`
- `0x180002790`
- `0x180008150`

## callees

- `0x180005c14`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005c5a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005c5a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005cb9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005cb9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180005c2a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180005c2a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180005c44`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180005c44`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005c63`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005c63`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005c9b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005c9b`

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
0x180005c14  push    rbx
0x180005c16  push    rbp
0x180005c17  push    rsi
0x180005c18  push    rdi
0x180005c19  push    r14
0x180005c1b  push    r15
0x180005c1d  sub     rsp, 28h
0x180005c21  mov     rbp, rdx
0x180005c24  mov     rsi, rcx
0x180005c27  mov     rcx, rdx; SRWLock
0x180005c2a  call    cs:__imp_AcquireSRWLockShared
0x180005c30  mov     rdi, [rsi+30h]
0x180005c34  sub     rdi, [rsi+28h]
0x180005c38  shr     rdi, 4
0x180005c3c  test    rbp, rbp
0x180005c3f  jz      short loc_180005C4A
0x180005c41  mov     rcx, rbp; SRWLock
0x180005c44  call    cs:__imp_ReleaseSRWLockShared
0x180005c4a  xor     ebx, ebx
0x180005c4c  test    rdi, rdi
0x180005c4f  jz      short loc_180005CC4
0x180005c51  xor     r14d, r14d
0x180005c54  xor     r15d, r15d
0x180005c57  mov     rcx, rsi; lpCriticalSection
0x180005c5a  call    cs:__imp_EnterCriticalSection
0x180005c60  mov     rcx, rbp; SRWLock
0x180005c63  call    cs:__imp_AcquireSRWLockExclusive
0x180005c69  cmp     rbx, rdi
0x180005c6c  jnb     short loc_180005C93
0x180005c6e  mov     rdx, [rsi+28h]
0x180005c72  lea     rax, [rbx+1]
0x180005c76  add     rbx, rbx
0x180005c79  lea     rcx, [rdx+rbx*8]
0x180005c7d  mov     rbx, rax
0x180005c80  cmp     [rcx], r14
0x180005c83  jnz     short loc_180005C8C
0x180005c85  cmp     rax, rdi
0x180005c88  jb      short loc_180005C72
0x180005c8a  jmp     short loc_180005C93
0x180005c8c  mov     r14, [rcx]
0x180005c8f  mov     r15, [rcx+8]
0x180005c93  test    rbp, rbp
0x180005c96  jz      short loc_180005CA1
0x180005c98  mov     rcx, rbp; SRWLock
0x180005c9b  call    cs:__imp_ReleaseSRWLockExclusive
0x180005ca1  test    r14, r14
0x180005ca4  jz      short loc_180005CB1
0x180005ca6  mov     rcx, r15
0x180005ca9  mov     rax, r14
0x180005cac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cb1  test    rsi, rsi
0x180005cb4  jz      short loc_180005CBF
0x180005cb6  mov     rcx, rsi; lpCriticalSection
0x180005cb9  call    cs:__imp_LeaveCriticalSection
0x180005cbf  cmp     rbx, rdi
0x180005cc2  jb      short loc_180005C51
0x180005cc4  add     rsp, 28h
0x180005cc8  pop     r15
0x180005cca  pop     r14
0x180005ccc  pop     rdi
0x180005ccd  pop     rsi
0x180005cce  pop     rbp
0x180005ccf  pop     rbx
0x180005cd0  retn
```
