# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x180006f20`
- end: `0x180006fe4`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `196`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800021a0`
- `0x1800021d0`
- `0x1800022d0`
- `0x180009c50`

## callees

- `0x180006f20`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006f72`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006f72`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006faa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006faa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180006f53`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180006f53`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006f69`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006f69`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180006f39`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180006f39`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006fc8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006fc8`

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
0x180006f20  mov     [rsp+arg_10], rbx
0x180006f25  push    rbp
0x180006f26  push    rsi
0x180006f27  push    rdi
0x180006f28  push    r14
0x180006f2a  push    r15
0x180006f2c  sub     rsp, 20h
0x180006f30  mov     rbp, rdx
0x180006f33  mov     rsi, rcx
0x180006f36  mov     rcx, rdx; SRWLock
0x180006f39  call    cs:__imp_AcquireSRWLockShared
0x180006f3f  mov     rdi, [rsi+30h]
0x180006f43  sub     rdi, [rsi+28h]
0x180006f47  shr     rdi, 4
0x180006f4b  test    rbp, rbp
0x180006f4e  jz      short loc_180006F59
0x180006f50  mov     rcx, rbp; SRWLock
0x180006f53  call    cs:__imp_ReleaseSRWLockShared
0x180006f59  xor     ebx, ebx
0x180006f5b  test    rdi, rdi
0x180006f5e  jz      short loc_180006FD3
0x180006f60  xor     r14d, r14d
0x180006f63  xor     r15d, r15d
0x180006f66  mov     rcx, rsi; lpCriticalSection
0x180006f69  call    cs:__imp_EnterCriticalSection
0x180006f6f  mov     rcx, rbp; SRWLock
0x180006f72  call    cs:__imp_AcquireSRWLockExclusive
0x180006f78  cmp     rbx, rdi
0x180006f7b  jnb     short loc_180006FA2
0x180006f7d  mov     rdx, [rsi+28h]
0x180006f81  lea     rax, [rbx+1]
0x180006f85  add     rbx, rbx
0x180006f88  lea     rcx, [rdx+rbx*8]
0x180006f8c  mov     rbx, rax
0x180006f8f  cmp     [rcx], r14
0x180006f92  jnz     short loc_180006F9B
0x180006f94  cmp     rax, rdi
0x180006f97  jb      short loc_180006F81
0x180006f99  jmp     short loc_180006FA2
0x180006f9b  mov     r14, [rcx]
0x180006f9e  mov     r15, [rcx+8]
0x180006fa2  test    rbp, rbp
0x180006fa5  jz      short loc_180006FB0
0x180006fa7  mov     rcx, rbp; SRWLock
0x180006faa  call    cs:__imp_ReleaseSRWLockExclusive
0x180006fb0  test    r14, r14
0x180006fb3  jz      short loc_180006FC0
0x180006fb5  mov     rcx, r15
0x180006fb8  mov     rax, r14
0x180006fbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fc0  test    rsi, rsi
0x180006fc3  jz      short loc_180006FCE
0x180006fc5  mov     rcx, rsi; lpCriticalSection
0x180006fc8  call    cs:__imp_LeaveCriticalSection
0x180006fce  cmp     rbx, rdi
0x180006fd1  jb      short loc_180006F60
0x180006fd3  mov     rbx, [rsp+48h+arg_10]
0x180006fd8  add     rsp, 20h
0x180006fdc  pop     r15
0x180006fde  pop     r14
0x180006fe0  pop     rdi
0x180006fe1  pop     rsi
0x180006fe2  pop     rbp
0x180006fe3  retn
```
