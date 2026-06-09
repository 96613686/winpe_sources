# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x18000c054`
- end: `0x18000c111`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800045e0`
- `0x180004610`
- `0x180004710`
- `0x180010e60`

## callees

- `0x18000c054`
- `0x180015010`

## import_xrefs

- `KERNEL32!AcquireSRWLockShared` at `0x18000c06a`
- `KERNEL32!AcquireSRWLockShared` at `0x18000c06a`
- `KERNEL32!ReleaseSRWLockShared` at `0x18000c084`
- `KERNEL32!ReleaseSRWLockShared` at `0x18000c084`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000c0a3`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000c0a3`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000c0db`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000c0db`
- `KERNEL32!EnterCriticalSection` at `0x18000c09a`
- `KERNEL32!EnterCriticalSection` at `0x18000c09a`
- `KERNEL32!LeaveCriticalSection` at `0x18000c0f9`
- `KERNEL32!LeaveCriticalSection` at `0x18000c0f9`

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
0x18000c054  push    rbx
0x18000c056  push    rbp
0x18000c057  push    rsi
0x18000c058  push    rdi
0x18000c059  push    r14
0x18000c05b  push    r15
0x18000c05d  sub     rsp, 28h
0x18000c061  mov     rbp, rdx
0x18000c064  mov     rsi, rcx
0x18000c067  mov     rcx, rdx; SRWLock
0x18000c06a  call    cs:__imp_AcquireSRWLockShared
0x18000c070  mov     rdi, [rsi+30h]
0x18000c074  sub     rdi, [rsi+28h]
0x18000c078  shr     rdi, 4
0x18000c07c  test    rbp, rbp
0x18000c07f  jz      short loc_18000C08A
0x18000c081  mov     rcx, rbp; SRWLock
0x18000c084  call    cs:__imp_ReleaseSRWLockShared
0x18000c08a  xor     ebx, ebx
0x18000c08c  test    rdi, rdi
0x18000c08f  jz      short loc_18000C104
0x18000c091  xor     r14d, r14d
0x18000c094  xor     r15d, r15d
0x18000c097  mov     rcx, rsi; lpCriticalSection
0x18000c09a  call    cs:__imp_EnterCriticalSection
0x18000c0a0  mov     rcx, rbp; SRWLock
0x18000c0a3  call    cs:__imp_AcquireSRWLockExclusive
0x18000c0a9  cmp     rbx, rdi
0x18000c0ac  jnb     short loc_18000C0D3
0x18000c0ae  mov     rdx, [rsi+28h]
0x18000c0b2  lea     rax, [rbx+1]
0x18000c0b6  add     rbx, rbx
0x18000c0b9  lea     rcx, [rdx+rbx*8]
0x18000c0bd  mov     rbx, rax
0x18000c0c0  cmp     [rcx], r14
0x18000c0c3  jnz     short loc_18000C0CC
0x18000c0c5  cmp     rax, rdi
0x18000c0c8  jb      short loc_18000C0B2
0x18000c0ca  jmp     short loc_18000C0D3
0x18000c0cc  mov     r14, [rcx]
0x18000c0cf  mov     r15, [rcx+8]
0x18000c0d3  test    rbp, rbp
0x18000c0d6  jz      short loc_18000C0E1
0x18000c0d8  mov     rcx, rbp; SRWLock
0x18000c0db  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c0e1  test    r14, r14
0x18000c0e4  jz      short loc_18000C0F1
0x18000c0e6  mov     rcx, r15
0x18000c0e9  mov     rax, r14
0x18000c0ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0f1  test    rsi, rsi
0x18000c0f4  jz      short loc_18000C0FF
0x18000c0f6  mov     rcx, rsi; lpCriticalSection
0x18000c0f9  call    cs:__imp_LeaveCriticalSection
0x18000c0ff  cmp     rbx, rdi
0x18000c102  jb      short loc_18000C091
0x18000c104  add     rsp, 28h
0x18000c108  pop     r15
0x18000c10a  pop     r14
0x18000c10c  pop     rdi
0x18000c10d  pop     rsi
0x18000c10e  pop     rbp
0x18000c10f  pop     rbx
0x18000c110  retn
```
