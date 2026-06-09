# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x14000a86c`
- end: `0x14000a929`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140006aa0`
- `0x140006ad0`
- `0x140006c70`
- `0x14000d080`

## callees

- `0x14000a86c`
- `0x14000f010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x14000a8bb`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000a8bb`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000a8f3`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000a8f3`
- `KERNEL32!AcquireSRWLockShared` at `0x14000a882`
- `KERNEL32!AcquireSRWLockShared` at `0x14000a882`
- `KERNEL32!ReleaseSRWLockShared` at `0x14000a89c`
- `KERNEL32!ReleaseSRWLockShared` at `0x14000a89c`
- `KERNEL32!LeaveCriticalSection` at `0x14000a911`
- `KERNEL32!LeaveCriticalSection` at `0x14000a911`
- `KERNEL32!EnterCriticalSection` at `0x14000a8b2`
- `KERNEL32!EnterCriticalSection` at `0x14000a8b2`

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
0x14000a86c  push    rbx
0x14000a86e  push    rbp
0x14000a86f  push    rsi
0x14000a870  push    rdi
0x14000a871  push    r14
0x14000a873  push    r15
0x14000a875  sub     rsp, 28h
0x14000a879  mov     rbp, rdx
0x14000a87c  mov     rsi, rcx
0x14000a87f  mov     rcx, rdx; SRWLock
0x14000a882  call    cs:__imp_AcquireSRWLockShared
0x14000a888  mov     rdi, [rsi+30h]
0x14000a88c  sub     rdi, [rsi+28h]
0x14000a890  shr     rdi, 4
0x14000a894  test    rbp, rbp
0x14000a897  jz      short loc_14000A8A2
0x14000a899  mov     rcx, rbp; SRWLock
0x14000a89c  call    cs:__imp_ReleaseSRWLockShared
0x14000a8a2  xor     ebx, ebx
0x14000a8a4  test    rdi, rdi
0x14000a8a7  jz      short loc_14000A91C
0x14000a8a9  xor     r14d, r14d
0x14000a8ac  xor     r15d, r15d
0x14000a8af  mov     rcx, rsi; lpCriticalSection
0x14000a8b2  call    cs:__imp_EnterCriticalSection
0x14000a8b8  mov     rcx, rbp; SRWLock
0x14000a8bb  call    cs:__imp_AcquireSRWLockExclusive
0x14000a8c1  cmp     rbx, rdi
0x14000a8c4  jnb     short loc_14000A8EB
0x14000a8c6  mov     rdx, [rsi+28h]
0x14000a8ca  lea     rax, [rbx+1]
0x14000a8ce  add     rbx, rbx
0x14000a8d1  lea     rcx, [rdx+rbx*8]
0x14000a8d5  mov     rbx, rax
0x14000a8d8  cmp     [rcx], r14
0x14000a8db  jnz     short loc_14000A8E4
0x14000a8dd  cmp     rax, rdi
0x14000a8e0  jb      short loc_14000A8CA
0x14000a8e2  jmp     short loc_14000A8EB
0x14000a8e4  mov     r14, [rcx]
0x14000a8e7  mov     r15, [rcx+8]
0x14000a8eb  test    rbp, rbp
0x14000a8ee  jz      short loc_14000A8F9
0x14000a8f0  mov     rcx, rbp; SRWLock
0x14000a8f3  call    cs:__imp_ReleaseSRWLockExclusive
0x14000a8f9  test    r14, r14
0x14000a8fc  jz      short loc_14000A909
0x14000a8fe  mov     rcx, r15
0x14000a901  mov     rax, r14
0x14000a904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a909  test    rsi, rsi
0x14000a90c  jz      short loc_14000A917
0x14000a90e  mov     rcx, rsi; lpCriticalSection
0x14000a911  call    cs:__imp_LeaveCriticalSection
0x14000a917  cmp     rbx, rdi
0x14000a91a  jb      short loc_14000A8A9
0x14000a91c  add     rsp, 28h
0x14000a920  pop     r15
0x14000a922  pop     r14
0x14000a924  pop     rdi
0x14000a925  pop     rsi
0x14000a926  pop     rbp
0x14000a927  pop     rbx
0x14000a928  retn
```
