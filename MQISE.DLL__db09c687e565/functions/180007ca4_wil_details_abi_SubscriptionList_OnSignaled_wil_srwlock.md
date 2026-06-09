# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x180007ca4`
- end: `0x180007d68`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `196`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002130`
- `0x180002160`
- `0x180002210`
- `0x18000ab20`

## callees

- `0x180007ca4`
- `0x180011010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180007d4f`
- `KERNEL32!LeaveCriticalSection` at `0x180007d4f`
- `KERNEL32!EnterCriticalSection` at `0x180007cec`
- `KERNEL32!EnterCriticalSection` at `0x180007cec`
- `KERNEL32!ReleaseSRWLockShared` at `0x180007cd5`
- `KERNEL32!ReleaseSRWLockShared` at `0x180007cd5`
- `KERNEL32!AcquireSRWLockShared` at `0x180007cba`
- `KERNEL32!AcquireSRWLockShared` at `0x180007cba`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180007d30`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180007d30`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180007cf6`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180007cf6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180007ca4  push    rbx
0x180007ca6  push    rbp
0x180007ca7  push    rsi
0x180007ca8  push    rdi
0x180007ca9  push    r14
0x180007cab  push    r15
0x180007cad  sub     rsp, 28h
0x180007cb1  mov     rbp, rdx
0x180007cb4  mov     rsi, rcx
0x180007cb7  mov     rcx, rdx; SRWLock
0x180007cba  call    cs:__imp_AcquireSRWLockShared
0x180007cc0  nop
0x180007cc1  mov     rdi, [rsi+30h]
0x180007cc5  sub     rdi, [rsi+28h]
0x180007cc9  shr     rdi, 4
0x180007ccd  test    rbp, rbp
0x180007cd0  jz      short loc_180007CDC
0x180007cd2  mov     rcx, rbp; SRWLock
0x180007cd5  call    cs:__imp_ReleaseSRWLockShared
0x180007cdb  nop
0x180007cdc  xor     ebx, ebx
0x180007cde  test    rdi, rdi
0x180007ce1  jz      short loc_180007D5B
0x180007ce3  xor     r14d, r14d
0x180007ce6  xor     r15d, r15d
0x180007ce9  mov     rcx, rsi; lpCriticalSection
0x180007cec  call    cs:__imp_EnterCriticalSection
0x180007cf2  nop
0x180007cf3  mov     rcx, rbp; SRWLock
0x180007cf6  call    cs:__imp_AcquireSRWLockExclusive
0x180007cfc  nop
0x180007cfd  cmp     rbx, rdi
0x180007d00  jnb     short loc_180007D28
0x180007d02  mov     rdx, [rsi+28h]
0x180007d06  lea     rax, [rbx+1]
0x180007d0a  add     rbx, rbx
0x180007d0d  lea     rcx, [rdx+rbx*8]
0x180007d11  mov     rbx, rax
0x180007d14  cmp     qword ptr [rcx], 0
0x180007d18  jnz     short loc_180007D21
0x180007d1a  cmp     rax, rdi
0x180007d1d  jb      short loc_180007D06
0x180007d1f  jmp     short loc_180007D28
0x180007d21  mov     r14, [rcx]
0x180007d24  mov     r15, [rcx+8]
0x180007d28  test    rbp, rbp
0x180007d2b  jz      short loc_180007D37
0x180007d2d  mov     rcx, rbp; SRWLock
0x180007d30  call    cs:__imp_ReleaseSRWLockExclusive
0x180007d36  nop
0x180007d37  test    r14, r14
0x180007d3a  jz      short loc_180007D47
0x180007d3c  mov     rcx, r15
0x180007d3f  mov     rax, r14
0x180007d42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d47  test    rsi, rsi
0x180007d4a  jz      short loc_180007D56
0x180007d4c  mov     rcx, rsi; lpCriticalSection
0x180007d4f  call    cs:__imp_LeaveCriticalSection
0x180007d55  nop
0x180007d56  cmp     rbx, rdi
0x180007d59  jb      short loc_180007CE3
0x180007d5b  add     rsp, 28h
0x180007d5f  pop     r15
0x180007d61  pop     r14
0x180007d63  pop     rdi
0x180007d64  pop     rsi
0x180007d65  pop     rbp
0x180007d66  pop     rbx
0x180007d67  retn
```
