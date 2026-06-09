# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x14000fab8`
- end: `0x14000fb75`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140005730`
- `0x140005760`
- `0x140005860`
- `0x140011920`

## callees

- `0x14000fab8`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000fafe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000fafe`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000face`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000face`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000fb5d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000fb5d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000fb3f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000fb3f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14000fae8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14000fae8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000fb07`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000fb07`

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
0x14000fab8  push    rbx
0x14000faba  push    rbp
0x14000fabb  push    rsi
0x14000fabc  push    rdi
0x14000fabd  push    r14
0x14000fabf  push    r15
0x14000fac1  sub     rsp, 28h
0x14000fac5  mov     rsi, rcx
0x14000fac8  mov     rbp, rdx
0x14000facb  mov     rcx, rdx; SRWLock
0x14000face  call    cs:__imp_AcquireSRWLockShared
0x14000fad4  mov     rdi, [rsi+30h]
0x14000fad8  sub     rdi, [rsi+28h]
0x14000fadc  shr     rdi, 4
0x14000fae0  test    rbp, rbp
0x14000fae3  jz      short loc_14000FAEE
0x14000fae5  mov     rcx, rbp; SRWLock
0x14000fae8  call    cs:__imp_ReleaseSRWLockShared
0x14000faee  xor     ebx, ebx
0x14000faf0  test    rdi, rdi
0x14000faf3  jz      short loc_14000FB68
0x14000faf5  mov     rcx, rsi; lpCriticalSection
0x14000faf8  xor     r14d, r14d
0x14000fafb  xor     r15d, r15d
0x14000fafe  call    cs:__imp_EnterCriticalSection
0x14000fb04  mov     rcx, rbp; SRWLock
0x14000fb07  call    cs:__imp_AcquireSRWLockExclusive
0x14000fb0d  cmp     rbx, rdi
0x14000fb10  jnb     short loc_14000FB37
0x14000fb12  mov     rdx, [rsi+28h]
0x14000fb16  lea     rax, [rbx+1]
0x14000fb1a  add     rbx, rbx
0x14000fb1d  lea     rcx, [rdx+rbx*8]
0x14000fb21  mov     rbx, rax
0x14000fb24  cmp     [rcx], r14
0x14000fb27  jnz     short loc_14000FB30
0x14000fb29  cmp     rax, rdi
0x14000fb2c  jb      short loc_14000FB16
0x14000fb2e  jmp     short loc_14000FB37
0x14000fb30  mov     r14, [rcx]
0x14000fb33  mov     r15, [rcx+8]
0x14000fb37  test    rbp, rbp
0x14000fb3a  jz      short loc_14000FB45
0x14000fb3c  mov     rcx, rbp; SRWLock
0x14000fb3f  call    cs:__imp_ReleaseSRWLockExclusive
0x14000fb45  test    r14, r14
0x14000fb48  jz      short loc_14000FB55
0x14000fb4a  mov     rcx, r15
0x14000fb4d  mov     rax, r14
0x14000fb50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fb55  test    rsi, rsi
0x14000fb58  jz      short loc_14000FB63
0x14000fb5a  mov     rcx, rsi; lpCriticalSection
0x14000fb5d  call    cs:__imp_LeaveCriticalSection
0x14000fb63  cmp     rbx, rdi
0x14000fb66  jb      short loc_14000FAF5
0x14000fb68  add     rsp, 28h
0x14000fb6c  pop     r15
0x14000fb6e  pop     r14
0x14000fb70  pop     rdi
0x14000fb71  pop     rsi
0x14000fb72  pop     rbp
0x14000fb73  pop     rbx
0x14000fb74  retn
```
