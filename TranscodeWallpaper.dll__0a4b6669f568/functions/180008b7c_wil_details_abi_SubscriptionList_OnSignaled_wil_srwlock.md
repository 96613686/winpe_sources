# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x180008b7c`
- end: `0x180008c39`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800070a0`
- `0x1800070d0`
- `0x180007180`
- `0x18000a680`

## callees

- `0x180008b7c`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008bac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008bac`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180008b92`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180008b92`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008c03`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008c03`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008bcb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008bcb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008c21`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008c21`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008bc2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008bc2`

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
0x180008b7c  push    rbx
0x180008b7e  push    rbp
0x180008b7f  push    rsi
0x180008b80  push    rdi
0x180008b81  push    r14
0x180008b83  push    r15
0x180008b85  sub     rsp, 28h
0x180008b89  mov     rbp, rdx
0x180008b8c  mov     rsi, rcx
0x180008b8f  mov     rcx, rdx; SRWLock
0x180008b92  call    cs:__imp_AcquireSRWLockShared
0x180008b98  mov     rdi, [rsi+30h]
0x180008b9c  sub     rdi, [rsi+28h]
0x180008ba0  shr     rdi, 4
0x180008ba4  test    rbp, rbp
0x180008ba7  jz      short loc_180008BB2
0x180008ba9  mov     rcx, rbp; SRWLock
0x180008bac  call    cs:__imp_ReleaseSRWLockShared
0x180008bb2  xor     ebx, ebx
0x180008bb4  test    rdi, rdi
0x180008bb7  jz      short loc_180008C2C
0x180008bb9  xor     r14d, r14d
0x180008bbc  xor     r15d, r15d
0x180008bbf  mov     rcx, rsi; lpCriticalSection
0x180008bc2  call    cs:__imp_EnterCriticalSection
0x180008bc8  mov     rcx, rbp; SRWLock
0x180008bcb  call    cs:__imp_AcquireSRWLockExclusive
0x180008bd1  cmp     rbx, rdi
0x180008bd4  jnb     short loc_180008BFB
0x180008bd6  mov     rdx, [rsi+28h]
0x180008bda  lea     rax, [rbx+1]
0x180008bde  add     rbx, rbx
0x180008be1  lea     rcx, [rdx+rbx*8]
0x180008be5  mov     rbx, rax
0x180008be8  cmp     [rcx], r14
0x180008beb  jnz     short loc_180008BF4
0x180008bed  cmp     rax, rdi
0x180008bf0  jb      short loc_180008BDA
0x180008bf2  jmp     short loc_180008BFB
0x180008bf4  mov     r14, [rcx]
0x180008bf7  mov     r15, [rcx+8]
0x180008bfb  test    rbp, rbp
0x180008bfe  jz      short loc_180008C09
0x180008c00  mov     rcx, rbp; SRWLock
0x180008c03  call    cs:__imp_ReleaseSRWLockExclusive
0x180008c09  test    r14, r14
0x180008c0c  jz      short loc_180008C19
0x180008c0e  mov     rcx, r15
0x180008c11  mov     rax, r14
0x180008c14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c19  test    rsi, rsi
0x180008c1c  jz      short loc_180008C27
0x180008c1e  mov     rcx, rsi; lpCriticalSection
0x180008c21  call    cs:__imp_LeaveCriticalSection
0x180008c27  cmp     rbx, rdi
0x180008c2a  jb      short loc_180008BB9
0x180008c2c  add     rsp, 28h
0x180008c30  pop     r15
0x180008c32  pop     r14
0x180008c34  pop     rdi
0x180008c35  pop     rsi
0x180008c36  pop     rbp
0x180008c37  pop     rbx
0x180008c38  retn
```
