# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x180007010`
- end: `0x1800070d4`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `196`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800023b0`
- `0x1800023e0`
- `0x1800024e0`
- `0x180009f30`

## callees

- `0x180007010`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180007029`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180007029`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800070b8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800070b8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180007043`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180007043`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000709a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000709a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007062`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007062`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007059`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007059`

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
0x180007010  mov     [rsp+arg_10], rbx
0x180007015  push    rbp
0x180007016  push    rsi
0x180007017  push    rdi
0x180007018  push    r14
0x18000701a  push    r15
0x18000701c  sub     rsp, 20h
0x180007020  mov     rbp, rdx
0x180007023  mov     rsi, rcx
0x180007026  mov     rcx, rdx; SRWLock
0x180007029  call    cs:__imp_AcquireSRWLockShared
0x18000702f  mov     rdi, [rsi+30h]
0x180007033  sub     rdi, [rsi+28h]
0x180007037  shr     rdi, 4
0x18000703b  test    rbp, rbp
0x18000703e  jz      short loc_180007049
0x180007040  mov     rcx, rbp; SRWLock
0x180007043  call    cs:__imp_ReleaseSRWLockShared
0x180007049  xor     ebx, ebx
0x18000704b  test    rdi, rdi
0x18000704e  jz      short loc_1800070C3
0x180007050  xor     r14d, r14d
0x180007053  xor     r15d, r15d
0x180007056  mov     rcx, rsi; lpCriticalSection
0x180007059  call    cs:__imp_EnterCriticalSection
0x18000705f  mov     rcx, rbp; SRWLock
0x180007062  call    cs:__imp_AcquireSRWLockExclusive
0x180007068  cmp     rbx, rdi
0x18000706b  jnb     short loc_180007092
0x18000706d  mov     rdx, [rsi+28h]
0x180007071  lea     rax, [rbx+1]
0x180007075  add     rbx, rbx
0x180007078  lea     rcx, [rdx+rbx*8]
0x18000707c  mov     rbx, rax
0x18000707f  cmp     [rcx], r14
0x180007082  jnz     short loc_18000708B
0x180007084  cmp     rax, rdi
0x180007087  jb      short loc_180007071
0x180007089  jmp     short loc_180007092
0x18000708b  mov     r14, [rcx]
0x18000708e  mov     r15, [rcx+8]
0x180007092  test    rbp, rbp
0x180007095  jz      short loc_1800070A0
0x180007097  mov     rcx, rbp; SRWLock
0x18000709a  call    cs:__imp_ReleaseSRWLockExclusive
0x1800070a0  test    r14, r14
0x1800070a3  jz      short loc_1800070B0
0x1800070a5  mov     rcx, r15
0x1800070a8  mov     rax, r14
0x1800070ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070b0  test    rsi, rsi
0x1800070b3  jz      short loc_1800070BE
0x1800070b5  mov     rcx, rsi; lpCriticalSection
0x1800070b8  call    cs:__imp_LeaveCriticalSection
0x1800070be  cmp     rbx, rdi
0x1800070c1  jb      short loc_180007050
0x1800070c3  mov     rbx, [rsp+48h+arg_10]
0x1800070c8  add     rsp, 20h
0x1800070cc  pop     r15
0x1800070ce  pop     r14
0x1800070d0  pop     rdi
0x1800070d1  pop     rsi
0x1800070d2  pop     rbp
0x1800070d3  retn
```
