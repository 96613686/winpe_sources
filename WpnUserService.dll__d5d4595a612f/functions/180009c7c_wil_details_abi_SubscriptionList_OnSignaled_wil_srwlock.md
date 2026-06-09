# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x180009c7c`
- end: `0x180009d39`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800074b0`
- `0x1800074e0`
- `0x180007610`
- `0x18000c740`

## callees

- `0x180009c7c`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009d03`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009d03`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009ccb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009ccb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180009c92`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180009c92`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180009cac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180009cac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009d21`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009d21`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009cc2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009cc2`

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
0x180009c7c  push    rbx
0x180009c7e  push    rbp
0x180009c7f  push    rsi
0x180009c80  push    rdi
0x180009c81  push    r14
0x180009c83  push    r15
0x180009c85  sub     rsp, 28h
0x180009c89  mov     rbp, rdx
0x180009c8c  mov     rsi, rcx
0x180009c8f  mov     rcx, rdx; SRWLock
0x180009c92  call    cs:__imp_AcquireSRWLockShared
0x180009c98  mov     rdi, [rsi+30h]
0x180009c9c  sub     rdi, [rsi+28h]
0x180009ca0  shr     rdi, 4
0x180009ca4  test    rbp, rbp
0x180009ca7  jz      short loc_180009CB2
0x180009ca9  mov     rcx, rbp; SRWLock
0x180009cac  call    cs:__imp_ReleaseSRWLockShared
0x180009cb2  xor     ebx, ebx
0x180009cb4  test    rdi, rdi
0x180009cb7  jz      short loc_180009D2C
0x180009cb9  xor     r14d, r14d
0x180009cbc  xor     r15d, r15d
0x180009cbf  mov     rcx, rsi; lpCriticalSection
0x180009cc2  call    cs:__imp_EnterCriticalSection
0x180009cc8  mov     rcx, rbp; SRWLock
0x180009ccb  call    cs:__imp_AcquireSRWLockExclusive
0x180009cd1  cmp     rbx, rdi
0x180009cd4  jnb     short loc_180009CFB
0x180009cd6  mov     rdx, [rsi+28h]
0x180009cda  lea     rax, [rbx+1]
0x180009cde  add     rbx, rbx
0x180009ce1  lea     rcx, [rdx+rbx*8]
0x180009ce5  mov     rbx, rax
0x180009ce8  cmp     [rcx], r14
0x180009ceb  jnz     short loc_180009CF4
0x180009ced  cmp     rax, rdi
0x180009cf0  jb      short loc_180009CDA
0x180009cf2  jmp     short loc_180009CFB
0x180009cf4  mov     r14, [rcx]
0x180009cf7  mov     r15, [rcx+8]
0x180009cfb  test    rbp, rbp
0x180009cfe  jz      short loc_180009D09
0x180009d00  mov     rcx, rbp; SRWLock
0x180009d03  call    cs:__imp_ReleaseSRWLockExclusive
0x180009d09  test    r14, r14
0x180009d0c  jz      short loc_180009D19
0x180009d0e  mov     rcx, r15
0x180009d11  mov     rax, r14
0x180009d14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d19  test    rsi, rsi
0x180009d1c  jz      short loc_180009D27
0x180009d1e  mov     rcx, rsi; lpCriticalSection
0x180009d21  call    cs:__imp_LeaveCriticalSection
0x180009d27  cmp     rbx, rdi
0x180009d2a  jb      short loc_180009CB9
0x180009d2c  add     rsp, 28h
0x180009d30  pop     r15
0x180009d32  pop     r14
0x180009d34  pop     rdi
0x180009d35  pop     rsi
0x180009d36  pop     rbp
0x180009d37  pop     rbx
0x180009d38  retn
```
