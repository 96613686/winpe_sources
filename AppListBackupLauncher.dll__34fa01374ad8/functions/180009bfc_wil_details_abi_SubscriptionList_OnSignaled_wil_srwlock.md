# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x180009bfc`
- end: `0x180009cb9`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180003060`
- `0x180003090`
- `0x180003190`
- `0x18000dae0`

## callees

- `0x180009bfc`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009c83`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009c83`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009c4b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009c4b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009ca1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009ca1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180009c2c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180009c2c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009c42`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009c42`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180009c12`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180009c12`

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
0x180009bfc  push    rbx
0x180009bfe  push    rbp
0x180009bff  push    rsi
0x180009c00  push    rdi
0x180009c01  push    r14
0x180009c03  push    r15
0x180009c05  sub     rsp, 28h
0x180009c09  mov     rbp, rdx
0x180009c0c  mov     rsi, rcx
0x180009c0f  mov     rcx, rdx; SRWLock
0x180009c12  call    cs:__imp_AcquireSRWLockShared
0x180009c18  mov     rdi, [rsi+30h]
0x180009c1c  sub     rdi, [rsi+28h]
0x180009c20  shr     rdi, 4
0x180009c24  test    rbp, rbp
0x180009c27  jz      short loc_180009C32
0x180009c29  mov     rcx, rbp; SRWLock
0x180009c2c  call    cs:__imp_ReleaseSRWLockShared
0x180009c32  xor     ebx, ebx
0x180009c34  test    rdi, rdi
0x180009c37  jz      short loc_180009CAC
0x180009c39  xor     r14d, r14d
0x180009c3c  xor     r15d, r15d
0x180009c3f  mov     rcx, rsi; lpCriticalSection
0x180009c42  call    cs:__imp_EnterCriticalSection
0x180009c48  mov     rcx, rbp; SRWLock
0x180009c4b  call    cs:__imp_AcquireSRWLockExclusive
0x180009c51  cmp     rbx, rdi
0x180009c54  jnb     short loc_180009C7B
0x180009c56  mov     rdx, [rsi+28h]
0x180009c5a  lea     rax, [rbx+1]
0x180009c5e  add     rbx, rbx
0x180009c61  lea     rcx, [rdx+rbx*8]
0x180009c65  mov     rbx, rax
0x180009c68  cmp     [rcx], r14
0x180009c6b  jnz     short loc_180009C74
0x180009c6d  cmp     rax, rdi
0x180009c70  jb      short loc_180009C5A
0x180009c72  jmp     short loc_180009C7B
0x180009c74  mov     r14, [rcx]
0x180009c77  mov     r15, [rcx+8]
0x180009c7b  test    rbp, rbp
0x180009c7e  jz      short loc_180009C89
0x180009c80  mov     rcx, rbp; SRWLock
0x180009c83  call    cs:__imp_ReleaseSRWLockExclusive
0x180009c89  test    r14, r14
0x180009c8c  jz      short loc_180009C99
0x180009c8e  mov     rcx, r15
0x180009c91  mov     rax, r14
0x180009c94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c99  test    rsi, rsi
0x180009c9c  jz      short loc_180009CA7
0x180009c9e  mov     rcx, rsi; lpCriticalSection
0x180009ca1  call    cs:__imp_LeaveCriticalSection
0x180009ca7  cmp     rbx, rdi
0x180009caa  jb      short loc_180009C39
0x180009cac  add     rsp, 28h
0x180009cb0  pop     r15
0x180009cb2  pop     r14
0x180009cb4  pop     rdi
0x180009cb5  pop     rsi
0x180009cb6  pop     rbp
0x180009cb7  pop     rbx
0x180009cb8  retn
```
