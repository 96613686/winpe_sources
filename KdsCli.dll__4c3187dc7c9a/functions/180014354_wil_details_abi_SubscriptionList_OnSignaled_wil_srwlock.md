# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x180014354`
- end: `0x180014411`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800110e0`
- `0x180011110`
- `0x1800111c0`
- `0x1800160e0`

## callees

- `0x180014354`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800143f9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800143f9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001439a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001439a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180014384`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180014384`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001436a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001436a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800143a3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800143a3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800143db`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800143db`

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
0x180014354  push    rbx
0x180014356  push    rbp
0x180014357  push    rsi
0x180014358  push    rdi
0x180014359  push    r14
0x18001435b  push    r15
0x18001435d  sub     rsp, 28h
0x180014361  mov     rsi, rcx
0x180014364  mov     rbp, rdx
0x180014367  mov     rcx, rdx; SRWLock
0x18001436a  call    cs:__imp_AcquireSRWLockShared
0x180014370  mov     rdi, [rsi+30h]
0x180014374  sub     rdi, [rsi+28h]
0x180014378  shr     rdi, 4
0x18001437c  test    rbp, rbp
0x18001437f  jz      short loc_18001438A
0x180014381  mov     rcx, rbp; SRWLock
0x180014384  call    cs:__imp_ReleaseSRWLockShared
0x18001438a  xor     ebx, ebx
0x18001438c  test    rdi, rdi
0x18001438f  jz      short loc_180014404
0x180014391  mov     rcx, rsi; lpCriticalSection
0x180014394  xor     r14d, r14d
0x180014397  xor     r15d, r15d
0x18001439a  call    cs:__imp_EnterCriticalSection
0x1800143a0  mov     rcx, rbp; SRWLock
0x1800143a3  call    cs:__imp_AcquireSRWLockExclusive
0x1800143a9  cmp     rbx, rdi
0x1800143ac  jnb     short loc_1800143D3
0x1800143ae  mov     rdx, [rsi+28h]
0x1800143b2  lea     rax, [rbx+1]
0x1800143b6  add     rbx, rbx
0x1800143b9  lea     rcx, [rdx+rbx*8]
0x1800143bd  mov     rbx, rax
0x1800143c0  cmp     [rcx], r14
0x1800143c3  jnz     short loc_1800143CC
0x1800143c5  cmp     rax, rdi
0x1800143c8  jb      short loc_1800143B2
0x1800143ca  jmp     short loc_1800143D3
0x1800143cc  mov     r14, [rcx]
0x1800143cf  mov     r15, [rcx+8]
0x1800143d3  test    rbp, rbp
0x1800143d6  jz      short loc_1800143E1
0x1800143d8  mov     rcx, rbp; SRWLock
0x1800143db  call    cs:__imp_ReleaseSRWLockExclusive
0x1800143e1  test    r14, r14
0x1800143e4  jz      short loc_1800143F1
0x1800143e6  mov     rcx, r15
0x1800143e9  mov     rax, r14
0x1800143ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143f1  test    rsi, rsi
0x1800143f4  jz      short loc_1800143FF
0x1800143f6  mov     rcx, rsi; lpCriticalSection
0x1800143f9  call    cs:__imp_LeaveCriticalSection
0x1800143ff  cmp     rbx, rdi
0x180014402  jb      short loc_180014391
0x180014404  add     rsp, 28h
0x180014408  pop     r15
0x18001440a  pop     r14
0x18001440c  pop     rdi
0x18001440d  pop     rsi
0x18001440e  pop     rbp
0x18001440f  pop     rbx
0x180014410  retn
```
