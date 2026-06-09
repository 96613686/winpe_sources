# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x140007c14`
- end: `0x140007cd1`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140002240`
- `0x140002270`
- `0x140002370`
- `0x14000afe0`

## callees

- `0x140007c14`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140007c2a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140007c2a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140007c5a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140007c5a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140007c63`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140007c63`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140007c9b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140007c9b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140007c44`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140007c44`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140007cb9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140007cb9`

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
0x140007c14  push    rbx
0x140007c16  push    rbp
0x140007c17  push    rsi
0x140007c18  push    rdi
0x140007c19  push    r14
0x140007c1b  push    r15
0x140007c1d  sub     rsp, 28h
0x140007c21  mov     rbp, rdx
0x140007c24  mov     rsi, rcx
0x140007c27  mov     rcx, rdx; SRWLock
0x140007c2a  call    cs:__imp_AcquireSRWLockShared
0x140007c30  mov     rdi, [rsi+30h]
0x140007c34  sub     rdi, [rsi+28h]
0x140007c38  shr     rdi, 4
0x140007c3c  test    rbp, rbp
0x140007c3f  jz      short loc_140007C4A
0x140007c41  mov     rcx, rbp; SRWLock
0x140007c44  call    cs:__imp_ReleaseSRWLockShared
0x140007c4a  xor     ebx, ebx
0x140007c4c  test    rdi, rdi
0x140007c4f  jz      short loc_140007CC4
0x140007c51  xor     r14d, r14d
0x140007c54  xor     r15d, r15d
0x140007c57  mov     rcx, rsi; lpCriticalSection
0x140007c5a  call    cs:__imp_EnterCriticalSection
0x140007c60  mov     rcx, rbp; SRWLock
0x140007c63  call    cs:__imp_AcquireSRWLockExclusive
0x140007c69  cmp     rbx, rdi
0x140007c6c  jnb     short loc_140007C93
0x140007c6e  mov     rdx, [rsi+28h]
0x140007c72  lea     rax, [rbx+1]
0x140007c76  add     rbx, rbx
0x140007c79  lea     rcx, [rdx+rbx*8]
0x140007c7d  mov     rbx, rax
0x140007c80  cmp     [rcx], r14
0x140007c83  jnz     short loc_140007C8C
0x140007c85  cmp     rax, rdi
0x140007c88  jb      short loc_140007C72
0x140007c8a  jmp     short loc_140007C93
0x140007c8c  mov     r14, [rcx]
0x140007c8f  mov     r15, [rcx+8]
0x140007c93  test    rbp, rbp
0x140007c96  jz      short loc_140007CA1
0x140007c98  mov     rcx, rbp; SRWLock
0x140007c9b  call    cs:__imp_ReleaseSRWLockExclusive
0x140007ca1  test    r14, r14
0x140007ca4  jz      short loc_140007CB1
0x140007ca6  mov     rcx, r15
0x140007ca9  mov     rax, r14
0x140007cac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007cb1  test    rsi, rsi
0x140007cb4  jz      short loc_140007CBF
0x140007cb6  mov     rcx, rsi; lpCriticalSection
0x140007cb9  call    cs:__imp_LeaveCriticalSection
0x140007cbf  cmp     rbx, rdi
0x140007cc2  jb      short loc_140007C51
0x140007cc4  add     rsp, 28h
0x140007cc8  pop     r15
0x140007cca  pop     r14
0x140007ccc  pop     rdi
0x140007ccd  pop     rsi
0x140007cce  pop     rbp
0x140007ccf  pop     rbx
0x140007cd0  retn
```
