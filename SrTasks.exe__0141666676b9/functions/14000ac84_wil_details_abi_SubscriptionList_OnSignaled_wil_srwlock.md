# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x14000ac84`
- end: `0x14000ad41`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140007b00`
- `0x140007b30`
- `0x140007be0`
- `0x14000c8d0`

## callees

- `0x14000ac84`
- `0x140011010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x14000acca`
- `KERNEL32!EnterCriticalSection` at `0x14000acca`
- `KERNEL32!LeaveCriticalSection` at `0x14000ad29`
- `KERNEL32!LeaveCriticalSection` at `0x14000ad29`
- `KERNEL32!ReleaseSRWLockShared` at `0x14000acb4`
- `KERNEL32!ReleaseSRWLockShared` at `0x14000acb4`
- `KERNEL32!AcquireSRWLockShared` at `0x14000ac9a`
- `KERNEL32!AcquireSRWLockShared` at `0x14000ac9a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000acd3`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000acd3`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000ad0b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000ad0b`

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
0x14000ac84  push    rbx
0x14000ac86  push    rbp
0x14000ac87  push    rsi
0x14000ac88  push    rdi
0x14000ac89  push    r14
0x14000ac8b  push    r15
0x14000ac8d  sub     rsp, 28h
0x14000ac91  mov     rsi, rcx
0x14000ac94  mov     rbp, rdx
0x14000ac97  mov     rcx, rdx; SRWLock
0x14000ac9a  call    cs:__imp_AcquireSRWLockShared
0x14000aca0  mov     rdi, [rsi+30h]
0x14000aca4  sub     rdi, [rsi+28h]
0x14000aca8  shr     rdi, 4
0x14000acac  test    rbp, rbp
0x14000acaf  jz      short loc_14000ACBA
0x14000acb1  mov     rcx, rbp; SRWLock
0x14000acb4  call    cs:__imp_ReleaseSRWLockShared
0x14000acba  xor     ebx, ebx
0x14000acbc  test    rdi, rdi
0x14000acbf  jz      short loc_14000AD34
0x14000acc1  mov     rcx, rsi; lpCriticalSection
0x14000acc4  xor     r14d, r14d
0x14000acc7  xor     r15d, r15d
0x14000acca  call    cs:__imp_EnterCriticalSection
0x14000acd0  mov     rcx, rbp; SRWLock
0x14000acd3  call    cs:__imp_AcquireSRWLockExclusive
0x14000acd9  cmp     rbx, rdi
0x14000acdc  jnb     short loc_14000AD03
0x14000acde  mov     rdx, [rsi+28h]
0x14000ace2  lea     rax, [rbx+1]
0x14000ace6  add     rbx, rbx
0x14000ace9  lea     rcx, [rdx+rbx*8]
0x14000aced  mov     rbx, rax
0x14000acf0  cmp     [rcx], r14
0x14000acf3  jnz     short loc_14000ACFC
0x14000acf5  cmp     rax, rdi
0x14000acf8  jb      short loc_14000ACE2
0x14000acfa  jmp     short loc_14000AD03
0x14000acfc  mov     r14, [rcx]
0x14000acff  mov     r15, [rcx+8]
0x14000ad03  test    rbp, rbp
0x14000ad06  jz      short loc_14000AD11
0x14000ad08  mov     rcx, rbp; SRWLock
0x14000ad0b  call    cs:__imp_ReleaseSRWLockExclusive
0x14000ad11  test    r14, r14
0x14000ad14  jz      short loc_14000AD21
0x14000ad16  mov     rcx, r15
0x14000ad19  mov     rax, r14
0x14000ad1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ad21  test    rsi, rsi
0x14000ad24  jz      short loc_14000AD2F
0x14000ad26  mov     rcx, rsi; lpCriticalSection
0x14000ad29  call    cs:__imp_LeaveCriticalSection
0x14000ad2f  cmp     rbx, rdi
0x14000ad32  jb      short loc_14000ACC1
0x14000ad34  add     rsp, 28h
0x14000ad38  pop     r15
0x14000ad3a  pop     r14
0x14000ad3c  pop     rdi
0x14000ad3d  pop     rsi
0x14000ad3e  pop     rbp
0x14000ad3f  pop     rbx
0x14000ad40  retn
```
