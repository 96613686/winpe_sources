# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x140009f14`
- end: `0x140009fd1`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140007760`
- `0x140007790`
- `0x140007840`
- `0x14000c220`

## callees

- `0x140009f14`
- `0x140013010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x140009f5a`
- `KERNEL32!EnterCriticalSection` at `0x140009f5a`
- `KERNEL32!LeaveCriticalSection` at `0x140009fb9`
- `KERNEL32!LeaveCriticalSection` at `0x140009fb9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140009f44`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140009f44`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140009f2a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140009f2a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140009f63`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140009f63`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140009f9b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140009f9b`

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
0x140009f14  push    rbx
0x140009f16  push    rbp
0x140009f17  push    rsi
0x140009f18  push    rdi
0x140009f19  push    r14
0x140009f1b  push    r15
0x140009f1d  sub     rsp, 28h
0x140009f21  mov     rbp, rdx
0x140009f24  mov     rsi, rcx
0x140009f27  mov     rcx, rdx; SRWLock
0x140009f2a  call    cs:__imp_AcquireSRWLockShared
0x140009f30  mov     rdi, [rsi+30h]
0x140009f34  sub     rdi, [rsi+28h]
0x140009f38  shr     rdi, 4
0x140009f3c  test    rbp, rbp
0x140009f3f  jz      short loc_140009F4A
0x140009f41  mov     rcx, rbp; SRWLock
0x140009f44  call    cs:__imp_ReleaseSRWLockShared
0x140009f4a  xor     ebx, ebx
0x140009f4c  test    rdi, rdi
0x140009f4f  jz      short loc_140009FC4
0x140009f51  xor     r14d, r14d
0x140009f54  xor     r15d, r15d
0x140009f57  mov     rcx, rsi; lpCriticalSection
0x140009f5a  call    cs:__imp_EnterCriticalSection
0x140009f60  mov     rcx, rbp; SRWLock
0x140009f63  call    cs:__imp_AcquireSRWLockExclusive
0x140009f69  cmp     rbx, rdi
0x140009f6c  jnb     short loc_140009F93
0x140009f6e  mov     rdx, [rsi+28h]
0x140009f72  lea     rax, [rbx+1]
0x140009f76  add     rbx, rbx
0x140009f79  lea     rcx, [rdx+rbx*8]
0x140009f7d  mov     rbx, rax
0x140009f80  cmp     [rcx], r14
0x140009f83  jnz     short loc_140009F8C
0x140009f85  cmp     rax, rdi
0x140009f88  jb      short loc_140009F72
0x140009f8a  jmp     short loc_140009F93
0x140009f8c  mov     r14, [rcx]
0x140009f8f  mov     r15, [rcx+8]
0x140009f93  test    rbp, rbp
0x140009f96  jz      short loc_140009FA1
0x140009f98  mov     rcx, rbp; SRWLock
0x140009f9b  call    cs:__imp_ReleaseSRWLockExclusive
0x140009fa1  test    r14, r14
0x140009fa4  jz      short loc_140009FB1
0x140009fa6  mov     rcx, r15
0x140009fa9  mov     rax, r14
0x140009fac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009fb1  test    rsi, rsi
0x140009fb4  jz      short loc_140009FBF
0x140009fb6  mov     rcx, rsi; lpCriticalSection
0x140009fb9  call    cs:__imp_LeaveCriticalSection
0x140009fbf  cmp     rbx, rdi
0x140009fc2  jb      short loc_140009F51
0x140009fc4  add     rsp, 28h
0x140009fc8  pop     r15
0x140009fca  pop     r14
0x140009fcc  pop     rdi
0x140009fcd  pop     rsi
0x140009fce  pop     rbp
0x140009fcf  pop     rbx
0x140009fd0  retn
```
