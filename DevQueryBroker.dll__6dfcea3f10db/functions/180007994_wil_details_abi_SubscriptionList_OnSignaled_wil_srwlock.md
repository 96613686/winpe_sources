# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x180007994`
- end: `0x180007a51`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180004810`
- `0x180004840`
- `0x1800048f0`
- `0x1800097c0`

## callees

- `0x180007994`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007a1b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007a1b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007a39`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007a39`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800079da`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800079da`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800079aa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800079aa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800079c4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800079c4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800079e3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800079e3`

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
0x180007994  push    rbx
0x180007996  push    rbp
0x180007997  push    rsi
0x180007998  push    rdi
0x180007999  push    r14
0x18000799b  push    r15
0x18000799d  sub     rsp, 28h
0x1800079a1  mov     rsi, rcx
0x1800079a4  mov     rbp, rdx
0x1800079a7  mov     rcx, rdx; SRWLock
0x1800079aa  call    cs:__imp_AcquireSRWLockShared
0x1800079b0  mov     rdi, [rsi+30h]
0x1800079b4  sub     rdi, [rsi+28h]
0x1800079b8  shr     rdi, 4
0x1800079bc  test    rbp, rbp
0x1800079bf  jz      short loc_1800079CA
0x1800079c1  mov     rcx, rbp; SRWLock
0x1800079c4  call    cs:__imp_ReleaseSRWLockShared
0x1800079ca  xor     ebx, ebx
0x1800079cc  test    rdi, rdi
0x1800079cf  jz      short loc_180007A44
0x1800079d1  mov     rcx, rsi; lpCriticalSection
0x1800079d4  xor     r14d, r14d
0x1800079d7  xor     r15d, r15d
0x1800079da  call    cs:__imp_EnterCriticalSection
0x1800079e0  mov     rcx, rbp; SRWLock
0x1800079e3  call    cs:__imp_AcquireSRWLockExclusive
0x1800079e9  cmp     rbx, rdi
0x1800079ec  jnb     short loc_180007A13
0x1800079ee  mov     rdx, [rsi+28h]
0x1800079f2  lea     rax, [rbx+1]
0x1800079f6  add     rbx, rbx
0x1800079f9  lea     rcx, [rdx+rbx*8]
0x1800079fd  mov     rbx, rax
0x180007a00  cmp     [rcx], r14
0x180007a03  jnz     short loc_180007A0C
0x180007a05  cmp     rax, rdi
0x180007a08  jb      short loc_1800079F2
0x180007a0a  jmp     short loc_180007A13
0x180007a0c  mov     r14, [rcx]
0x180007a0f  mov     r15, [rcx+8]
0x180007a13  test    rbp, rbp
0x180007a16  jz      short loc_180007A21
0x180007a18  mov     rcx, rbp; SRWLock
0x180007a1b  call    cs:__imp_ReleaseSRWLockExclusive
0x180007a21  test    r14, r14
0x180007a24  jz      short loc_180007A31
0x180007a26  mov     rcx, r15
0x180007a29  mov     rax, r14
0x180007a2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a31  test    rsi, rsi
0x180007a34  jz      short loc_180007A3F
0x180007a36  mov     rcx, rsi; lpCriticalSection
0x180007a39  call    cs:__imp_LeaveCriticalSection
0x180007a3f  cmp     rbx, rdi
0x180007a42  jb      short loc_1800079D1
0x180007a44  add     rsp, 28h
0x180007a48  pop     r15
0x180007a4a  pop     r14
0x180007a4c  pop     rdi
0x180007a4d  pop     rsi
0x180007a4e  pop     rbp
0x180007a4f  pop     rbx
0x180007a50  retn
```
