# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x14000ab4c`
- end: `0x14000ac09`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140007d80`
- `0x140007db0`
- `0x140007e60`
- `0x14000d7a0`

## callees

- `0x14000ab4c`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000ab9b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000ab9b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000ab92`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000ab92`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000abd3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000abd3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000ab62`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000ab62`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14000ab7c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14000ab7c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000abf1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000abf1`

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
0x14000ab4c  push    rbx
0x14000ab4e  push    rbp
0x14000ab4f  push    rsi
0x14000ab50  push    rdi
0x14000ab51  push    r14
0x14000ab53  push    r15
0x14000ab55  sub     rsp, 28h
0x14000ab59  mov     rbp, rdx
0x14000ab5c  mov     rsi, rcx
0x14000ab5f  mov     rcx, rdx; SRWLock
0x14000ab62  call    cs:__imp_AcquireSRWLockShared
0x14000ab68  mov     rdi, [rsi+30h]
0x14000ab6c  sub     rdi, [rsi+28h]
0x14000ab70  shr     rdi, 4
0x14000ab74  test    rbp, rbp
0x14000ab77  jz      short loc_14000AB82
0x14000ab79  mov     rcx, rbp; SRWLock
0x14000ab7c  call    cs:__imp_ReleaseSRWLockShared
0x14000ab82  xor     ebx, ebx
0x14000ab84  test    rdi, rdi
0x14000ab87  jz      short loc_14000ABFC
0x14000ab89  xor     r14d, r14d
0x14000ab8c  xor     r15d, r15d
0x14000ab8f  mov     rcx, rsi; lpCriticalSection
0x14000ab92  call    cs:__imp_EnterCriticalSection
0x14000ab98  mov     rcx, rbp; SRWLock
0x14000ab9b  call    cs:__imp_AcquireSRWLockExclusive
0x14000aba1  cmp     rbx, rdi
0x14000aba4  jnb     short loc_14000ABCB
0x14000aba6  mov     rdx, [rsi+28h]
0x14000abaa  lea     rax, [rbx+1]
0x14000abae  add     rbx, rbx
0x14000abb1  lea     rcx, [rdx+rbx*8]
0x14000abb5  mov     rbx, rax
0x14000abb8  cmp     [rcx], r14
0x14000abbb  jnz     short loc_14000ABC4
0x14000abbd  cmp     rax, rdi
0x14000abc0  jb      short loc_14000ABAA
0x14000abc2  jmp     short loc_14000ABCB
0x14000abc4  mov     r14, [rcx]
0x14000abc7  mov     r15, [rcx+8]
0x14000abcb  test    rbp, rbp
0x14000abce  jz      short loc_14000ABD9
0x14000abd0  mov     rcx, rbp; SRWLock
0x14000abd3  call    cs:__imp_ReleaseSRWLockExclusive
0x14000abd9  test    r14, r14
0x14000abdc  jz      short loc_14000ABE9
0x14000abde  mov     rcx, r15
0x14000abe1  mov     rax, r14
0x14000abe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000abe9  test    rsi, rsi
0x14000abec  jz      short loc_14000ABF7
0x14000abee  mov     rcx, rsi; lpCriticalSection
0x14000abf1  call    cs:__imp_LeaveCriticalSection
0x14000abf7  cmp     rbx, rdi
0x14000abfa  jb      short loc_14000AB89
0x14000abfc  add     rsp, 28h
0x14000ac00  pop     r15
0x14000ac02  pop     r14
0x14000ac04  pop     rdi
0x14000ac05  pop     rsi
0x14000ac06  pop     rbp
0x14000ac07  pop     rbx
0x14000ac08  retn
```
