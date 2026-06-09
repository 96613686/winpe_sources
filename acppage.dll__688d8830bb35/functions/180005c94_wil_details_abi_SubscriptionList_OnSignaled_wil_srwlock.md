# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x180005c94`
- end: `0x180005d51`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002440`
- `0x180002470`
- `0x180002520`
- `0x180007d70`

## callees

- `0x180005c94`
- `0x180017010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180005cda`
- `KERNEL32!EnterCriticalSection` at `0x180005cda`
- `KERNEL32!LeaveCriticalSection` at `0x180005d39`
- `KERNEL32!LeaveCriticalSection` at `0x180005d39`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180005d1b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180005d1b`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180005ce3`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180005ce3`
- `KERNEL32!ReleaseSRWLockShared` at `0x180005cc4`
- `KERNEL32!ReleaseSRWLockShared` at `0x180005cc4`
- `KERNEL32!AcquireSRWLockShared` at `0x180005caa`
- `KERNEL32!AcquireSRWLockShared` at `0x180005caa`

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
0x180005c94  push    rbx
0x180005c96  push    rbp
0x180005c97  push    rsi
0x180005c98  push    rdi
0x180005c99  push    r14
0x180005c9b  push    r15
0x180005c9d  sub     rsp, 28h
0x180005ca1  mov     rsi, rcx
0x180005ca4  mov     rbp, rdx
0x180005ca7  mov     rcx, rdx; SRWLock
0x180005caa  call    cs:__imp_AcquireSRWLockShared
0x180005cb0  mov     rdi, [rsi+30h]
0x180005cb4  sub     rdi, [rsi+28h]
0x180005cb8  shr     rdi, 4
0x180005cbc  test    rbp, rbp
0x180005cbf  jz      short loc_180005CCA
0x180005cc1  mov     rcx, rbp; SRWLock
0x180005cc4  call    cs:__imp_ReleaseSRWLockShared
0x180005cca  xor     ebx, ebx
0x180005ccc  test    rdi, rdi
0x180005ccf  jz      short loc_180005D44
0x180005cd1  mov     rcx, rsi; lpCriticalSection
0x180005cd4  xor     r14d, r14d
0x180005cd7  xor     r15d, r15d
0x180005cda  call    cs:__imp_EnterCriticalSection
0x180005ce0  mov     rcx, rbp; SRWLock
0x180005ce3  call    cs:__imp_AcquireSRWLockExclusive
0x180005ce9  cmp     rbx, rdi
0x180005cec  jnb     short loc_180005D13
0x180005cee  mov     rdx, [rsi+28h]
0x180005cf2  lea     rax, [rbx+1]
0x180005cf6  add     rbx, rbx
0x180005cf9  lea     rcx, [rdx+rbx*8]
0x180005cfd  mov     rbx, rax
0x180005d00  cmp     [rcx], r14
0x180005d03  jnz     short loc_180005D0C
0x180005d05  cmp     rax, rdi
0x180005d08  jb      short loc_180005CF2
0x180005d0a  jmp     short loc_180005D13
0x180005d0c  mov     r14, [rcx]
0x180005d0f  mov     r15, [rcx+8]
0x180005d13  test    rbp, rbp
0x180005d16  jz      short loc_180005D21
0x180005d18  mov     rcx, rbp; SRWLock
0x180005d1b  call    cs:__imp_ReleaseSRWLockExclusive
0x180005d21  test    r14, r14
0x180005d24  jz      short loc_180005D31
0x180005d26  mov     rcx, r15
0x180005d29  mov     rax, r14
0x180005d2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d31  test    rsi, rsi
0x180005d34  jz      short loc_180005D3F
0x180005d36  mov     rcx, rsi; lpCriticalSection
0x180005d39  call    cs:__imp_LeaveCriticalSection
0x180005d3f  cmp     rbx, rdi
0x180005d42  jb      short loc_180005CD1
0x180005d44  add     rsp, 28h
0x180005d48  pop     r15
0x180005d4a  pop     r14
0x180005d4c  pop     rdi
0x180005d4d  pop     rsi
0x180005d4e  pop     rbp
0x180005d4f  pop     rbx
0x180005d50  retn
```
